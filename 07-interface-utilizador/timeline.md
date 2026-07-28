# Timeline

## Propósito
Definir o componente de timeline para visualização do histórico de processos.

## Comportamento

| Característica | Descrição |
|---|---|
| **Ordem Cronológica** | Eventos ordenados do mais recente ao mais antigo |
| **Agrupamento** | Eventos do mesmo dia agrupados |
| **Ícones por Tipo** | Cada tipo de evento tem um ícone distinto |
| **Filtros** | Filtrar por tipo de evento |
| **Expandir** | Detalhes do evento ao clicar |

## Estrutura do Evento

| Campo | Descrição |
|---|---|
| Data/Hora | Timestamp do evento |
| Tipo | Criação, Transição, Decisão, Documento |
| Descrição | Texto descritivo |
| Autor | Quem executou |
| Detalhes | Informação adicional (expansível) |

## Documentos Relacionados

- [Visualização de Processos](visualizacao-processos.md)
- [03 — Event Sourcing](../03-arquitetura/event-sourcing.md)
