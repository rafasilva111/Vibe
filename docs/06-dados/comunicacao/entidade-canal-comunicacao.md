# Canal de Comunicação

## Descrição
Configuração de um canal de comunicação (email, SMS, etc.).

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | Enum | Email, SMS, Push, WhatsApp |
| configuracao | JSON | Configuração do canal |
| activo | Boolean | Se está activo |
