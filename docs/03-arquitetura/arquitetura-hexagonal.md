# Arquitectura Hexagonal

## Propósito

Descrever a aplicação do padrão de Arquitectura Hexagonal (Ports and Adapters) na Junta Observatory Platform, garantindo que o núcleo de domínio permanece isolado de frameworks, bases de dados e sistemas externos.

## Responsabilidades

- Definir a estrutura hexagonal padrão para cada microserviço
- Estabelecer as portas (ports) de entrada e saída
- Documentar os adaptadores (adapters) de infraestrutura
- Garantir a testabilidade do domínio sem dependências externas

## Descrição Detalhada

### Estrutura Hexagonal

```mermaid
flowchart TD
    subgraph "Núcleo (Domínio)"
        AGG[Aggregate]
        ENT[Entity]
        VO[Value Object]
        DOM_SVC[Domain Service]
        SPEC[Specification]
        EVT[Domain Event]
        REPO_PORT[Repository Port<br/>Interface]
        EVT_PORT[Event Publisher Port<br/>Interface]
        SVC_PORT[External Service Port<br/>Interface]
    end

    subgraph "Esquerda — Inbound Adapters"
        REST[REST Controller]
        GRPC[gRPC Service]
        EVT_LISTENER[Event Listener]
        JOB[Scheduler]
    end

    subgraph "Direita — Outbound Adapters"
        REPO_IMPL[Repository Implementation<br/>PostgreSQL / EventStore]
        EVT_PUB[Event Publisher<br/>Kafka]
        CLI_HTTP[HTTP Client<br/>REST / gRPC]
        CACHE_IMPL[Cache Provider<br/>Redis]
    end

    subgraph "Aplicação (Use Cases)"
        CMD[Command Handler]
        QRY[Query Handler]
        APP_SVC[Application Service]
    end

    REST --> CMD
    REST --> QRY
    GRPC --> CMD
    EVT_LISTENER --> APP_SVC
    JOB --> APP_SVC

    CMD --> AGG
    CMD --> DOM_SVC
    CMD --> REPO_PORT
    CMD --> EVT_PORT
    QRY --> REPO_PORT
    APP_SVC --> DOM_SVC
    APP_SVC --> SVC_PORT
    APP_SVC --> REPO_PORT

    REPO_PORT --> REPO_IMPL
    EVT_PORT --> EVT_PUB
    SVC_PORT --> CLI_HTTP
    SVC_PORT --> CACHE_IMPL

    REPO_IMPL --> DB[(Database)]
    EVT_PUB --> KAFKA[Kafka]
    CLI_HTTP --> EXT[External System]
    CACHE_IMPL --> REDIS[Redis]
```

### Organização de Pacotes

```
com.juntaobservatory.servico/
│
├── application/
│   ├── port/
│   │   ├── inbound/
│   │   │   ├── CriarServicoUseCase.java
│   │   │   └── ConsultarServicoUseCase.java
│   │   └── outbound/
│   │       ├── ServicoRepository.java
│   │       └── EventPublisher.java
│   ├── command/
│   │   ├── CriarServicoCommand.java
│   │   └── AtualizarServicoCommand.java
│   ├── query/
│   │   ├── ListarServicosQuery.java
│   │   └── ObterServicoQuery.java
│   └── service/
│       ├── CriarServicoService.java
│       └── ConsultarServicoService.java
│
├── domain/
│   ├── model/
│   │   ├── Servico.java              (Aggregate Root)
│   │   ├── CategoriaServico.java      (Entity)
│   │   └── Taxa.java                  (Value Object)
│   ├── event/
│   │   └── ServicoCriadoEvent.java
│   ├── spec/
│   │   └── ServicoActivoSpec.java
│   └── service/
│       └── ValidacaoServicoService.java
│
├── infrastructure/
│   ├── adapter/
│   │   ├── inbound/
│   │   │   ├── rest/
│   │   │   │   ├── ServicoController.java
│   │   │   │   └── ServicoDTO.java
│   │   │   └── kafka/
│   │   │       └── ServicoEventConsumer.java
│   │   └── outbound/
│   │       ├── persistence/
│   │       │   ├── ServicoRepositoryJPA.java
│   │       │   ├── ServicoEntity.java
│   │       │   └── ServicoMapper.java
│   │       └── messaging/
│   │           └── ServicoEventPublisherKafka.java
│   └── config/
│       ├── BeanConfiguration.java
│       └── KafkaConfig.java
│
└── shared/
    ├── dto/
    ├── exception/
    └── util/
```

### Regras da Arquitectura Hexagonal

| Regra | Descrição | Verificação |
|---|---|---|
| **Domínio sem dependências externas** | Nenhuma importação de frameworks na camada domain | ArchTest (ArchUnit) |
| **Ports são interfaces no domínio** | Ports de saída são interfaces na camada domain | ArchTest |
| **Adapters implementam ports** | Adapters de infraestrutura implementam interfaces do domínio | ArchTest |
| **Aplicação orquestra, domínio decide** | Application chama domain, não o contrário | Código |
| **Injeção de dependência** | Adapters são injectados nas ports via DI | Spring DI |
| **DTOs na fronteira** | Adaptadores convertem entre DTOs e modelos de domínio | Código |

### Benefícios

| Benefício | Descrição |
|---|---|
| **Testabilidade** | Domínio testável sem infraestrutura (mocks nas interfaces) |
| **Troca de tecnologia** | Substituir PostgreSQL por MongoDB? Apenas o adapter muda |
| **Isolamento de frameworks** | Framework web ou BD podem mudar sem afectar o domínio |
| **Clareza de responsabilidades** | Cada camada tem um papel bem definido |
| **Evolução independente** | Adapters podem evoluir em ritmos diferentes |

## Critérios de Aceitação

- A verificação ArchUnit confirma que o domínio não depende de frameworks
- Cada serviço tem testes unitários para a camada de domínio sem mocks
- É possível substituir a base de dados sem alterar a camada de domínio

## Documentos Relacionados

- [Diagrama de Componentes](diagrama-de-componentes.md)
- [Microserviços](microservicos.md)
- [12 — Normas de Código](../12-desenvolvimento/normas-codigo.md)
- [12 — Testes Unidade](../12-desenvolvimento/testes-unidade.md)
