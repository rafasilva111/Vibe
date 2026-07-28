# Workflow

## Descrição
Definição do workflow associado a um serviço.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| nome | String | Nome do workflow |
| versao | String | Versão semântica |
| definicao_estados | JSON | Mapa de estados possíveis |
| definicao_transicoes | JSON | Mapa de transições permitidas |
| estado | Enum | Rascunho, Activo, Arquivado |
