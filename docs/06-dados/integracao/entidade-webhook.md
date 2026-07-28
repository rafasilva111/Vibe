# Webhook

## Descrição
Webhook configurado para envio de eventos a sistemas externos.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| url | String | URL de destino |
| eventos | JSON | Lista de eventos que disparam |
| segredo | String | Secret para assinatura HMAC |
| activo | Boolean | Se está activo |
| ultimo_envio | Datetime | Data do último envio |
