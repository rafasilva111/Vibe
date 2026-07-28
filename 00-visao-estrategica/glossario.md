# Glossário

## Propósito

Unificar a terminologia utilizada em toda a documentação da Junta Observatory Platform, garantindo que todos os stakeholders partilham o mesmo vocabulário e evitando ambiguidades.

## Responsabilidades

- Definir e manter os termos de negócio e técnicos
- Servir como referência única para interpretação dos documentos
- Evoluir com a plataforma, registando novos termos

## Descrição Detalhada

### Termos de Negócio

| Termo | Definição |
|---|---|
| **Junta de Freguesia** | Órgão autárquico local que administra uma freguesia em Portugal |
| **Presidente da Junta** | Dirigente máximo do órgão executivo da freguesia |
| **Executivo** | Conjunto de membros eleitos que compõem o órgão executivo |
| **Assembleia de Freguesia** | Órgão deliberativo da freguesia |
| **Pelouro** | Área de responsabilidade atribuída a um membro do executivo |
| **Munícipe / Cidadão** | Pessoa que reside ou interage com a Junta de Freguesia |
| **Serviço** | Prestação oferecida pela Junta ao cidadão (ex: emissão de atestado) |
| **Processo** | Conjunto de actividades organizadas para produzir um resultado |
| **Workflow** | Sequência modelada de passos que executam um processo |
| **Pedido** | Solicitação formal de um cidadão para aceder a um serviço |
| **Caso** | Instância de um processo associada a um pedido específico |
| **Parecer** | Opinião técnica ou jurídica emitida no âmbito de um processo |
| **Atestado** | Documento oficial emitido pela Junta comprovando um facto |
| **Licenciamento** | Autorização administrativa para exercer uma actividade |
| **SLA** | Acordo de Nível de Serviço (Service Level Agreement) |
| **KPI** | Indicador-Chave de Desempenho (Key Performance Indicator) |
| **TAT** | Tempo de Atendimento / Turnaround Time |

### Termos Técnicos

| Termo | Definição |
|---|---|
| **Multi-inquilino** | Arquitectura onde uma única instância serve múltiplas organizações |
| **Event Sourcing** | Padrão onde o estado é derivado de uma sequência imutável de eventos |
| **CQRS** | Command Query Responsibility Segregation — separação entre leitura e escrita |
| **Bounded Context** | Contexto delimitado no DDD com modelo e linguagem próprios |
| **Hexagonal Architecture** | Padrão de portas e adaptadores para isolamento do domínio |
| **Microserviço** | Serviço autónomo, independente e especializado |
| **API Gateway** | Ponto único de entrada para chamadas a microserviços |
| **Saga** | Padrão para gestão de transacções distribuídas com compensação |
| **RBAC** | Role-Based Access Control — controlo de acesso baseado em funções |
| **Event Store** | Base de dados optimizada para armazenamento de eventos imutáveis |
| **Process Mining** | Técnica de análise de processos baseada em logs de eventos |
| **RAG** | Retrieval-Augmented Generation — geração aumentada por recuperação |
| **LLM** | Large Language Model — modelo de linguagem de grande escala |
| **eIDAS** | Regulamento europeu sobre identificação electrónica e serviços de confiança |
| **Chave Móvel Digital** | Sistema nacional de autenticação digital para cidadãos |
| **Autenticação.gov** | Plataforma de autenticação da Administração Pública Portuguesa |

### Siglas e Acrónimos

| Sigla | Significado |
|---|---|
| **AMA** | Agência para a Modernização Administrativa |
| **RGPD** | Regulamento Geral de Protecção de Dados (GDPR) |
| **CEPD** | Comité Europeu para a Protecção de Dados |
| **RNID** | Registo Nacional de Identificação Digital |
| **RNPC** | Registo Nacional de Pessoas Colectivas |
| **SIG** | Sistema de Informação Geográfica |
| **SLA** | Service Level Agreement |
| **KPI** | Key Performance Indicator |
| **TAT** | Turnaround Time |
| **API** | Application Programming Interface |
| **REST** | Representational State Transfer |
| **DDD** | Domain-Driven Design |
| **CQRS** | Command Query Responsibility Segregation |
| **RBAC** | Role-Based Access Control |
| **RAG** | Retrieval-Augmented Generation |
| **LLM** | Large Language Model |
| **QA** | Quality Assurance |
| **CI/CD** | Continuous Integration / Continuous Deployment |
| **DR** | Disaster Recovery |

## Requisitos

- O glossário deve ser mantido actualizado ao longo de todo o ciclo de vida do projecto
- Cada novo termo introduzido na documentação deve ser registado no glossário
- Termos duplicados ou com definições conflituantes devem ser resolvidos

## Regras de Negócio

- Termos em português são preferenciais; termos ingleses são aceites quando não existe tradução consagrada
- A primeira ocorrência de um termo do glossário em cada documento deve conter link para a definição

## Critérios de Aceitação

- O glossário contém todos os termos utilizados nos documentos
- Cada termo tem uma definição clara e inequívoca

## Melhorias Futuras

- Glossário dinâmico com extração automática de termos dos documentos
- API do glossário para consulta programática

## Documentos Relacionados

- [Visão Geral](visao-geral.md)
- [Toda a documentação referência este glossário como fonte única de terminologia]
