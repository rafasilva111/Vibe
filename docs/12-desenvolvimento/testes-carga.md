# Testes de Carga

## Propósito
Definir a estratégia de testes de carga.

## Ferramenta

| Aspecto | Detalhe |
|---|---|
| **Ferramenta** | k6 / JMeter |
| **Métricas** | Latência, throughput, taxa de erro |
| **Cenários** | Pico, carga constante, stress |

## Cenários

| Cenário | Descrição | Alvo |
|---|---|---|
| **Carga Normal** | Tráfego esperado | Latência p95 < 500ms |
| **Pico** | 5x tráfego normal | Latência p95 < 2s |
| **Stress** | 10x até falhar | Identificar ponto de rutura |
| **Resistência** | 24h de carga constante | Sem degradação |
