# SLOs e SLIs

## Propósito
Definir os Service Level Objectives e Service Level Indicators da plataforma.

## SLIs

| SLI | Descrição | Fonte |
|---|---|---|
| **Disponibilidade** | % de tempo com serviço disponível | Health checks |
| **Latência p95** | Percentil 95 de latência de requests | Tracing |
| **Taxa de Erro** | % de requests com erro | Logs |
| **Duração do Processo** | Tempo médio de conclusão | Event Store |

## SLOs

| SLO | Alvo | Janela |
|---|---|---|
| **Disponibilidade** | ≥ 99.9% | 30 dias |
| **Latência p95** | ≤ 500ms | 7 dias |
| **Taxa de Erro** | ≤ 0.1% | 7 dias |
| **Cumprimento de Prazos** | ≥ 95% | Mensal |

## Documentos Relacionados

- [03 — Disponibilidade](../03-arquitetura/disponibilidade.md)
- [04 — SLAs](../04-servicos-plataforma/plataforma-slas.md)
