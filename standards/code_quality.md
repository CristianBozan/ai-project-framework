# Standard: Qualidade de Código

> Padrão universal de qualidade aplicável a qualquer linguagem ou paradigma.
> Seções específicas de linguagem devem ser adicionadas em `standards/languages/` conforme o projeto.

---

## Objetivo

Garantir que o código produzido seja legível, manutenível, correto, testável e consistente ao longo do tempo — independentemente de quem o escreveu ou quando.

---

## Critérios Obrigatórios

### Legibilidade
- Nomes de variáveis, funções, classes e arquivos são descritivos e revelam intenção.
- Abreviações são evitadas, exceto quando universalmente reconhecidas no domínio (ex: `id`, `url`, `http`).
- Funções fazem uma coisa — se o nome precisar de "e" ou "ou", provavelmente deve ser dividida.
- Funções têm no máximo **20 linhas** como referência — exceções documentadas.
- Arquivos têm no máximo **300 linhas** como referência — exceções documentadas.
- Aninhamento máximo de **3 níveis** de blocos condicionais ou loops — usar early return para reduzir.

### Comentários
- Comentários explicam o **por quê**, nunca o **o quê** (o código já faz isso).
- Comentários não descrevem o que a função faz — o nome da função faz isso.
- Comentários referentes a tarefas futuras usam `// TODO:` com descrição objetiva.
- Código comentado não é commitado — se não é usado, é deletado.

### Estrutura e Organização
- Um arquivo, uma responsabilidade principal.
- Dependências são injetadas, não instanciadas internamente (favorece testabilidade).
- Lógica de negócio é separada de lógica de infraestrutura (I/O, HTTP, banco de dados).
- Constantes mágicas são nomeadas — nunca números ou strings literais espalhados pelo código.
- Imports são organizados: dependências externas primeiro, depois internas, depois relativas.

### Tratamento de Erros
- Erros são tratados no nível apropriado — nem muito cedo (esconde o problema) nem muito tarde (contexto perdido).
- Exceções genéricas (`catch (e) {}`) são proibidas sem re-throw ou log.
- Funções que podem falhar retornam ou lançam erros explícitos — nunca retornam `null` silenciosamente para indicar falha.
- Toda operação assíncrona tem tratamento de erro.

### Testes
- Todo código de produção tem cobertura de testes adequada ao risco.
- Testes são independentes entre si — a ordem de execução não importa.
- Testes não dependem de estado global ou de outros testes.
- Testes têm nomes que descrevem o comportamento esperado: `deve retornar erro quando campo está vazio`.
- Mocks são usados apenas na fronteira do sistema (I/O, APIs externas) — nunca para mockar lógica interna.

### Versionamento
- Commits são atômicos — uma mudança lógica por commit.
- Mensagens de commit descrevem o motivo da mudança, não o que foi mudado.
- Nunca commitar código que quebra o build ou falha nos testes.
- Branches têm nomes descritivos (`feat/nome-da-feature`, `fix/descricao-do-bug`).

---

## Checklist

Use antes de considerar qualquer PR como pronto para revisão.

### Legibilidade
- [ ] Nomes descrevem intenção sem necessidade de comentário
- [ ] Funções têm responsabilidade única
- [ ] Funções dentro do limite de linhas (ou exceção documentada)
- [ ] Aninhamento máximo respeitado
- [ ] Sem abreviações desnecessárias

### Comentários
- [ ] Sem comentários que descrevem o quê (apenas o porquê)
- [ ] Sem código comentado
- [ ] TODOs têm descrição objetiva

### Estrutura
- [ ] Sem constantes mágicas
- [ ] Lógica de negócio separada de I/O
- [ ] Imports organizados
- [ ] Arquivo com responsabilidade única

### Tratamento de Erros
- [ ] Sem `catch` vazio ou que engole exceções silenciosamente
- [ ] Toda operação assíncrona tem tratamento de erro
- [ ] Erros retornados são explícitos

### Testes
- [ ] Cobertura adequada ao risco da mudança
- [ ] Testes independentes entre si
- [ ] Nomes de testes descrevem comportamento esperado
- [ ] Mocks apenas na fronteira do sistema

### Versionamento
- [ ] Commits atômicos
- [ ] Mensagens de commit descrevem o porquê
- [ ] Build e testes passando antes do commit

---

## Critérios Mínimos Aceitáveis

Um código é considerado aceitável quando:

- Passa nos linters e formatadores configurados no projeto sem warnings ignorados.
- Cobertura de testes não regride em relação à versão anterior.
- Nenhum `catch` vazio ou silencioso presente.
- Nenhuma constante mágica sem nome.
- Nenhum código comentado commitado.
- Build e todos os testes passam.

---

## Critérios Recomendados

Práticas que elevam a maturidade da qualidade de código:

- Cobertura de testes ≥ 80% nas camadas de lógica de negócio.
- Análise estática automatizada no CI (linters, type checkers, complexidade ciclomática).
- Code review obrigatório por pelo menos um par antes de merge.
- Complexidade ciclomática máxima de 10 por função.
- Pair programming ou mob programming para código crítico ou complexo.
- Refactoring contínuo — regra do escoteiro: deixe o código melhor do que encontrou.
- Documentar dívidas técnicas conhecidas em `docs/backlog.md` com severidade e impacto estimado.
- Definir e revisar periodicamente os padrões de linguagem específica em `standards/languages/`.
