# Operações — Infraestrutura

## Propósito
Documentar a infraestrutura operacional da Junta Observatory Platform.

## Ambientes

| Ambiente | Finalidade | Kubernetes | Base de Dados | Acesso |
|---|---|---|---|---|
| **Produção** | Sistema em produção | EKS produção | RDS produção | Restrito |
| **Staging** | Pré-produção e testes | EKS staging | RDS staging | Equipa |
| **Desenvolvimento** | Desenvolvimento | K8s dev | RDS dev | Todos |

## Recursos

| Recurso | Produção | Staging | Dev |
|---|---|---|---|
| **Nós K8s** | 6+ (3 AZ) | 3 | 2 |
| **CPU** | 16+ vCPU | 8 vCPU | 4 vCPU |
| **RAM** | 64+ GB | 32 GB | 16 GB |
| **Armazenamento** | 500+ GB | 200 GB | 100 GB |
