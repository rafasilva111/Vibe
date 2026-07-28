# Requerente

## Descrição
Entidade que submete um pedido (pode ser cidadão ou entidade).

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| tipo | Enum | Cidadão, Empresa, Associação |
| nome | String | Nome completo / razão social |
| nif | String | Número de identificação fiscal |
| contacto_email | String | Email de contacto |
| contacto_telefone | String | Telefone de contacto |
