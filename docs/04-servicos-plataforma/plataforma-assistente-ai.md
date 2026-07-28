# Plataforma — Assistente AI

## Propósito

Descrever o assistente baseado em inteligência artificial da Junta Observatory Platform, que auxilia cidadãos e funcionários na interacção com a plataforma.

## Responsabilidades

- Responder a perguntas de cidadãos sobre processos e serviços
- Sugerir acções e preencher formulários automaticamente
- Auxiliar funcionários na pesquisa de informação
- Classificar e encaminhar pedidos

## Descrição Detalhada

### Canais

| Canal | Público | Funcionalidades |
|---|---|---|
| **Chat Web** | Cidadão | FAQ, estado do processo, documentos necessários |
| **Chat Funcionário** | Funcionário | Pesquisa de processos, sugestão de despacho |
| **Voice (futuro)** | Cidadão | Interacção por voz (CTI) |

### Capacidades

| Capacidade | Descrição | Modelo |
|---|---|---|
| **FAQ Inteligente** | Responder perguntas frequentes com base na documentação | RAG (embeddings) |
| **Preenchimento Automático** | Sugerir respostas em formulários com base em dados existentes | LLM + dados do cidadão |
| **Classificação** | Classificar pedidos por tipo, urgência e serviço | Classificador (ML) |
| **Sumarização** | Sumarizar processos longos para decisão | LLM |
| **Encaminhamento** | Sugerir técnico responsável com base na carga | Regras + ML |

## Documentos Relacionados

- [09 — Inteligência Artificial](../09-inteligencia-artificial/index.md)
- [02 — RF020](../02-requisitos/funcionais/rf020.md)
- [05 — Core / Atendimento](../05-dominios-negocio/core/dominio-atendimento/index.md)
