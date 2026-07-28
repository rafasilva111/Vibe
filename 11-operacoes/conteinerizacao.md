# Conteinerização

## Propósito
Definir a estratégia de conteinerização dos serviços.

## Imagens

| Serviço | Imagem Base | Tamanho Alvo |
|---|---|---|
| **API Gateway** | nginx:alpine | < 50 MB |
| **Serviços Java** | eclipse-temurin:21-jre-alpine | < 200 MB |
| **Serviços Python** | python:3.12-slim | < 150 MB |
| **Workers** | eclipse-temurin:21-jre-alpine | < 200 MB |

## Práticas

| Prática | Descrição |
|---|---|
| **Multi-stage** | Build separado do runtime |
| **Imagem Mínima** | Apenas runtime, sem build tools |
| **Scanning** | Trivy para vulnerabilidades |
| **Tagging** | Git commit SHA + versão semântica |
| **Registry** | ECR / Docker Hub privado |
