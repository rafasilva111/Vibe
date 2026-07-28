# Métricas de Processo

## Propósito
Definir as métricas de negócio para monitorização de processos.

## Métricas

| Métrica | Descrição | Cálculo |
|---|---|---|
| **Processos em aberto** | Nº de processos não concluídos | Contagem |
| **Tempo médio de resposta** | Dias desde abertura até decisão | Média |
| **Taxa de cumprimento** | % dentro do prazo | Concluídos dentro do prazo / Total |
| **Processos por serviço** | Distribuição por tipo | Contagem agrupada |
| **Tarefas pendentes** | Nº de tarefas não concluídas | Contagem |
| **Tempo por fase** | Dias em cada fase | Média por fase |

## Fontes

- Event Store (eventos de domínio)
- Workflow Engine (estados e transições)
- Task Service (tarefas)
