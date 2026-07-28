# Regra de Automação

## Descrição
Regra que define uma automação no sistema.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| inquilino_id | UUID (FK) | Junta associada |
| nome | String | Nome da regra |
| evento_gatilho | String | Evento que dispara a regra |
| condicao | JSON | Condições para execução |
| accao | JSON | Acção a executar |
| ordem | Integer | Ordem de avaliação |
| activo | Boolean | Se está activa |
