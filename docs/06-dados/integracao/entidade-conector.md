# Conector

## Descrição
Conector específico para um sistema externo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| integracao_id | UUID (FK) | Integração associada |
| tipo | Enum | REST, SOAP, LDAP, SQL, SFTP |
| url | String | URL do endpoint |
| autenticacao | JSON | Configuração de autenticação |
| esquema | JSON | Mapeamento de dados |
