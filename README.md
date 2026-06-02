# Framework Base Projetos

> Um sistema de governança para desenvolvimento de software com AI.
> Elimina o trabalho de configuração inicial e garante que todo projeto começa com
> estrutura, padrões, documentação e fluxo de trabalho já definidos.

---

## O Que É

**Framework Base Projetos** é um template de projeto que define como você e o AI (Claude Code) trabalham juntos — do primeiro "o que você quer construir?" até o código em produção.

Em vez de começar cada projeto do zero e reinventar as mesmas convenções, este framework entrega:

- **Protocolo de colaboração** com o AI já definido
- **Especialistas prontos** (skills) para cada domínio do desenvolvimento
- **Padrões obrigatórios** de qualidade, segurança, acessibilidade, performance e documentação
- **Templates** para todos os documentos recorrentes
- **Sistema de descoberta** que transforma uma ideia vaga em contexto estruturado antes de escrever código
- **Exemplos reais** de como tudo se encaixa em projetos diferentes

O framework não é uma biblioteca de código. É uma estrutura de **processo e governança** que funciona com qualquer linguagem, stack ou tipo de projeto.

---

## Estrutura do Framework

```
Framework Base Projetos/
│
├── README.md                    ← Você está aqui
├── START_NEW_PROJECT.md         ← Guia completo (SaaS, times, projetos robustos)
├── START_LITE_PROJECT.md        ← Guia simplificado (portfólio, TCC, MVP solo)
├── AI_PROJECT_PROTOCOL.md       ← Regras de colaboração entre você e o AI
├── SKILLS_INDEX.md              ← Mapa: qual especialista acionar por tipo de tarefa
│
├── project/                     ← Arquivos do projeto — modo Completo
│   ├── PROJECT_CONTEXT.md       ← 11 seções (vazio no template)
│   └── STATUS.md                ← Completo (vazio no template)
│
├── project-lite/                ← Arquivos do projeto — modo Lite
│   ├── PROJECT_CONTEXT.md       ← 4 campos (vazio no template)
│   └── STATUS.md                ← Simplificado (vazio no template)
│
├── skills/                      ← Especialistas ativáveis
│   ├── business_analyst.md      ← Requisitos, descoberta e regras de negócio
│   ├── project_manager.md       ← Planejamento, backlog e acompanhamento
│   ├── ui_ux.md                 ← Fluxos, usabilidade e design de interface
│   ├── frontend.md              ← Componentes, telas e integração com APIs
│   ├── backend.md               ← APIs, lógica de negócio e integrações
│   ├── database.md              ← Schema, queries, migrations e performance
│   ├── testing.md               ← Estratégia de testes e qualidade
│   ├── documentation.md         ← Documentação técnica e de produto
│   └── devops.md                ← CI/CD, infraestrutura e operação
│
├── standards/                   ← Padrões obrigatórios aplicáveis a qualquer projeto
│   ├── code_quality.md          ← Legibilidade, estrutura e boas práticas
│   ├── security.md              ← OWASP, autenticação e proteção de dados
│   ├── accessibility.md         ← WCAG 2.1 AA e usabilidade inclusiva
│   ├── performance.md           ← Core Web Vitals e SLOs de API
│   └── documentation.md         ← O que documentar, onde e como
│
├── templates/                   ← Modelos para documentos recorrentes
│   ├── project_context_template.md
│   ├── status_template.md
│   ├── backlog_template.md
│   ├── decision_template.md
│   └── risk_template.md
│
├── examples/                    ← Projetos de referência
│   ├── portfolio_example.md
│   ├── ecommerce_example.md
│   ├── saas_example.md
│   └── academic_project_example.md
│
├── docs/                        ← Preenchido por projeto
└── src/                         ← Código-fonte (preenchido por projeto)
```

---

## Instalação

> Primeira vez? Leia `GETTING_STARTED.md` — tem o caminho certo para cada situação (portfólio, TCC, freela, MVP, aprendizado).

O framework não tem dependências de código. A instalação é obter os arquivos e abrir no editor.

### Caminho A — "Use this template" no GitHub (recomendado)

```
1. Acesse github.com/CristianBozan/ai-project-framework
2. Clique em "Use this template" → "Create a new repository"
3. Nome do projeto em kebab-case (ex: portfolio-pessoal)
4. Public ou Private → "Create repository"
5. git clone https://github.com/seu-usuario/nome-do-projeto.git
```

### Caminho B — `degit` (local, sem GitHub agora)

```bash
npx degit CristianBozan/ai-project-framework nome-do-projeto
cd nome-do-projeto
git init && git add . && git commit -m "feat: setup from ai-project-framework"
```

### Caminho C — Download ZIP

```
github.com/CristianBozan/ai-project-framework → "Code" → "Download ZIP"
```

### Verificar a estrutura

Confirme que todos os arquivos estão presentes:

```
✓ README.md
✓ GETTING_STARTED.md
✓ START_NEW_PROJECT.md
✓ START_LITE_PROJECT.md
✓ AI_PROJECT_PROTOCOL.md
✓ SKILLS_INDEX.md
✓ project/PROJECT_CONTEXT.md     (modo Completo)
✓ project/STATUS.md              (modo Completo)
✓ project-lite/PROJECT_CONTEXT.md (modo Lite)
✓ project-lite/STATUS.md          (modo Lite)
✓ skills/ (9 arquivos)
✓ standards/ (5 arquivos)
✓ templates/ (5 arquivos)
✓ examples/ (4 arquivos)
✓ docs/
✓ src/
```

---

## Como Usar — Visão Geral

O framework opera em dois momentos:

**1. Ao iniciar um projeto** — você copia o framework, escolhe o modo (Completo ou Lite), o AI conduz a descoberta e gera a documentação base.

**2. Durante o desenvolvimento** — a cada tarefa, o AI consulta o SKILLS_INDEX, ativa o especialista correto e segue o protocolo definido em AI_PROJECT_PROTOCOL.md.

### Qual modo escolher?

| | Lite | Completo |
|-|------|---------|
| Portfólio, TCC, estudo | ✓ | — |
| MVP solo ou freelance pequeno | ✓ | — |
| Prazo curto (< 2 meses) | ✓ | — |
| SaaS, sistema web de longa duração | — | ✓ |
| Time de 2+ pessoas | — | ✓ |
| Cliente corporativo | — | ✓ |
| Descoberta | 3 blocos (~20 min) | 6 blocos (~60 min) |
| PROJECT_CONTEXT | 4 campos | 11 seções |
| Skills ativas | 3 principais | Todas as 9 |
| Standards obrigatórios | Segurança + Qualidade | Todos os 5 |

---

## Como Criar um Novo Projeto

> Guia completo em `START_NEW_PROJECT.md`. Aqui está o resumo.

### 1. Copiar e renomear

```
Copie:   Framework Base Projetos/
Para:    Projetos/nome-do-projeto/
```

### 2. Abrir no editor e iniciar conversa com o AI

**Modo Lite** — cole esta mensagem:
```
Primeira mensagem da conversa.
Projeto: [nome do projeto]
Modo: Lite

Leia: AI_PROJECT_PROTOCOL.md e skills/business_analyst.md
project-lite/PROJECT_CONTEXT.md está vazio — inicie o Modo de Descoberta Lite.
```

**Modo Completo** — cole esta mensagem:
```
Primeira mensagem da conversa.
Projeto: [nome do projeto]

Leia os seguintes arquivos antes de qualquer coisa:
1. AI_PROJECT_PROTOCOL.md
2. SKILLS_INDEX.md

Confirme que leu e aguarde minha instrução.
```

### 3. Descoberta

**Lite** — 3 blocos (~20 min):
```
Bloco L1 → Problema e Usuário
Bloco L2 → MVP e Requisitos
Bloco L3 → Restrições e Riscos
```

**Completo** — 6 blocos (~60 min):
```
Bloco 1 → Problema
Bloco 2 → Usuários e Stakeholders
Bloco 3 → Objetivos e Métricas
Bloco 4 → MVP e Requisitos
Bloco 5 → Restrições
Bloco 6 → Riscos
```

Ao final, o AI gera o `PROJECT_CONTEXT.md` do modo escolhido para sua aprovação.

### 4. Gerar backlog e arquitetura

Após aprovar o project/PROJECT_CONTEXT.md, o AI gera:
- `docs/backlog.md` — todas as tarefas priorizadas
- Stack tecnológica com justificativas
- Estrutura de pastas do projeto
- ADRs das decisões técnicas em `docs/decisions/`

### 5. Iniciar o desenvolvimento

Com contexto, backlog e arquitetura aprovados, o desenvolvimento segue o ciclo:

```
Tarefa → Consultar SKILLS_INDEX → Ativar skill → Analisar → Implementar → Testar → Atualizar STATUS
```

---

## Como Utilizar Skills

Skills são **especialistas ativáveis** — cada um com responsabilidades, checklist e perguntas obrigatórias para seu domínio.

### Quando ativar uma skill

Consulte `SKILLS_INDEX.md` para o mapeamento completo. Resumo:

| Tipo de tarefa | Skill |
|---------------|-------|
| Requisitos não claros | `business_analyst` |
| Planejamento, backlog, status | `project_manager` |
| Fluxo de usuário, usabilidade | `ui_ux` |
| Componentes, telas, frontend | `frontend` |
| APIs, lógica de servidor | `backend` |
| Schema, queries, banco de dados | `database` |
| Testes, qualidade, bugs | `testing` |
| Criar ou revisar documentação | `documentation` |
| CI/CD, deploy, infraestrutura | `devops` |

### Como ativar

Envie ao AI:

```
Ative a skill [nome].
Leia o arquivo skills/[nome].md.

[Descrição da tarefa]
```

### Múltiplas skills

Algumas tarefas cruzam domínios. Exemplos:

```
Nova feature completa:
  business_analyst → ui_ux → backend → frontend → database → testing

Bug de produção:
  testing (investigar) → skill do domínio (corrigir) → devops (monitorar)

Mudança de schema:
  database (impacto nos dados) → backend (adaptações na API) → devops (migration em produção)
```

### O que cada skill entrega

Ao ativar uma skill, o AI assume o papel daquele especialista e:

- Faz as **perguntas obrigatórias** do arquivo antes de implementar
- Segue as **responsabilidades** definidas
- Usa o **checklist** antes de considerar a tarefa concluída
- Aplica os **critérios de validação** ao final

---

## Como Utilizar Standards

Standards são **padrões obrigatórios** aplicados a todo código produzido, independentemente da tarefa.

### Os 5 standards

| Arquivo | O que garante |
|---------|--------------|
| `standards/code_quality.md` | Legibilidade, funções com responsabilidade única, sem código morto, commits atômicos |
| `standards/security.md` | OWASP Top 10, zero credenciais no código, validação de entrada, erros genéricos ao cliente |
| `standards/accessibility.md` | WCAG 2.1 AA, navegação por teclado, contraste, semântica HTML |
| `standards/performance.md` | Core Web Vitals (LCP ≤ 2.5s, INP ≤ 200ms, CLS ≤ 0.1), SLOs de API, sem N+1 |
| `standards/documentation.md` | O que documentar, onde, como manter sincronizado com o código |

### Como funcionam na prática

O AI aplica os standards automaticamente — não é necessário lembrá-lo a cada tarefa. O fluxo é:

```
Skill ativada
    ↓
Implementação
    ↓
Checklist da skill (específico da tarefa)
    +
Checklist dos standards relevantes (obrigatório)
    ↓
Tarefa concluída
```

### Quando referenciar manualmente

Se quiser reforçar um standard específico em uma tarefa:

```
Implemente o formulário de login.
Verifique o checklist de standards/security.md antes de considerar pronto.
```

### Critérios mínimos aceitáveis

Cada standard define um **critério mínimo** para produção e **critérios recomendados** para maturidade. O mínimo é não-negociável. Os recomendados são o alvo a longo prazo.

---

## Fluxo Completo

```
╔══════════════════════════════════════════════════════════╗
║              INÍCIO DE PROJETO                           ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  1. Copiar framework → renomear pasta                    ║
║  2. Abrir no editor + nova conversa com AI               ║
║  3. AI lê: AI_PROJECT_PROTOCOL.md + SKILLS_INDEX.md      ║
║                                                          ║
╠══════════════════════════════════════════════════════════╣
║              DESCOBERTA (business_analyst)               ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  Bloco 1: Problema                                       ║
║  Bloco 2: Usuários e Stakeholders                        ║
║  Bloco 3: Objetivos e Métricas                           ║
║  Bloco 4: MVP e Requisitos                               ║
║  Bloco 5: Restrições                                     ║
║  Bloco 6: Riscos                                         ║
║       ↓                                                  ║
║  project/PROJECT_CONTEXT.md gerado e aprovado                    ║
║                                                          ║
╠══════════════════════════════════════════════════════════╣
║              PLANEJAMENTO (project_manager)              ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  docs/backlog.md gerado e priorizado                     ║
║  project/STATUS.md inicializado                                  ║
║                                                          ║
╠══════════════════════════════════════════════════════════╣
║              ARQUITETURA                                 ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  Stack definida e justificada                            ║
║  Estrutura de pastas criada                              ║
║  ADRs em docs/decisions/                                 ║
║  project/PROJECT_CONTEXT.md atualizado                           ║
║                                                          ║
╠══════════════════════════════════════════════════════════╣
║              CICLO DE DESENVOLVIMENTO                    ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  ┌─────────────────────────────────────────────┐        ║
║  │                                             │        ║
║  │  Receber tarefa                             │        ║
║  │       ↓                                    │        ║
║  │  Consultar SKILLS_INDEX.md                  │        ║
║  │       ↓                                    │        ║
║  │  Ativar skill correspondente               │        ║
║  │       ↓                                    │        ║
║  │  Análise + confirmação de entendimento      │        ║
║  │       ↓                                    │        ║
║  │  Implementação incremental                 │        ║
║  │       ↓                                    │        ║
║  │  Testes                                    │        ║
║  │       ↓                                    │        ║
║  │  Checklist da skill + standards            │        ║
║  │       ↓                                    │        ║
║  │  Atualizar project/STATUS.md e documentação        │        ║
║  │       ↓                                    │        ║
║  │  Próxima tarefa ────────────────────────── ┘        ║
║  │                                                      ║
╠══════════════════════════════════════════════════════════╣
║              REVISÃO PERIÓDICA (project_manager)         ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  project/STATUS.md atualizado e preciso?                         ║
║  Backlog repriorizado?                                   ║
║  Decisões e riscos revisados?                            ║
║  project/PROJECT_CONTEXT.md ainda reflete a realidade?           ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

---

## Referência Rápida de Arquivos

| Quando você precisa de... | Leia |
|--------------------------|------|
| Está começando e tem dúvidas | `GETTING_STARTED.md` |
| Entender as regras da colaboração com o AI | `AI_PROJECT_PROTOCOL.md` |
| Saber qual skill ativar para uma tarefa | `SKILLS_INDEX.md` |
| Iniciar projeto robusto (SaaS, time, cliente) | `START_NEW_PROJECT.md` |
| Iniciar projeto simples (portfólio, TCC, MVP) | `START_LITE_PROJECT.md` |
| Contexto do projeto — modo Completo | `project/PROJECT_CONTEXT.md` |
| Contexto do projeto — modo Lite | `project-lite/PROJECT_CONTEXT.md` |
| Estado atual — modo Completo | `project/STATUS.md` |
| Estado atual — modo Lite | `project-lite/STATUS.md` |
| Ver todas as tarefas e prioridades | `docs/backlog.md` |
| Ver as decisões técnicas tomadas | `docs/decisions/` |
| Usar um especialista | `skills/[nome].md` |
| Verificar padrões obrigatórios | `standards/[nome].md` |
| Começar um documento do zero | `templates/[nome]_template.md` |
| Ver como o framework funciona em projetos reais | `examples/` |

---

## Perguntas Frequentes

**O framework funciona com qualquer linguagem?**
Sim. O framework é agnóstico de tecnologia. Os standards e skills se aplicam a qualquer stack. A única especialização por linguagem vai em `standards/languages/` — uma pasta que você cria conforme o projeto exige.

**Preciso usar todas as skills em todo projeto?**
Não. Ative apenas as skills relevantes para cada tarefa. Um projeto solo de portfólio raramente precisa de `devops` ou `database` com profundidade. Um SaaS B2B vai usar todas.

**O que faço quando uma tarefa não se encaixa em nenhuma skill?**
Use o próprio AI diretamente. As skills são atalhos para contexto estruturado — não são obrigatórias quando a tarefa é simples o suficiente para não precisar de especialização.

**Posso modificar o framework?**
Sim, mas modifique na cópia do projeto, não no original. Se encontrar uma melhoria que faz sentido para todos os projetos, atualize o original depois.

**O AI precisa ser o Claude Code?**
O framework foi projetado para Claude Code (Claude Sonnet), mas os princípios funcionam com qualquer AI conversacional. A qualidade do resultado depende da capacidade do modelo de seguir instruções complexas e manter contexto.

**E se o project/PROJECT_CONTEXT.md ficar desatualizado?**
O `AI_PROJECT_PROTOCOL.md` define revisão periódica (Seção 11) que inclui validar se o project/PROJECT_CONTEXT.md ainda reflete a realidade. Se algo mudou — novo objetivo, nova restrição, nova decisão técnica — atualize imediatamente.

---

## Contribuindo com o Framework

Para melhorar o framework original:

1. Identifique o que está faltando ou está errado em um projeto real.
2. Proponha a mudança com justificativa — o que melhora e por quê.
3. Teste em um projeto real antes de atualizar o original.
4. Atualize este README se a mudança afeta como o framework é usado.

---

*Framework Base Projetos — universal, reutilizável, agnóstico de stack.*
