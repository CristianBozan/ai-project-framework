# Como Iniciar um Novo Projeto

> Guia de uso do Framework Base Projetos.
> Siga as etapas em ordem. Não pule etapas — cada uma é pré-requisito da próxima.
> Tempo estimado para completar o setup: 30 a 90 minutos, dependendo da complexidade do projeto.

---

## Pré-requisito

Você tem a pasta `Framework Base Projetos` com a seguinte estrutura:

```
Framework Base Projetos/
├── AI_PROJECT_PROTOCOL.md
├── PROJECT_CONTEXT.md
├── STATUS.md
├── README.md
├── SKILLS_INDEX.md
├── START_NEW_PROJECT.md
├── docs/
├── examples/
├── skills/
├── standards/
├── templates/
└── src/
```

---

## Etapa 1 — Copiar o Framework

Copie a pasta `Framework Base Projetos` completa para o local onde seus projetos ficam armazenados.

```
Antes:
  Documentos/
  └── Framework Base Projetos/   ← original (nunca edite este)

Depois:
  Documentos/
  ├── Framework Base Projetos/   ← original intacto
  └── [Projetos]/
      └── meu-projeto/           ← cópia que você vai usar
```

> A pasta original é o molde. Nunca edite diretamente — sempre trabalhe na cópia.

---

## Etapa 2 — Renomear a Pasta

Renomeie a cópia com o nome do seu projeto em kebab-case.

```
Exemplos:
  portfolio-pessoal
  loja-natura-organica
  flowdesk-saas
  tcc-sentineledu
```

Regras do nome:
- Letras minúsculas
- Palavras separadas por hífen
- Sem espaços, acentos ou caracteres especiais
- Descritivo o suficiente para identificar o projeto sem contexto adicional

---

## Etapa 3 — Abrir o Projeto

Abra a pasta renomeada no seu editor (VS Code, Cursor ou equivalente) e inicie uma nova conversa com o AI (Claude Code).

Cole a seguinte mensagem de abertura:

```
Primeira mensagem da conversa.

Projeto: [nome do projeto]
Localização: [caminho da pasta]

Leia os seguintes arquivos antes de qualquer coisa:
1. AI_PROJECT_PROTOCOL.md
2. SKILLS_INDEX.md

Confirme que leu e aguarde minha instrução.
```

> Isso garante que o AI começa com o protocolo carregado e o mapa de skills em contexto.

---

## Etapa 4 — Ativar o Business Analyst

Com o AI pronto, envie a seguinte instrução:

```
Ative a skill business_analyst.
Leia o arquivo skills/business_analyst.md.

Vamos começar a fase de descoberta do projeto.
Faça as perguntas necessárias para entender o problema,
os usuários, os objetivos e as restrições.

Não proponha soluções ainda. Apenas descubra.
```

O AI assumirá o papel de analista e fará perguntas estruturadas.

> Responda com o máximo de detalhe que você tiver agora.
> Não precisa ter tudo definido — incertezas e hipóteses são válidas e devem ser declaradas.

---

## Etapa 5 — Fase de Descoberta

Esta é a etapa mais importante do projeto. Invista tempo aqui.

O AI conduzirá uma sessão de perguntas cobrindo:

**Problema e contexto:**
- Qual problema real este projeto resolve?
- Quem sofre com este problema hoje? Como sofre?
- O que acontece se o problema não for resolvido?

**Usuários:**
- Quem vai usar o sistema? Em qual contexto?
- O que cada perfil de usuário precisa fazer?
- Qual é o nível de familiaridade com tecnologia?

**Objetivos:**
- O que define que o projeto foi bem-sucedido?
- Quais são as métricas de sucesso?
- O que este projeto explicitamente não é?

**Restrições:**
- Prazo, orçamento, tecnologia obrigatória?
- Regulatório, compliance, privacidade de dados?
- Integrações obrigatórias com sistemas existentes?

**Escopo inicial:**
- O que entra no MVP (primeira entrega)?
- O que fica para depois?

> Ao final desta etapa você deve conseguir descrever o projeto em 3 frases para qualquer pessoa.
> Se não conseguir, a descoberta não terminou.

---

## Etapa 6 — Gerar o PROJECT_CONTEXT.md

Com a descoberta concluída, instrua o AI:

```
Com base na nossa conversa de descoberta:

1. Preencha o arquivo PROJECT_CONTEXT.md usando o template
   em templates/project_context_template.md como base.

2. Onde não tivermos informação definida,
   marque como [A DEFINIR] com uma nota do que precisamos descobrir.

3. Apresente o resultado para minha revisão antes de salvar.
```

**Revise o PROJECT_CONTEXT.md gerado verificando:**

- [ ] O problema está descrito sem mencionar a solução?
- [ ] Os usuários e seus contextos estão corretos?
- [ ] O objetivo principal cabe em uma frase?
- [ ] O que está fora do escopo está explícito?
- [ ] As restrições reais estão listadas?
- [ ] As métricas de sucesso são mensuráveis?
- [ ] Os itens `[A DEFINIR]` são aceitáveis por agora?

Aprove ou corrija antes de prosseguir.

> PROJECT_CONTEXT.md é a fonte de verdade do projeto.
> O AI o lerá no início de cada sessão futura.
> Vale 30 minutos a mais para deixá-lo correto.

---

## Etapa 7 — Gerar o Backlog Inicial

Com o contexto aprovado, instrua o AI:

```
Ative a skill project_manager.
Leia o arquivo skills/project_manager.md.

Com base no PROJECT_CONTEXT.md aprovado:

1. Crie o arquivo docs/backlog.md usando
   templates/backlog_template.md como base.

2. Gere as tarefas do MVP como itens de alta prioridade.

3. Gere as tarefas pós-MVP como itens de média e baixa prioridade.

4. Cada tarefa deve ter: título, o quê, por quê e critério de conclusão.

5. Apresente para revisão antes de salvar.
```

**Revise o backlog verificando:**

- [ ] As tarefas do MVP estão completas para entregar o objetivo principal?
- [ ] Cada tarefa tem critério de conclusão claro e testável?
- [ ] As dependências entre tarefas estão mapeadas?
- [ ] A ordem de prioridade faz sentido (o que bloqueia o que)?
- [ ] Há tarefas muito grandes que deveriam ser quebradas?
- [ ] Há tarefas duplicadas ou sobrepostas?

Aprove ou ajuste antes de prosseguir.

---

## Etapa 8 — Gerar a Arquitetura

Com backlog aprovado, instrua o AI:

```
Agora vamos definir a arquitetura do projeto.

Com base no PROJECT_CONTEXT.md e no backlog:

1. Proponha a stack tecnológica justificando cada escolha.

2. Proponha a estrutura de pastas do projeto.

3. Identifique as decisões arquiteturais que precisam de ADR.

4. Crie os ADRs principais em docs/decisions/.

5. Atualize PROJECT_CONTEXT.md com as decisões tomadas
   nas seções de Stack e Arquitetura de Alto Nível.

Apresente cada proposta separadamente para minha aprovação
antes de passar para a próxima.
```

**Para cada decisão técnica, avalie:**

- [ ] A escolha resolve o problema real ou é over-engineering?
- [ ] A equipe (ou eu) tem domínio suficiente desta tecnologia?
- [ ] O custo (financeiro e de aprendizado) é compatível com o projeto?
- [ ] A decisão é reversível se se mostrar errada?
- [ ] O ADR registra o trade-off, não apenas a escolha?

> Não aceite uma stack "porque é moderna".
> Aceite uma stack porque resolve seu problema com o menor risco possível.

---

## Etapa 9 — Iniciar o Desenvolvimento

Com contexto, backlog e arquitetura aprovados, instrua o AI:

```
Setup do projeto está completo.

Antes de iniciar:
1. Atualize o STATUS.md com a fase atual e os primeiros passos.
2. Confirme qual é a primeira tarefa do backlog a ser implementada.

Consulte SKILLS_INDEX.md para identificar qual skill ativar
para a primeira tarefa e me informe antes de começar.
```

A partir daqui, cada sessão de desenvolvimento segue o fluxo definido em `AI_PROJECT_PROTOCOL.md`:

```
Receber tarefa
    ↓
Consultar SKILLS_INDEX.md
    ↓
Ativar skill correspondente
    ↓
Análise e confirmação de entendimento
    ↓
Implementação incremental
    ↓
Testes
    ↓
Atualizar STATUS.md e docs
```

---

## Resumo do Fluxo Completo

```
[1] COPIAR
    Framework Base Projetos → nova pasta

[2] RENOMEAR
    nome-do-projeto em kebab-case

[3] ABRIR
    Editor + nova conversa com AI
    Carregar: AI_PROJECT_PROTOCOL.md + SKILLS_INDEX.md

[4] ATIVAR business_analyst
    skills/business_analyst.md

[5] DESCOBERTA
    Problema → Usuários → Objetivos → Restrições → Escopo do MVP

[6] PROJECT_CONTEXT.md
    Preencher com template → Revisar → Aprovar

[7] BACKLOG
    Gerar com project_manager → Revisar → Aprovar

[8] ARQUITETURA
    Stack → Estrutura de pastas → ADRs → Aprovar

[9] DESENVOLVIMENTO
    Atualizar STATUS.md → Primeira tarefa → SKILLS_INDEX.md → Implementar
```

---

## Referências

| Arquivo | Para quê |
|---------|---------|
| `AI_PROJECT_PROTOCOL.md` | Regras de colaboração com o AI |
| `SKILLS_INDEX.md` | Mapa de qual skill ativar por tipo de tarefa |
| `templates/project_context_template.md` | Base para o PROJECT_CONTEXT.md |
| `templates/status_template.md` | Base para o STATUS.md |
| `templates/backlog_template.md` | Base para o docs/backlog.md |
| `templates/decision_template.md` | Base para ADRs em docs/decisions/ |
| `templates/risk_template.md` | Base para docs/risks.md |
| `examples/` | Projetos de referência para calibrar nível de detalhe |
| `standards/` | Padrões obrigatórios de qualidade, segurança e acessibilidade |
