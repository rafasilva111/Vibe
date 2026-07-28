# Monitorização de Infraestrutura

## Propósito
Definir a monitorização de infraestrutura da plataforma.

## Componentes

| Componente | Métricas | Alerta |
|---|---|---|
| **Kubernetes** | CPU, memória, pods, nós | Nó NotReady > 5min |
| **Base de Dados** | Conexões, IOPS, replicação lag | Réplica lag > 10s |
| **Kafka** | Lag, taxas de produção/consumo | Lag > 10000 |
| **Redis** | Hit rate, memória, evictions | Memória > 80% |
| **Elasticsearch** | Status cluster, shards | Cluster status != green |

## Dashboard

- Grafana dashboards por camada
- Alertas no PagerDuty para críticos
- Relatório semanal de tendências
