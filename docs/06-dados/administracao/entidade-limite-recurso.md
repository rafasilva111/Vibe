# Limite de Recurso

## Descrição
Limite de utilização de recursos por inquilino.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Inquilino |
| recurso | Enum | Utilizadores, Armazenamento, Processos, API |
| limite | Integer | Quantidade máxima |
| usado | Integer | Quantidade actual |
