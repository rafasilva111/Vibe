# Serviço

## Descrição
Serviço prestado pela junta, configurado no catálogo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Junta proprietária |
| nome | String | Nome do serviço |
| descricao | Text | Descrição detalhada |
| workflow_id | UUID (FK) | Workflow associado |
| formulario_id | UUID (FK) | Formulário de pedido |
| taxa | Decimal | Valor da taxa |
| estado | Enum | Rascunho, Publicado, Descontinuado |
