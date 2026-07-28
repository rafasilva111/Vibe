# Inquilino

## Descrição
Junta de freguesia cliente da plataforma (tenant).

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome da junta |
| nif | String | NIF |
| email | String | Email institucional |
| site | String | URL do site |
| plano_id | UUID (FK) | Plano de subscrição |
| estado | Enum | Trial, Activo, Suspenso, Cancelado |
| configuracao | JSON | Configurações específicas |
| criado_em | Datetime | Data de criação |
