# Testes Unitários

## Propósito
Definir as práticas de testes unitários.

## Framework

| Linguagem | Framework |
|---|---|
| **Java** | JUnit 5 + Mockito |
| **TypeScript** | Jest + Vitest |
| **Python** | pytest |

## Práticas

| Prática | Descrição |
|---|---|
| **Arrange-Act-Assert** | Estrutura padrão |
| **Mocks** | Apenas para dependências externas |
| **Nome** | `methodName_deve_comportamento` |
| **Independentes** | Não partilhar estado |
| **Rápidos** | < 100ms cada |
