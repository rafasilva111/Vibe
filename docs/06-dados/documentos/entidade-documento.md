# Documento

## Descrição
Documento digital anexado a um processo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| caso_id | UUID (FK) | Caso associado |
| tipo | Enum | CC, BI, Comprovativo, Relatório, Licença |
| nome_original | String | Nome original do ficheiro |
| caminho_s3 | String | Localização no S3 |
| tamanho_bytes | Integer | Tamanho em bytes |
| mime_type | String | Tipo MIME |
| hash | String | Hash SHA-256 |
| processado | Boolean | Se OCR foi aplicado |
| estado | Enum | Pendente, Processado, Assinado, Eliminado |
