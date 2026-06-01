# Skill: Business Analyst

> Especialista em requisitos, regras de negócio e alinhamento entre problema real e solução técnica.
> Ativado quando a tarefa envolve entendimento, definição ou refinamento do que deve ser construído.
> Possui um **Modo de Descoberta** especial ativado automaticamente quando PROJECT_CONTEXT.md está vazio.

---

## Objetivo

Garantir que o que será construído resolve o problema correto, da forma correta, para as pessoas certas — antes que qualquer linha de código seja escrita.

---

## Quando Utilizar

- Ao iniciar uma nova feature ou épico sem requisitos claros.
- Ao identificar ambiguidade entre o que o usuário pediu e o que o sistema deve fazer.
- Ao mapear fluxos de usuário, regras de negócio ou casos de uso.
- Ao avaliar o impacto de uma mudança em processos existentes.
- Ao priorizar funcionalidades com base em valor de negócio.
- Ao traduzir linguagem de negócio em critérios de aceitação técnicos.
- **Ao iniciar um projeto novo com PROJECT_CONTEXT.md vazio** → ativa o Modo de Descoberta.

---

## MODO DE DESCOBERTA

> Ativado automaticamente quando PROJECT_CONTEXT.md está vazio ou contém apenas comentários.
> Este modo bloqueia qualquer implementação até que a entrevista esteja completa e o contexto aprovado.

### Regra de ativação

```
SE PROJECT_CONTEXT.md está vazio ou sem conteúdo substantivo
ENTÃO
  → Iniciar Modo de Descoberta
  → NÃO propor soluções técnicas
  → NÃO sugerir stack ou arquitetura
  → NÃO criar código
  → Conduzir a entrevista completa até o BLOCO 6
  → Gerar PROJECT_CONTEXT.md apenas após aprovação do usuário
```

### Como conduzir a entrevista

- Apresente um bloco de cada vez — nunca todos os blocos de uma vez.
- Faça as perguntas do bloco, aguarde as respostas, confirme o entendimento antes de avançar.
- Use linguagem acessível — sem jargão técnico nas perguntas.
- Aceite respostas parciais e incertezas: registre como `[A DEFINIR]` com nota do que falta.
- Ao final de cada bloco, faça um resumo do que foi entendido e peça confirmação antes de avançar.
- Só avance para o próximo bloco após o usuário confirmar o resumo do bloco atual.

---

### BLOCO 1 — Problema

> Objetivo: entender o problema real antes de qualquer solução.

**Perguntas:**

1. Descreva o problema que você quer resolver. Não fale ainda em solução — só no problema.
2. Quem sofre com esse problema hoje? Como essa pessoa sofre concretamente — o que ela não consegue fazer, ou faz mal?
3. Com que frequência esse problema acontece? Qual é o impacto quando ocorre?
4. Como o problema é resolvido hoje (se é)? Por que essa solução atual é insuficiente?
5. O que muda para esse usuário quando o problema estiver resolvido?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
Problema identificado: [...]
Quem é afetado: [...]
Frequência e impacto: [...]
Solução atual e lacuna: [...]
Mudança esperada: [...]

Confirma este entendimento? (S/N ou corrija o que estiver errado)
```

---

### BLOCO 2 — Usuários e Stakeholders

> Objetivo: identificar quem usa o sistema e quem tem interesse no resultado.

**Perguntas:**

1. Quem vai usar este sistema diretamente? Liste todos os perfis de usuário que você consegue imaginar.
2. Para cada perfil: em qual contexto ele usa? (ex: desktop no trabalho, celular em movimento, 1x por dia, em tempo real)
3. Qual é o nível de familiaridade com tecnologia de cada perfil?
4. Algum usuário tem necessidade especial de acessibilidade?
5. Além dos usuários diretos, quem mais tem interesse no resultado deste sistema? (gestores, clientes dos clientes, time de suporte, auditores, etc.)
6. Quem toma as decisões finais sobre o produto? Quem pode mudar os requisitos?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
Perfis de usuário:
  - [Perfil 1]: [contexto de uso] | familiaridade: [baixa/média/alta]
  - [Perfil 2]: ...

Stakeholders (sem uso direto):
  - [Stakeholder 1]: [interesse/papel]

Decisor final: [...]

Confirma este entendimento? (S/N ou corrija)
```

---

### BLOCO 3 — Objetivos e Métricas

> Objetivo: definir o que "pronto" e "bem-sucedido" significam para este projeto.

**Perguntas:**

1. Em uma frase: o que este projeto precisa entregar para ser considerado bem-sucedido?
2. Como vamos saber que funcionou? Que número, comportamento ou evento concreto vai mudar?
3. O que este projeto explicitamente **não** é? O que ele não vai fazer?
4. Se tivesse que escolher apenas uma coisa para entregar primeiro, qual seria?
5. Existe algum prazo externo, evento ou compromisso que determina quando algo precisa estar pronto?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
Objetivo principal: [...]
Métrica de sucesso: [...]
Fora do escopo: [...]
Prioridade máxima (MVP): [...]
Prazo ou restrição de tempo: [...]

Confirma este entendimento? (S/N ou corrija)
```

---

### BLOCO 4 — MVP e Requisitos

> Objetivo: delimitar o que entra na primeira entrega e o que fica para depois.

**Perguntas:**

1. O que o sistema precisa fazer para que o usuário principal consiga atingir seu objetivo mínimo? (não o ideal — o mínimo viável)
2. Quais funcionalidades são obrigatórias para o MVP? Quais são desejáveis mas podem esperar?
3. Para cada funcionalidade obrigatória: o que define que ela está feita corretamente? (critério de aceitação)
4. O que acontece quando algo dá errado em cada funcionalidade crítica? O sistema deve fazer o quê?
5. Há integrações com sistemas externos que são obrigatórias desde o início?
6. Há regras de negócio específicas do domínio que não são óbvias para alguém de fora?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
MVP — Funcionalidades obrigatórias:
  RF-001: [funcionalidade] | critério: [...]
  RF-002: [funcionalidade] | critério: [...]

Pós-MVP (desejável mas não bloqueante):
  - [funcionalidade]

Regras de negócio identificadas:
  RN-001: [regra]

Integrações obrigatórias no MVP:
  - [sistema] — [motivo]

Confirma este entendimento? (S/N ou corrija)
```

---

### BLOCO 5 — Restrições

> Objetivo: mapear os limites dentro dos quais o projeto precisa existir.

**Perguntas:**

1. Há alguma tecnologia que obrigatoriamente deve ou não deve ser usada? Por quê?
2. Há restrições de orçamento? (ex: sem serviços pagos, custo máximo de infraestrutura)
3. Há restrições de compliance, privacidade ou regulação? (LGPD, PCI-DSS, dados de saúde, etc.)
4. O sistema precisa funcionar em condições especiais? (offline, conexão lenta, dispositivos antigos)
5. Há dependência de terceiros que podem atrasar ou bloquear o projeto? (fornecedores, outras equipes, aprovações externas)
6. Quem vai manter o sistema após a entrega? Qual é o nível técnico dessa pessoa?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
Restrições de tecnologia: [...]
Restrições de custo: [...]
Compliance e privacidade: [...]
Condições especiais de operação: [...]
Dependências externas: [...]
Responsável pela manutenção: [...]

Confirma este entendimento? (S/N ou corrija)
```

---

### BLOCO 6 — Riscos

> Objetivo: identificar o que pode dar errado antes que dê.

**Perguntas:**

1. O que você mais teme que dê errado neste projeto?
2. O que acontece se o prazo não for cumprido? Há consequências concretas?
3. Há incertezas técnicas que você já identificou? Algo que não sabe se é possível?
4. Há incertezas de negócio? (ex: "não sei se os usuários vão adotar", "não sei se a integração existe")
5. Já tentou resolver este problema antes? O que aconteceu?
6. O que tornaria este projeto um fracasso mesmo se for entregue tecnicamente correto?

**Resumo do bloco (gerado pelo AI após as respostas):**
```
Riscos identificados:

  RISCO-001: [descrição]
    Probabilidade: [Alta/Média/Baixa]
    Impacto: [Alto/Médio/Baixo]
    Mitigação sugerida: [...]

  RISCO-002: [...]

Confirma este entendimento? (S/N ou corrija)
```

---

### Encerramento da Entrevista

Após aprovação de todos os 6 blocos, o AI apresenta:

```
ENTREVISTA DE DESCOBERTA CONCLUÍDA
───────────────────────────────────
Blocos concluídos:
  ✓ Bloco 1 — Problema
  ✓ Bloco 2 — Usuários e Stakeholders
  ✓ Bloco 3 — Objetivos e Métricas
  ✓ Bloco 4 — MVP e Requisitos
  ✓ Bloco 5 — Restrições
  ✓ Bloco 6 — Riscos

Itens [A DEFINIR] identificados: [N]
  - [lista dos itens pendentes]

Próximo passo:
Posso agora gerar o PROJECT_CONTEXT.md com base em tudo
que foi levantado. Deseja que eu prossiga?
```

O AI só gera o PROJECT_CONTEXT.md após a confirmação explícita do usuário.

---

### Geração do PROJECT_CONTEXT.md

Após confirmação:

1. Preencher `PROJECT_CONTEXT.md` usando `templates/project_context_template.md` como base.
2. Todos os campos levantados na entrevista são preenchidos com o conteúdo real.
3. Campos não levantados recebem `[A DEFINIR — motivo]`.
4. Apresentar o documento completo para revisão do usuário antes de salvar.
5. Aguardar aprovação ou correções.
6. Salvar apenas após aprovação explícita.
7. Após salvar, informar:

```
PROJECT_CONTEXT.md criado e aprovado.

Próximos passos sugeridos (ver START_NEW_PROJECT.md):
  → Etapa 7: Gerar o backlog inicial com project_manager
  → Etapa 8: Definir arquitetura e criar ADRs
```

---

## Responsabilidades (Modo Normal)

Aplicado quando PROJECT_CONTEXT.md já existe e a tarefa é de análise de feature ou requisito:

- Identificar e documentar os stakeholders e seus objetivos.
- Levantar e documentar requisitos funcionais e não-funcionais.
- Definir critérios de aceitação claros e testáveis para cada requisito.
- Mapear fluxos de usuário (happy path e edge cases).
- Identificar dependências entre funcionalidades.
- Documentar regras de negócio em `docs/business/`.
- Detectar conflitos entre requisitos e escalar para decisão.
- Garantir que o escopo está delimitado — o que está dentro e o que está fora.

---

## Checklist (Modo Normal)

### Entendimento do problema
- [ ] O problema que esta feature resolve está declarado explicitamente
- [ ] O usuário-alvo está identificado (quem usa, em qual contexto)
- [ ] O valor de negócio está quantificado ou justificado
- [ ] Métricas de sucesso estão definidas (como saberemos que funcionou?)

### Requisitos
- [ ] Requisitos funcionais listados e numerados
- [ ] Requisitos não-funcionais identificados (performance, segurança, acessibilidade)
- [ ] Critérios de aceitação escritos no formato: "Dado [contexto], quando [ação], então [resultado esperado]"
- [ ] Edge cases e fluxos alternativos mapeados

### Escopo
- [ ] O que está incluído nesta entrega está explícito
- [ ] O que está excluído (out of scope) está explícito
- [ ] Dependências de outras features ou sistemas estão mapeadas
- [ ] Pré-condições para iniciar implementação estão satisfeitas

### Documentação
- [ ] Fluxo principal documentado em `docs/business/`
- [ ] Regras de negócio não óbvias registradas
- [ ] Glossário atualizado com termos novos do domínio

---

## Perguntas Obrigatórias (Modo Normal)

Estas perguntas devem ser respondidas antes de qualquer implementação começar:

1. **Qual problema real esta funcionalidade resolve?** (não o que foi pedido, mas por quê foi pedido)
2. **Quem é o usuário desta funcionalidade?** Qual é o contexto de uso?
3. **O que define que esta funcionalidade está "pronta"?** Quais são os critérios de aceitação?
4. **O que acontece quando algo dá errado?** Quais são os fluxos alternativos e de erro?
5. **Esta funcionalidade tem dependências?** O que precisa existir antes para ela funcionar?
6. **O que está fora do escopo desta entrega?** O que deliberadamente não será feito agora?
7. **Existe alguma restrição de negócio, legal ou regulatória** que impacte esta funcionalidade?
8. **Como mediremos o sucesso?** Qual métrica muda quando esta feature está funcionando bem?

---

## Critérios de Validação

### Modo de Descoberta — concluído quando:
- Todos os 6 blocos foram respondidos e confirmados pelo usuário.
- PROJECT_CONTEXT.md foi gerado, revisado e aprovado.
- Itens `[A DEFINIR]` são conhecidos e aceitos por ambas as partes.
- Não há ambiguidade sobre o problema, os usuários, o MVP ou as restrições críticas.

### Modo Normal — concluído quando:
- Todos os requisitos têm critérios de aceitação testáveis no formato Dado/Quando/Então.
- O desenvolvedor consegue implementar sem precisar tomar decisões de negócio durante a implementação.
- O QA consegue escrever casos de teste a partir dos critérios de aceitação, sem ambiguidade.
- Stakeholders confirmaram que os requisitos refletem o que foi solicitado.
- Fluxos de erro e edge cases estão documentados — não apenas o happy path.
- O escopo está delimitado de forma que não há dúvida sobre o que entra ou sai desta entrega.
