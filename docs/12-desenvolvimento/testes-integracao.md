# Testes de Integração

## Propósito
Definir as práticas de testes de integração.

## Escopo

| Integração | Descrição |
|---|---|
| **Base de Dados** | Queries, transações, concorrência |
| **Kafka** | Produção/consumo de eventos |
| **API** | Endpoints REST completos |
| **Serviços** | Comunicação entre serviços |

## Setup

| Recurso | Tecnologia |
|---|---|
| **BD** | Testcontainers (PostgreSQL) |
| **Kafka** | Testcontainers (Kafka) |
| **Redis** | Testcontainers (Redis) |
| **S3** | MinIO / LocalStack |
