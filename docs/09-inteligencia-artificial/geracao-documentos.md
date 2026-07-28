# Geração de Documentos

## Propósito
Definir a geração automática de documentos usando IA.

## Documentos Gerados

| Documento | Fonte |
|---|---|
| **Minuta de Despacho** | Dados do processo + similaridade |
| **Notificação** | Template + dados do processo |
| **Parecer** | Análise de documentos + legislação |
| **Relatório** | Dados agregados + templates |

## Fluxo

```mermaid
flowchart TD
    D[Dados] --> LLM[LLM Gera Conteúdo]
    LLM --> V{Validação Humana?}
    V -->|Automático| F[Documento Final]
    V -->|Revisão| H[Humano Revê]
    H --> F
```
