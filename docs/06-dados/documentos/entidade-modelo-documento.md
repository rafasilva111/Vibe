# Modelo de Documento

## Descrição
Template para geração automática de documentos.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do modelo |
| tipo | Enum | Atestado, Licença, Notificação, Declaração |
| template | Text | Template (ODT/docx) |
| variaveis | JSON | Variáveis disponíveis |
| versao | String | Versão |
