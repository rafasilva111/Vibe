# RF-019 — Assistente IA

## Propósito

Disponibilizar um assistente de inteligência artificial que auxilie funcionários e cidadãos na execução de tarefas, pesquisa de informação, geração de documentos e sugestão de acções, melhorando a produtividade e a experiência de utilização.

## Descrição

O Assistente IA utiliza modelos de linguagem (LLM) combinados com recuperação aumentada por conhecimento (RAG) para responder a perguntas, gerir documentos, sugerir workflows e automatizar tarefas com base no contexto do utilizador e nos dados da plataforma.

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-019.01 | O assistente deve responder a perguntas em linguagem natural sobre processos, documentos e serviços | Alta |
| RF-019.02 | O assistente deve pesquisar na base de conhecimento e documentos para fundamentar respostas | Alta |
| RF-019.03 | O assistente deve gerar documentos a partir de modelos com preenchimento automático | Alta |
| RF-019.04 | O assistente deve sumarizar processos, documentos e históricos de eventos | Alta |
| RF-019.05 | O assistente deve sugerir o próximo passo num workflow com base no contexto | Média |
| RF-019.06 | O assistente deve recomendar acções de automação baseadas em padrões de uso | Média |
| RF-019.07 | O assistente deve permitir conversação contextual (histórico da sessão) | Alta |
| RF-019.08 | O assistente deve respeitar as permissões do utilizador (só responde com info autorizada) | Alta |
| RF-019.09 | O assistente deve suportar pesquisa semântica em todos os documentos indexados | Alta |
| RF-019.10 | O sistema deve registar todas as interacções com o assistente para auditoria e melhoria | Média |

## Critérios de Aceitação

- O assistente responde a perguntas sobre processos em menos de 3 segundos
- As respostas incluem referência aos documentos fonte utilizados
- A geração de um documento padrão (ex: certidão) demora menos de 5 segundos
- O assistente não revela informação que o utilizador não tenha permissão para aceder
- As conversas são retomadas correctamente entre sessões (contexto preservado)

## Regras de Negócio

- O assistente não pode executar acções críticas (despachar, arquivar, eliminar) sem confirmação humana
- As respostas do assistente devem incluir aviso de verificação humana para decisões vinculativas
- Dados pessoais só são utilizados no contexto da pergunta e não para treino do modelo
- O histórico de interacções é retido por 90 dias para melhoria do modelo

## Métricas

- Taxa de respostas consideradas úteis (feedback do utilizador)
- Percentagem de perguntas respondidas sem intervenção humana
- Tempo médio de resposta
- Número de interacções por utilizador por dia
- Precisão da pesquisa semântica (top-3 relevante)

## Documentos Relacionados

- [RF-006 — Base de Conhecimento](rf006-base-de-conhecimento.md)
- [RF-008 — Motor de Pesquisa](rf008-motor-de-pesquisa.md)
- [09 — Inteligência Artificial](../../09-inteligencia-artificial/index.md)
- [09 — Assistente Virtual](../../09-inteligencia-artificial/assistente-virtual.md)
- [09 — Estratégia LLM](../../09-inteligencia-artificial/estrategia-llm.md)
