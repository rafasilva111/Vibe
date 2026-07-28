# Modelo de Notificação

## Descrição
Template de notificação configurável.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do template |
| tipo | Enum | Email, SMS, Push |
| assunto | String | Assunto (email) |
| corpo | Text | Corpo da mensagem (com placeholders) |
| variaveis | JSON | Variáveis disponíveis |
