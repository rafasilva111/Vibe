# Âmbito

## Propósito

Definir os limites da Junta Observatory Platform — o que está incluído, o que está excluído, os condicionantes e as fronteiras com sistemas externos.

## Responsabilidades

- Clarificar o perímetro funcional da plataforma
- Evitar ambiguidades sobre o que a plataforma faz ou não faz
- Estabelecer as fronteiras de integração com o ecossistema nacional

## Descrição Detalhada

### Incluído (In-Scope)

**Funcionalidades Core:**
- Catálogo de serviços da Junta de Freguesia
- Motor de workflows com versionamento e histórico
- Gestão de tarefas, subtarefas e checklists
- Gestão documental com templates e assinatura digital
- Formulários dinâmicos com lógica condicional
- Base de conhecimento com pesquisa semântica
- Motor de notificações multi-canal (email, SMS, push)
- Pesquisa full-text e semântica
- Relatórios operacionais e dashboards executivos
- Gestão de SLAs com monitorização automática
- Motor de automação baseado em regras e eventos
- Gestão de versões para workflows, formulários e documentos
- Administração, gestão de utilizadores e RBAC
- Auditoria e event sourcing
- Multi-inquilino com isolamento de dados
- API pública e interna

**Domínios de Negócio Core:**
- Atendimento ao Munícipe
- Licenciamento (obras, actividades, canídeos, etc.)
- Atestados e Certidões
- Gestão de Processos (casos)
- Gestão Documental

**Domínios de Negócio Plugin:**
- Gestão de Espaços e Equipamentos
- Actividades Culturais, Desportivas e Recreativas
- Acção Social
- Obras e Manutenção Urbana
- Ambiente e Sustentabilidade
- Protecção Civil
- Feiras e Mercados
- Cemitérios
- Gestão Financeira e Orçamental
- Recursos Humanos
- Protocolo e Comunicação

**Observabilidade:**
- Modelo de eventos (Event Sourcing)
- Trilha de auditoria completa
- Métricas técnicas, de negócio e de processo
- Dashboards e alertas
- Process mining e detecção de gargalos

**Inteligência Artificial:**
- Assistente virtual para funcionários e cidadãos
- Geração e sumarização de documentos
- Recomendações e sugestões de workflow
- Pesquisa semântica
- Análise preditiva

**Integrações:**
- Chave Móvel Digital
- Autenticação.gov
- ePortugal (conectores)
- Sistemas contabilísticos
- SIG (Sistemas de Informação Geográfica)
- Plataformas nacionais (RNID, RNPC, etc.)

### Excluído (Out-of-Scope)

- **Processamento de pagamentos** — a plataforma integra com gateways externos, não processa pagamentos directamente
- **Contabilidade** — a plataforma regista movimentos, mas não substitui um sistema contabilístico certificado
- **Recursos Humanos (processamento salarial)** — a plataforma gere processos de RH, não processa salários
- **Correio electrónico interno** — a plataforma envia notificações, não substitui o cliente de email
- **Videochamada** — a plataforma regista atendimento remoto, não fornece infraestrutura de videochamada
- **Assinatura digital qualificada (QES)** — a plataforma integra com prestadores de confiança, não emite certificados

### Condicionantes

- A plataforma depende da disponibilidade dos sistemas nacionais (Chave Móvel Digital, Autenticação.gov)
- A adopção da plataforma requer formação dos funcionários da Junta
- A migração de processos existentes requer levantamento prévio por domínio

## Requisitos

- O âmbito deve ser revisto a cada marco do roadmap para confirmar inclusões/exclusões
- A decisão de incluir novo domínio plugin deve ser validada com pelo menos três Juntas de Freguesia

## Regras de Negócio

- Funcionalidades out-of-scope não devem ser planeadas no roadmap sem validação do comité de produto
- Novos domínios plugin seguem o template definido em [template-de-dominio.md](../05-dominios-negocio/plugins/template-de-dominio.md)

## Critérios de Aceitação

- O âmbito está documentado e aprovado pelos stakeholders identificados
- Existe um processo claro para propostas de alteração ao âmbito

## Melhorias Futuras

- Expansão para outro tipo de autarquias locais (Câmaras Municipais)
- Marketplace público de domínios plugin de terceiros

## Documentos Relacionados

- [Visão Geral](visao-geral.md)
- [Objectivos](objetivos.md)
- [Modelo de Valor](modelo-de-valor.md)
- [05 — Domínios de Negócio](../05-dominios-negocio/index.md)
