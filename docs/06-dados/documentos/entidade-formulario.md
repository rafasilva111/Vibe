# Formulário

## Descrição
Definição de formulário dinâmico associado a um serviço.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| servico_id | UUID (FK) | Serviço associado |
| nome | String | Nome do formulário |
| versao | String | Versão semântica |
| estado | Enum | Rascunho, Publicado, Substituido |
