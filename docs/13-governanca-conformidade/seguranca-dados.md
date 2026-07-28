# Segurança de Dados

## Propósito
Definir as medidas de segurança para protecção de dados.

## Medidas

| Dimensão | Medida |
|---|---|
| **Encriptação repouso** | AES-256 (BD, S3, Kafka) |
| **Encriptação trânsito** | TLS 1.3 |
| **Pseudonimização** | Dados pessoais pseudonimizados em analytics |
| **Controlo de acesso** | RBAC + MFA |
| **Auditoria** | Todos os acessos a dados pessoais são registados |
| **Backup** | Encriptado, cross-region |

## Classificação

| Nível | Dados | Requisitos |
|---|---|---|
| **Público** | Informações genéricas | Sem restrições |
| **Interno** | Procedimentos, relatórios | Autenticação |
| **Confidencial** | Dados pessoais, processos | RBAC + encriptação |
| **Restrito** | Dados sociais, saúde | RBAC + MFA + auditoria |
