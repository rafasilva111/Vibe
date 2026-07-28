# Métricas de Qualidade

## Propósito
Definir as métricas para avaliação da qualidade.

## Métricas

| Métrica | Descrição | Alvo |
|---|---|---|
| **Cobertura de código** | % de código coberto por testes | ≥ 80% |
| **Dívida técnica** | % de esforço para corrigir código | < 5% |
| **Duplicação** | % de código duplicado | < 3% |
| **Complexidade ciclomática** | Complexidade média por função | < 10 |
| **Tempo de build** | Duração do pipeline CI | < 15 min |
| **Defeitos** | Nº de defeitos por release | < 10 |

## Ferramentas

| Ferramenta | Utilização |
|---|---|
| **SonarQube** | Análise estática, dívida técnica |
| **JaCoCO / Istanbul** | Cobertura de testes |
| **Checkstyle / ESLint** | Estilo de código |
