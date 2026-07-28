# Tarefa

## Descrição
Tarefa atribuída a um utilizador no âmbito de um caso.

## Campos

| Campo | Tipo | Descrição |
|---|---|---|
| id | UUID (PK) | Identificador único |
| caso_id | UUID (FK) | Caso associado |
| responsavel_id | UUID (FK) | Utilizador responsável |
| titulo | String | Título da tarefa |
| descricao | Text | Descrição detalhada |
| tipo | Enum | Análise, Parecer, Despacho, Notificação |
| prioridade | Enum | Baixa, Normal, Alta, Crítica |
| estado | Enum | Pendente, Atribuida, Em Curso, Concluida |
| prazo | Date | Prazo limite |
| concluido_em | Datetime | Data de conclusão |
