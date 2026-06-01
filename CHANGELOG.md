# Changelog

> Histórico de versões do Framework Base Projetos.
> Formato baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/).
> Versões seguem [Semantic Versioning](https://semver.org/lang/pt-BR/):
> MAJOR.MINOR.PATCH — breaking change . nova feature . correção

---

## [1.0.0] — 2026-06-01

Versão inicial do framework. Estabelece a estrutura base de governança para desenvolvimento de software com AI.

### Adicionado

#### Estrutura Base
- `AI_PROJECT_PROTOCOL.md` — protocolo de colaboração entre humano e AI com 13 seções: princípios, fluxo obrigatório, análise, documentação, implementação, testes, project/STATUS.md, decisões técnicas, brainstorms, backlog, revisão periódica, comunicação e referência rápida
- `project/PROJECT_CONTEXT.md` — arquivo-fonte de verdade do projeto (vazio no template, preenchido por projeto)
- `project/STATUS.md` — rastreamento do estado atual do projeto (vazio no template)
- `README.md` — documentação completa do framework com instalação, uso, fluxo e FAQ
- `START_NEW_PROJECT.md` — guia passo a passo de 9 etapas para iniciar novos projetos
- `SKILLS_INDEX.md` — mapa de ativação de skills por tipo de tarefa, palavras-chave e combinações frequentes
- `CHANGELOG.md` — este arquivo

#### Sistema de Skills (9 especialistas)
- `skills/business_analyst.md` — análise de requisitos e regras de negócio com **Modo de Descoberta** especial para project/PROJECT_CONTEXT.md vazio (entrevista estruturada de 6 blocos)
- `skills/project_manager.md` — planejamento, backlog, project/STATUS.md e revisão periódica
- `skills/ui_ux.md` — fluxos de usuário, arquitetura de informação e design de interface
- `skills/frontend.md` — componentes, telas, integração com APIs e acessibilidade no código
- `skills/backend.md` — APIs, lógica de negócio, autenticação e integrações
- `skills/database.md` — schema, queries, migrations, índices e integridade de dados
- `skills/testing.md` — estratégia de testes, qualidade e investigação de falhas
- `skills/documentation.md` — documentação técnica e de produto
- `skills/devops.md` — CI/CD, infraestrutura, observabilidade e operação

#### Standards Obrigatórios (5 padrões)
- `standards/code_quality.md` — legibilidade, estrutura, comentários, testes e versionamento
- `standards/security.md` — OWASP Top 10, autenticação, validação de entrada e proteção de dados
- `standards/accessibility.md` — WCAG 2.1 AA, navegação por teclado, contraste e semântica HTML
- `standards/performance.md` — Core Web Vitals, SLOs de API, índices e sem queries N+1
- `standards/documentation.md` — o que documentar, onde, como e quando

#### Templates (5 modelos)
- `templates/project_context_template.md` — 11 seções cobrindo visão geral, problema, usuários, objetivos, métricas, restrições, decisões, arquitetura, stack, equipe e glossário
- `templates/status_template.md` — em andamento, bloqueios, concluídos, próximos passos, riscos e notas de sessão
- `templates/backlog_template.md` — IDs sequenciais, 3 faixas de prioridade, concluídos, descartados e tags
- `templates/decision_template.md` — ADR no formato MADR com contexto, opções, decisão e consequências
- `templates/risk_template.md` — probabilidade × impacto, plano de mitigação e de contingência

#### Sistema de Descoberta
- Modo de Descoberta integrado à skill `business_analyst` — ativado automaticamente quando `project/PROJECT_CONTEXT.md` está vazio
- Entrevista estruturada em 6 blocos sequenciais: Problema, Usuários e Stakeholders, Objetivos e Métricas, MVP e Requisitos, Restrições, Riscos
- Protocolo de confirmação por bloco — AI só avança após aprovação explícita do usuário
- Geração do `project/PROJECT_CONTEXT.md` bloqueada até entrevista concluída e aprovada

#### Exemplos de Referência (4 projetos)
- `examples/portfolio_example.md` — projeto solo, baixa complexidade, Next.js + Vercel
- `examples/ecommerce_example.md` — projeto médio-alto, e-commerce com Stripe, monorepo
- `examples/saas_example.md` — projeto de alta complexidade, SaaS B2B com multitenancy e assinaturas
- `examples/academic_project_example.md` — TCC com ML, adaptado para contexto universitário

---

## Convenções de Versionamento

| Tipo de mudança | Incrementa |
|----------------|-----------|
| Mudança incompatível com versões anteriores do protocolo | MAJOR (2.0.0) |
| Nova skill, standard, template ou seção de protocolo | MINOR (1.1.0) |
| Correção de conteúdo, clareza ou erro em arquivo existente | PATCH (1.0.1) |

---

## Roadmap (não versionado)

Melhorias identificadas para versões futuras:

- `standards/languages/` — padrões específicos por linguagem (TypeScript, Python, Go)
- `skills/security_reviewer.md` — especialista dedicado a revisão de segurança
- `skills/architect.md` — especialista em decisões de arquitetura de sistemas
- `templates/brainstorm_template.md` — template para sessões de exploração de ideias
- `templates/onboarding_template.md` — guia de onboarding para novos colaboradores
- `templates/incident_template.md` — registro e post-mortem de incidentes
- Sistema de versionamento do próprio framework via git tags
