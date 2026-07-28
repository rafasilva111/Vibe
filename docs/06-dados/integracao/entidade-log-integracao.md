# Log de Integração

## Descrição
Registo de execução de uma integração.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| integracao_id | UUID (FK) | Integração |
| direcao | Enum | Entrada, Saída |
| estado | Enum | Sucesso, Falhou |
| request | JSON | Payload enviado/recebido |
| response | JSON | Resposta |
| erro | Text | Mensagem de erro |
| duracao_ms | Integer | Duração em ms |
| executado_em | Datetime | Data |
