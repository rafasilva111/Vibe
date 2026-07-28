# Testes de Regressão

## Propósito
Definir a estratégia de testes de regressão.

## Seleção

| Nível | Seleção | Frequência |
|---|---|---|
| **Unitários** | Todos | Cada commit |
| **Integração** | Todos | Cada commit |
| **E2E** | Fluxos críticos | Cada PR |
| **E2E completo** | Todos os fluxos | Semanal |
| **Visual** | Screenshot diff | Semanal |

## Smoke Tests

| Smoke Test | Verificação |
|---|---|
| **Login** | Autenticação funcional |
| **Criar processo** | Criação de caso |
| **Pesquisar** | Pesquisa retorna resultados |
| **Notificação** | Envio de notificação |
| **API** | Endpoints principais respondem |
