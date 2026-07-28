# Entidade Externa

## Descrição
Entidade externa (empresa, associação, organismo) que interage com a plataforma.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | Enum | Empresa, Associação, Organismo, IPSS |
| nome | String | Nome / razão social |
| nif | String | NIF |
| contacto_nome | String | Nome do contacto |
| contacto_email | String | Email do contacto |
| contacto_telefone | String | Telefone |
