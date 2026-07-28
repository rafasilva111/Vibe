---
description: Pipeline completo para criar uma nova funcionalidade na Junta Observatory Platform: especificação → arquitectura → implementação → testes.
agent: build
---

# Build Feature Pipeline

Este comando orquestra a criação de uma nova funcionalidade na Junta Observatory Platform. Executa 4 fases em sequência, cada uma delegada a um agente especializado.

## Input

$ARGUMENTS

Descreve a funcionalidade a construir (ex: "Adicionar fluxo de licenciamento com validação de prazos").

## Fases

### Fase 1: Especificação (spec-writer)

Delega ao agente **spec-writer** com a descrição da funcionalidade.

O agente deve:
1. Pesquisar documentação existente em `./docs/`
2. Produzir especificação detalhada seguindo o template IEEE 29148
3. Numerar requisitos (RF e RNF)
4. Guardar o ficheiro em `./docs/<secção apropriada>/`

### Fase 2: Arquitectura (architect)

Delega ao agente **architect** com a especificação produzida na Fase 1.

O agente deve:
1. Identificar Bounded Contexts afectados
2. Desenhar diagramas C4 (Mermaid)
3. Definir contratos de API e eventos
4. Guardar em `./docs/03-arquitetura/`

### Fase 3: Implementação (developer)

Delega ao agente **developer** com a especificação e o desenho arquitectural.

O agente deve:
1. Implementar o código seguindo as normas
2. Escrever testes unitários e de integração
3. Criar Dockerfile multi-stage
4. Documentar API (OpenAPI 3.1)

### Fase 4: Testes (tester)

Delega ao agente **tester** com o código implementado.

O agente deve:
1. Correr lint e build
2. Completar testes em falta
3. Executar suíte completa
4. Reportar cobertura e resultados

## Report Final

Após as 4 fases, apresenta um resumo com:
- Funcionalidade criada
- Ficheiros produzidos (especificação, arquitectura, código, testes)
- Cobertura de testes
- Decisões arquitecturais tomadas
