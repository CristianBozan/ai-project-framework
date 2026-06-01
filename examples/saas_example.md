# Exemplo: SaaS

> Demonstração de como o framework é aplicado a um produto SaaS B2B.
> Projeto de alta complexidade: multitenancy, assinaturas, onboarding, métricas de produto.

---

## Contexto do Projeto

**Nome:** FlowDesk — Gestão de Atendimento ao Cliente
**Fase:** Desenvolvimento | Sprint 4 de 8 (MVP em construção)
**Stack:** Next.js 15 + Node.js + PostgreSQL + Redis + Stripe + AWS
**Idioma:** Português Brasileiro

### Problema

Pequenas e médias empresas de serviços perdem clientes por falta de organização no atendimento: tickets abertos sem resposta, histórico espalhado em e-mail e WhatsApp, sem visibilidade de SLA, sem métricas de desempenho do time de suporte.

### Solução

SaaS de gestão de tickets de suporte para PMEs: inbox unificado (e-mail + WhatsApp), atribuição de tickets, SLA automático, respostas com templates, relatórios básicos e plano por assentos (seats).

### Quem usa

| Perfil | Contexto | Necessidade |
|--------|---------|------------|
| Agente de suporte | Desktop, 8h/dia | Responder tickets rapidamente sem perder contexto |
| Gestor do time | Desktop, algumas vezes ao dia | Ver métricas, redistribuir tickets, monitorar SLA |
| Admin da conta | Desktop, raramente | Configurar integrações, gerenciar usuários, ver fatura |

### Restrições

- Multitenancy obrigatório desde o dia 1 — dados de tenants nunca se misturam
- Conformidade com LGPD — dados de usuários finais dos clientes
- Modelo de pricing: Free (3 agentes, 100 tickets/mês) + Pro (R$49/agente/mês)
- Sem dependência de vendor único para inbox (WhatsApp via Meta API, e-mail via IMAP/SMTP próprio)
- Prazo para beta fechado: 2026-08-01

### Métricas de sucesso

| Métrica | Meta |
|---------|------|
| Tempo médio de primeira resposta (MTTR) | Visível no dashboard em tempo real |
| Onboarding completo (criar conta → primeiro ticket respondido) | < 10 minutos |
| Taxa de conversão Free → Pro | ≥ 8% em 60 dias |
| Churn mensal | < 3% |
| NPS do produto | ≥ 40 após 3 meses |

---

## MVP — O Que Entra na Primeira Entrega (Beta Fechado)

### Entra no MVP

**Produto core:**
- Cadastro e onboarding de empresa (tenant)
- Gestão de agentes (convidar, papéis: agent / manager / admin)
- Inbox de tickets via e-mail (IMAP/SMTP próprio do cliente)
- Criação manual de tickets
- Atribuição e status de ticket (aberto, em andamento, resolvido)
- Respostas com templates de texto
- SLA básico configurável por prioridade
- Notificações por e-mail para o agente ao receber ticket

**Plataforma:**
- Autenticação com Magic Link (sem senha)
- Multitenancy com isolamento por schema no PostgreSQL
- Plano Free com limites aplicados
- Plano Pro com cobrança via Stripe (mensal, por seat)
- Portal de faturamento (Stripe Customer Portal)

### Fora do MVP

- Integração com WhatsApp Business (Meta API)
- Chat em tempo real (WebSocket)
- IA para sugestão de respostas
- Relatórios avançados e exportação
- Automações e workflows
- App mobile
- Integração com Slack/Teams para notificações
- API pública para integrações customizadas

---

## Backlog

### Alta Prioridade (Sprints 1-3 — Concluídos)

- [x] **BK-001** — Infraestrutura base: multitenancy com schema isolation `[database] [infra]` — 2026-04-10
- [x] **BK-002** — Autenticação com Magic Link (email) `[backend]` — 2026-04-15
- [x] **BK-003** — Onboarding de tenant (nome da empresa, subdomínio, primeiro usuário) `[backend] [frontend]` — 2026-04-22
- [x] **BK-004** — Convite e gestão de agentes `[backend] [frontend]` — 2026-04-30
- [x] **BK-005** — CRUD de tickets (criação manual, atribuição, status) `[backend] [frontend]` — 2026-05-08
- [x] **BK-006** — Inbox com paginação e filtros (status, agente, prioridade) `[frontend]` — 2026-05-15

### Alta Prioridade (Sprint 4 — Em andamento)

- [ ] **BK-007** — Integração de e-mail de entrada via IMAP `[backend]`
  - **O quê:** Polling de caixa IMAP do cliente, parse de e-mail, criar ticket automaticamente
  - **Por quê:** Canal principal de entrada de tickets no MVP
  - **Critério:** E-mail recebido → ticket criado em < 2 minutos; threading correto; attachments salvos no S3

- [ ] **BK-008** — Resposta a tickets com envio de e-mail via SMTP `[backend] [frontend]`
  - **O quê:** Editor de resposta, templates, envio via SMTP do cliente, atualização de status
  - **Por quê:** Ação central do produto — sem resposta, não há suporte
  - **Critério:** E-mail enviado em nome do cliente (from: suporte@empresa.com); histórico de thread preservado

- [ ] **BK-009** — SLA automático por prioridade `[backend]`
  - **O quê:** Calcular deadline de resposta ao abrir ticket, alertar ao aproximar do SLA
  - **Por quê:** Diferencial de produto e retenção de gestores
  - **Critério:** Deadline calculado corretamente excluindo fins de semana; notificação 30min antes do vencimento

### Alta Prioridade (Sprints 5-6)

- [ ] **BK-010** — Planos e limites (Free vs. Pro) com enforcement `[backend]`
- [ ] **BK-011** — Integração com Stripe: assinatura mensal por seat `[backend]`
- [ ] **BK-012** — Portal de faturamento (Stripe Customer Portal) `[backend] [frontend]`
- [ ] **BK-013** — Dashboard de métricas básicas (volume, SLA, tempo de resposta) `[frontend] [backend]`
- [ ] **BK-014** — Testes E2E do fluxo crítico: e-mail → ticket → resposta `[testing]`

### Média Prioridade (Sprints 7-8)

- [ ] **BK-015** — Notificações push no browser (ticket atribuído, SLA próximo) `[frontend]`
- [ ] **BK-016** — Relatório exportável (CSV) de tickets do período `[backend] [frontend]`
- [ ] **BK-017** — Auditoria de ações sensíveis (login, exclusão, mudança de papel) `[backend] [security]`
- [ ] **BK-018** — Onboarding interativo (guia passo-a-passo na primeira sessão) `[frontend] [ux]`

### Baixa Prioridade / Pós-MVP

- [ ] **BK-019** — Integração WhatsApp Business `[backend]`
- [ ] **BK-020** — IA para sugestão de resposta (Claude API) `[backend]`
- [ ] **BK-021** — Automações: regras "se X então Y" `[backend]`
- [ ] **BK-022** — App mobile (React Native) `[mobile]`

---

## Estrutura de Pastas

```
flowdesk/
├── AI_PROJECT_PROTOCOL.md
├── README.md
├── project/
│   ├── PROJECT_CONTEXT.md
│   └── STATUS.md
│
├── docs/
│   ├── decisions/
│   │   ├── ADR-0001.md          ← Schema isolation vs. row-level multitenancy
│   │   ├── ADR-0002.md          ← Magic Link vs. senha tradicional
│   │   ├── ADR-0003.md          ← Redis para jobs de e-mail vs. SQS
│   │   └── ADR-0004.md          ← Subdomínio por tenant vs. path-based routing
│   ├── api/
│   │   ├── tickets.md
│   │   ├── agents.md
│   │   ├── tenants.md
│   │   └── webhooks.md
│   ├── business/
│   │   ├── ticket-lifecycle.md  ← Máquina de estados do ticket
│   │   ├── sla-rules.md         ← Regras de SLA por prioridade
│   │   ├── pricing.md           ← Planos, limites e lógica de cobrança
│   │   └── onboarding-flow.md   ← Fluxo de onboarding de novos tenants
│   ├── brainstorms/
│   │   └── 2026-04-05-ai-suggestions.md  ← Exploração de IA para respostas
│   └── backlog.md
│
├── apps/
│   ├── web/                     ← Next.js (App Router)
│   │   └── src/
│   │       ├── app/
│   │       │   ├── (auth)/      ← Login, magic link callback
│   │       │   ├── (app)/       ← Área autenticada (por tenant via subdomínio)
│   │       │   │   ├── inbox/
│   │       │   │   ├── tickets/[id]/
│   │       │   │   ├── settings/
│   │       │   │   └── billing/
│   │       │   └── api/
│   │       │       ├── tickets/
│   │       │       ├── agents/
│   │       │       └── webhooks/
│   │       ├── components/
│   │       └── lib/
│   │           ├── tenant.ts    ← Resolução de tenant por subdomínio
│   │           └── permissions.ts
│
├── packages/
│   ├── db/                      ← Drizzle ORM + migrations
│   │   ├── schema/
│   │   │   ├── tenants.ts
│   │   │   ├── tickets.ts
│   │   │   ├── agents.ts
│   │   │   └── sla.ts
│   │   └── migrations/
│   ├── email-worker/            ← Worker de polling IMAP (Node.js)
│   │   ├── imap-poller.ts
│   │   ├── email-parser.ts
│   │   └── ticket-creator.ts
│   └── queue/                   ← BullMQ + Redis
│       ├── email-ingestion.queue.ts
│       └── sla-monitor.queue.ts
│
├── infra/
│   ├── docker-compose.yml       ← PostgreSQL + Redis para desenvolvimento
│   └── terraform/               ← IaC para AWS (ECS, RDS, ElastiCache)
│
└── .github/
    └── workflows/
        ├── ci.yml               ← Lint, type check, testes
        └── deploy.yml           ← Deploy para staging e produção
```

### Decisões técnicas registradas

| Decisão | Escolha | Motivo |
|---------|---------|--------|
| Multitenancy | Schema isolation por tenant | Máximo isolamento de dados; custo aceitável até ~500 tenants |
| Auth | Magic Link (Resend) | Sem gerenciamento de senha; melhor UX para B2B small teams |
| Fila de jobs | BullMQ + Redis | Polling IMAP e SLA precisam de jobs confiáveis; sem overhead de SQS |
| Roteamento multi-tenant | Subdomínio (tenant.flowdesk.app) | UX superior; permite futuro CNAME customizado |
| Modelo de preço | Por seat/mês | Alinha receita com valor entregue; padrão do mercado de SaaS B2B |

### Riscos ativos

| Risco | Probabilidade | Impacto | Mitigação |
|-------|-------------|--------|----------|
| Limite de conexões PostgreSQL com muitos schemas | Média | Alto | PgBouncer desde o início; monitorar conexões por tenant |
| Rate limit da Meta API (WhatsApp) em pós-MVP | Alta | Médio | Não comprometer delivery do WhatsApp no roadmap público ainda |
| Deliverability de e-mails enviados via SMTP do cliente | Alta | Alto | Documentar requisitos de SPF/DKIM no onboarding |
| Churn alto no plano Free sem conversão | Média | Alto | Feature gate agressivo no Free; in-app nudges para Pro |
