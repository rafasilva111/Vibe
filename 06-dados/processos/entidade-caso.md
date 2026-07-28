# Caso

## Descrição
Entidade central do sistema que representa um processo administrativo.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| numero_processo | String | Número do processo (gerado automaticamente) |
| servico_id | UUID (FK) | Serviço associado |
| requerente_id | UUID (FK) | Cidadão requerente |
| workflow_instancia_id | UUID (FK) | Instância do workflow em execução |
| estado | Enum | Rascunho, Pendente, Em Instrução, Decidido, Arquivado |
| prazo_limite | Date | Prazo legal para decisão |
| criado_em | Datetime | Data de criação |
| concluido_em | Datetime | Data de conclusão |

## Relacionamentos

- N:1 com Servico
- N:1 com Utilizador (requerente)
- 1:N com Tarefa
- 1:N com Documento
