# Diagrama de Contentores (C4 Nível 2)

## Propósito

Mostrar a arquitectura de alto nível da Junta Observatory Platform, decompondo o sistema nos seus principais contentores (microserviços, bases de dados, message broker, etc.) e as relações entre eles.

## Responsabilidades

- Identificar todos os microserviços e sistemas de armazenamento
- Mostrar os protocolos de comunicação entre contentores
- Estabelecer a separação entre frontend, backend, dados e infraestrutura

## Descrição Detalhada

```mermaid
flowchart TB
    subgraph "Clientes"
        WEB[Web App<br/>React + TypeScript]
        API_CLI[API Client<br/>REST/GraphQL]
        CMD_CLI[CMD /<br/>Autenticação.gov]
    end

    subgraph "Edge"
        CDN[CDN / CloudFront]
        WAF[WAF / DDoS Protection]
    end

    subgraph "API Gateway"
        GW[API Gateway<br/>Kong / Traefik]
        RATE[Rate Limiter]
        AUTH_GW[Auth Gateway]
    end

    subgraph "Microserviços Core"
        MS_CAT[Catálogo<br/>de Serviços]
        MS_WF[Motor de<br/>Workflows]
        MS_TASK[Gestão de<br/>Tarefas]
        MS_DOC[Gestão<br/>Documental]
        MS_FORM[Formulários<br/>Digitais]
    end

    subgraph "Microserviços Suporte"
        MS_NOTIF[Notificações]
        MS_KB[Base de<br/>Conhecimento]
        MS_SEARCH[Pesquisa]
        MS_REPORT[Relatórios]
        MS_SLA[Gestão de SLAs]
    end

    subgraph "Microserviços Plataforma"
        MS_AUDIT[Auditoria]
        MS_EVENT[Eventos]
        MS_AUTH[Autenticação<br/>e Autorização]
        MS_ADMIN[Administração<br/>Multi-Tenant]
        MS_AI[Assistente IA]
    end

    subgraph "Domínios Plugin"
        MS_LIC[Licenciamento]
        MS_ATEST[Atestados]
        MS_ESP[Espaços]
        MS_SOCIAL[Ação Social]
        MS_FIN[Financeiro]
    end

    subgraph "Armazenamento"
        PG[(PostgreSQL<br/>Dados Relacionais)]
        ES[(Event Store<br/>Eventos Imutáveis)]
        MONGO[(MongoDB<br/>Read Models)]
        ELK[(Elasticsearch<br/>Search Index)]
        REDIS[(Redis<br/>Cache / Sessões)]
        S3[(Object Store<br/>Documentos)]
        VDB[(Vector DB<br/>Embeddings)]
    end

    subgraph "Infraestrutura"
        KAFKA[Apache Kafka<br/>Event Bus]
        K8S[Kubernetes<br/>Orquestração]
    end

    WEB --> CDN
    CDN --> WAF
    WAF --> GW
    API_CLI --> GW
    CMD_CLI --> GW

    GW --> MS_CAT
    GW --> MS_WF
    GW --> MS_TASK
    GW --> MS_DOC
    GW --> MS_FORM
    GW --> MS_NOTIF
    GW --> MS_KB
    GW --> MS_SEARCH
    GW --> MS_REPORT
    GW --> MS_SLA
    GW --> MS_AUDIT
    GW --> MS_EVENT
    GW --> MS_AUTH
    GW --> MS_ADMIN
    GW --> MS_AI
    GW --> MS_LIC
    GW --> MS_ATEST
    GW --> MS_ESP
    GW --> MS_SOCIAL
    GW --> MS_FIN

    MS_CAT --> PG
    MS_WF --> ES
    MS_WF --> PG
    MS_TASK --> PG
    MS_DOC --> S3
    MS_DOC --> PG
    MS_FORM --> PG
    MS_KB --> PG
    MS_SEARCH --> ELK
    MS_REPORT --> PG
    MS_SLA --> PG
    MS_AUDIT --> ES
    MS_EVENT --> KAFKA
    MS_AUTH --> REDIS
    MS_AUTH --> PG
    MS_ADMIN --> PG
    MS_AI --> VDB
    MS_AI --> MONGO
    MS_LIC --> PG
    MS_ATEST --> PG
    MS_ESP --> PG
    MS_SOCIAL --> PG
    MS_FIN --> PG

    MS_CAT --> KAFKA
    MS_WF --> KAFKA
    MS_TASK --> KAFKA
    MS_DOC --> KAFKA
    KAFKA --> MS_NOTIF
    KAFKA --> MS_REPORT
    KAFKA --> MS_AUDIT
    KAFKA --> MS_AI

    K8S --> Todos_MS[Todos os Microserviços]
```

### Legenda de Contentores

| Contentor | Descrição | Tecnologia |
|---|---|---|
| **Web App** | Interface de utilizador SPA | React 19 + TypeScript |
| **API Gateway** | Ponto único de entrada, autenticação, rate limiting | Kong / Traefik |
| **Microserviços Core** | Serviços fundamentais da plataforma | Java 21+ / Spring Boot |
| **Microserviços Suporte** | Serviços de suporte operacional | Java 21+ / Spring Boot |
| **Microserviços Plataforma** | Serviços transversais | Java 21+ / Spring Boot |
| **Domínios Plugin** | Serviços de domínio de negócio opcionais | Java 21+ / Spring Boot |
| **PostgreSQL** | Dados relacionais e de referência | PostgreSQL 16+ |
| **Event Store** | Armazenamento de eventos imutáveis | EventStoreDB / PostgreSQL |
| **MongoDB** | Read models e projecções | MongoDB 7+ |
| **Elasticsearch** | Índices de pesquisa | Elasticsearch 8+ |
| **Redis** | Cache, sessões, rate limiting | Redis 7+ |
| **Object Store** | Armazenamento de documentos | MinIO / S3 |
| **Vector DB** | Embeddings para pesquisa semântica | Qdrant |
| **Apache Kafka** | Barramento de eventos assíncronos | Kafka 3+ |

### Protocolos de Comunicação

| Comunicação | Protocolo | Formato |
|---|---|---|
| Browser → API Gateway | HTTPS | — |
| API Client → API Gateway | HTTPS REST | JSON (JSON:API) |
| API Gateway → Microserviços | HTTP/gRPC | JSON / Protobuf |
| Microserviço → Microserviço | gRPC (sync) | Protobuf |
| Microserviço → Kafka | Kafka Protocol | Avro / JSON |
| Kafka → Microserviço | Kafka Protocol | Avro / JSON |
| Microserviço → Base de Dados | TCP | SQL / Wire Protocol |
| Microserviço → Object Store | S3 API | Binary |

## Regras de Negócio

- Cada microserviço tem a sua própria base de dados (database-per-service)
- A comunicação síncrona entre microserviços é evitada sempre que possível
- O API Gateway é o único ponto de entrada pública
- A descoberta de serviços é feita via Kubernetes DNS / Service Mesh

## Critérios de Aceitação

- Todos os contentores identificados estão mapeados a um ou mais Bounded Contexts
- O diagrama reflecte a separação de responsabilidades entre serviços
- As bases de dados estão atribuídas correctamente a cada serviço

## Documentos Relacionados

- [Diagrama de Contexto](diagrama-de-contexto.md)
- [Diagrama de Componentes](diagrama-de-componentes.md)
- [Bounded Contexts](bounded-contexts.md)
- [Microserviços](microservicos.md)
- [Comunicação entre Serviços](comunicacao-entre-servicos.md)
