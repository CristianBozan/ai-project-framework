# Standard: Performance

> Padrão universal de performance aplicável a qualquer projeto com interface de usuário ou API.
> Métricas são referência — adapte os valores-alvo à natureza e contexto do projeto.

---

## Objetivo

Garantir que o produto ofereça tempos de resposta aceitáveis, uso eficiente de recursos e experiência fluida para o usuário, tanto em condições ideais quanto em redes lentas ou dispositivos de baixo desempenho.

---

## Critérios Obrigatórios

### Web — Core Web Vitals (Google)
- **LCP (Largest Contentful Paint):** ≤ 2.5s — tempo até o maior elemento visível carregar.
- **INP (Interaction to Next Paint):** ≤ 200ms — responsividade a interações do usuário.
- **CLS (Cumulative Layout Shift):** ≤ 0.1 — estabilidade visual da página.

### Web — Carregamento
- Nenhuma requisição bloqueante de renderização sem justificativa documentada.
- Scripts de terceiros não críticos carregam de forma assíncrona (`async` ou `defer`).
- Imagens possuem dimensões explícitas definidas (evita layout shift).
- Imagens são servidas no formato adequado (WebP/AVIF para web) e com tamanho proporcional ao uso.
- Fontes externas usam `font-display: swap` ou equivalente.

### API e Backend
- Endpoints de leitura simples respondem em ≤ 200ms (p95) em condições normais de carga.
- Endpoints de escrita respondem em ≤ 500ms (p95).
- Queries ao banco de dados possuem índices adequados para os padrões de acesso.
- Nenhuma query N+1 em fluxos de leitura de dados.
- Paginação implementada em toda listagem sem limite fixo de registros.

### Geral
- Nenhum loop ou operação pesada bloqueia a thread principal (UI ou event loop do servidor).
- Recursos externos (APIs, bancos) possuem timeout configurado.
- Operações de longa duração são executadas de forma assíncrona com feedback ao usuário.
- Cache é utilizado para dados que mudam com baixa frequência e têm alto custo de acesso.

---

## Checklist

Use antes de considerar qualquer feature ou PR como pronto.

### Web — Carregamento
- [ ] LCP ≤ 2.5s medido no Lighthouse ou WebPageTest
- [ ] INP ≤ 200ms
- [ ] CLS ≤ 0.1
- [ ] Nenhum script crítico bloqueando renderização desnecessariamente
- [ ] Imagens com dimensões explícitas definidas
- [ ] Imagens no formato e tamanho adequados
- [ ] Fontes com `font-display: swap` configurado

### Web — Recursos
- [ ] Bundle JavaScript analisado — sem dependências desnecessariamente grandes
- [ ] Code splitting aplicado em rotas ou features pesadas
- [ ] Assets estáticos servidos com cache de longa duração (`Cache-Control`)
- [ ] Compressão habilitada no servidor (gzip ou brotli)

### API e Backend
- [ ] p95 de endpoints de leitura ≤ 200ms
- [ ] p95 de endpoints de escrita ≤ 500ms
- [ ] Queries críticas têm índices verificados com `EXPLAIN`
- [ ] Nenhuma query N+1 identificada nas listagens
- [ ] Paginação implementada em todas as listagens

### Geral
- [ ] Timeout configurado para chamadas a recursos externos
- [ ] Operações longas são assíncronas
- [ ] Cache implementado onde apropriado
- [ ] Nenhuma operação pesada na thread principal

---

## Critérios Mínimos Aceitáveis

Um projeto é considerado aceitável em performance quando:

- Core Web Vitals estão dentro dos limites definidos (LCP, INP, CLS).
- APIs respondem dentro dos SLOs definidos sob carga normal.
- Nenhuma query N+1 está presente em fluxos críticos.
- Paginação está implementada em todas as listagens.
- Não há regressões de performance em relação à versão anterior.

---

## Critérios Recomendados

Práticas que elevam a maturidade de performance do projeto:

- Monitoramento contínuo de Core Web Vitals em produção (ex: Google Search Console, Sentry).
- Alertas automáticos para regressões de performance no CI (ex: Lighthouse CI, k6).
- Profiling periódico de queries e endpoints mais lentos.
- Implementar cache em múltiplas camadas (CDN, servidor, banco) com estratégia de invalidação documentada.
- Definir e monitorar SLOs (Service Level Objectives) formais para latência e disponibilidade.
- Realizar testes de carga antes de releases com tráfego significativamente maior esperado.
- Lazy loading para imagens e componentes fora da viewport inicial.
- Documentar decisões de cache e suas estratégias de invalidação em `docs/guides/`.
