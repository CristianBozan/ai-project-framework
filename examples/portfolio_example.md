# Exemplo: Portfólio Pessoal

> Demonstração de como o framework é aplicado a um projeto pessoal de portfólio.
> Referência: use `templates/project_context_template.md` como base ao iniciar seu projeto.

---

## Contexto do Projeto

**Nome:** Portfólio — Cristian Bozan
**Fase:** Desenvolvimento | MVP
**Stack:** Next.js 15 + TypeScript + Tailwind CSS + Vercel
**Idioma:** Português Brasileiro

### Problema

Recrutadores e clientes potenciais não conseguem avaliar o trabalho e as habilidades do desenvolvedor porque não há um ponto de referência centralizado — projetos estão espalhados em GitHub, LinkedIn e conversas avulsas.

### Solução

Site estático de portfólio com apresentação pessoal, projetos destacados, stack tecnológica, blog técnico e formulário de contato — hospedado com deploy contínuo na Vercel.

### Quem acessa

| Perfil | Contexto | Necessidade |
|--------|---------|------------|
| Recrutador técnico | Desktop, durante triagem de candidatos | Avaliar fit técnico em menos de 2 minutos |
| Cliente potencial | Mobile ou desktop, referenciado por alguém | Entender o que o dev faz e como contratar |
| Colega de área | Qualquer dispositivo | Ver projetos e trocar conhecimento |

### Métricas de sucesso

| Métrica | Meta |
|---------|------|
| Tempo para entender o que o dev faz | < 30 segundos |
| Score Lighthouse (Performance) | ≥ 95 |
| Score Lighthouse (Acessibilidade) | ≥ 95 |
| Taxa de cliques no contato | ≥ 5% das visitas |

---

## MVP — O Que Entra na Primeira Entrega

O MVP entrega valor imediato com escopo mínimo. Tudo que não está aqui é backlog.

### Entra no MVP

- Página inicial com apresentação pessoal e foto
- Seção de projetos com cards linkando para GitHub ou demo
- Seção de stack tecnológica
- Formulário de contato funcional (envio por e-mail)
- Design responsivo (mobile e desktop)
- Deploy automático na Vercel a cada push na main

### Fora do MVP (backlog)

- Blog técnico
- Modo escuro
- Animações e micro-interações
- Analytics
- Versão em inglês
- Filtro de projetos por tecnologia

---

## Backlog

### Alta Prioridade (MVP)

- [ ] **BK-001** — Setup inicial do projeto Next.js com TypeScript e Tailwind `[infra]`
  - **O quê:** Criar repositório, configurar Next.js 15, Tailwind, ESLint, Prettier e deploy na Vercel
  - **Por quê:** Base para tudo que vem depois
  - **Critério:** App rodando localmente e deploy automático funcionando na Vercel

- [ ] **BK-002** — Layout base e componentes de navegação `[frontend]`
  - **O quê:** Header com nav, footer, layout responsivo global
  - **Por quê:** Estrutura que todas as páginas usarão
  - **Critério:** Navegação funcional no mobile e desktop, foco de teclado visível

- [ ] **BK-003** — Seção Hero (apresentação pessoal) `[frontend]`
  - **O quê:** Nome, título profissional, breve bio, foto e links (GitHub, LinkedIn)
  - **Por quê:** Primeira impressão — responde "quem é essa pessoa" em 10 segundos
  - **Critério:** Carrega sem layout shift, alt na foto, texto legível em mobile

- [ ] **BK-004** — Seção de Projetos `[frontend]`
  - **O quê:** Grid de cards com nome, descrição, stack usada, link para GitHub e demo
  - **Por quê:** Maior interesse de recrutadores e clientes
  - **Critério:** Cards com estado de hover, acessíveis por teclado, sem imagens quebradas

- [ ] **BK-005** — Seção de Stack Tecnológica `[frontend]`
  - **O quê:** Lista visual das tecnologias com ícone, nome e nível de experiência
  - **Por quê:** Recrutadores filtram por tecnologia antes de ler o resto
  - **Critério:** Legível sem ícones (texto sempre presente), responsivo

- [ ] **BK-006** — Formulário de contato funcional `[frontend] [backend]`
  - **O quê:** Form com nome, e-mail, mensagem e envio via API (Resend ou Nodemailer)
  - **Por quê:** Canal de conversão principal
  - **Critério:** Validação client-side e server-side, feedback de sucesso/erro, anti-spam básico

### Média Prioridade (pós-MVP)

- [ ] **BK-007** — Blog técnico com MDX `[frontend] [docs]`
  - **O quê:** Sistema de posts em markdown com listagem e página individual
  - **Por quê:** Demonstra capacidade de comunicação técnica e melhora SEO
  - **Dependências:** BK-001

- [ ] **BK-008** — Modo escuro `[frontend] [ux]`
  - **O quê:** Toggle de tema respeitando `prefers-color-scheme`
  - **Por quê:** Preferência comum entre devs; melhora experiência noturna
  - **Dependências:** BK-002

- [ ] **BK-009** — Analytics com Plausible (privacy-first) `[infra]`
  - **O quê:** Integração com Plausible para ver visitas, origens e cliques de contato
  - **Por quê:** Medir se o portfólio gera resultado
  - **Dependências:** BK-001

### Baixa Prioridade / Ideias

- [ ] **BK-010** — Versão em inglês `[frontend] [docs]`
- [ ] **BK-011** — Filtro de projetos por tecnologia `[frontend]`
- [ ] **BK-012** — Animações de entrada com Framer Motion `[frontend] [ux]`

---

## Estrutura de Pastas

```
portfolio/
├── AI_PROJECT_PROTOCOL.md       ← Protocolo de colaboração com AI
├── README.md                    ← Como rodar o projeto
├── project/
│   ├── PROJECT_CONTEXT.md       ← Contexto, objetivos e decisões do projeto
│   └── STATUS.md                ← Estado atual e próximos passos
│
├── docs/
│   ├── decisions/
│   │   ├── ADR-0001.md          ← Escolha do Next.js
│   │   └── ADR-0002.md          ← Escolha do provedor de e-mail
│   └── backlog.md               ← Backlog completo (este arquivo no projeto real)
│
├── templates/                   ← Templates do framework (copiados do framework base)
├── standards/                   ← Padrões de código e acessibilidade
│
├── src/
│   ├── app/                     ← App Router do Next.js
│   │   ├── page.tsx             ← Página inicial
│   │   ├── layout.tsx           ← Layout global
│   │   └── api/
│   │       └── contact/
│   │           └── route.ts     ← Endpoint do formulário de contato
│   │
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   └── Footer.tsx
│   │   └── sections/
│   │       ├── Hero.tsx
│   │       ├── Projects.tsx
│   │       ├── Stack.tsx
│   │       └── Contact.tsx
│   │
│   ├── data/
│   │   ├── projects.ts          ← Lista de projetos (dados estáticos)
│   │   └── stack.ts             ← Lista de tecnologias
│   │
│   └── styles/
│       └── globals.css
│
├── public/
│   ├── images/
│   │   └── profile.webp
│   └── favicon.ico
│
├── .env.local                   ← Variáveis de ambiente (não commitado)
├── .env.example                 ← Exemplo de variáveis (commitado, sem valores)
├── next.config.ts
├── tailwind.config.ts
└── package.json
```

### Decisões técnicas registradas

| Decisão | Escolha | Motivo |
|---------|---------|--------|
| Framework | Next.js 15 (App Router) | SSG nativo, excelente para portfólio estático com SEO |
| Estilo | Tailwind CSS | Velocidade de desenvolvimento; sem CSS extra em bundle |
| Hospedagem | Vercel | Deploy automático gratuito, CDN global, integração nativa com Next.js |
| E-mail | Resend + react-email | API simples, tier gratuito suficiente para portfólio |
| Dados de projetos | Arquivo `.ts` estático | Volume pequeno; banco de dados seria over-engineering |
