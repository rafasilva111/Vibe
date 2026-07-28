# 07 — Interface Utilizador

## Propósito

Esta secção documenta a interface de utilizador da Junta Observatory Platform, incluindo o sistema de design, navegação, componentes, formulários, dashboards, acessibilidade, modo escuro e padrões de interacção.

## Responsabilidades

- Definir o sistema de design e os componentes de UI
- Estabelecer os padrões de navegação e interacção
- Garantir acessibilidade, responsividade e consistência
- Servir como referência para a equipa de frontend e design

## Documentos

| Documento | Descrição |
|---|---|
| [Princípios de Design](principios-design.md) | Princípios de UX e identidade visual |
| [Sistema de Design](sistema-de-design.md) | Design system (cores, tipografia, spacing) |
| [Navegação](navegacao.md) | Estrutura de navegação global |
| [Painel Principal](painel-principal.md) | Dashboard principal do utilizador |
| [Formulários](formularios.md) | Padrões de formulários |
| [Pesquisa](pesquisa-interface.md) | Interface de pesquisa |
| [Acessibilidade](acessibilidade.md) | Conformidade WCAG 2.1 AA |
| [Design Responsivo](design-responsivo.md) | Adaptação a múltiplos dispositivos |
| [Modo Escuro](modo-escuro.md) | Dark mode |
| [Notificações](notificacoes-interface.md) | Interface de notificações |
| [Timeline](timeline.md) | Visualização de timeline de processos |
| [Construtor de Workflows](construtor-de-workflows.md) | Editor visual de workflows |
| [Painel de Administração](painel-de-administracao.md) | Interface administrativa |
| [Gestão de Perfis](gestao-de-perfis.md) | Perfis de utilizador |
| [Visualização de Processos](visualizacao-processos.md) | Vista detalhada de processos |
| [Componentes](componentes.md) | Catálogo de componentes UI |
| [Padrões de Interacção](padroes-de-interacao.md) | Micro-interações e feedback |

## Stack Frontend (Referência)

| Camada | Tecnologia |
|---|---|
| Framework | React 19 + TypeScript |
| Design System | Storybook + Tailwind CSS |
| State Management | Zustand / TanStack Query |
| Forms | React Hook Form + Zod |
| Charts | Recharts / D3.js |
| Workflow Builder | React Flow |
| Testing | Playwright + Vitest |
| Build | Vite |
| PWA | Workbox |

## Documentos Relacionados

- [02 — Requisitos Funcionais](../02-requisitos/funcionais/index.md)
- [03 — Arquitectura](../03-arquitetura/index.md)
- [14 — Qualidade / Acessibilidade](../14-qualidade/index.md)
