# Notificação

## Descrição
Registo de notificação enviada a um utilizador.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| destino_id | UUID (FK) | Utilizador destino |
| canal | Enum | Email, SMS, Push, CaixaPostal |
| template | String | Template utilizado |
| parametros | JSON | Parâmetros do template |
| estado | Enum | Pendente, Enviada, Falhou, Lida |
| criado_em | Datetime | Data de criação |
| enviado_em | Datetime | Data de envio |
