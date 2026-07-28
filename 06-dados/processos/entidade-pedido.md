# Pedido

## Descrição
Registo do pedido inicial que deu origem ao processo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| caso_id | UUID (FK) | Caso associado |
| dados_formulario | JSON | Dados submetidos no formulário |
| canal | Enum | Presencial, Digital, Telefónico |
| submetido_em | Datetime | Data de submissão |
