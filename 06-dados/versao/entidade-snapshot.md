# Snapshot

## Descrição
Snapshot de estado de um agregado para recovery.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| agregado_tipo | String | Tipo de agregado |
| agregado_id | UUID | ID do agregado |
| versao | Integer | Versão do agregado |
| dados | JSON | Dados do snapshot |
| criado_em | Datetime | Data de criação |
