# Recuperação de Conhecimento (RAG)

## Propósito
Definir o sistema de Retrieval-Augmented Generation para respostas contextuais.

## Fluxo

```mermaid
flowchart TD
    P[Pergunta] --> E[Embedding]
    E --> VS[Vector Store]
    VS --> D[Documentos Relevantes]
    D --> P2[Prompt + Contexto]
    P2 --> LLM[LLM]
    LLM --> R[Resposta]
```

## Fontes de Conhecimento

| Fonte | Chunking | Indexação |
|---|---|---|
| Base de Conhecimento | 512 tokens | Diária |
| Legislação | 1024 tokens | Semanal |
| FAQs | Por pergunta | Diária |
| Processos Anónimos | 512 tokens | Mensal |

## Documentos Relacionados

- [Estratégia LLM](estrategia-llm.md)
- [Pesquisa Semântica](pesquisa-semantica.md)
