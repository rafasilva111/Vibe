# Anexo

## Descrição
Anexo associado a um documento ou tarefa.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| documento_id | UUID (FK) | Documento associado |
| nome | String | Nome do anexo |
| caminho_s3 | String | Localização no S3 |
