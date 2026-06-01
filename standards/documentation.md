# Standard: Documentação

> Padrão universal de documentação aplicável a qualquer projeto que adote este framework.
> Define o que documentar, onde, como e quando — eliminando documentação desnecessária e garantindo a útil.

---

## Objetivo

Garantir que qualquer pessoa (ou AI) chegando ao projeto consiga entender o contexto, tomar decisões informadas e contribuir efetivamente — sem depender de conhecimento tácito de quem criou o projeto.

---

## Critérios Obrigatórios

### O que sempre deve estar documentado
- **Por que o projeto existe** — problema resolvido e objetivos (`PROJECT_CONTEXT.md`).
- **Como rodar o projeto** — pré-requisitos, instalação e execução (`README.md`).
- **Decisões arquiteturais relevantes** — contexto, decisão e consequências (`docs/decisions/`).
- **Contratos de API** — endpoints, parâmetros, respostas e erros (`docs/api/`).
- **Regras de negócio não óbvias** — o que o código implementa mas não explica (`docs/business/`).
- **Estado atual do projeto** — fase, bloqueios e próximos passos (`STATUS.md`).

### O que nunca deve ser documentado no código
- O que o código faz — nomes claros já comunicam isso.
- Como a linguagem funciona — assume-se conhecimento do leitor.
- Histórico de mudanças — isso pertence ao git log e ao ADR.
- Referências à tarefa ou issue que motivou o código — pertence ao commit ou PR.

### Localização
- Documentação de produto e negócio: `docs/business/`
- Documentação técnica de arquitetura: `docs/decisions/` (ADRs)
- Documentação de APIs: `docs/api/`
- Guias de processo e operação: `docs/guides/`
- Exploração de ideias: `docs/brainstorms/`
- Backlog e tarefas: `docs/backlog.md`
- Padrões e convenções: `standards/`
- Instruções reutilizáveis para o AI: `skills/`

### Sincronização com o código
- Documentação é atualizada **no mesmo PR ou commit** que altera o comportamento que ela descreve.
- Documentação obsoleta é removida ou marcada com `[DEPRECATED - substituído por: link]`.
- Nunca deixar documentação que contradiz o comportamento atual do sistema.

### Linguagem e formato
- Linguagem padrão do projeto definida em `PROJECT_CONTEXT.md` — seguida por toda documentação.
- Markdown é o formato padrão para toda documentação textual.
- Títulos seguem hierarquia (H1 → H2 → H3) — nunca pular nível.
- Listas são usadas para enumerações, tabelas para comparações, código para exemplos técnicos.
- Exemplos de código em documentação são funcionais e testados — nunca pseudo-código sem aviso.

---

## Checklist

Use antes de considerar qualquer feature, decisão ou mudança de comportamento como documentada.

### Conteúdo
- [ ] O "por quê" da mudança está registrado (ADR, commit ou PR)
- [ ] Comportamento novo ou alterado está refletido na documentação existente
- [ ] Nenhuma documentação contradiz o comportamento atual
- [ ] Documentação obsoleta foi removida ou marcada como deprecated

### Localização
- [ ] Documento está no diretório correto conforme a tabela de localização
- [ ] Arquivo tem nome descritivo em kebab-case
- [ ] Se é um ADR: segue o formato padrão definido em `AI_PROJECT_PROTOCOL.md`

### README.md
- [ ] Pré-requisitos de instalação estão atualizados
- [ ] Instruções de execução refletem o estado atual
- [ ] Variáveis de ambiente necessárias estão listadas (sem valores sensíveis)

### API
- [ ] Novos endpoints documentados com método, rota, parâmetros e resposta
- [ ] Endpoints removidos ou alterados têm documentação atualizada
- [ ] Códigos de erro documentados

### Código
- [ ] Sem comentários que descrevem o quê (apenas o porquê)
- [ ] Sem código comentado
- [ ] Lógica não óbvia tem comentário explicando a restrição ou invariante

---

## Critérios Mínimos Aceitáveis

Um projeto é considerado aceitável em documentação quando:

- `README.md` permite que alguém novo rode o projeto sem assistência.
- `PROJECT_CONTEXT.md` explica o problema e os objetivos de forma que qualquer colaborador entenda.
- Toda decisão arquitetural relevante dos últimos 6 meses tem ADR correspondente.
- Nenhuma documentação contradiz o comportamento atual do sistema.
- APIs públicas têm contratos documentados e atualizados.

---

## Critérios Recomendados

Práticas que elevam a maturidade da documentação do projeto:

- Diagrama de arquitetura de alto nível em `docs/` — atualizado a cada mudança estrutural.
- Diagrama de fluxo dos processos de negócio principais em `docs/business/`.
- Glossário do domínio em `docs/business/glossario.md` — termos técnicos e de negócio definidos.
- Runbook operacional em `docs/guides/runbook.md` — procedimentos para deploy, rollback e incidentes.
- Onboarding guide em `docs/guides/onboarding.md` — guia para novos colaboradores.
- Links para documentação externa referenciados de forma centralizada (não espalhados pelo código).
- Revisão da documentação incluída no processo de revisão periódica do projeto (ver `AI_PROJECT_PROTOCOL.md` Seção 11).
- Documentação de APIs gerada automaticamente a partir do código quando possível (ex: OpenAPI/Swagger).
