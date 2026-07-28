# Métricas Técnicas

## Propósito
Definir as métricas técnicas para monitorização da infraestrutura.

## Métricas

| Métrica | Descrição | Alerta |
|---|---|---|
| **CPU Usage** | % de CPU por serviço | > 80% |
| **Memory Usage** | % de memória utilizada | > 85% |
| **Request Latency p95** | Latência percentil 95 | > 500ms |
| **Error Rate** | % de requests com erro | > 1% |
| **Throughput** | Requests por segundo | — |
| **Disk Usage** | % de disco utilizado | > 80% |
| **Database Connections** | Conexões activas | > 80% do max |
| **Kafka Lag** | Atraso em mensagens | > 10000 |

## Ferramentas

| Componente | Ferramenta |
|---|---|
| Métricas | Prometheus |
| Dashboards | Grafana |
| Alertas | Alertmanager |
| Logs | Loki / CloudWatch |
| Tracing | Tempo / X-Ray |
