# Utilizador

## Descrição
Entidade que representa um utilizador da plataforma.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Junta associada |
| nome | String | Nome completo |
| nif | String | Número de identificação fiscal |
| email | String | Email |
| telefone | String | Telemóvel |
| tipo | Enum | Cidadão, Funcionário, Admin, Sistema |
| estado | Enum | Activo, Suspenso, Arquivado |
| idioma | String | Idioma preferido (pt-PT) |
| criado_em | Datetime | Data de registo |
