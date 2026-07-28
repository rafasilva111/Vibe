# Cidadão

## Descrição
Dados específicos do cidadão (extensão do Utilizador).

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| utilizador_id | UUID (FK, UK) | Utilizador associado |
| morada | String | Morada completa |
| freguesia | String | Freguesia de residência |
| concelho | String | Concelho |
| codigo_postal | String | Código postal |
| consentimento_rgpd | Boolean | Consentimento RGPD |
| cmd_validado | Boolean | CMD validado |
