# Organização

## Descrição
Entidade organizacional (junta, departamento).

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | Enum | Junta, Departamento, Pelouro |
| nome | String | Nome |
| sigla | String | Sigla |
| nif | String | NIF (para juntas) |
| responsavel_id | UUID (FK) | Responsável |
