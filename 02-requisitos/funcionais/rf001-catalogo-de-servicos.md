# RF-001 — Catálogo de Serviços

## Propósito

Permitir que cada Junta de Freguesia defina, organize e publique o seu catálogo de serviços disponíveis aos cidadãos, servindo como ponto de partida para todos os processos da plataforma.

## Descrição

O Catálogo de Serviços é a estrutura central que organiza todos os serviços prestados pela Junta. Cada serviço pode ter múltiplas versões, formulários associados, documentos necessários, prazos legais, taxas e fluxos de workflow. O catálogo é configurável por inquilino e permite categorização hierárquica.

## Requisitos

| ID | Requisito | Prioridade |
|---|---|---|
| RF-001.01 | O sistema deve permitir criar, editar e desactivar serviços no catálogo | Alta |
| RF-001.02 | Cada serviço deve ter: nome, descrição, categoria, departamento responsável, prazo legal, taxa (opcional) | Alta |
| RF-001.03 | O catálogo deve suportar hierarquia de categorias (níveis) | Alta |
| RF-001.04 | O catálogo deve permitir associar a cada serviço: formulários, documentos necessários, workflow, SLA | Alta |
| RF-001.05 | O sistema deve suportar versionamento de serviços | Alta |
| RF-001.06 | O catálogo deve ser pesquisável por nome, categoria e palavra-chave | Alta |
| RF-001.07 | O sistema deve permitir definir serviços como "disponível online", "presencial" ou "ambos" | Média |
| RF-001.08 | O sistema deve permitir definir canais de submissão (balcão, portal, email) | Média |
| RF-001.09 | O catálogo deve ser exportável em formato aberto (JSON, CSV) | Baixa |

## Critérios de Aceitação

- Um administrador consegue criar um novo serviço com todos os campos obrigatórios em menos de 5 minutos
- O catálogo apresenta os serviços organizados por categoria e pesquisáveis
- Cada serviço exibe: descrição, documentos necessários, prazo, taxa e estado
- É possível criar uma nova versão de um serviço sem afectar os processos em curso na versão anterior
- A pesquisa no catálogo retorna resultados em menos de 2 segundos

## Regras de Negócio

- Um serviço só pode ser disponibilizado publicamente após associação a um workflow activo
- Serviços desactivados não são apresentados aos cidadãos mas permanecem no histórico
- A alteração de um serviço com processos em curso requer criação de nova versão
- Cada serviço pertence a um único departamento responsável

## Métricas

- Tempo médio para criação de novo serviço
- Número de serviços activos por inquilino
- Percentagem de serviços com workflow associado
- Taxa de utilização de cada serviço (pedidos submetidos)

## Documentos Relacionados

- [RF-002 — Motor de Workflows](rf002-motor-de-workflows.md)
- [RF-005 — Formulários Digitais](rf005-formularios-digitais.md)
- [RF-013 — Gestão de Versões](rf013-gestao-de-versoes.md)
- [04 — Serviço Plataforma / Catálogo](../../04-servicos-plataforma/plataforma-catalogo.md)
- [06 — Dados / Serviço](../../06-dados/servicos/entidade-servico.md)
