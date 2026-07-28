# Regras de Negócio Globais

## Propósito

Estabelecer as regras de negócio que são transversais a todos os domínios da Junta Observatory Platform, garantindo consistência e conformidade regulatória em toda a plataforma.

## Responsabilidades

- Definir as regras de negócio que aplicam a todos os domínios
- Garantir alinhamento com o enquadramento legal das autarquias
- Servir como referência para validação de processos e workflows

## Descrição Detalhada

### Regras Fundamentais

| ID | Regra | Fundamentação Legal |
|---|---|---|
| RG-01 | Todo o processo deve ter um número de processo único e sequencial por ano | CPA (Código do Procedimento Administrativo) |
| RG-02 | Todo o processo deve ser decidido dentro do prazo legal | CPA, Art. 128.º |
| RG-03 | O cidadão tem direito a consultar o estado do seu processo | CPA, Art. 82.º |
| RG-04 | O cidadão tem direito a obter certidão do processo | CPA, Art. 83.º |
| RG-05 | O silêncio da Administração decorrido o prazo constitui deferimento/indeferimento tácito | CPA, Art. 130.º |
| RG-06 | Toda a decisão deve ser fundamentada de facto e de direito | CPA, Art. 152.º |
| RG-07 | O interessado deve ser ouvido antes da decisão final (direito de audiência prévia) | CPA, Art. 121.º |
| RG-08 | Os dados pessoais só podem ser recolhidos para finalidades determinadas e legítimas | RGPD, Art. 5.º |
| RG-09 | O consentimento do titular deve ser livre, específico, informado e explícito | RGPD, Art. 7.º |
| RG-10 | Os prazos legais são contínuos, não se suspendendo aos sábados, domingos e feriados | CPA, Art. 87.º (salvo excepções) |

### Regras de Validação

| ID | Regra | Domínio |
|---|---|---|
| RG-11 | Um pedido só pode ser submetido se o cidadão estiver identificado | Transversal |
| RG-12 | Um documento só pode ser anexado em formatos permitidos (.pdf, .jpg, .png, .docx) | Documental |
| RG-13 | O tamanho máximo de cada anexo é 20 MB | Documental |
| RG-14 | Um processo não pode ser arquivado se tiver sub-processos pendentes | Processos |
| RG-15 | Um workflow só pode ser activado se tiver pelo menos um passo | Workflow |
| RG-16 | Um formulário só pode ser publicado se todos os campos obrigatórios estiverem definidos | Formulários |
| RG-17 | Uma notificação só é enviada se o destinatário tiver consentido o canal | Notificações |
| RG-18 | Um SLA só é válido se tiver um objectivo mensurável e um prazo | SLA |

### Regras de Transição

| ID | Regra |
|---|---|
| RG-19 | A transição entre estados de um processo deve respeitar a máquina de estados definida |
| RG-20 | Um processo em estado "Em curso" não pode voltar ao estado "Pendente" |
| RG-21 | Um processo "Arquivado" só pode ser reaberto por decisão do Presidente |
| RG-22 | A anulação de um processo requer registo do motivo e identificação do responsável |

### Regras de Auditoria

| ID | Regra |
|---|---|
| RG-23 | Todas as acções sobre processos devem ser registadas no log de auditoria |
| RG-24 | O registo de auditoria é imutável (append-only) |
| RG-25 | O registo de auditoria deve incluir: quem, quando, o quê, em que processo |
| RG-26 | O acesso ao log de auditoria é restrito a funções autorizadas (Presidente, Admin) |

## Requisitos

- As regras de negócio globais devem ser implementadas no motor de workflows
- A violação de uma regra deve impedir a acção e gerar notificação
- As regras baseadas em lei devem referenciar o artigo legal correspondente

## Regras de Negócio (Meta)

- As regras de negócio globais só podem ser alteradas pelo Administrador Global
- Alterações a regras baseadas em lei requerem validação jurídica antes de implementação
- Novas regras devem ser testadas contra processos existentes antes de activação

## Critérios de Aceitação

- As regras RG-01 a RG-10 estão implementadas e validadas com um jurista especializado
- As regras são verificadas automaticamente pelo motor de workflows
- A violação de cada regra produz um erro claro e accionável
- O log de auditoria regista todas as verificações de regras (pass/fail)

## Melhorias Futuras

- Motor de regras de negócio configurável (Business Rules Engine) para personalização por inquilino
- Alertas proactivos para prazos prestes a expirar
- Simulação de impacto antes de alterar regras

## Documentos Relacionados

- [Modelo de Governo](modelo-de-governo.md)
- [Matriz de Permissões](matriz-permissoes.md)
- [Ciclo de Vida de Processos](ciclo-de-vida-processos.md)
- [04 — Serviços Plataforma / Workflow](../04-servicos-plataforma/plataforma-workflow.md)
- [13 — Governança / Lei Administrativa](../13-governanca-conformidade/lei-administrativa.md)
