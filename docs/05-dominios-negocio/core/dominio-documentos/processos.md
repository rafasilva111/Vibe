# Documentos — Processos

## Processos

| Processo | Descrição |
|---|---|
| **Upload de Documento** | Submissão de documento por cidadão ou funcionário |
| **Processamento de Documento** | OCR, classificação, extração de metadados |
| **Assinatura Digital** | Assinatura com CMD, CC ou eIDAS |
| **Partilha de Documento** | Disponibilização a terceiros autorizados |
| **Eliminação de Documento** | Eliminação conforme política de retenção |

### Upload e Processamento

```mermaid
flowchart TD
    U[Upload] --> V[Validação<br/>Tipo, Tamanho, Virus]
    V -->|OK| S[Armazenar S3]
    V -->|Inválido| R[Rejeitar]
    S --> P[Processamento<br/>OCR / Classificação]
    P --> I[Indexar no Elasticsearch]
    I --> A[Associar a Processo]
    A --> FIM[Documento Disponível]
```

## Documentos Relacionados

- [Serviços](servicos.md)
- [04 — Documentos](../../../04-servicos-plataforma/plataforma-documentos.md)
