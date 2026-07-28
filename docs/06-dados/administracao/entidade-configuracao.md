# Configuração

## Descrição
Configuração do sistema por inquilino.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Inquilino |
| chave | String | Chave da configuração |
| valor | JSON | Valor |
| tipo | Enum | Global, Inquilino, Utilizador |
