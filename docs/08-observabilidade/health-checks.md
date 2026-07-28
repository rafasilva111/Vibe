# Health Checks

## Propósito
Definir os health checks para monitorização de serviços.

## Endpoints

| Endpoint | Descrição | Intervalo |
|---|---|---|
| `/health` | Liveness — serviço está vivo | 10s |
| `/ready` | Readiness — serviço pronto para tráfego | 10s |
| `/health/db` | Conexão à base de dados | 30s |
| `/health/kafka` | Conexão ao Kafka | 30s |
| `/health/cache` | Conexão ao Redis | 30s |

## Resposta

```json
{
  "status": "healthy",
  "checks": [
    { "name": "database", "status": "healthy", "latency_ms": 5 },
    { "name": "kafka", "status": "healthy", "latency_ms": 12 }
  ],
  "timestamp": "2024-06-15T10:30:00Z"
}
```

## Documentos Relacionados

- [03 — Disponibilidade](../03-arquitetura/disponibilidade.md)
- [11 — Operações](../11-operacoes/index.md)
