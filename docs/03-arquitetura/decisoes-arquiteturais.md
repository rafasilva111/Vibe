# Decisões Arquitecturais (ADR)

## Propósito

Registo das Decisões de Arquitectura (Architecture Decision Records) tomadas ao longo do ciclo de vida da Junta Observatory Platform, documentando o contexto, opções consideradas e justificação de cada decisão.

## Formato

Cada ADR segue o formato [MADR](https://adr.github.io/madr/) (Markdown Any Decision Records):

- **Título**: Número + título curto (ex: `ADR-001: Uso de Event Sourcing`)
- **Estado**: Proposto, Aceite, Depreciado, Substituído
- **Contexto**: Problema ou oportunidade que motiva a decisão
- **Decisão**: A decisão tomada
- **Consequências**: Impactos positivos e negativos
- **Alternativas**: Opções consideradas e rejeitadas

---

### ADR-001: Uso de Event Sourcing

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-01-15 |

**Contexto**: Necessidade de auditabilidade total dos processos, capacidade de replay para analytics e process mining, e suporte a CQRS.

**Decisão**: Adoptar Event Sourcing híbrido — o motor de workflows e o módulo de processos usam Event Store (baseado em PostgreSQL) como fonte de verdade; os dados de referência (catálogos, utilizadores) usam modelo relacional tradicional.

**Consequências**:
- Positivas: Auditabilidade completa, capacidade de reconstruir estado a qualquer momento, feed natural para process mining
- Negativas: Complexidade adicional, curva de aprendizagem, necessidade de snapshots para performance

**Alternativas**:
- Apenas relacional: Rejeitado (falta auditabilidade)
- Full Event Sourcing (tudo no event store): Rejeitado (complexidade desnecessária para dados de referência)

---

### ADR-002: Arquitectura Hexagonal (Ports & Adapters)

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-01-15 |

**Contexto**: Necessidade de isolar a lógica de domínio de frameworks e infraestrutura, facilitar testes e permitir substituição de componentes externos.

**Decisão**: Cada microsserviço segue a arquitectura hexagonal com portas (interfaces) para driven e driving adapters.

**Consequências**:
- Positivas: Domínio testável isoladamente, substituição de adapters sem impacto no core, clara separação de responsabilidades
- Negativas: Mais código boilerplate (interfaces), necessidade de disciplina na equipa

---

### ADR-003: PostgreSQL como Banco de Dados Principal

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-01-20 |

**Contexto**: Selecção do banco de dados relacional para suportar tanto o event store como os dados de referência.

**Decisão**: Utilizar PostgreSQL como base de dados relacional principal, com suporte a JSONB para dados semi-estruturados e replicação por WAL.

**Consequências**:
- Positivas: Maturidade, performance, ecossistema rico, custo zero de licenciamento, suporte a JSONB
- Negativas: Escalabilidade vertical limitada (mitigado com sharding futuro e réplicas de leitura)

**Alternativas**:
- MySQL: Rejeitado (menos suporte a JSON, replicação mais limitada)
- Oracle: Rejeitado (custo proibitivo para SaaS)

---

### ADR-004: Microsserviços vs Monólito

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-01-20 |

**Contexto**: Escolha do estilo arquitectural para a plataforma.

**Decisão**: Microsserviços com bounded contexts bem definidos, comunicações assíncronas via Kafka, síncronas via REST/GraphQL para queries.

**Consequências**:
- Positivas: Escalabilidade independente, deploy independente, equipas autónomas, resiliência
- Negativas: Complexidade de orquestração, observabilidade crítica, consistência eventual

**Alternativas**:
- Monólito: Rejeitado (escalabilidade limitada, deploy monolítico, risco de acoplamento)
- Modulith: Considerado mas rejeitado (não escala para o volume esperado)

---

### ADR-005: Kubernetes como Orquestrador

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-02-01 |

**Contexto**: Selecção da plataforma de orquestração de containers.

**Decisão**: Utilizar Kubernetes (EKS/AKS/GKE) como plataforma de orquestração com Helm Charts para gestão de deploy.

**Consequências**:
- Positivas: Portabilidade, ecossistema rico, auto-scaling, self-healing
- Negativas: Complexidade operacional, curva de aprendizagem, custo do cluster de gestão

---

### ADR-006: Kafka como Event Bus

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-02-01 |

**Contexto**: Necessidade de um barramento de eventos fiável, durável e escalável para comunicação assíncrona entre serviços.

**Decisão**: Utilizar Apache Kafka (MSK) como event bus principal, com tópicos por domínio e consumidores em grupos.

**Consequências**:
- Positivas: Durabilidade, throughput elevado, replay de eventos, ecossistema Kafka Connect
- Negativas: Complexidade operacional, latência adicional vs chamadas síncronas, necessidade de schema registry

---

### ADR-007: Autenticação via OIDC com Federação Nacional

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-02-10 |

**Contexto**: Autenticação de cidadãos portugueses e europeus com os sistemas nacionais (CMD, Autenticação.gov, Cartão Cidadão, eIDAS).

**Decisão**: Utilizar Keycloak como Identity Provider que orquestra a federação com os IdPs nacionais via OIDC/SAML.

**Consequências**:
- Positivas: Um único ponto de integração, suporte a múltiplos protocolos, self-service de conta
- Negativas: Ponto crítico (HA obrigatório), complexidade de configuração dos IdPs

---

### ADR-008: Motor de Workflows Baseado em Eventos

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-02-15 |

**Contexto**: Necessidade de um motor de workflows flexível que suporte processos definidos por configuração (BPMN-like).

**Decisão**: Desenvolver motor de workflows próprio baseado em eventos, com estados definidos por configuração (YAML/JSON), transições accionadas por eventos e validação por regras.

**Consequências**:
- Positivas: Flexibilidade total, integração natural com event sourcing, sem dependência externa
- Negativas: Desenvolvimento interno, necessidade de maturidade, documentação cuidada

**Alternativas**:
- Camunda: Rejeitado (custo de licenciamento, complexidade, overhead)
- Temporal: Rejeitado (curva de aprendizagem, imaturidade na época)

---

### ADR-009: Process Mining Integrado

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-03-01 |

**Contexto**: Funcionalidade de process mining como diferencial competitivo, extraindo processos reais do event store.

**Decisão**: Implementar módulo de process mining que lê do event store e aplica algoritmos de descoberta (Heuristic Miner, Inductive Miner) para gerar modelos de processo.

**Consequências**:
- Positivas: Diferencial competitivo, capacidade de identificar desvios e gargalos, valor analítico
- Negativas: Complexidade algorítmica, custo computacional (batch processing), necessidade de especialização

---

### ADR-010: Multi-Inquilino com Isolamento por Schema

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-03-01 |

**Contexto**: Suporte a múltiplas juntas (inquilinos) com isolamento de dados.

**Decisão**: Isolamento por schema no PostgreSQL (um schema por inquilino) + filas Kafka prefixadas por inquilino + bucket S3 prefixado.

**Consequências**:
- Positivas: Isolamento forte, partilha de recursos, custo reduzido vs bases de dados separadas
- Negativas: Complexidade de migrações, limites de schemas no PostgreSQL, tenant-aware queries

---

### ADR-011: CI/CD com GitOps

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-03-10 |

**Contexto**: Estratégia de deploy e gestão de configuração.

**Decisão**: GitOps com ArgoCD para Kubernetes + CI pipelines (GitLab CI/GitHub Actions) para build, testes e scanning.

**Consequências**:
- Positivas: Git como fonte de verdade, deploy auditável, rollback simples
- Negativas: Complexidade inicial, necessidade de disciplina nos commits

---

### ADR-012: ILM para Elasticsearch

| Campo | Valor |
|---|---|
| **Estado** | Aceite |
| **Data** | 2024-03-15 |

**Contexto**: Gestão do ciclo de vida dos índices do Elasticsearch para process mining e logs.

**Decisão**: Implementar ILM (Index Lifecycle Management) com fases Hot → Warm → Cold → Delete, com index rotation baseada em tempo.

**Consequências**:
- Positivas: Gestão automática de retenção, performance previsível, redução de custos
- Negativas: Complexidade de configuração, necessidade de tuning

---

## ADRs Futuros (Previstos)

| ADR | Tópico | Previsão |
|---|---|---|
| ADR-013 | API Gateway (Kong vs Zuul vs custom) | Fase 2 |
| ADR-014 | GraphQL vs REST (ou ambos) | Fase 2 |
| ADR-015 | Sharding horizontal do PostgreSQL | Fase 3 |
| ADR-016 | Service Mesh (Istio) | Fase 3 |
| ADR-017 | AI/ML pipeline (arquitectura de inferência) | Fase 3 |

## Documentos Relacionados

- [Princípios Arquitecturais](principios.md)
- [Microserviços](microservicos.md)
- [Comunicação entre Serviços](comunicacao-entre-servicos.md)
- [12 — Desenvolvimento](../12-desenvolvimento/index.md)
