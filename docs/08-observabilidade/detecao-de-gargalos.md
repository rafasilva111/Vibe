# Deteção de Gargalos

## Propósito
Definir a abordagem para deteção de gargalos nos processos.

## Método

| Fase | Descrição |
|---|---|
| **1. Recolha** | Extrair eventos do Event Store |
| **2. Filtragem** | Agrupar por tipo de processo |
| **3. Análise** | Calcular tempo médio por fase |
| **4. Identificação** | Detetar fases com maior tempo de espera |
| **5. Visualização** | Apresentar em dashboard |

## Indicadores de Gargalo

| Indicador | Descrição |
|---|---|
| **Tempo médio por fase** | Fase com maior duração |
| **Variância** | Fase com maior dispersão de tempo |
| **Fila de espera** | Nº de processos à espera numa fase |
| **Reincidência** | Fase com mais devoluções |

## Documentos Relacionados

- [Process Mining](process-mining.md)
- [04 — Dashboards](../04-servicos-plataforma/plataforma-dashboards.md)
