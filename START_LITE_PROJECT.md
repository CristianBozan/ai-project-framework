# Como Iniciar um Projeto Lite

> Versão simplificada do guia de uso.
> Use quando o projeto for: portfólio, TCC, estudo, MVP solo ou freelance pequeno.
> Para projetos maiores (SaaS, times, clientes corporativos) use `START_NEW_PROJECT.md`.

---

## Quando usar o modo Lite vs. Completo

| Característica | Lite | Completo |
|---------------|------|---------|
| Desenvolvedor solo | ✓ | ✓ |
| Prazo curto (< 2 meses) | ✓ | — |
| Portfólio, estudo ou TCC | ✓ | — |
| MVP solo ou freelance pequeno | ✓ | — |
| Time de 2+ pessoas | — | ✓ |
| SaaS ou sistema de longa duração | — | ✓ |
| Cliente corporativo | — | ✓ |
| Múltiplas integrações externas | — | ✓ |

---

## Etapa 1 — Copiar e Renomear

Copie a pasta `Framework Base Projetos` e renomeie com o nome do projeto:

```
Copie:   Framework Base Projetos/
Para:    nome-do-projeto/
```

---

## Etapa 2 — Abrir no Editor e Iniciar Conversa

Abra a pasta no editor e inicie uma nova conversa com o AI. Cole esta mensagem:

```
Primeira mensagem da conversa.

Projeto: [nome do projeto]
Modo: Lite

Leia os seguintes arquivos:
1. AI_PROJECT_PROTOCOL.md
2. skills/business_analyst.md

project-lite/PROJECT_CONTEXT.md está vazio.
Inicie o Modo de Descoberta Lite.
```

---

## Etapa 3 — Descoberta Lite (3 blocos)

O AI conduzirá uma entrevista curta de **3 blocos** — em vez dos 6 do modo completo.

```
Bloco 1 → Problema e Usuário      (~5 min)
Bloco 2 → MVP e Requisitos        (~10 min)
Bloco 3 → Restrições e Riscos     (~5 min)
```

Ao final, o AI gera o `project-lite/PROJECT_CONTEXT.md` para sua aprovação.

> Tempo total estimado: 20 a 30 minutos.

---

## Etapa 4 — Gerar o Backlog

Com o PROJECT_CONTEXT.md aprovado:

```
Ative a skill project_manager.
Leia skills/project_manager.md.

Com base em project-lite/PROJECT_CONTEXT.md:
Gere um backlog simples em docs/backlog.md.
Máximo 15 tarefas. Apenas Alta e Baixa prioridade.
```

**Revise verificando:**
- [ ] As tarefas do MVP estão todas listadas?
- [ ] Cada tarefa tem critério de conclusão?
- [ ] A ordem faz sentido (o que depende do quê)?

---

## Etapa 5 — Iniciar Desenvolvimento

Com backlog aprovado:

```
Atualize project-lite/STATUS.md com a fase atual
e a primeira tarefa a ser feita.

Consulte SKILLS_INDEX.md para identificar
qual skill ativar para a primeira tarefa.
```

A partir daqui, o ciclo é:

```
Tarefa → SKILLS_INDEX → Skill → Implementar → Testar → Atualizar STATUS
```

---

## Skills no Modo Lite

No modo Lite você raramente precisará de mais de 3 skills por projeto:

| Quando | Skill |
|--------|-------|
| Sempre (início) | `business_analyst` |
| Organizar tarefas | `project_manager` |
| Código de interface | `frontend` |
| Código de servidor ou API | `backend` |
| Banco de dados | `database` |
| Testes | `testing` |

> As skills de `devops`, `ui_ux` e `documentation` são opcionais no modo Lite.
> Use-as se a tarefa específica exigir — não por padrão.

---

## Standards no Modo Lite

Os standards de **segurança** e **qualidade de código** são obrigatórios mesmo no modo Lite.
Os demais são recomendados mas não bloqueantes:

| Standard | Lite |
|----------|------|
| `security.md` | Obrigatório |
| `code_quality.md` | Obrigatório |
| `accessibility.md` | Recomendado |
| `performance.md` | Recomendado |
| `documentation.md` | Opcional |

---

## Atualização do STATUS.md no Modo Lite

Uma regra simples: **atualize ao fim de cada sessão**.

Não precisa de revisão periódica formal. Só mantenha os três campos principais:
- O que está sendo feito agora
- O que vem a seguir
- Se há algum bloqueio

---

## Fluxo Completo Lite

```
[1] COPIAR → renomear pasta

[2] ABRIR → nova conversa com AI
    Carregar: AI_PROJECT_PROTOCOL.md + business_analyst.md

[3] DESCOBERTA LITE (3 blocos — ~20 min)
    Bloco 1: Problema e Usuário
    Bloco 2: MVP e Requisitos
    Bloco 3: Restrições e Riscos
        ↓
    project-lite/PROJECT_CONTEXT.md aprovado

[4] BACKLOG
    Gerar com project_manager → Máx. 15 tarefas → Aprovar

[5] DESENVOLVIMENTO
    Atualizar STATUS → Skill → Implementar → Testar → Repetir
```

---

## Quando Migrar do Lite para o Completo

Se durante o desenvolvimento você perceber que o projeto cresceu além do esperado, migre:

```
Você ativará o modo completo quando:
- O projeto ganhar um segundo desenvolvedor
- O prazo ultrapassar 3 meses
- Surgirem integrações externas críticas
- Um cliente real entrar no escopo

Como migrar:
1. Copiar o conteúdo de project-lite/PROJECT_CONTEXT.md
   para project/PROJECT_CONTEXT.md e expandir as seções faltantes
2. Trocar project-lite/STATUS.md por project/STATUS.md
3. Seguir START_NEW_PROJECT.md a partir da Etapa 7
```

---

## Referências

| Arquivo | Para quê |
|---------|---------|
| `AI_PROJECT_PROTOCOL.md` | Regras de colaboração com o AI |
| `SKILLS_INDEX.md` | Qual skill ativar por tipo de tarefa |
| `project-lite/PROJECT_CONTEXT.md` | Contexto do projeto (modo Lite) |
| `project-lite/STATUS.md` | Estado atual (modo Lite) |
| `templates/backlog_template.md` | Base para o backlog |
| `START_NEW_PROJECT.md` | Guia completo (projetos maiores) |
