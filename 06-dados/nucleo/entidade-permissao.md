# Permissão

## Descrição
Permissão atribuída a um perfil ou utilizador.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| codigo | String | Código único (ex: caso.ler) |
| nome | String | Nome amigável |
| descricao | String | Descrição |
| recurso | String | Recurso alvo (caso, documento, etc.) |
| accao | String | Acção (ler, criar, editar, eliminar) |
