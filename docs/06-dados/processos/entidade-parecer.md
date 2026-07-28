# Parecer

## Descrição
Parecer técnico emitido no âmbito de um processo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| caso_id | UUID (FK) | Caso associado |
| autor_id | UUID (FK) | Utilizador que emitiu |
| tipo | Enum | Técnico, Jurídico, Financeiro |
| conteudo | Text | Texto do parecer |
| conclusao | Enum | Favorável, Desfavorável, Condicionado |
| emitido_em | Datetime | Data de emissão |
