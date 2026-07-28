# RF-002 — Motor de Workflows

## Propósito

Fornecer um motor de execução de workflows que permita modelar, executar, versionar e monitorizar os processos da Junta de Freguesia, garantindo rastreabilidade total e conformidade com as regras de negócio.

## Descrição

O Motor de Workflows é o coração da plataforma. Permite definir diagramas de processos com passos, transições, condições, prazos e responsáveis. Cada workflow é versionado e pode ser associado a um ou mais serviços do catálogo. A execução de cada instância de processo é registada como uma sequência imutável de eventos.

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-002.01 | O sistema deve permitir modelar workflows visualmente (construtor drag-and-drop) | Alta |
| RF-002.02 | O workflow deve suportar passos: humanos, automáticos, de decisão, de sub-processo | Alta |
| RF-002.03 | O workflow deve suportar condições e ramificações (exclusivas, paralelas, inclusivas) | Alta |
| RF-002.04 | O sistema deve permitir definir prazos por passo e para o workflow completo | Alta |
| RF-002.05 | O sistema deve associar responsáveis a cada passo (função, grupo ou utilizador específico) | Alta |
| RF-002.06 | O sistema deve suportar versionamento completo de workflows | Alta |
| RF-002.07 | O motor deve executar workflows iniciando novas instâncias quando um pedido é submetido | Alta |
| RF-002.08 | O motor deve emitir eventos para cada transição de estado | Alta |
| RF-002.09 | O motor deve verificar regras de negócio e impedir transições inválidas | Alta |
| RF-002.10 | O sistema deve permitir suspender, retomar e cancelar instâncias de workflow | Média |
| RF-002.11 | O sistema deve suportar sub-processos (workflow dentro de workflow) | Média |
| RF-002.12 | O sistema deve permitir delegar temporariamente tarefas a outro utilizador | Média |

## Critérios de Aceitação

- Um administrador consegue modelar um workflow de 5 passos em menos de 10 minutos
- O motor executa correctamente fluxos sequenciais, paralelos e com condições
- Cada transição de estado é registada como evento imutável
- Workflows com erros de modelação são rejeitados com mensagens claras
- Uma nova versão de workflow não afecta instâncias em execução na versão anterior

## Regras de Negócio

- Um workflow só pode ser activado se tiver pelo menos um passo e um estado final
- A alteração de um workflow com instâncias em execução requer nova versão
- Um passo automático não pode ter responsável humano atribuído
- O deadline de cada passo é calculado com base no calendário da Junta (dias úteis)
- Instâncias paradas há mais de 90 dias são automaticamente notificadas ao administrador

## Métricas

- Número de workflows por inquilino
- Tempo médio de execução por tipo de workflow
- Percentagem de workflows concluídos dentro do prazo
- Número de instâncias canceladas vs concluídas
- Topologia de gargalos por passo do workflow

## Documentos Relacionados

- [RF-001 — Catálogo de Serviços](rf001-catalogo-de-servicos.md)
- [RF-003 — Gestão de Tarefas](rf003-gestao-de-tarefas.md)
- [RF-012 — Automação](rf012-automacao.md)
- [RF-013 — Gestão de Versões](rf013-gestao-de-versoes.md)
- [04 — Serviço Plataforma / Workflow](../../04-servicos-plataforma/plataforma-workflow.md)
- [08 — Observabilidade / Process Mining](../../08-observabilidade/process-mining.md)
