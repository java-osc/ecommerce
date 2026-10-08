# E-commerce · Java Open Source Collective

**Software livre. Experiência prática. Conhecimento compartilhado.**

[![License: MIT](https://img.shields.io/badge/license-MIT-olive.svg)](LICENSE)
[![Status: Planning](https://img.shields.io/badge/status-planejamento-orange.svg)](#estado-do-projeto)
[![Community](https://img.shields.io/badge/comunidade-Java_Open_Source_Collective-darkgreen.svg)](https://github.com/java-osc)

Um e-commerce de código aberto construído em comunidade, com escopo definido e uma evolução planejada: **do monólito modular aos microsserviços**.

Este é o primeiro projeto da **Java Open Source Collective**, uma iniciativa **100% sem fins lucrativos**, gratuita e baseada em colaboração voluntária. Nosso objetivo é criar software útil e um ambiente onde desenvolvedores possam aprender, experimentar e compartilhar experiência.

**Iniciantes, juniores e pessoas experientes são bem-vindos.** Também há espaço para contribuições em produto, design, testes, documentação e infraestrutura.

> Um laboratório de engenharia de software: tecnologias novas, decisões explicadas, code reviews construtivos e entregas organizadas em sprints.

## Navegação

- [Estado do projeto](#estado-do-projeto)
- [Por que participar](#por-que-participar)
- [O produto](#o-produto)
- [Stack e arquitetura](#stack-e-arquitetura)
- [Roadmap](#roadmap)
- [Como trabalhamos](#como-trabalhamos)
- [Como contribuir](#como-contribuir)
- [Ambiente local](#ambiente-local)
- [Convivência e manutenção](#convivência-e-manutenção)
- [Licença](#licença)

## Estado do projeto

**Em planejamento. Ainda não há aplicação executável ou release disponível.**

Este repositório começa com a apresentação do projeto e sua licença. O backlog, a estrutura da aplicação e as instruções de execução serão adicionados durante a preparação do primeiro ciclo.

O roadmap abaixo representa o plano de trabalho, **não funcionalidades já implementadas**. Datas de início e horários de reuniões ainda serão combinados.

## Por que participar

### Para quem está começando

- Transformar requisitos e critérios de aceitação em código.
- Praticar Git, branches, issues, pull requests, testes e revisão.
- Entender como uma equipe planeja, entrega e melhora um produto.
- Receber feedback técnico com explicação do motivo e do impacto.
- Construir um histórico público de contribuições para apresentar no portfólio.
- Aprender a comunicar decisões, pedir ajuda e sinalizar bloqueios.

### Para quem já tem experiência

- Exercitar mentoria, liderança técnica e revisão de código.
- Discutir arquitetura e registrar decisões e seus trade-offs.
- Experimentar Java e Spring modernos em um produto compartilhado.
- Praticar migração incremental, mensageria e operação de sistemas distribuídos.
- Aprender com outras perspectivas e contribuir para software livre.

A comunidade não é uma vaga de trabalho ou um curso com aulas obrigatórias. **Não há promessa de emprego, remuneração ou certificação.** O aprendizado acontece através da colaboração.

## O produto

Um e-commerce pensado inicialmente para **Brasil e Portugal**, com **uma loja por instalação** e um fluxo de compra completo:

**Consultar catálogo → adicionar ao carrinho → informar endereço → criar pedido → simular pagamento → acompanhar pedido.**

### Escopo da primeira versão

- Cadastro, autenticação e permissões de cliente e administrador.
- Catálogo, categorias, variantes de produtos e estoque.
- Carrinho e checkout.
- Endereços de entrega.
- Pedidos e acompanhamento de seus estados.
- Pagamentos simulados e reserva de estoque.
- Administração de produtos e pedidos.
- Notificações.
- Configuração de país, idioma e moeda, inicialmente pt-BR/pt-PT e BRL/EUR.

### Fora do escopo inicial

- Marketplace e múltiplos vendedores.
- Assinaturas, recomendações e promoções complexas.
- Integrações reais com pagamentos e transportadoras.
- Faturação fiscal e regras tributárias específicas de cada país.

Pagamentos e frete terão contratos próprios e implementações simuladas. Integrações reais poderão ser discutidas depois das duas fases iniciais.

## Stack e arquitetura

| Área | Direção |
| --- | --- |
| Backend | Java 25 e Spring Boot 4 |
| Modularidade | Spring Modulith |
| Fase 1 | Monólito modular por domínio |
| Fase 2 | Extração incremental de microsserviços e mensageria |
| API | REST |
| Infraestrutura | VPS disponível para hospedagem |
| Ambiente e entrega | Docker e CI/CD no planejamento |
| Frontend | A definir |
| Banco de dados | A definir |
| Broker de mensagens | A definir |

As versões exatas, dependências e configurações serão registradas no início da implementação.

### Fase 1 — monólito modular

Entregar uma aplicação funcional com limites claros entre os domínios. Trabalhar modularidade, transações, segurança, testes e comunicação entre módulos antes de introduzir distribuição.

### Fase 2 — microsserviços e eventos

Evoluir o mesmo produto mantendo o fluxo de compra. Extrair gradualmente notificações, pagamentos e estoque; estudar contratos, autonomia de dados, idempotência, retries e compensações.

Não existe compromisso de transformar todo módulo em um serviço. Cada extração deve ter uma justificativa documentada. Catálogo e pedidos podem permanecer juntos inicialmente.

## Roadmap

**11 sprints: 5 na fase 1 e 6 na fase 2.** A cadência proposta é de duas semanas por sprint, com capacidade ajustada à disponibilidade dos participantes.

| Sprint | Foco | Entrega planejada |
| --- | --- | --- |
| 1 | Fundação | Estrutura da aplicação, CI, login, catálogo básico e primeiro deploy |
| 2 | Catálogo e estoque | Gestão de produtos e consulta de disponibilidade |
| 3 | Carrinho e checkout | Carrinho, endereço e criação de pedido |
| 4 | Pagamentos e pedidos | Pagamento simulado, reserva de estoque e transições do pedido |
| 5 | Release do monólito | Notificações, testes dos fluxos principais e documentação |
| 6 | Preparação da migração | Contratos, broker, observabilidade e plano de extração |
| 7 | Notificações | Serviço independente com consumo de eventos e tratamento de falhas |
| 8 | Pagamentos | Serviço de pagamentos simulados com idempotência |
| 9 | Estoque | Serviço de reservas e liberação de estoque |
| 10 | Checkout distribuído | Coordenação do fluxo e compensações |
| 11 | Release distribuída | Testes de falhas, deploy automatizado e documentação operacional |

Antes da sprint 1, haverá preparação de ambiente, onboarding e orientação para a primeira contribuição. A sequência é um plano inicial e poderá ser refinada conforme o aprendizado e a capacidade real da equipe.

## Como trabalhamos

Usamos uma rotina ágil próxima do mercado, adaptada a uma comunidade voluntária.

**Issue → discussão → implementação → pull request → review → ajustes → merge → demonstração.**

### Organização das sprints

| Atividade | Objetivo |
| --- | --- |
| Planning | Definir objetivo, capacidade e tarefas da sprint |
| Acompanhamento assíncrono | Compartilhar progresso, próximo passo e bloqueios |
| Refinamento | Preparar tarefas com contexto e critérios claros |
| Review | Demonstrar o que foi entregue |
| Retrospectiva | Escolher uma melhoria para a próxima sprint |

Não há daily obrigatória. Disponibilidade e horários serão combinados com a equipe.

### Issues e pull requests

Cada tarefa deve ter contexto, escopo pequeno, critérios de aceitação e uma forma de verificar o resultado.

Cada PR deve explicar:

- O problema e a solução proposta.
- A issue relacionada, quando houver.
- Como a mudança foi verificada.
- Limitações ou decisões relevantes.

Prefira mudanças pequenas e focadas. Discuta alterações maiores antes de começar a implementação.

### Code reviews construtivos

| Categoria | Uso |
| --- | --- |
| **Blocking** | Erro, risco ou requisito não atendido que precisa de correção |
| **Suggestion** | Melhoria acompanhada de justificativa |
| **Question** | Pedido de contexto ou oportunidade de aprendizado |

Revisamos o código com respeito. O reviewer explica o motivo e o impacto; o autor pode perguntar, discordar e propor alternativas.

### Quando uma tarefa está concluída

- Critérios de aceitação atendidos.
- Verificações aplicáveis executadas e aprovadas.
- Testes relevantes adicionados ou ajustados quando necessários.
- Review concluído e comentários bloqueantes resolvidos.
- Documentação relevante atualizada.
- Mudança integrada e pronta para demonstração.

## Como contribuir

**Não é necessário ter experiência profissional para começar.**

1. Leia o escopo, o roadmap e o estado atual do projeto.
2. Consulte as [issues](https://github.com/java-osc/ecommerce/issues) existentes.
3. Comente na tarefa em que deseja trabalhar e alinhe o escopo antes de implementar.
4. Se ainda não houver uma tarefa adequada, abra uma issue apresentando sua ideia, dúvida ou interesse em participar.
5. Quando a implementação começar, use um fork e uma branch para sua contribuição.
6. Abra um pull request explicando a mudança e participe do review.

Não precisa começar com uma funcionalidade grande. Documentação, reprodução de problemas, testes e pequenas melhorias também são contribuições importantes.

### Outras formas de ajudar

- Refinar requisitos e fluxos de negócio.
- Propor e revisar interfaces.
- Testar comportamento e acessibilidade.
- Melhorar onboarding e documentação.
- Apoiar CI/CD, observabilidade e ambiente local.
- Revisar PRs e acompanhar participantes iniciantes.

Contribuições de pessoas experientes devem facilitar a participação de outras pessoas e compartilhar o raciocínio por trás das soluções.

## Ambiente local

Ainda não há código de aplicação para executar.

Quando a base técnica estiver disponível, esta seção incluirá pré-requisitos, comandos de build e testes, configuração local e execução com Docker. Não são necessários credenciais de produção ou acesso à VPS para começar a contribuir.

## Convivência e manutenção

- Trate todas as pessoas com respeito, independentemente de experiência ou origem.
- Critique soluções e ideias; não ataque pessoas.
- Avise quando estiver bloqueado ou não puder continuar uma tarefa.
- Respeite o tempo de quem contribui voluntariamente.
- Não publique senhas, tokens, dados pessoais ou dados reais de clientes em issues, PRs ou código.
- Documente decisões relevantes para que outras pessoas possam entendê-las e questioná-las.

**Mantenedor inicial:** [Sergio Henrique Silva (@SergioHs)](https://github.com/SergioHs).

O código de conduta completo, o guia de contribuição e o processo de manutenção serão preparados no onboarding. A participação de novos mantenedores será discutida conforme a comunidade crescer.

Para dúvidas gerais, propostas e relatos de bugs, use as issues. **Não divulgue vulnerabilidades com detalhes exploráveis em uma issue pública**; o canal privado de segurança será definido antes da primeira release.

## Licença

Este projeto é software livre, distribuído sob a [licença MIT](LICENSE).

Você pode usar, estudar, modificar e redistribuir o software, respeitando os termos da licença. A comunidade é sem fins lucrativos; **isso não restringe os usos comerciais permitidos pela licença MIT**.

---

**Construir juntos. Aprender fazendo. Compartilhar sempre.**
