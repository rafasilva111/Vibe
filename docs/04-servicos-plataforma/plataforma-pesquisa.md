# Plataforma — Pesquisa

## Propósito

Disponibilizar funcionalidades de pesquisa full-text e estruturada na Junta Observatory Platform, permitindo encontrar processos, documentos, utilizadores e informação relevante.

## Responsabilidades

- Indexar processos, documentos e metadados
- Disponibilizar pesquisa full-text com relevância
- Suportar filtros por tipo, data, estado, serviço
- Garantir pesquisa segura (por permissões)

## Descrição Detalhada

### Índices

| Índice | Conteúdo | Actualização |
|---|---|---|
| **Processos** | Número, serviço, estado, interessado, datas | Quase real-time (CDC) |
| **Documentos** | Nome, tipo, OCR (texto extraído), metadados | Após processamento |
| **Utilizadores** | Nome, email, NIF, perfil | Near real-time |
| **Catálogo** | Nome do serviço, descrição, grupo | On demand |
| **Conhecimento** | Artigos, legislação, FAQs | On demand |

### Motor de Pesquisa

| Componente | Tecnologia |
|---|---|
| **Indexação** | Elasticsearch |
| **Search API** | Elasticsearch Query DSL |
| **Autocomplete** | Edge n-grams + suggester |
| **Facetas** | Aggregations |
| **Relevância** | BM25 + boosting por campo |

### Segurança na Pesquisa

Os resultados são filtrados por permissão do utilizador:
- **Cidadão**: Apenas os seus próprios processos e documentos
- **Funcionário**: Processos do seu pelouro/equipa
- **Dirigente**: Todos os processos da junta
- **Admin**: Todos os dados

## Documentos Relacionados

- [07 — Interface / Pesquisa](../07-interface-utilizador/index.md)
- [04 — Documentos](plataforma-documentos.md)
- [06 — Dados / Índices](../06-dados/index.md)
