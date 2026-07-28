# Diagramas de Estado

## Propósito

Documentar as máquinas de estado dos principais agregados da Junta Observatory Platform, definindo os estados, transições, eventos e regras de cada entidade.

## Responsabilidades

- Definir a máquina de estado de cada agregado
- Garantir que as transições são válidas e consistentes
- Servir como especificação para implementação do motor de workflows

## Descrição Detalhada

### Caso (Processo)

```mermaid
stateDiagram-v2
    [*] --> Rascunho
    Rascunho --> Pendente: Submeter Pedido
    Rascunho --> [*]: Cidadão Desiste
    
    Pendente --> Em_Triagem: Triagem Automática
    Pendente --> Devolvido: Documentos Insuficientes
    Devolvido --> Pendente: Cidadão Corrige
    
    Em_Triagem --> Em_Instrucao: Atribuir Técnico
    Em_Triagem --> Aguarda_Pagamento: Taxa Devida
    Aguarda_Pagamento --> Em_Instrucao: Pagamento Confirmado
    
    Em_Instrucao --> Aguarda_Esclarecimento: Pedir Info Adicional
    Aguarda_Esclarecimento --> Em_Instrucao: Cidadão Responde
    Aguarda_Esclarecimento --> Arquivado: Sem Resposta (Prazo)
    
    Em_Instrucao --> Parecer: Solicitar Parecer Interno
    Parecer --> Em_Instrucao: Parecer Recebido
    
    Em_Instrucao --> Audiencia_Previa: CPA Art. 121
    Audiencia_Previa --> Em_Instrucao: Cidadão Responde
    Audiencia_Previa --> Decisao: Sem Resposta (Prescinde)
    
    Em_Instrucao --> Concluso_Decisao: Instrução Completa
    
    Concluso_Decisao --> Decisao_Favoravel: Despacho
    Concluso_Decisao --> Decisao_Desfavoravel: Despacho
    Concluso_Decisao --> Decisao_Condicionada: Despacho
    
    Decisao_Favoravel --> Notificado: Notificar Cidadão
    Decisao_Desfavoravel --> Notificado: Notificar Cidadão
    Decisao_Condicionada --> Notificado: Notificar Cidadão
    
    Notificado --> Em_Execucao: Cidadão Cumpre Condições
    Notificado --> Recurso: Cidadão Reclama
    
    Recurso --> Decisao_Favoravel: Recurso Deferido
    Recurso --> Decisao_Desfavoravel: Recurso Indeferido
    
    Em_Execucao --> Emissao_Documento: Condições Cumpridas
    Emissao_Documento --> Concluido: Documento Emitido
    
    Concluido --> Arquivado: Arquivo Automático (30 dias)
    
    Arquivado --> [*]
    Arquivado --> Reaberto: Presidente Decide
    Reaberto --> Em_Instrucao
```

### Tarefa

```mermaid
stateDiagram-v2
    [*] --> Pendente: Criada pelo Workflow
    Pendente --> Atribuida: Responsável Designado
    Atribuida --> Em_Curso: Responsável Inicia
    Em_Curso --> Suspensa: Responsável Suspende
    Suspensa --> Em_Curso: Responsável Retoma
    Em_Curso --> Concluida: Responsável Conclui
    Concluida --> Validada: Supervisor Valida
    Concluida --> Reaberta: Validação Falha
    Reaberta --> Em_Curso: Correcção Iniciada
    Pendente --> Cancelada: Workflow Cancelado
    Em_Curso --> Cancelada: Workflow Cancelado
    Validada --> [*]
    Cancelada --> [*]
    
    state Pendente {
        [*] --> Aguarda_Atribuicao
        Aguarda_Atribuicao --> [*]
    }
```

### Workflow

```mermaid
stateDiagram-v2
    [*] --> Rascunho: Criado
    Rascunho --> Em_Validacao: Submeter para Revisão
    Em_Validacao --> Rascunho: Revisão Solicita Alterações
    Em_Validacao --> Activo: Aprovado e Publicado
    Activo --> Desactivado: Administrador Desactiva
    Desactivado --> Activo: Administrador Reactiva
    Activo --> Substituido: Nova Versão Publicada
    Substituido --> Arquivado: Versão Anterior
    Desactivado --> Arquivado: Sem Uso por 180 dias
    Rascunho --> [*]: Eliminado
    Arquivado --> [*]
```

### Documento

```mermaid
stateDiagram-v2
    [*] --> Pendente: Upload Iniciado
    Pendente --> Processando: Upload Completo
    Processando --> Indexado: OCR + Extração OK
    Processando --> Erro: OCR / Extração Falha
    Erro --> Processando: Reprocessar
    Indexado --> Associado: Vinculado a Processo
    Associado --> Substituido: Nova Versão
    Substituido --> Indexado: (versão anterior)
    Indexado --> Arquivado: Processo Arquivado
    Arquivado --> Eliminado: Política de Retenção
    Associado --> Eliminado: Administrador (soft delete)
    Eliminado --> [*]: Hard Delete (após retenção)
```

### Inquilino

```mermaid
stateDiagram-v2
    [*] --> Trial: Registo Inicial
    Trial --> Activo: Subscrição Confirmada
    Trial --> Cancelado: Fim do Trial sem Conversão
    Activo --> Suspenso: Pagamento em Falta (30 dias)
    Activo --> Suspenso: Violação de Termos
    Suspenso --> Activo: Pagamento Regularizado
    Suspenso --> Cancelado: Suspensão > 90 dias
    Activo --> Cancelado: Pedido de Cancelamento
    Cancelado --> [*]: Dados Eliminados (RGPD)
```

## Regras de Negócio

- As transições não especificadas nos diagramas são inválidas por definição
- Cada transição requer um evento válido e autorização do responsável
- Transições entre estados não adjacentes são bloqueadas (excepto rollback autorizado)
- Estados finais (Arquivado, Cancelado, Eliminado) são irreversíveis excepto com autorização especial
- O histórico de todas as transições é registado no event store

## Critérios de Aceitação

- Todas as transições possíveis estão representadas nos diagramas
- O motor de workflows implementa exactamente as transições documentadas
- Transições inválidas retornam erro com a regra violada
- É possível auditar o histórico de estados de qualquer entidade

## Documentos Relacionados

- [Modelo de Domínio](modelo-de-dominio.md)
- [Ciclo de Vida de Processos](../01-analise-de-negocio/ciclo-de-vida-processos.md)
- [04 — Plataforma / Workflow](../04-servicos-plataforma/plataforma-workflow.md)
- [06 — Dados / Caso](../06-dados/processos/entidade-caso.md)
