# Logging Centralizado

## Propósito
Definir a estratégia de logging centralizado.

## Stack

| Componente | Tecnologia |
|---|---|
| **Colecta** | Fluentd / Vector |
| **Armazenamento** | Loki (CloudWatch) |
| **Pesquisa** | Grafana / Kibana |
| **Retenção** | 30 dias (quente) + 1 ano (frio) |

## Estrutura

- Logs estruturados em JSON
- Correlation ID (traceId) em todos os logs
- Níveis: DEBUG, INFO, WARN, ERROR
- Indexado por serviço, ambiente, tenant

## Documentos Relacionados

- [08 — Gestão de Logs](../08-observabilidade/gestao-de-logs.md)
