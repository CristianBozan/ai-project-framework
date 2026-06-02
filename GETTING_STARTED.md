# Guia para Iniciantes

> Se você está começando na programação ou é a primeira vez que usa este framework, comece aqui.
> Este guia responde às perguntas mais comuns antes de qualquer código ser escrito.

---

## Antes de Começar — O Que Você Precisa Ter Instalado

Antes de usar o framework você precisa de três ferramentas. Se já tem, pule para a próxima seção.

### 1. Git

Git é o sistema que controla versões do seu código e permite publicar no GitHub.

**Verificar se já tem:**
```bash
git --version
```
Se aparecer `git version 2.x.x`, está instalado. Se der erro, baixe em: https://git-scm.com/downloads

### 2. Node.js (para usar o degit)

Node.js é necessário para rodar o comando `npx degit` — a forma recomendada de copiar o framework.

**Verificar se já tem:**
```bash
node --version
```
Se aparecer `v20.x.x` ou superior, está instalado. Se der erro, baixe a versão LTS em: https://nodejs.org

### 3. Editor de Código com Claude Code

Este framework foi projetado para trabalhar com **Claude Code** — a versão do Claude que roda dentro do editor e lê os arquivos do seu projeto.

- **VS Code** + extensão Claude Code: https://code.visualstudio.com
- Ou use diretamente em: https://claude.ai/code

---

## Análise de Situações

Encontre abaixo a situação que mais se parece com a sua. Cada uma indica o caminho certo a seguir.

---

### Situação 1 — "Quero criar meu portfólio pessoal"

**Perfil:** desenvolvedor solo, projeto pessoal, prazo flexível, objetivo de mostrar trabalho para recrutadores.

**Modo recomendado:** Lite

**Caminho:**
```
1. Use this template no GitHub → crie repo "portfolio-pessoal"
2. git clone do novo repositório
3. Abra no VS Code + Claude Code
4. Use START_LITE_PROJECT.md
5. Descoberta Lite: ~20 min
6. Comece a codar
```

**O que o framework vai te dar:**
- Clareza sobre o que colocar no portfólio (os projetos certos, a mensagem certa)
- Estrutura de pastas organizada desde o início
- Padrões de qualidade e acessibilidade aplicados automaticamente

**O que você pode ignorar por agora:**
- `project/` (pasta do modo Completo — não é para você)
- `examples/` (referência — pode deletar do seu repo)
- `standards/devops.md` (não tem CI/CD em portfólio)

---

### Situação 2 — "Tenho um TCC para entregar"

**Perfil:** estudante, prazo fixo, entregáveis formais (texto + protótipo), orientador para satisfazer.

**Modo recomendado:** Lite com elementos do Completo

**Caminho:**
```
1. Use this template → crie repo "tcc-nome-do-projeto"
2. git clone
3. Use START_LITE_PROJECT.md
4. Na descoberta: informe o prazo de defesa como restrição crítica
5. Peça ao AI para criar um cronograma de entregáveis no backlog
```

**O que o framework vai te dar:**
- Estrutura de projeto que impressiona a banca (ADRs documentam decisões técnicas)
- Backlog com as tarefas do TCC + as tarefas do texto
- Registro das decisões de tecnologia e metodologia que você vai precisar justificar na defesa

**Dica importante para TCC:**
No bloco de descoberta, informe explicitamente:
```
"Este é um TCC. Preciso de um protótipo funcional E de um texto acadêmico.
Prazo de defesa: [data]. Orientador revisa a cada 2 semanas."
```
O AI vai organizar o backlog considerando as duas frentes — código e escrita.

---

### Situação 3 — "Quero construir um MVP para validar uma ideia"

**Perfil:** empreendedor ou dev solo, ideia de produto, quer lançar rápido para ver se tem demanda.

**Modo recomendado:** Lite (se solo) ou Completo (se já tem sócio ou cliente)

**Caminho:**
```
1. Use this template → crie repo "nome-do-mvp"
2. git clone
3. Se solo: START_LITE_PROJECT.md
   Se com sócio/cliente: START_NEW_PROJECT.md
4. Na descoberta: seja brutal sobre o escopo
   "O que é o MÍNIMO para alguém pagar por isso?"
```

**O que o framework vai te dar:**
- Separação clara entre o que entra no MVP e o que é sonho de produto
- Prevenção do erro mais comum em MVPs: construir demais antes de validar
- Estrutura que escala para o Completo quando o produto crescer

**Pergunta crítica para o AI na descoberta:**
```
"Se eu tivesse apenas 4 semanas para construir algo que alguém pagaria,
o que eu cortaria desta lista de funcionalidades?"
```

---

### Situação 4 — "Tenho um freela para um cliente"

**Perfil:** desenvolvedor freelancer, cliente real, dinheiro envolvido, escopo pode mudar.

**Modo recomendado:** Completo (mesmo sendo solo — cliente = complexidade)

**Caminho:**
```
1. Use this template → crie repo privado "cliente-nome-do-projeto"
2. git clone
3. Use START_NEW_PROJECT.md
4. Na descoberta: trate o cliente como stakeholder
   Anote tudo que ele pede, inclusive o que parece óbvio
5. Gere o PROJECT_CONTEXT.md e mostre ao cliente para validar
```

**Por que modo Completo para freela?**
- Cliente muda de ideia — você precisa de registro do que foi acordado
- Scope creep é o maior problema de freela — o backlog e o PROJECT_CONTEXT.md são sua proteção
- ADRs documentam por que você escolheu tal tecnologia — protege você se o cliente questionar depois

**Dica de ouro:**
Envie o `project/PROJECT_CONTEXT.md` aprovado para o cliente por e-mail com a mensagem:
```
"Este documento resume o que entendi do projeto e o que será entregue.
Confirme se está correto antes de começarmos."
```
Isso vale como escopo acordado.

---

### Situação 5 — "Estou aprendendo a programar"

**Perfil:** iniciante, estudando por conta própria ou em curso, fazendo projetos de estudo.

**Modo recomendado:** Lite — mas com paciência na descoberta

**Caminho:**
```
1. degit (sem criar repo no GitHub ainda)
   npx degit CristianBozan/ai-project-framework meu-projeto-estudo
   cd meu-projeto-estudo
2. Abra no VS Code + Claude Code
3. Use START_LITE_PROJECT.md
4. Na descoberta: seja honesto sobre seu nível
   "Estou aprendendo [tecnologia]. Este é um projeto de estudo."
```

**O que muda quando você informa que está aprendendo:**
O AI vai:
- Adaptar a linguagem das explicações ao seu nível
- Sugerir uma stack mais simples e adequada para aprendizado
- Incluir tarefas de "entender X antes de implementar Y" no backlog
- Explicar o porquê das decisões, não só o como

**O que o framework vai te dar no contexto de aprendizado:**
- Você não vai mais começar um projeto e abandonar no meio porque não sabe para onde ir
- Cada projeto de estudo vai ter backlog, contexto e documentação — isso vira portfólio automaticamente
- Você vai aprender a pensar em projetos como profissionais pensam

---

### Situação 6 — "Quero construir um SaaS ou sistema web para time"

**Perfil:** desenvolvedor sênior ou time pequeno, produto com usuários reais, ciclo de vida longo.

**Modo recomendado:** Completo

**Caminho:**
```
1. Use this template → crie repositório do produto
2. Todos do time fazem git clone
3. Um único responsável conduz START_NEW_PROJECT.md
4. A descoberta (~60 min) é feita com todos os stakeholders presentes
5. PROJECT_CONTEXT.md aprovado vira a constituição do produto
```

**O que o framework vai te dar:**
- Alinhamento do time antes de escrever código
- Decisões técnicas documentadas — novo dev entende o histórico em 30 min
- Revisões periódicas que evitam que o projeto derive sem direção

---

## Como Instalar — Os Três Caminhos

### Caminho A — "Use this template" no GitHub (recomendado na maioria dos casos)

Use quando: quer criar um repositório GitHub para o projeto novo.

```
1. Acesse github.com/CristianBozan/ai-project-framework
2. Clique no botão verde "Use this template"
3. Clique em "Create a new repository"
4. Preencha:
   - Owner: seu usuário do GitHub
   - Repository name: nome-do-projeto (ex: portfolio-pessoal)
   - Visibility: Public ou Private
5. Clique em "Create repository"
6. Na página do novo repositório, clique em "Code" → copie a URL
7. No terminal:
   git clone https://github.com/seu-usuario/nome-do-projeto.git
   cd nome-do-projeto
8. Abra no VS Code:
   code .
```

**Resultado:** repositório novo no GitHub, sem o histórico do framework, pronto para começar.

---

### Caminho B — `degit` (recomendado para uso local)

Use quando: quer trabalhar localmente sem criar repositório no GitHub agora.

```bash
# Instala e executa degit (não precisa instalar permanentemente)
npx degit CristianBozan/ai-project-framework nome-do-projeto

# Entra na pasta
cd nome-do-projeto

# Inicializa git limpo
git init
git add .
git commit -m "feat: setup from ai-project-framework"

# Abre no VS Code
code .
```

**Resultado:** pasta local com os arquivos do framework, histórico git limpo, sem vínculo com o repositório original.

---

### Caminho C — Download ZIP (sem terminal)

Use quando: não quer usar o terminal agora.

```
1. Acesse github.com/CristianBozan/ai-project-framework
2. Clique em "Code" → "Download ZIP"
3. Extraia o ZIP onde quiser
4. Renomeie a pasta para o nome do seu projeto
5. Abra no VS Code
```

**Resultado:** funciona, mas você não terá controle de versão imediato. Recomendado apenas para explorar o framework antes de decidir usá-lo de verdade.

---

## Qual Caminho de Instalação Escolher?

```
Quero publicar o projeto no GitHub?
├── Sim → Caminho A (Use this template)
└── Não
    ├── Tenho Node.js instalado? → Sim → Caminho B (degit)
    └── Não quero usar terminal agora → Caminho C (ZIP)
```

---

## Perguntas Frequentes de Iniciantes

**"Preciso saber tudo sobre Git para usar o framework?"**
Não. Para começar você precisa de apenas 4 comandos: `git clone`, `git add .`, `git commit -m "mensagem"` e `git push`. O AI te ajuda com o resto.

**"Posso usar o framework sem o Claude Code?"**
Sim, mas a experiência é muito melhor com ele. O Claude Code lê os arquivos do projeto automaticamente, então o AI já começa com contexto. Sem ele, você precisa colar o conteúdo dos arquivos manualmente na conversa.

**"O que faço se errar algo na descoberta?"**
Nada é definitivo antes de você aprovar. O AI apresenta o PROJECT_CONTEXT.md para revisão antes de salvar. Você pode corrigir, adicionar ou pedir para refazer qualquer parte.

**"Preciso preencher todos os campos do PROJECT_CONTEXT.md?"**
No modo Lite, não — são só 4 campos e campos incertos ficam como `[A DEFINIR]`. No modo Completo, complete o que souber agora e vá preenchendo os `[A DEFINIR]` conforme o projeto evolui.

**"Posso mudar de ideia durante o projeto?"**
Sim. Projetos mudam. Quando isso acontecer, diga ao AI: `"O escopo mudou. Vamos atualizar o PROJECT_CONTEXT.md."` O AI conduz a atualização e registra o que mudou e por quê.

**"E se eu quiser usar uma tecnologia que o AI não conhece?"**
O framework é agnóstico de tecnologia — funciona com qualquer linguagem ou framework. Basta informar na descoberta: `"Quero usar [tecnologia X]"`. O AI vai adaptar as recomendações.

**"Posso usar o framework para projetos que já existem?"**
Sim. Para projetos existentes, pule a descoberta e preencha o PROJECT_CONTEXT.md diretamente descrevendo o que já existe. Depois gere o backlog com as tarefas pendentes e continue a partir daí.

**"Tenho que usar todas as skills?"**
Não. Ative só as que a tarefa atual exige. Um projeto simples de portfólio raramente precisa de mais de 3 skills durante todo o desenvolvimento.

---

## Armadilhas Comuns para Iniciantes

| Armadilha | O que acontece | Como evitar |
|-----------|---------------|-------------|
| Pular a descoberta | O projeto começa sem clareza, muda de direção no meio e nunca termina | Sempre faça a descoberta, mesmo que seja a versão Lite de 20 min |
| Usar o modo Completo para tudo | Processo pesado demais para projetos pequenos, você abandona o framework | Comece pelo Lite — migre para o Completo se o projeto crescer |
| Não atualizar o STATUS.md | Você perde o fio da meada entre sessões e o AI não sabe o que já foi feito | 2 minutos ao fim de cada sessão — é suficiente |
| Tentar implementar tudo de uma vez | Código bagunçado, sem testes, difícil de manter | O framework força incrementos pequenos — confie no processo |
| Aceitar o primeiro backlog sem revisar | Tarefas vagas ou na ordem errada geram retrabalho | Revise sempre: `"esta tarefa tem critério de conclusão claro?"` |
| Usar `git clone` para criar projetos novos | Novo projeto herda histórico sujo do framework | Use "Use this template" ou `degit` |

---

## Próximos Passos

Encontrou sua situação? Escolheu o modo?

```
Modo Lite  → leia START_LITE_PROJECT.md
Modo Completo → leia START_NEW_PROJECT.md
Dúvida sobre qual skill usar → leia SKILLS_INDEX.md
```
