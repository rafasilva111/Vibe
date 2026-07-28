# RNF-001 — Desempenho

## Propósito

Definir os requisitos de desempenho da Junta Observatory Platform, garantindo tempos de resposta adequados, capacidade de processamento e experiência de utilização satisfatória.

## Descrição

Os requisitos de desempenho cobrem tempos de resposta, capacidade de processamento, concorrência e eficiência em cenários típicos e de pico.

## Requisitos

| ID | Requisito | Limite |
|---|---|---|
| RNF-001.01 | Tempo de resposta da API (p95) | ≤ 500ms |
| RNF-001.02 | Tempo de resposta da API (p99) | ≤ 2s |
| RNF-001.03 | Carregamento de página web | ≤ 3s (p95) |
| RNF-001.04 | Pesquisa full-text | ≤ 2s (p95) |
| RNF-001.05 | Geração de documento a partir de template | ≤ 5s |
| RNF-001.06 | Geração de relatório padrão | ≤ 10s |
| RNF-001.07 | Replay de eventos (10.000 eventos) | ≤ 3s |
| RNF-001.08 | Upload de documento (10 MB) | ≤ 5s |
| RNF-001.09 | Resposta do assistente IA | ≤ 5s |
| RNF-001.10 | Sincronização de dados entre microserviços | ≤ 1s (eventual consistency) |

## Critérios de Aceitação

- Os testes de carga simulam 10x o volume esperado para o primeiro ano
- Os limites são monitorizados em produção com alertas em 80% do limite
- Não há degradação perceptível com 500 utilizadores simultâneos
- O tempo de resposta é medido com tracing distribuído (OpenTelemetry)

## Estratégia de Teste

- Testes de carga com k6 ou Locust simulando perfis de utilizador reais
- Testes de stress para identificar o ponto de ruptura
- Testes de pico (Black Friday da Junta — renovação anual de licenças)
- Monitorização contínua com dashboards de latência

## Métricas

- Latência (p50, p95, p99) por endpoint
- Throughput (requisições/segundo)
- Taxa de erros timeout
- Tempo de resposta do motor de workflows
- Percentil de relatórios gerados dentro do SLA de desempenho

## Documentos Relacionados

- [03 — Arquitectura / Escalabilidade](../../03-arquitetura/escalabilidade.md)
- [12 — Desenvolvimento / Testes de Carga](../../12-desenvolvimento/testes-carga.md)
- [08 — Observabilidade / Métricas Técnicas](../../08-observabilidade/metricas-tecnicas.md)
- [14 — Qualidade](../../14-qualidade/index.md)
