# AI Project Protocol

> Protocolo universal de governança para colaboração entre humano e AI (Claude Code).
> Aplica-se a qualquer projeto que adote esta estrutura base.
> Versão: 1.0 | Criado em: 2026-06-01

---

## 1. Princípios Fundamentais

1. **Clareza antes de ação** — nenhuma implementação começa sem entendimento confirmado.
2. **Aprovação explícita** — mudanças destrutivas ou de grande impacto exigem confirmação do usuário.
3. **Rastreabilidade** — toda decisão, mudança e aprendizado é registrado.
4. **Incrementalidade** — entregas pequenas e verificáveis são preferíveis a grandes saltos.
5. **Documentação como cidadão de primeira classe** — não é etapa final, é parte do fluxo.
6. **Status sempre atualizado** — STATUS.md reflete a realidade ao fim de cada sessão.

---

## 2. Fluxo Obrigatório de Trabalho

Todo trabalho segue este ciclo. Nenhuma etapa pode ser pulada sem registro explícito do motivo.

```
RECEBER TAREFA
     │
     ▼
[1. ANÁLISE] ──────────────────────────────────────────────
     │  • Ler PROJECT_CONTEXT.md e STATUS.md               │
     │  • Identificar escopo, impacto e dependências        │
     │  • Levantar dúvidas ANTES de prosseguir             │
     ▼                                                      │
[2. CONFIRMAÇÃO DE ENTENDIMENTO]                           │
     │  • Apresentar interpretação da tarefa                │
     │  • Aguardar aprovação explícita do usuário           │
     ▼                                                      │
[3. DOCUMENTAÇÃO PRÉVIA]                                   │
     │  • Registrar decisão técnica (se aplicável)          │
     │  • Atualizar backlog / STATUS.md                     │
     ▼                                                      │
[4. IMPLEMENTAÇÃO]                                         │
     │  • Executar em incrementos verificáveis              │
     │  • Reportar progresso a cada etapa significativa     │
     ▼                                                      │
[5. TESTES]                                                │
     │  • Executar testes relevantes                        │
     │  • Documentar resultado                              │
     ▼                                                      │
[6. ATUALIZAÇÃO FINAL]                                     │
     │  • Atualizar STATUS.md                               │
     │  • Atualizar documentação afetada                    │
     └──────────────────────────────────────────────────────┘
```

---

## 3. Processo de Análise

### 3.1 Antes de qualquer tarefa

O AI deve, obrigatoriamente:

1. Ler `PROJECT_CONTEXT.md` — entender objetivos, restrições e decisões vigentes.
2. Ler `STATUS.md` — entender fase atual, bloqueios e próximos passos.
3. Verificar se existe documentação relevante em `docs/` para a tarefa.
4. Verificar se há padrões aplicáveis em `standards/`.

### 3.2 Levantamento de dúvidas

- Toda ambiguidade deve ser levantada **antes** de iniciar implementação.
- Dúvidas são apresentadas de forma numerada e objetiva.
- O AI não assume intenção do usuário — pergunta quando não está claro.
- Se a tarefa conflita com uma decisão registrada, o conflito é apontado explicitamente.

### 3.3 Confirmação de entendimento

Antes de implementar, o AI apresenta:

```
ENTENDIMENTO DA TAREFA
- O que será feito: [descrição]
- O que NÃO será feito: [escopo excluído]
- Impacto esperado: [arquivos, sistemas, dados afetados]
- Dependências: [o que precisa existir antes]
- Riscos identificados: [se houver]

Aguardando confirmação para prosseguir.
```

---

## 4. Processo de Documentação

### 4.1 Tipos de documentação

| Tipo | Local | Quando criar |
|------|-------|-------------|
| Contexto do projeto | `PROJECT_CONTEXT.md` | Setup inicial e mudanças de escopo |
| Decisões técnicas (ADR) | `docs/decisions/ADR-XXXX.md` | Toda decisão arquitetural relevante |
| Documentação de API | `docs/api/` | Ao criar ou modificar APIs |
| Fluxos de negócio | `docs/business/` | Ao definir fluxos e regras de negócio |
| Guias técnicos | `docs/guides/` | Ao definir processos recorrentes |
| Brainstorms | `docs/brainstorms/` | Ao explorar soluções não finalizadas |
| Backlog | `docs/backlog.md` | Contínuo |

### 4.2 Regras de documentação

- Documentação é **atualizada junto com o código**, nunca depois.
- Comentários no código são usados apenas quando o "por quê" não é óbvio.
- Nunca criar docstrings ou blocos de comentário longos — máximo uma linha objetiva.
- Documentação obsoleta é removida ou marcada como `[DEPRECATED]` imediatamente.

### 4.3 Formato de ADR (Architecture Decision Record)

```markdown
# ADR-XXXX: [Título da Decisão]

**Data:** YYYY-MM-DD
**Status:** [Proposto | Aceito | Deprecado | Substituído por ADR-XXXX]

## Contexto
[Qual problema ou situação motivou esta decisão]

## Decisão
[O que foi decidido]

## Consequências
[O que muda, o que fica mais fácil, o que fica mais difícil]
```

---

## 5. Processo de Implementação

### 5.1 Antes de implementar

- Confirmar entendimento foi aprovado (Seção 3.3).
- Verificar padrões de código em `standards/`.
- Verificar se existe skill reutilizável em `skills/`.

### 5.2 Durante a implementação

- Implementar em incrementos — uma responsabilidade por vez.
- Não introduzir abstrações além do necessário para a tarefa atual.
- Não adicionar tratamento de erros para cenários impossíveis.
- Não criar features extras não solicitadas.
- Reportar ao usuário a cada etapa significativa concluída.

### 5.3 Operações que exigem confirmação explícita

O AI **para e solicita confirmação** antes de:

- Deletar arquivos ou diretórios.
- Modificar arquivos de configuração de CI/CD ou infraestrutura.
- Fazer push para repositório remoto.
- Criar ou fechar PRs e issues.
- Executar operações com `--force` ou equivalentes destrutivos.
- Modificar banco de dados (migrations, drops, truncates).
- Alterar dependências (adicionar, remover, fazer downgrade).

### 5.4 Operações autônomas permitidas

O AI pode executar sem confirmação:

- Ler qualquer arquivo do projeto.
- Criar ou editar arquivos dentro de `src/`, `docs/`, `standards/`, `skills/`.
- Executar testes.
- Executar builds locais.
- Criar commits locais.

---

## 6. Processo de Testes

### 6.1 Obrigações de teste

- Toda funcionalidade nova deve ter testes antes de ser considerada concluída.
- Testes são executados localmente antes de qualquer commit.
- Falhas de teste são investigadas e corrigidas — nunca ignoradas ou contornadas com `--no-verify`.

### 6.2 Tipos de teste esperados

| Tipo | Quando aplicar |
|------|----------------|
| Unitário | Lógica de negócio isolada |
| Integração | Interação entre módulos ou com banco de dados |
| E2E | Fluxos críticos do usuário |
| Manual | Mudanças de UI ou comportamento visual |

### 6.3 Reporte de resultado

Após execução de testes, o AI informa:

```
RESULTADO DOS TESTES
- Testes executados: [N]
- Passou: [N]
- Falhou: [N]
- Cobertura (se disponível): [%]
- Ação necessária: [nenhuma | [descrição do que deve ser corrigido]]
```

---

## 7. Processo de Atualização do STATUS.md

### 7.1 Quando atualizar

- **Obrigatório** ao fim de cada sessão de trabalho.
- **Obrigatório** ao concluir uma tarefa significativa.
- **Obrigatório** ao encontrar um bloqueio.
- Opcional: ao iniciar uma tarefa longa (para registrar o que está em andamento).

### 7.2 Estrutura do STATUS.md

```markdown
# Project Status

**Última atualização:** YYYY-MM-DD
**Fase atual:** [Ex: Discovery | Design | Desenvolvimento | Testes | Deploy]

## Em andamento
- [ ] [Descrição da tarefa] — [responsável ou contexto]

## Concluído recentemente
- [x] [Descrição] — concluído em YYYY-MM-DD

## Bloqueios
- [Descrição do bloqueio] — aguardando [o quê / quem]

## Próximos passos
1. [Próxima tarefa prioritária]
2. [Segunda tarefa]
3. [Terceira tarefa]

## Notas da sessão
[Observações relevantes que não cabem em outros campos]
```

---

## 8. Processo de Tomada de Decisões Técnicas

### 8.1 Quando registrar uma decisão

Uma decisão técnica deve ser registrada como ADR quando:

- Envolve escolha de tecnologia, biblioteca ou arquitetura.
- Tem impacto duradouro no projeto (não é apenas implementação).
- Pode ser questionada no futuro sem o contexto de hoje.
- Representa uma troca consciente (trade-off).

### 8.2 Fluxo de decisão

```
DECISÃO NECESSÁRIA
     │
     ▼
AI apresenta: opções, prós/contras e recomendação
     │
     ▼
Usuário aprova ou redireciona
     │
     ▼
AI registra ADR em docs/decisions/
     │
     ▼
AI atualiza PROJECT_CONTEXT.md se a decisão afeta a visão geral
```

### 8.3 Decisões que o AI pode tomar autonomamente

- Escolhas de implementação interna sem impacto arquitetural.
- Nomes de variáveis, funções e arquivos (seguindo os padrões existentes).
- Ordem de execução de operações equivalentes.

### 8.4 Decisões que sempre exigem aprovação

- Escolha de framework, biblioteca ou linguagem.
- Mudanças em schema de banco de dados.
- Mudanças em API pública ou contratos entre serviços.
- Qualquer decisão que afete outros times ou sistemas externos.

---

## 9. Processo de Registro de Brainstorms

### 9.1 Propósito

Brainstorms documentam **exploração de ideias não finalizadas**. São diferentes de decisões: não são vinculantes, mas preservam o raciocínio para sessões futuras.

### 9.2 Quando criar um brainstorm

- Ao explorar soluções alternativas para um problema complexo.
- Ao discutir features ou melhorias ainda não priorizadas.
- Ao investigar a causa raiz de um problema antes de propor solução.
- Quando o usuário pede uma análise exploratória ("o que poderíamos fazer sobre X?").

### 9.3 Formato de brainstorm

Local: `docs/brainstorms/YYYY-MM-DD-[slug-do-tema].md`

```markdown
# Brainstorm: [Tema]

**Data:** YYYY-MM-DD
**Status:** [Em exploração | Pausado | Convertido em tarefa | Descartado]
**Contexto:** [Qual problema ou pergunta motivou este brainstorm]

## Ideias exploradas

### Ideia 1: [Nome]
- Descrição:
- Prós:
- Contras:
- Viabilidade estimada:

### Ideia 2: [Nome]
...

## Conclusão preliminar
[O que parece mais promissor e por quê — ou "sem conclusão ainda"]

## Próximos passos sugeridos
[Se alguma ideia merece virar tarefa ou ADR]
```

---

## 10. Processo de Gerenciamento de Backlog

### 10.1 Local

`docs/backlog.md` — arquivo único e centralizado.

### 10.2 Estrutura do backlog

```markdown
# Backlog

## Prioridade Alta
- [ ] [ID] [Título] — [contexto ou motivação breve]

## Prioridade Média
- [ ] [ID] [Título] — [contexto ou motivação breve]

## Prioridade Baixa / Ideias
- [ ] [ID] [Título] — [contexto ou motivação breve]

## Descartados
- [x] [ID] [Título] — descartado em YYYY-MM-DD por [motivo]
```

### 10.3 Regras do backlog

- Toda tarefa tem um ID sequencial (`BK-001`, `BK-002`, ...).
- Uma tarefa no backlog pode referenciar um ADR ou brainstorm relacionado.
- Itens concluídos são movidos para `## Concluídos` no final do arquivo com a data de conclusão.
- O backlog é revisado a cada **revisão periódica do projeto** (Seção 11).
- O AI pode adicionar itens ao backlog autonomamente quando identifica pendências durante o trabalho, mas deve informar o usuário ao final da sessão.

---

## 11. Processo de Revisão Periódica do Projeto

### 11.1 Frequência recomendada

| Porte do projeto | Frequência |
|-----------------|------------|
| Pessoal / solo | Quinzenal |
| Time pequeno | Semanal |
| Time médio ou grande | Duas vezes por semana |

### 11.2 Pauta padrão da revisão

A revisão é conduzida como uma sessão estruturada com o seguinte roteiro:

```
1. STATUS.md — está atualizado e preciso?
2. Backlog — prioridades ainda fazem sentido? Itens a adicionar ou descartar?
3. Decisões técnicas — alguma decisão precisa ser revisitada?
4. Brainstorms abertos — algum deve ser convertido em tarefa ou descartado?
5. PROJECT_CONTEXT.md — o contexto ainda reflete a realidade do projeto?
6. Padrões — algum padrão em standards/ precisa ser criado ou atualizado?
7. Riscos — novos riscos identificados? Bloqueios antigos resolvidos?
8. Próximo ciclo — quais são as prioridades até a próxima revisão?
```

### 11.3 Output da revisão

Ao final de cada revisão, o AI atualiza:

- `STATUS.md` com o resultado da revisão e próximos passos.
- `docs/backlog.md` com as mudanças de prioridade acordadas.
- Qualquer ADR ou documento que tenha ficado desatualizado.

---

## 12. Comunicação e Tom

- Respostas são **diretas e objetivas** — sem enrolação, sem resumos desnecessários ao final.
- Quando algo não está claro, o AI pergunta. Não assume.
- Quando o AI discorda de uma abordagem, diz claramente e explica o motivo — mas executa a decisão do usuário após o alerta.
- Erros do AI são reportados sem rodeios, com a causa e a correção.
- Linguagem padrão deste projeto: **Português Brasileiro**.

---

## 13. Estrutura de Referência Rápida

```
AI_PROJECT_PROTOCOL.md   ← Este arquivo. Regras da colaboração.
PROJECT_CONTEXT.md        ← O quê e por quê do projeto.
STATUS.md                 ← Onde estamos agora.
README.md                 ← Como usar o projeto.
docs/
  decisions/              ← ADRs
  brainstorms/            ← Exploração de ideias
  business/               ← Regras e fluxos de negócio
  api/                    ← Documentação de APIs
  guides/                 ← Guias técnicos
  backlog.md              ← Backlog centralizado
skills/                   ← Prompts reutilizáveis para tarefas recorrentes
standards/                ← Padrões de código e processo
src/                      ← Código-fonte
```
