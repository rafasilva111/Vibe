# Template de Domínio Plugin

## Propósito

Este documento serve como template para a criação de novos domínios plugin na Junta Observatory Platform. Cada novo domínio de negócio deve seguir esta estrutura para garantir consistência e completeza da documentação.

## Como Utilizar

1. Copiar a pasta `05-dominios-negocio/plugins/template/` para `05-dominios-negocio/plugins/novo-dominio/`
2. Renomear ficheiros e referências conforme o domínio
3. Preencher cada documento seguindo o template
4. Actualizar o `index.md` do domínio com a informação específica

## Estrutura

```
novo-dominio/
├── index.md               # Visão geral do domínio
├── servicos.md            # Serviços oferecidos pelo domínio
├── processos.md           # Processos típicos do domínio
├── fluxos-de-trabalho.md  # Workflows específicos
├── tarefas.md             # Tarefas operacionais
├── documentos.md          # Documentos necessários e gerados
├── pontos-de-decisao.md   # Decisões críticas do domínio
├── metricas.md            # Métricas e KPIs
├── eventos.md             # Eventos de domínio
├── automacoes.md          # Oportunidades de automação
└── oportunidades-ai.md    # Oportunidades de IA
```

## Modelo de Negócio

Os domínios plugin podem ser:

- **Incluídos no plano base** (ex: Profissional, Enterprise)
- **Add-ons pagos** por domínio adicional
- **Desenvolvidos por terceiros** (marketplace)

## Regras para Plugins

- Um domínio plugin não pode depender de outro domínio plugin (apenas dos core)
- Cada plugin regista os seus serviços no Catálogo de Serviços
- Cada plugin segue o modelo de Bounded Context com fronteiras bem definidas
- A desactivação de um plugin não afecta processos concluídos

## Documentos Relacionados

- [00 — Âmbito](../../00-visao-estrategica/ambito.md)
- [03 — Arquitectura / Bounded Contexts](../../03-arquitetura/bounded-contexts.md)
- [05 — Domínios de Negócio](../index.md)
