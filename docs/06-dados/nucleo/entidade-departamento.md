# Departamento

## Descrição
Departamento ou pelouro dentro da junta.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| organizacao_id | UUID (FK) | Organização associada |
| nome | String | Nome do departamento |
| responsavel_id | UUID (FK) | Chefe de departamento |
