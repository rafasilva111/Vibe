# Diagramas de Sequência

## Propósito

Documentar os principais fluxos de interacção entre componentes da Junta Observatory Platform, mostrando a sequência de mensagens trocadas entre actores, serviços e sistemas externos.

## Responsabilidades

- Ilustrar os fluxos de interacção críticos do sistema
- Validar o desenho arquitectural antes da implementação
- Servir como especificação para a equipa de desenvolvimento

## Descrição Detalhada

### Fluxo: Submissão de Pedido (Cidadão → Plataforma)

```mermaid
sequenceDiagram
    participant C as Cidadão
    participant GW as API Gateway
    participant AUTH as Auth Service
    participant CAT as Catálogo
    participant WF as Motor Workflows
    participant DOC as Documentos
    participant TASK as Tarefas
    participant NOTIF as Notificações
    participant ES as Event Store
    participant KAFKA as Event Bus

    C->>GW: POST /api/v1/casos
    Note over C,GW: JWT Token, Dados do Pedido
    GW->>AUTH: Validar Token + Permissões
    AUTH-->>GW: OK
    GW->>CAT: GET /servicos/servicoId
    CAT-->>GW: Serviço + WorkflowId
    GW->>WF: POST /workflows/instancias
    Note over GW,WF: Iniciar workflow com dados do pedido
    activate WF
    WF->>ES: Append Evento.caso.criado
    ES-->>WF: OK
    WF->>KAFKA: Publicar Evento
    WF-->>GW: instanciaId, casoId
    deactivate WF
    GW->>C: 201 Created, casoId

    par Processamento Assíncrono
        KAFKA->>DOC: Evento: documentos.solicitados
        activate DOC
        DOC-->>KAFKA: Documentos Disponíveis
        deactivate DOC
        KAFKA->>TASK: Evento: tarefa.criada
        activate TASK
        TASK-->>KAFKA: Tarefa Criada
        deactivate TASK
        KAFKA->>NOTIF: Evento: notificacao.enviar
        activate NOTIF
        NOTIF->>C: Email/SMS: Pedido Recebido
        deactivate NOTIF
    end
```

### Fluxo: Despacho de Processo (Dirigente → Decisão)

```mermaid
sequenceDiagram
    participant D as Dirigente
    participant GW as API Gateway
    participant AUTH as Auth Service
    participant WF as Motor Workflows
    participant DOC as Documentos
    participant NOTIF as Notificações
    participant ES as Event Store
    participant KAFKA as Event Bus
    participant CID as Cidadão

    D->>GW: POST /api/v1/casos/casoId/despachar
    Note over D,GW: Despacho + Fundamentação
    GW->>AUTH: Validar Permissões (pelouro, SoD)
    AUTH-->>GW: OK (pode despachar)
    GW->>WF: Command: DespacharCaso
    activate WF
    WF->>WF: Validar Regras de Negócio
    WF->>WF: Verificar SoD (não foi instrutor)
    WF->>WF: Calcular prazo legal
    WF->>ES: Append Evento.caso.decidido
    ES-->>WF: OK
    WF->>KAFKA: Publicar Evento
    WF-->>GW: Decisão Registada
    deactivate WF
    GW-->>D: 200 OK, Decisão

    par Processamento
        KAFKA->>DOC: Evento: documento.emitir
        activate DOC
        DOC->>DOC: Gerar Documento de Decisão
        DOC-->>KAFKA: Documento Emitido
        deactivate DOC
        KAFKA->>NOTIF: Evento: notificacao.enviar
        activate NOTIF
        NOTIF->>NOTIF: Template: Decisão Favorável
        NOTIF->>CID: Email: Decisão do seu pedido
        deactivate NOTIF
    end
```

### Fluxo: Autenticação com Chave Móvel Digital

```mermaid
sequenceDiagram
    participant C as Cidadão
    participant APP as Web App
    participant GW as API Gateway
    participant AUTH as Auth Service
    participant CMD as Chave Móvel Digital

    C->>APP: Clicar "Login com CMD"
    APP->>AUTH: Redirect para /oauth2/authorization/cmd
    AUTH->>CMD: Authorization Request (OIDC)
    CMD-->>C: Inserir NIF + PIN
    C->>CMD: Submeter Credenciais
    CMD-->>CMD: Validar NIF + PIN
    CMD-->>AUTH: Authorization Code
    AUTH->>CMD: Token Request (code + client_secret)
    CMD-->>AUTH: ID Token + Access Token
    AUTH->>AUTH: Validar ID Token (sub, aud, exp)
    AUTH->>AUTH: Mapear Claims → Utilizador
    AUTH-->>APP: Session Cookie + JWT Token
    APP-->>C: Dashboard
```

### Fluxo: Notificação de Prazo Prestes a Expirar

```mermaid
sequenceDiagram
    participant S as Scheduler
    participant WF as Motor Workflows
    participant TASK as Tarefas
    participant NOTIF as Notificações
    participant C as Cidadão
    participant F as Funcionário

    S->>WF: Job: Verificar Prazos (horário)
    activate WF
    WF->>TASK: Query: Tarefas a expirar em 5 dias
    TASK-->>WF: Lista de Tarefas
    loop Para cada tarefa
        WF->>NOTIF: Enviar Alerta de Prazo
        NOTIF->>F: Email: "Prazo limite: 5 dias"
        WF->>NOTIF: Enviar Alerta ao Cidadão
        NOTIF->>C: SMS/Email: "O seu processo está próximo do prazo"
    end
    WF->>WF: Marcar Verificação
    deactivate WF
```

### Fluxo: Process Mining — Descoberta de Processo

```mermaid
sequenceDiagram
    participant A as Administrador
    participant PM as Process Mining
    participant ES as Event Store
    participant DASH as Dashboard

    A->>PM: Iniciar Análise: Workflow X
    activate PM
    PM->>ES: Query: Eventos do Workflow X (últimos 6 meses)
    ES-->>PM: Lista de Eventos
    PM->>PM: Filtrar, Ordenar, Agrupar por Caso
    PM->>PM: Aplicar Algoritmo de Descoberta (Alpha/Heuristic)
    PM->>PM: Gerar Modelo Descoberto (BPMN/PNML)
    PM->>PM: Detectar Desvios vs Modelo Oficial
    PM->>PM: Identificar Gargalos (tempo médio por passo)
    PM-->>A: Resultados
    A->>A: Visualizar no Dashboard
    deactivate PM
```

## Regras de Negócio

- Os diagramas de sequência devem ser actualizados sempre que o fluxo implementado mudar
- Todos os fluxos assíncronos devem incluir tratamento de falhas (timeout, retry, dead letter)
- As interacções com sistemas externos devem incluir circuit breaker

## Critérios de Aceitação

- Os fluxos documentados correspondem exactamente à implementação
- Todos os cenários de erro estão representados (timeout, falha, rejeição)
- Os diagramas são gerados a partir de código ou mantidos manualmente com revisão trimestral

## Documentos Relacionados

- [Diagrama de Contexto](diagrama-de-contexto.md)
- [Diagrama de Contentores](diagrama-de-contentores.md)
- [Comunicação entre Serviços](comunicacao-entre-servicos.md)
- [04 — Plataforma / Workflow](../04-servicos-plataforma/plataforma-workflow.md)
