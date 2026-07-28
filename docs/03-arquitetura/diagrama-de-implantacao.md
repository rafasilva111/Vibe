# Diagrama de Implantação (C4 Nível 4)

## Propósito

Descrever a infraestrutura de implantação da Junta Observatory Platform, incluindo a topologia de rede, distribuição geográfica, ambientes e componentes físicos/virtuais.

## Responsabilidades

- Documentar a topologia de implantação
- Definir os ambientes (dev, staging, produção)
- Estabelecer a estratégia de rede, DNS e certificados
- Servir como referência para a equipa de operações

## Descrição Detalhada

```mermaid
flowchart TB
    subgraph "Internet"
        USERS[Utilizadores<br/>Browser / App]
        EXTERNAL[Sistemas Externos<br/>CMD, AGov, ePortugal]
    end

    subgraph "CDN / Edge"
        CDN[Cloud CDN<br/>CloudFront / Cloudflare]
        WAF[WAF<br/>ModSecurity / AWS WAF]
        DNS[Route53 / Cloud DNS]
    end

    subgraph "VPC Produção - Zona Pública"
        GW_LB[Load Balancer<br/>ALB / Nginx]
        GW_KONG[API Gateway<br/>Kong / Traefik]
        AUTH_SVC[Auth Service<br/>Keycloak]
    end

    subgraph "VPC Produção - Zona Privada - Aplicação"
        K8S_CTRL[Kubernetes<br/>Control Plane]
        K8S_WORKER[Worker Nodes<br/>ECS / EKS / AKS]
        subgraph "Pods"
            MS1[Microserviço<br/>Catálogo]
            MS2[Microserviço<br/>Workflows]
            MS3[Microserviço<br/>Documentos]
            MS_N[Mais N<br/>Microserviços]
            WEB_APP[Web App<br/>Nginx + React]
        end
    end

    subgraph "VPC Produção - Zona Privada - Dados"
        PG_HA[PostgreSQL<br/>RDS / Cloud SQL<br/>Multi-AZ]
        ES_HA[EventStoreDB<br/>Cluster 3 nós]
        MONGO_HA[MongoDB<br/>Replica Set]
        REDIS_CL[Redis<br/>ElastiCache / Cluster]
        KAFKA_CL[Kafka<br/>MSK / Confluent<br/>Cluster 3 nós]
        ELK_HA[Elasticsearch<br/>Cluster 3 nós]
        VDB_CL[Qdrant<br/>Vector DB]
        S3_STORE[S3 / MinIO<br/>Object Storage]
    end

    subgraph "Ambiente de Staging"
        STG_K8S[Kubernetes Staging]
        STG_PG[PostgreSQL Staging]
        STG_ES[EventStore Staging]
    end

    subgraph "Ambiente de Desenvolvimento"
        DEV_K8S[Kubernetes Dev]
        DEV_PG[PostgreSQL Dev]
    end

    subgraph "Observabilidade"
        PROM[Prometheus<br/>HA]
        GRA[Grafana<br/>HA]
        LOKI[Loki<br/>Logs]
        TEMPO[Tempo<br/>Tracing]
        ALT[Alertmanager]
    end

    subgraph "CI/CD"
        GIT[GitLab / GitHub]
        CI_CD[CI/CD Pipeline]
        REG[Docker Registry]
    end

    USERS --> DNS
    DNS --> CDN
    CDN --> WAF
    WAF --> GW_LB
    EXTERNAL --> GW_LB
    GW_LB --> GW_KONG
    GW_KONG --> AUTH_SVC
    GW_KONG --> WEB_APP
    GW_KONG --> K8S_WORKER

    K8S_WORKER --> PG_HA
    K8S_WORKER --> ES_HA
    K8S_WORKER --> MONGO_HA
    K8S_WORKER --> REDIS_CL
    K8S_WORKER --> KAFKA_CL
    K8S_WORKER --> ELK_HA
    K8S_WORKER --> VDB_CL
    K8S_WORKER --> S3_STORE

    K8S_WORKER --> PROM
    K8S_WORKER --> LOKI
    K8S_WORKER --> TEMPO
    PROM --> GRA
    LOKI --> GRA
    TEMPO --> GRA
    GRA --> ALT

    CI_CD --> REG
    CI_CD --> K8S_WORKER
    CI_CD --> STG_K8S
    GIT --> CI_CD

    STG_K8S --> STG_PG
    STG_K8S --> STG_ES
    DEV_K8S --> DEV_PG
```

### Ambientes

| Ambiente | Propósito | Replicação | SLA |
|---|---|---|---|
| **Produção** | Operação real, dados reais | Multi-AZ, cluster | 99.9% |
| **Staging** | Testes de integração, UAT | Single-AZ | Best effort |
| **Desenvolvimento** | Desenvolvimento diário | Single-AZ, limitado | Best effort |
| **DR (Disaster Recovery)** | Recuperação em caso de desastre | Região secundária | RTO ≤ 4h, RPO ≤ 15min |

### Topologia de Rede

| Recurso | Especificação |
|---|---|
| **Cloud Provider** | AWS, Azure ou GCP (cloud-agnostic) |
| **Região Primária** | EU-WEST (Portugal, Irlanda, Frankfurt) |
| **Região DR** | EU-CENTRAL (Alemanha) |
| **VPC** | 10.0.0.0/16 com subnets públicas e privadas |
| **Subnets Públicas** | Load balancers, API Gateway, NAT Gateways |
| **Subnets Privadas** | Kubernetes, bases de dados, cache, message broker |
| **TLS** | TLS 1.3+ com certificados ACME / Let's Encrypt |

### Dimensionamento (Produção)

| Recurso | Especificação | Escalabilidade |
|---|---|---|
| Kubernetes Workers | 6-12 nós (t3.large / Standard_D2s_v3) | Auto-scaling (3-20 nós) |
| PostgreSQL | 2+ nós (db.r6g.large), Multi-AZ | Read replicas (3+) |
| Kafka | 3+ nós (m5.large), Multi-AZ | Partições por tópico |
| Redis | 2+ nós (cache.r6g.large), Cluster | Sharding automático |
| Elasticsearch | 3+ nós (m5.large) | Sharding por índice |

## Critérios de Aceitação

- A infraestrutura é replicável via Infrastructure as Code (Terraform)
- O tempo de provisionamento de um ambiente completo é ≤ 60 minutos
- A recuperação de desastre é testada trimestralmente
- O escalonamento automático está activo e testado para picos de carga

## Documentos Relacionados

- [Infraestrutura](infraestrutura.md)
- [Disponibilidade](disponibilidade.md)
- [Backup](backup.md)
- [Recuperação de Desastre](recuperacao-de-desastre.md)
- [11 — Operações](../11-operacoes/index.md)
