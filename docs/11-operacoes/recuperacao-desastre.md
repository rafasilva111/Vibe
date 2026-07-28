# Recuperação de Desastre

## Propósito
Definir o plano de recuperação de desastre operacional.

## Estratégia

| Cenário | RTO | RPO | Acção |
|---|---|---|---|
| **Falha de AZ** | < 30s | 0 | Multi-AZ automático |
| **Falha de Região** | < 15 min | < 5 min | Failover para DR |
| **Corrupção de Dados** | < 4h | < 1h | Restore PITR |

## Runbook

1. Confirmar indisponibilidade da região primária
2. Acionar failover para região DR
3. Promover réplica de BD
4. Redirecionar DNS
5. Verificar integridade
6. Notificar stakeholders

## Documentos Relacionados

- [03 — Recuperação de Desastre](../03-arquitetura/recuperacao-de-desastre.md)
