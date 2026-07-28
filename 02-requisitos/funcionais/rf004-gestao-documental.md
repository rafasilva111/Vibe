# RF-004 — Gestão Documental

## Propósito

Fornecer um sistema de gestão documental que permita armazenar, organizar, pesquisar, versionar e controlar o ciclo de vida de todos os documentos produzidos e recebidos pela Junta de Freguesia.

## Descrição

A Gestão Documental cria, armazena e controla documentos digitais (e digitalizações), incluindo modelos de documentos, templates, assinatura digital e controlo de versões. Suporta categorização, metadados, pesquisa full-text e políticas de retenção.

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-004.01 | O sistema deve permitir carregar, armazenar e descarregar documentos | Alta |
| RF-004.02 | O sistema deve suportar os formatos: PDF, DOCX, XLSX, PNG, JPG, TXT | Alta |
| RF-004.03 | O sistema deve extrair e indexar texto de documentos para pesquisa full-text | Alta |
| RF-004.04 | O sistema deve suportar versionamento de documentos | Alta |
| RF-004.05 | O sistema deve permitir definir modelos de documentos com campos dinâmicos | Alta |
| RF-004.06 | O sistema deve gerar documentos a partir de modelos (preenchimento automático) | Alta |
| RF-004.07 | O sistema deve controlar acesso a documentos por função e por processo | Alta |
| RF-004.08 | O sistema deve suportar assinatura digital (simples) e integração com assinatura qualificada | Alta |
| RF-004.09 | O sistema deve permitir categorizar documentos com metadados (tipo, data, processo, etc.) | Alta |
| RF-004.10 | O sistema deve aplicar políticas de retenção e eliminação automática | Média |
| RF-004.11 | O sistema deve permitir digitalizar documentos com OCR integrado | Média |
| RF-004.12 | O sistema deve suportar carimbos digitais e anotações | Baixa |

## Critérios de Aceitação

- Um documento de 10 MB é carregado em menos de 5 segundos
- A pesquisa full-text retorna resultados em menos de 2 segundos
- A geração de um documento a partir de template demora menos de 3 segundos
- O versionamento preserva o histórico completo com possibilidade de restauro
- As políticas de retenção são aplicadas automaticamente na data de eliminação

## Regras de Negócio

- Um documento só pode ser eliminado se não estiver associado a um processo activo
- Documentos com valor legal (certidões, atas) não podem ser eliminados antes do prazo legal
- A substituição de um documento requer justificação e cria nova versão
- Documentos confidenciais (dados de saúde, processos judiciais) têm controlo de acesso restrito

## Métricas

- Número de documentos armazenados por inquilino
- Espaço de armazenamento utilizado
- Percentagem de documentos com OCR completo
- Tempo médio de geração de documentos a partir de modelos

## Documentos Relacionados

- [RF-005 — Formulários Digitais](rf005-formularios-digitais.md)
- [RF-013 — Gestão de Versões](rf013-gestao-de-versoes.md)
- [04 — Serviço Plataforma / Documentos](../../04-servicos-plataforma/plataforma-documentos.md)
- [06 — Dados / Documento](../../06-dados/documentos/entidade-documento.md)
