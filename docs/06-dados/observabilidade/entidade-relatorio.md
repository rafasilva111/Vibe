# Relatório

## Descrição
Relatório gerado pelo sistema.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | Enum | Operacional, Estatístico, Regulatório, Financeiro |
| formato | Enum | PDF, XLSX, CSV |
| parametros | JSON | Parâmetros de geração |
| caminho_s3 | String | Localização do ficheiro |
| gerado_em | Datetime | Data de geração |
