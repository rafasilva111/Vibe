# Desenvolvimento — Pipeline CI

## Propósito
Definir o pipeline de Continuous Integration.

## Etapas

| Etapa | Duração | Ferramenta |
|---|---|---|
| **Lint** | 2 min | ESLint, Checkstyle |
| **Build** | 5 min | Maven / Gradle / npm |
| **Testes Unitários** | 5 min | JUnit, pytest, Jest |
| **SAST** | 3 min | SonarQube |
| **SCA** | 2 min | Trivy, Snyk |
| **Imagem Docker** | 3 min | Docker build |
| **Push Registry** | 1 min | ECR / Docker Hub |

## Ferramenta

| Aspecto | Detalhe |
|---|---|
| **Plataforma** | GitLab CI / GitHub Actions |
| **Self-hosted** | Runner Kubernetes (escalável) |
| **Cache** | Cache de dependências entre runs |
| **Artefactos** | Relatórios de teste, cobertura, scan |
