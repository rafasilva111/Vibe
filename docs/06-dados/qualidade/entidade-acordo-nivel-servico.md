# Acordo de Nível de Serviço

## Descrição
Acordo contratual de nível de serviço com o inquilino.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Inquilino |
| disponibilidade | Decimal | % disponibilidade |
| rto | Integer | RTO em minutos |
| rpo | Integer | RPO em minutos |
| suporte_horas | String | Horário de suporte |
