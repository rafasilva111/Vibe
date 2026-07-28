# Tracing Distribuído

## Propósito
Definir a estratégia de tracing distribuído para correlação de requisições entre serviços.

## Implementação

| Componente | Tecnologia |
|---|---|
| **Instrumentação** | OpenTelemetry |
| **Backend** | Tempo (Grafana) / X-Ray (AWS) |
| **Propagação** | W3C Trace Context |
| **Amostragem** | Head-based (10% produção, 100% staging) |

## Informações por Span

| Campo | Descrição |
|---|---|
| `traceId` | ID do trace |
| `spanId` | ID do span |
| `parentSpanId` | Span pai |
| `serviceName` | Nome do serviço |
| `operation` | Operação executada |
| `duration` | Duração em ms |
| `status` | OK / Error |
| `tags` | Tags contextuais |

## Documentos Relacionados

- [03 — Comunicação entre Serviços](../03-arquitetura/comunicacao-entre-servicos.md)
