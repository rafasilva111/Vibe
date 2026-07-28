# Execução de Automação

## Descrição
Registo de execução de uma regra de automação.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| regra_id | UUID (FK) | Regra executada |
| evento_id | UUID (FK) | Evento que disparou |
| resultado | Enum | Sucesso, Falhou, Ignorado |
| detalhes | JSON | Detalhes da execução |
| executado_em | Datetime | Data de execução |
