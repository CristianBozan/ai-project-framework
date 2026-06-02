# Skills Index

> Mapa de ativação de especialistas.
> Use este índice para identificar qual skill acionar com base na tarefa recebida.
> Múltiplas skills podem ser ativadas simultaneamente para tarefas que cruzam domínios.

---

## Índice Rápido

| Skill | Arquivo | Ativar quando... |
|-------|---------|-----------------|
| Business Analyst | `skills/business_analyst.md` | A tarefa não está clara o suficiente para implementar |
| Project Manager | `skills/project_manager.md` | O trabalho precisa ser organizado, priorizado ou acompanhado |
| UI/UX Designer | `skills/ui_ux.md` | A solução envolve interface e experiência do usuário |
| Frontend Developer | `skills/frontend.md` | A tarefa envolve código de interface ou integração com API no cliente |
| Backend Developer | `skills/backend.md` | A tarefa envolve lógica de servidor, APIs ou integrações |
| Database Specialist | `skills/database.md` | A tarefa envolve dados, schema ou queries |
| QA / Testing | `skills/testing.md` | A tarefa envolve qualidade, testes ou investigação de falhas |
| Technical Writer | `skills/documentation.md` | A tarefa envolve criar ou atualizar documentação |
| DevOps | `skills/devops.md` | A tarefa envolve entrega, infraestrutura ou operação |

---

## Mapeamento por Tipo de Tarefa

### Análise e Descoberta

| Tarefa | Skill(s) |
|--------|---------|
| Entender o que o usuário realmente quer | **business_analyst** |
| Levantar e refinar requisitos | **business_analyst** |
| Definir critérios de aceitação | **business_analyst** |
| Mapear fluxo do usuário (jornada) | **business_analyst** + **ui_ux** |
| Identificar regras de negócio ocultas | **business_analyst** |
| Avaliar viabilidade técnica de um requisito | **business_analyst** + skill do domínio |
| Delimitar escopo (o que entra e o que não entra) | **business_analyst** + **project_manager** |
| Identificar stakeholders e impactos | **business_analyst** |
| Definir métricas de sucesso | **business_analyst** + **project_manager** |

---

### Planejamento e Gestão

| Tarefa | Skill(s) |
|--------|---------|
| Planejar um ciclo de trabalho | **project_manager** |
| Priorizar o backlog | **project_manager** |
| Quebrar uma feature grande em tarefas | **project_manager** + skill do domínio |
| Atualizar o project/STATUS.md | **project_manager** |
| Identificar e registrar bloqueios | **project_manager** |
| Identificar e registrar riscos | **project_manager** |
| Conduzir revisão periódica do projeto | **project_manager** |
| Estimar esforço de uma tarefa | **project_manager** + skill do domínio |
| Detectar scope creep | **project_manager** |
| Planejar entregáveis e marcos | **project_manager** |

---

### Experiência do Usuário

| Tarefa | Skill(s) |
|--------|---------|
| Projetar fluxo de uma nova tela ou feature | **ui_ux** |
| Definir arquitetura de informação | **ui_ux** |
| Avaliar usabilidade de interface existente | **ui_ux** |
| Projetar estados de tela (loading, erro, vazio) | **ui_ux** |
| Garantir consistência visual do produto | **ui_ux** |
| Revisar contraste e acessibilidade no design | **ui_ux** |
| Definir nomenclatura e terminologia da UI | **ui_ux** + **business_analyst** |
| Especificar comportamentos de interação | **ui_ux** |
| Criar handoff para desenvolvimento | **ui_ux** + **frontend** |
| Avaliar se o design resiste a dados reais | **ui_ux** + **backend** |

---

### Interface e Frontend

| Tarefa | Skill(s) |
|--------|---------|
| Criar componente de UI | **frontend** |
| Criar tela ou página | **frontend** + **ui_ux** |
| Integrar frontend com API | **frontend** + **backend** |
| Implementar formulário com validação | **frontend** |
| Gerenciar estado da aplicação | **frontend** |
| Implementar responsividade | **frontend** |
| Corrigir bug visual ou de comportamento | **frontend** |
| Otimizar performance de carregamento | **frontend** + **devops** |
| Implementar acessibilidade em componente | **frontend** |
| Implementar rota e navegação | **frontend** |
| Configurar bundler, linter ou build tool | **frontend** + **devops** |
| Escrever testes de componente | **frontend** + **testing** |

---

### API e Backend

| Tarefa | Skill(s) |
|--------|---------|
| Criar ou modificar endpoint de API | **backend** |
| Definir contrato de API (request/response) | **backend** + **business_analyst** |
| Implementar autenticação | **backend** |
| Implementar autorização (permissões) | **backend** |
| Integrar com serviço externo (pagamento, e-mail, terceiros) | **backend** |
| Implementar processamento em background / fila | **backend** + **devops** |
| Tratar erros e exceções no servidor | **backend** |
| Implementar rate limiting | **backend** + **devops** |
| Implementar cache de dados | **backend** + **database** |
| Escrever testes de integração de API | **backend** + **testing** |
| Garantir idempotência de operações | **backend** |

---

### Banco de Dados

| Tarefa | Skill(s) |
|--------|---------|
| Criar ou modificar tabela (schema) | **database** |
| Criar migration | **database** |
| Escrever query complexa | **database** |
| Otimizar query lenta | **database** |
| Definir índices | **database** |
| Modelar relacionamentos entre entidades | **database** + **business_analyst** |
| Avaliar impacto de mudança em dados existentes | **database** + **project_manager** |
| Implementar soft delete | **database** |
| Planejar backfill de dados | **database** + **devops** |
| Avaliar strategy de backup | **database** + **devops** |
| Investigar problema de performance no banco | **database** |

---

### Qualidade e Testes

| Tarefa | Skill(s) |
|--------|---------|
| Definir estratégia de testes da feature | **testing** |
| Escrever testes unitários | **testing** + skill do domínio |
| Escrever testes de integração | **testing** + **backend** |
| Escrever testes E2E | **testing** + **frontend** |
| Investigar causa raiz de um bug | **testing** + skill do domínio |
| Revisar cobertura de testes antes de release | **testing** |
| Configurar pipeline de testes no CI | **testing** + **devops** |
| Reportar bug com reprodução mínima | **testing** |
| Avaliar se feature atende critérios de aceitação | **testing** + **business_analyst** |
| Definir dados de teste e fixtures | **testing** + **database** |

---

### Documentação

| Tarefa | Skill(s) |
|--------|---------|
| Criar ou atualizar README | **documentation** |
| Documentar API (endpoints, contratos) | **documentation** + **backend** |
| Registrar decisão arquitetural (ADR) | **documentation** + skill do domínio |
| Documentar regras de negócio | **documentation** + **business_analyst** |
| Criar guia de uso ou onboarding | **documentation** |
| Criar runbook operacional | **documentation** + **devops** |
| Atualizar documentação após mudança de comportamento | **documentation** |
| Identificar lacunas de documentação | **documentation** |
| Registrar brainstorm | **documentation** |
| Criar ou atualizar glossário do domínio | **documentation** + **business_analyst** |

---

### Infraestrutura e Entrega

| Tarefa | Skill(s) |
|--------|---------|
| Configurar ou modificar pipeline de CI/CD | **devops** |
| Configurar ambiente de desenvolvimento | **devops** |
| Criar ou modificar Dockerfile ou docker-compose | **devops** |
| Configurar variáveis de ambiente e segredos | **devops** |
| Fazer deploy em staging ou produção | **devops** |
| Investigar falha de infraestrutura | **devops** |
| Configurar monitoramento e alertas | **devops** |
| Definir estratégia de deploy (blue/green, canary) | **devops** |
| Configurar backup e disaster recovery | **devops** + **database** |
| Escrever infraestrutura como código (IaC) | **devops** |
| Analisar logs de produção | **devops** |

---

## Mapeamento por Palavras-Chave

Use esta seção quando a tarefa vem descrita de forma vaga ou como frase natural.

| Se a tarefa menciona... | Acionar |
|------------------------|---------|
| "o que precisa ser feito", "o que o usuário quer" | **business_analyst** |
| "requisito", "critério de aceite", "regra de negócio" | **business_analyst** |
| "planejamento", "backlog", "prioridade", "ciclo" | **project_manager** |
| "bloqueio", "risco", "status", "progresso" | **project_manager** |
| "tela", "página", "layout", "fluxo de usuário" | **ui_ux** → **frontend** |
| "componente", "botão", "formulário", "responsivo" | **frontend** |
| "estado", "loading", "erro na tela", "vazio" | **ui_ux** + **frontend** |
| "API", "endpoint", "rota", "controller", "service" | **backend** |
| "autenticação", "autorização", "permissão", "token" | **backend** |
| "integração", "webhook", "terceiro", "pagamento" | **backend** |
| "tabela", "migration", "schema", "query", "índice" | **database** |
| "lento", "N+1", "explain", "performance do banco" | **database** |
| "teste", "cobertura", "bug", "reprodução", "falha" | **testing** |
| "CI falhou", "pipeline", "build quebrado" | **testing** + **devops** |
| "documentar", "escrever", "ADR", "README", "guia" | **documentation** |
| "deploy", "produção", "container", "docker", "infra" | **devops** |
| "log", "alerta", "monitoramento", "SLO" | **devops** |
| "segredo", "variável de ambiente", "credencial" | **devops** + **security** |
| "acessibilidade", "contraste", "leitor de tela" | **frontend** (código) / **ui_ux** (design) |
| "performance", "Core Web Vitals", "LCP", "bundle" | **frontend** + **devops** |

---

## Combinações Frequentes

Algumas tarefas ativam naturalmente mais de uma skill. Use a primeira listada como perspectiva principal.

| Cenário | Skills envolvidas | Perspectiva principal |
|---------|-----------------|----------------------|
| Nova feature do zero | business_analyst + ui_ux + backend + frontend + database + testing | **business_analyst** (começa aqui) |
| Bug de produção | testing + devops + skill do domínio | **testing** (investigar primeiro) |
| Mudança de schema | database + backend + devops | **database** (impacto em dados primeiro) |
| Otimização de performance | frontend + backend + database + devops | depende de onde está o gargalo |
| Onboarding de novo colaborador | documentation + devops | **documentation** |
| Revisão periódica | project_manager + business_analyst | **project_manager** |
| Decisão técnica importante | business_analyst + skill do domínio + documentation | **business_analyst** (contexto de negócio primeiro) |
| Release / entrega | devops + testing + project_manager | **devops** (execução) |

---

## Skills por Modo

### Modo Lite — 3 skills principais

| Skill | Quando |
|-------|--------|
| `business_analyst` | Sempre — conduz a Descoberta Lite (3 blocos) |
| `project_manager` | Gerar e organizar o backlog |
| skill do domínio | `frontend`, `backend` ou `database` conforme a tarefa |

As skills `devops`, `ui_ux` e `documentation` são **opcionais** no modo Lite — use se a tarefa exigir.

### Modo Completo — todas as 9 skills disponíveis

Use o mapeamento completo das seções anteriores.

---

## Como Usar na Prática

```
1. Receber uma tarefa do usuário

2. Verificar o modo do projeto (Lite ou Completo)
   → project-lite/PROJECT_CONTEXT.md existe? → Modo Lite
   → project/PROJECT_CONTEXT.md existe?      → Modo Completo

3. Consultar este índice:
   - Qual tipo de tarefa é?
   - Quais palavras-chave aparecem na descrição?

4. Identificar a(s) skill(s) relevante(s)

5. Ler o arquivo da skill antes de começar
   → O arquivo define Responsabilidades, Checklist e Perguntas Obrigatórias

6. Se houver dúvida sobre o escopo ou o que fazer:
   → Ativar business_analyst primeiro

7. Se houver dúvida sobre por onde começar:
   → Ativar project_manager primeiro
```
