# Exemplo: E-commerce

> Demonstração de como o framework é aplicado a um projeto de e-commerce.
> Projeto de complexidade média-alta com múltiplos domínios: catálogo, carrinho, pagamento, pedidos.

---

## Contexto do Projeto

**Nome:** Loja Natura Orgânica
**Fase:** Desenvolvimento | Sprint 2 de 5
**Stack:** Next.js 15 + Node.js + PostgreSQL + Stripe + AWS S3
**Idioma:** Português Brasileiro

### Problema

Uma marca de cosméticos naturais vende apenas via WhatsApp e Instagram. O processo manual de pedidos, controle de estoque e pagamentos consome 4 horas por dia da proprietária e gera erros frequentes (produtos fora de estoque vendidos, pagamentos não confirmados, pedidos perdidos).

### Solução

Loja virtual com catálogo gerenciável, carrinho, checkout com Stripe, área do cliente para acompanhar pedidos e painel administrativo simples para a proprietária gerenciar produtos, estoque e pedidos.

### Quem usa

| Perfil | Contexto | Necessidade |
|--------|---------|------------|
| Comprador | Mobile (majoritário), durante o dia | Encontrar produto, comprar e acompanhar entrega sem fricção |
| Proprietária (admin) | Desktop, 1x ao dia | Ver pedidos do dia, atualizar estoque, marcar como enviado |

### Restrições

- Orçamento limitado — sem tecnologias pagas além de Stripe (tarifa por transação)
- Proprietária sem conhecimento técnico — admin deve ser extremamente simples
- LGPD — dados de clientes armazenados no Brasil
- Prazo: MVP em 10 semanas

### Métricas de sucesso

| Métrica | Meta |
|---------|------|
| Tempo de checkout (produto → pagamento) | < 3 minutos |
| Redução de tempo da proprietária em gestão manual | ≥ 60% |
| Taxa de abandono de carrinho | < 70% |
| LCP na página de produto | ≤ 2.5s em 4G |

---

## MVP — O Que Entra na Primeira Entrega

### Entra no MVP

**Comprador:**
- Catálogo com listagem e página de produto
- Carrinho persistente (localStorage)
- Checkout com endereço e pagamento via Stripe
- E-mail de confirmação de pedido
- Página de acompanhamento de pedido por número

**Administrador:**
- Login protegido por senha
- Listagem de pedidos do dia com status
- Atualização de status do pedido (aguardando, enviado, entregue)
- Adição e edição de produtos com foto, preço e estoque

### Fora do MVP

- Sistema de contas de usuário (login de clientes)
- Cupons e promoções
- Avaliações de produtos
- Múltiplos métodos de pagamento (apenas Stripe no MVP)
- Relatórios e dashboard com gráficos
- Programa de fidelidade
- Integração com transportadoras para cálculo de frete automático (frete fixo no MVP)

---

## Backlog

### Alta Prioridade (Sprint 1 — Concluído)

- [x] **BK-001** — Setup do projeto e infraestrutura base `[infra]` — concluído em 2026-05-05
- [x] **BK-002** — Modelagem do banco de dados (produtos, pedidos, endereços) `[database]` — concluído em 2026-05-07
- [x] **BK-003** — API de produtos (CRUD) `[backend]` — concluído em 2026-05-12
- [x] **BK-004** — Página de catálogo com listagem `[frontend]` — concluído em 2026-05-15
- [x] **BK-005** — Página de produto individual `[frontend]` — concluído em 2026-05-18

### Alta Prioridade (Sprint 2 — Em andamento)

- [ ] **BK-006** — Carrinho de compras (adicionar, remover, alterar quantidade) `[frontend]`
  - **O quê:** Carrinho persistido em localStorage com cálculo de total
  - **Por quê:** Núcleo da jornada de compra
  - **Critério:** Persiste entre reloads; atualiza total em tempo real; acessível por teclado

- [ ] **BK-007** — Checkout — etapa de endereço `[frontend] [backend]`
  - **O quê:** Formulário de endereço com validação e cálculo de frete fixo
  - **Por quê:** Primeira etapa do fluxo de pagamento
  - **Critério:** Validação server-side; CEP com autocomplete via ViaCEP; frete fixo R$15

- [ ] **BK-008** — Checkout — integração com Stripe `[backend]`
  - **O quê:** Criação de PaymentIntent, webhook de confirmação, atualização de status do pedido
  - **Por quê:** Monetização — sem isso não há e-commerce
  - **Critério:** Pagamento processado end-to-end em staging; webhook idempotente; falha tratada

- [ ] **BK-009** — E-mail de confirmação de pedido `[backend]`
  - **O quê:** Disparo automático via Resend após confirmação do Stripe
  - **Por quê:** Comprador precisa de confirmação imediata para confiar na compra
  - **Critério:** E-mail recebido em até 1 minuto; contém número do pedido e itens

### Alta Prioridade (Sprint 3)

- [ ] **BK-010** — Painel admin — login e autenticação `[backend] [frontend]`
- [ ] **BK-011** — Painel admin — listagem e atualização de pedidos `[frontend] [backend]`
- [ ] **BK-012** — Painel admin — gestão de produtos e estoque `[frontend] [backend]`
- [ ] **BK-013** — Upload de imagens de produtos para S3 `[backend] [infra]`

### Média Prioridade (Sprints 4-5)

- [ ] **BK-014** — Página de acompanhamento de pedido por número `[frontend]`
- [ ] **BK-015** — Controle de estoque automático ao confirmar pedido `[backend]`
- [ ] **BK-016** — Testes E2E do fluxo de compra completo `[testing]`
- [ ] **BK-017** — Otimização de imagens de produto (WebP, lazy load) `[performance]`

### Baixa Prioridade / Pós-MVP

- [ ] **BK-018** — Login de clientes com histórico de pedidos `[backend] [frontend]`
- [ ] **BK-019** — Cupons de desconto `[backend] [frontend]`
- [ ] **BK-020** — Integração com Correios para cálculo de frete `[backend]`
- [ ] **BK-021** — Dashboard com gráficos de vendas `[frontend]`

---

## Estrutura de Pastas

```
loja-natura-organica/
├── AI_PROJECT_PROTOCOL.md
├── PROJECT_CONTEXT.md
├── STATUS.md
├── README.md
│
├── docs/
│   ├── decisions/
│   │   ├── ADR-0001.md          ← Monorepo vs. repositórios separados
│   │   ├── ADR-0002.md          ← PostgreSQL vs. MongoDB para catálogo
│   │   └── ADR-0003.md          ← Stripe como único gateway no MVP
│   ├── api/
│   │   ├── products.md          ← Contrato da API de produtos
│   │   ├── orders.md            ← Contrato da API de pedidos
│   │   └── webhooks.md          ← Eventos do Stripe
│   ├── business/
│   │   ├── checkout-flow.md     ← Fluxo completo de checkout com estados
│   │   └── order-states.md      ← Máquina de estados do pedido
│   └── backlog.md
│
├── apps/
│   ├── web/                     ← Next.js (loja + checkout)
│   │   └── src/
│   │       ├── app/
│   │       │   ├── (shop)/      ← Rotas da loja
│   │       │   │   ├── page.tsx             ← Catálogo
│   │       │   │   ├── produto/[slug]/
│   │       │   │   ├── carrinho/
│   │       │   │   └── checkout/
│   │       │   ├── (admin)/     ← Rotas do painel admin
│   │       │   │   ├── login/
│   │       │   │   ├── pedidos/
│   │       │   │   └── produtos/
│   │       │   └── api/
│   │       │       ├── products/
│   │       │       ├── orders/
│   │       │       └── webhooks/stripe/
│   │       ├── components/
│   │       ├── lib/
│   │       │   ├── stripe.ts
│   │       │   ├── db.ts
│   │       │   └── email.ts
│   │       └── types/
│
├── packages/
│   └── db/                      ← Schema e migrations (Drizzle ORM)
│       ├── schema/
│       │   ├── products.ts
│       │   ├── orders.ts
│       │   └── addresses.ts
│       └── migrations/
│
├── .env.example
└── package.json                 ← Workspace root (pnpm workspaces)
```

### Decisões técnicas registradas

| Decisão | Escolha | Motivo |
|---------|---------|--------|
| Monorepo | pnpm workspaces | Compartilhar tipos e schema entre web e futuras apps |
| ORM | Drizzle | Type-safe, migrations controladas, sem overhead de ActiveRecord |
| Gateway de pagamento | Stripe | API madura, webhooks confiáveis, SDK oficial para Node e React |
| Upload de imagens | AWS S3 + presigned URLs | Custo baixo, sem processar binário no servidor da API |
| Estado do pedido | Máquina de estados explícita | Pedidos têm fluxo complexo; evita estados inválidos |

### Riscos ativos

| Risco | Probabilidade | Impacto | Mitigação |
|-------|-------------|--------|----------|
| Webhook do Stripe recebido duplicado | Média | Alto | Idempotency key em todas as operações de pedido |
| Produto vendido sem estoque disponível | Alta | Alto | Lock otimista + verificação de estoque no início do checkout |
| Frete fixo insatisfaz clientes de regiões remotas | Média | Médio | Comunicar claramente no checkout; BK-020 pós-MVP |
