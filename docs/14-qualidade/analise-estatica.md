# Análise Estática

## Propósito
Definir as ferramentas e regras de análise estática de código.

## Ferramentas

| Linguagem | Ferramenta | Perfil |
|---|---|---|
| **Java** | SonarQube + Checkstyle | Qualidade + Estilo |
| **TypeScript** | ESLint + Prettier | Qualidade + Estilo |
| **Python** | Ruff + mypy | Qualidade + Tipos |
| **YAML** | yamllint | Estrutura |

## Regras

| Regra | Severidade | Acção |
|---|---|---|
| **Vulnerabilidade** | Blocker | Bloqueia merge |
| **Bug** | Critical | Bloqueia merge |
| **Code Smell** | Major | Revisão obrigatória |
| **Duplicação** | Minor | Sugestão |
| **Formatação** | Info | Auto-fix |
