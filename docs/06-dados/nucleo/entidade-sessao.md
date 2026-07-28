# Sessão

## Descrição
Registo de sessão de autenticação.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| utilizador_id | UUID (FK) | Utilizador |
| token_jwt | String | JWT token |
| ip_origem | String | IP de origem |
| user_agent | String | User agent |
| autenticacao | Enum | CMD, CC, eIDAS, AGov, Interna |
| expiracao | Datetime | Data de expiração |
| criado_em | Datetime | Data de criação |
