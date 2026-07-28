# Backup

## Propósito
Definir as operações de backup da plataforma.

## Política

| Recurso | Frequência | Retenção | Destino |
|---|---|---|---|
| **Base de Dados** | 6h snapshot + WAL contínuo | 35 dias | S3 + Cross-region |
| **Kafka** | Contínuo (replicação) | 7 dias | Cluster + S3 |
| **Elasticsearch** | 12h snapshot | 30 dias | S3 |
| **S3** | Versionamento + CRR | 35 dias | S3 DR |

## Verificação

- Teste de restauro mensal
- Verificação de integridade semanal
- Relatório de backup diário

## Documentos Relacionados

- [03 — Backup](../03-arquitetura/backup.md)
