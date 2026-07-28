# Diagrama Entidade-Relacionamento

## Propósito

Apresentar o diagrama entidade-relacionamento (DER) conceptual da Junta Observatory Platform, mapeando as principais entidades e seus relacionamentos.

## Entidades Core

```mermaid
erDiagram
    Utilizador ||--o{ Caso : "submete"
    Utilizador ||--o{ Tarefa : "executa"
    Utilizador ||--o{ Documento : "anexa"
    Utilizador {
        uuid id PK
        string nome
        string nif
        string email
        string telefone
        string morada
        enum tipo "CIDADAO, FUNCIONARIO, ADMIN"
        datetime criado_em
    }
    Caso ||--o{ Tarefa : "contem"
    Caso ||--o{ Documento : "possui"
    Caso ||--|| Servico : "refere"
    Caso ||--|| WorkflowInstancia : "executa"
    Caso {
        uuid id PK
        string numero_processo
        uuid servico_id FK
        uuid requerente_id FK
        uuid workflow_instancia_id FK
        enum estado
        datetime criado_em
        datetime concluido_em
    }
    Servico {
        uuid id PK
        string nome
        string descricao
        uuid workflow_id FK
        uuid formulario_id FK
        decimal taxa
        enum estado "ACTIVO, INACTIVO"
    }
    Tarefa ||--|| TipoTarefa : "classifica"
    Tarefa {
        uuid id PK
        uuid caso_id FK
        uuid responsavel_id FK
        string titulo
        enum estado "PENDENTE, EM_CURSO, CONCLUIDA"
        date prazo
        datetime concluido_em
    }
```

## Entidades de Domínio

```mermaid
erDiagram
    Inquilino ||--o{ Utilizador : "tem"
    Inquilino ||--o{ Servico : "oferece"
    Inquilino {
        uuid id PK
        string nome
        string nif
        string email
        enum plano
        enum estado "TRIAL, ACTIVO, SUSPENSO, CANCELADO"
    }
    Documento ||--o{ VersaoDocumento : "tem"
    Documento {
        uuid id PK
        uuid caso_id FK
        enum tipo
        string nome_original
        string caminho_s3
        enum estado
        datetime criado_em
    }
    Workflow {
        uuid id PK
        string nome
        json definicao_estados
        json definicao_transicoes
        enum estado
    }
    WorkflowInstancia {
        uuid id PK
        uuid workflow_id FK
        uuid caso_id FK
        string estado_atual
        json contexto
        datetime iniciado_em
    }
    Notificacao {
        uuid id PK
        uuid destinatario_id FK
        enum canal "EMAIL, SMS, PUSH"
        string template
        json parametros
        enum estado "PENDENTE, ENVIADA, FALHOU"
        datetime criado_em
    }
```

## Documentos Relacionados

- [06 — Índice](index.md)
- [03 — Modelo de Domínio](../03-arquitetura/modelo-de-dominio.md)
