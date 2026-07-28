# Motor de Recomendação

## Propósito
Definir o motor de recomendação para sugerir acções e decisões.

## Recomendações

| Tipo | Descrição | Base |
|---|---|---|
| **Serviço** | Sugerir serviço adequado ao pedido | Histórico + Regras |
| **Documento** | Sugerir documentos necessários | Checklist do serviço |
| **Despacho** | Sugerir minuta de decisão | Casos similares |
| **Encaminhamento** | Sugerir técnico responsável | Carga + Competência |

## Algoritmo

| Abordagem | Aplicação |
|---|---|
| **Filtragem Colaborativa** | Casos similares ao actual |
| **Baseada em Conteúdo** | Regras do serviço + perfil |
| **Híbrida** | Combinação das anteriores |
