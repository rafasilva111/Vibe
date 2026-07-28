# Diagrama de Componentes (C4 Nível 3)

## Propósito

Decompor cada contentor (microserviço) nos seus componentes internos, mostrando a estrutura, responsabilidades e relações entre camadas.

## Responsabilidades

- Mostrar o desenho interno de cada microserviço
- Documentar o padrão de Arquitectura Hexagonal
- Estabelecer a separação entre domínio, aplicação e infraestrutura

## Descrição Detalhada

### Componentes Comuns a Cada Microserviço

```mermaid
flowchart TD
    subgraph "Microserviço (Hexagonal)"
        subgraph "Interface Adapters (Inbound)"
            REST[REST Controller]
            GRPC[gRPC Service]
            EVT_IN[Event Subscriber]
            JOB[Scheduler Job]
        end

        subgraph "Application Layer"
            CMD[Command Handler]
            QRY[Query Handler]
            SVC[Application Service]
            DTO[DTO / Mapper]
        end

        subgraph "Domain Layer"
            AGG[Aggregate Root]
            ENT[Entity]
            VO[Value Object]
            DOM_SVC[Domain Service]
            SPEC[Specification]
            EVT_DOM[Domain Event]
        end

        subgraph "Interface Adapters (Outbound)"
            REPO[Repository Implementation]
            EVT_PUB[Event Publisher]
            CLI[External Client]
            CACHE[Cache Provider]
        end

        subgraph "Infrastructure"
            DB[(Database)]
            QUEUE[(Message Queue)]
            EXT[External API]
            CACHE_S[(Cache)]
        end

        REST --> CMD
        REST --> QRY
        GRPC --> CMD
        GRPC --> QRY
        EVT_IN --> SVC
        JOB --> SVC
        CMD --> AGG
        CMD --> DOM_SVC
        QRY --> REPO
        SVC --> DOM_SVC
        AGG --> EVT_DOM
        AGG --> ENT
        ENT --> VO
        AGG --> SPEC
        DOM_SVC --> AGG
        CMD --> REPO
        SVC --> CLI
        SVC --> CACHE
        REPO --> DB
        EVT_PUB --> QUEUE
        CLI --> EXT
        CACHE --> CACHE_S
    end
```

### Exemplo: Componentes do Motor de Workflows

```mermaid
flowchart TD
    subgraph "Motor de Workflows"
        WF_REST[WorkflowController<br/>REST API]
        WF_gRPC[WorkflowgRPC<br/>gRPC Service]
        WF_EVT[WorkflowEventSubscriber<br/>Kafka Consumer]

        WF_CMD[WorkflowCommandHandler]
        WF_QRY[WorkflowQueryHandler]
        WF_SVC[WorkflowService]

        WF_AGG[WorkflowAggregate]
        STEP_AGG[StepAggregate]
        WF_VO[WorkflowValueObjects<br/>Step, Transition, Condition]

        WF_REPO[WorkflowRepository<br/>PostgreSQL + EventStore]
        WF_PUB[WorkflowEventPublisher<br/>Kafka]
        WF_CLI[TaskServiceClient<br/>gRPC]

        WF_REST --> WF_CMD
        WF_REST --> WF_QRY
        WF_gRPC --> WF_CMD
        WF_EVT --> WF_SVC

        WF_CMD --> WF_AGG
        WF_CMD --> STEP_AGG
        WF_QRY --> WF_REPO
        WF_SVC --> WF_AGG

        WF_AGG --> WF_VO
        STEP_AGG --> WF_VO

        WF_CMD --> WF_REPO
        WF_CMD --> WF_PUB
        WF_SVC --> WF_CLI

        WF_REPO --> PG[(PostgreSQL)]
        WF_REPO --> ES[(Event Store)]
        WF_PUB --> KAFKA[Kafka]
        WF_CLI --> TASK[Task Service]
    end
```

### Padrão por Camada

| Camada | Responsabilidade | Tecnologia | Testabilidade |
|---|---|---|---|
| **Interface Adapters (Inbound)** | Receber pedidos, validar input, serializar resposta | Spring MVC, gRPC, Kafka Listener | Testes de integração |
| **Application Layer** | Orquestrar casos de uso, transacções, autorização | Spring Service, @Transactional | Testes de integração |
| **Domain Layer** | Lógica de negócio, regras, invariantes, eventos | Plain Java/Kotlin | Testes unitários (sem mock) |
| **Interface Adapters (Outbound)** | Persistência, publicação de eventos, chamadas externas | Spring Data, Kafka Template, RestClient | Testes de integração |
| **Infrastructure** | Base de dados, message queue, cache | PostgreSQL, Kafka, Redis | Testes de contrato |

### Regras por Camada

| Regra | Descrição |
|---|---|
| A camada de domínio não depende de nenhuma framework ou biblioteca externa | Pure Java/Kotlin |
| A camada de aplicação não contém lógica de negócio | Apenas orquestração |
| A camada de interface adapters não contém lógica de negócio | Apenas validação e serialização |
| A comunicação entre camadas é feita por interfaces (ports) | Ports in/out |
| A implementação dos ports (adapters) é injectada por DI | Spring DI |

## Critérios de Aceitação

- Cada microserviço segue a mesma estrutura de componentes
- A camada de domínio é testável sem infraestrutura (mocks zero)
- As portas (ports) estão definidas como interfaces na camada de domínio

## Documentos Relacionados

- [Arquitectura Hexagonal](arquitetura-hexagonal.md)
- [Diagrama de Contentores](diagrama-de-contentores.md)
- [Comunicação entre Serviços](comunicacao-entre-servicos.md)
- [12 — Normas de Código](../12-desenvolvimento/normas-codigo.md)
