# Planeamento de Capacidade

## Propósito
Definir a estratégia de planeamento de capacidade.

## Métricas

| Métrica | Fonte | Horizonte |
|---|---|---|
| **Crescimento de processos** | Event Store | 12 meses |
| **Crescimento de armazenamento** | S3 | 12 meses |
| **Utilização de CPU/RAM** | Prometheus | 6 meses |
| **Utilização de BD** | RDS | 6 meses |
| **Throughput de API** | API Gateway | 6 meses |

## Acções

| Cenário | Acção |
|---|---|
| Uso de BD > 70% | Planear upgrade ou sharding |
| Armazenamento > 75% | Solicitar aumento de capacidade |
| CPU > 70% consistente | Aumentar pods / escala vertical |
| Throughput > 1000 req/s | Rever auto-scaling |
