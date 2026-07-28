# Artigo de Conhecimento

## Descrição
Artigo da base de conhecimento.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| categoria_id | UUID (FK) | Categoria |
| titulo | String | Título do artigo |
| conteudo | Text | Conteúdo (Markdown) |
| estado | Enum | Rascunho, Publicado, Arquivado |
| tags | JSON | Etiquetas |
| criado_em | Datetime | Data de criação |
| atualizado_em | Datetime | Data de actualização |
