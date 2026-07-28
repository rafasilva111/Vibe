# Registo de Auditoria

## Descrição
Registo imutável de acções para auditoria.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| ator_id | UUID | Utilizador ou sistema |
| ator_tipo | Enum | Utilizador, Sistema, API |
| accao | String | Acção executada |
| recurso_tipo | String | Tipo de recurso |
| recurso_id | String | ID do recurso |
| dados_anteriores | JSON | Estado anterior |
| dados_novos | JSON | Estado novo |
| ip_origem | String | IP de origem |
| registado_em | Datetime | Data de registo |
