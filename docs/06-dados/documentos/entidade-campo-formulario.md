# Campo de Formulário

## Descrição
Campo individual de um formulário dinâmico.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| formulario_id | UUID (FK) | Formulário associado |
| tipo | Enum | Texto, Número, Data, Selecção, Ficheiro |
| rotulo | String | Rótulo do campo |
| obrigatorio | Boolean | Se é obrigatório |
| ordem | Integer | Ordem de apresentação |
| validacao | JSON | Regras de validação |
| opcoes | JSON | Opções (para selecção) |
