# Modelo de Domínio

## Propósito

Descrever o modelo de domínio global da Junta Observatory Platform, representando as entidades de negócio e as suas relações no nível mais abstracto, independente de implementação técnica.

## Responsabilidades

- Definir a taxonomia de entidades de domínio
- Estabelecer os relacionamentos conceptuais entre entidades
- Servir como base para a implementação dos agregados DDD

## Descrição Detalhada

```mermaid
classDiagram
    class Organizacao {
        +UUID id
        +String nome
        +String nif
        +String morada
        +String plano
    }

    class Departamento {
        +UUID id
        +String nome
        +String sigla
    }

    class Utilizador {
        +UUID id
        +String nome
        +String email
        +Role role
    }

    class Funcao {
        +UUID id
        +String nome
        +List~Permissao~ permissoes
    }

    class Servico {
        +UUID id
        +String nome
        +String categoria
        +Status status
    }

    class Workflow {
        +UUID id
        +String nome
        +int versaoActual
        +EstadoWorkflow estado
    }

    class VersaoWorkflow {
        +UUID id
        +int numero
        +String modelo
        +EstadoVersao estado
    }

    class Passo {
        +UUID id
        +String nome
        +TipoPasso tipo
        +int ordem
    }

    class InstanciaWorkflow {
        +UUID id
        +EstadoInstancia estado
        +DateTime iniciadoEm
    }

    class Pedido {
        +UUID id
        +String numero
        +String canal
        +DateTime dataSubmissao
    }

    class Caso {
        +UUID id
        +String numeroProcesso
        +EstadoCaso estado
    }

    class Cidadao {
        +UUID id
        +String nome
        +String nif
        +String cmd
    }

    class Documento {
        +UUID id
        +String nome
        +String tipo
        +int versao
    }

    class Evento {
        +UUID id
        +String tipo
        +String dados
        +DateTime timestamp
    }

    class Tarefa {
        +UUID id
        +String descricao
        +EstadoTarefa estado
        +DateTime deadline
    }

    class Notificacao {
        +UUID id
        +String titulo
        +String canal
        +boolean lida
    }

    class SLA {
        +UUID id
        +String nome
        +int prazoHoras
    }

    class KPI {
        +UUID id
        +String nome
        +String formula
        +double meta
    }

    Organizacao "1" --> "*" Departamento
    Organizacao "1" --> "*" Utilizador
    Organizacao "1" --> "*" Servico
    Departamento "1" --> "*" Utilizador
    Utilizador "*" --> "*" Funcao
    Funcao "1" --> "*" Permissao
    Servico "1" --> "*" Workflow
    Workflow "1" --> "*" VersaoWorkflow
    VersaoWorkflow "1" --> "*" Passo
    Workflow "1" --> "*" InstanciaWorkflow
    Pedido "1" --> "1" InstanciaWorkflow
    InstanciaWorkflow "1" --> "1" Caso
    Caso "1" --> "*" Documento
    Caso "1" --> "*" Evento
    Caso "1" --> "*" Tarefa
    Caso "1" --> "*" Notificacao
    Utilizador "*" --> "*" Tarefa
    Cidadao "1" --> "*" Pedido
    Servico "1" --> "1" SLA
    SLA "1" --> "*" KPI
```

### Agregados

| Agregado | Raiz | Entidades | Value Objects |
|---|---|---|---|
| **Organização** | Organizacao | Departamento, Utilizador | Morada, Contacto |
| **Serviço** | Servico | CategoriaServico | Taxa, PrazoLegal |
| **Workflow** | Workflow | VersaoWorkflow, Passo, Transicao | Condicao, Estado |
| **Instância** | Caso | Pedido, Tarefa, Documento, Evento | NumeroProcesso |
| **Identidade** | Utilizador | Funcao, Permissao | Credenciais |
| **Notificação** | Notificacao | — | Template, Canal |

### Relações Transversais

```mermaid
flowchart LR
    subgraph "Ciclo de Pedido"
        P[Pedido] --> I[Instância Workflow]
        I --> C[Caso]
        C --> D[Documentos]
        C --> T[Tarefas]
        C --> E[Eventos]
        C --> N[Notificações]
    end
    subgraph "Configuração"
        S[Serviço] --> W[Workflow]
        W --> V[Versão]
        V --> PS[Passos]
    end
    subgraph "Governança"
        O[Organização] --> DP[Departamentos]
        DP --> U[Utilizadores]
        U --> F[Funções]
        F --> PM[Permissões]
    end
```

## Regras de Negócio

- Cada agregado tem um ciclo de vida bem definido com início e fim
- Agregados comunicam entre si através de eventos de domínio
- O raiz do agregado é a única entidade que garante consistência
- Referências a entidades de outros agregados são feitas por ID (não por referência objecto)

## Critérios de Aceitação

- O modelo de domínio está alinhado com os Bounded Contexts definidos
- Cada agregado tem uma raíz claramente identificada
- As relações entre agregados são por ID ou por evento

## Documentos Relacionados

- [Bounded Contexts](bounded-contexts.md)
- [Diagramas de Estado](diagramas-de-estado.md)
- [06 — Dados](../06-dados/index.md)
- [01 — Análise de Negócio](../01-analise-de-negocio/index.md)
