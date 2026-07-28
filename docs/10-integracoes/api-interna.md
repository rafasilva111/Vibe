# API Interna

## Propósito
Definir a API interna para comunicação entre serviços.

## Protocolo

| Aspecto | Detalhe |
|---|---|
| **Formato** | gRPC (comandos) + REST (queries) |
| **Autenticação** | mTLS |
| **Service Mesh** | Istio (futuro) |
| **Descoberta** | Kubernetes DNS |

## Segurança

- mTLS obrigatório para todas as chamadas
- Autorização baseada em permissões do serviço
- Rate limiting por serviço
- Timeout máximo de 10s

## Documentos Relacionados

- [03 — Comunicação entre Serviços](../03-arquitetura/comunicacao-entre-servicos.md)
