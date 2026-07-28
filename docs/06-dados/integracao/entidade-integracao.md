# Integração

## Descrição
Configuração de integração com sistema externo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome da integração |
| tipo | Enum | API, Webhook, Ficheiro, LDAP |
| sistema_externo | String | Nome do sistema externo |
| configuracao | JSON | Configuração de conexão |
| estado | Enum | Activa, Inactiva, Erro |
