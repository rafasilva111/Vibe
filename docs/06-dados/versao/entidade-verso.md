# Versão

## Descrição
Registo de versão de uma entidade configurável.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| entidade_tipo | String | Tipo de entidade versionada |
| entidade_id | UUID | ID da entidade |
| versao | String | Versão semântica |
| dados | JSON | Snapshot dos dados |
| autor_id | UUID (FK) | Autor da alteração |
| criado_em | Datetime | Data da versão |
