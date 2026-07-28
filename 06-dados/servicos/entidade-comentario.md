# Comentário

## Descrição
Comentário interno num caso ou tarefa.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| caso_id | UUID (FK) | Caso associado |
| autor_id | UUID (FK) | Autor do comentário |
| conteudo | Text | Conteúdo do comentário |
| criado_em | Datetime | Data de criação |
