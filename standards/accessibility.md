# Standard: Acessibilidade

> Padrão universal de acessibilidade para interfaces de usuário.
> Aplicável a projetos web, mobile e desktop que possuam componentes de UI.

---

## Objetivo

Garantir que o produto seja utilizável pelo maior número possível de pessoas, independentemente de limitações visuais, motoras, cognitivas ou tecnológicas, seguindo as diretrizes WCAG 2.1 como referência base.

---

## Critérios Obrigatórios

### Percepção
- Toda imagem não decorativa possui texto alternativo (`alt`) descritivo e significativo.
- Imagens decorativas têm `alt=""` ou são aplicadas via CSS.
- Informações nunca são transmitidas exclusivamente por cor — sempre acompanhadas de texto, ícone ou padrão.
- Contraste mínimo de **4.5:1** para texto normal e **3:1** para texto grande (≥18pt ou ≥14pt negrito).
- Vídeos com áudio possuem legendas ou transcrição.
- Conteúdo de áudio possui transcrição disponível.

### Operabilidade
- Toda funcionalidade é acessível exclusivamente pelo teclado (sem depender de mouse).
- Foco de teclado é visível e com contraste adequado — nunca removido com `outline: none` sem substituto.
- A ordem de foco segue a ordem lógica do conteúdo.
- Nenhum conteúdo pisca mais de 3 vezes por segundo (prevenção de convulsões fotossensíveis).
- Usuário tem controle sobre conteúdo que se move, rola ou atualiza automaticamente.
- Áreas clicáveis têm tamanho mínimo de **44×44px** (WCAG 2.5.5).

### Compreensibilidade
- O idioma da página é definido no atributo `lang` do HTML.
- Labels são associados explicitamente aos seus campos de formulário (`for`/`id` ou `aria-label`).
- Mensagens de erro de formulário identificam o campo com problema e descrevem como corrigir.
- Navegação e nomenclatura são consistentes ao longo de toda a interface.
- Ações irreversíveis solicitam confirmação antes de executar.

### Robustez
- HTML semântico é usado para estruturar conteúdo (`header`, `nav`, `main`, `footer`, `section`, `article`, `aside`).
- Atributos ARIA são usados corretamente — nunca para substituir semântica HTML nativa disponível.
- Componentes interativos customizados implementam os padrões ARIA Authoring Practices Guide.
- Interface é testada e funcional com leitores de tela (NVDA, VoiceOver ou TalkBack).

---

## Checklist

Use antes de considerar qualquer componente ou tela como pronto.

### Imagens e Mídia
- [ ] Imagens informativas têm `alt` descritivo
- [ ] Imagens decorativas têm `alt=""` ou são em CSS
- [ ] Vídeos com áudio têm legendas ou transcrição

### Cor e Contraste
- [ ] Contraste de texto ≥ 4.5:1 (normal) ou ≥ 3:1 (grande)
- [ ] Informação não depende exclusivamente de cor

### Teclado e Foco
- [ ] Toda funcionalidade acessível por teclado
- [ ] Foco visível em todos os elementos interativos
- [ ] Ordem de foco é lógica e intuitiva
- [ ] Nenhum `outline: none` sem substituto visual

### Formulários
- [ ] Todos os campos têm label associado
- [ ] Erros de validação identificam o campo e descrevem a correção
- [ ] Campos obrigatórios são identificados visualmente e programaticamente

### Estrutura e Semântica
- [ ] HTML semântico usado para estrutura de página
- [ ] `lang` definido no elemento `html`
- [ ] Headings seguem hierarquia lógica (h1 → h2 → h3)
- [ ] Links têm texto descritivo (não "clique aqui" ou "saiba mais")

### Componentes Interativos
- [ ] Botões e links são distinguíveis semanticamente
- [ ] Modais/dialogs prendem o foco enquanto abertos
- [ ] ARIA usado somente quando HTML nativo não é suficiente

---

## Critérios Mínimos Aceitáveis

Uma interface é considerada aceitável quando atinge conformidade com **WCAG 2.1 Nível AA**, o que exige:

- Contraste de cor conforme especificado.
- Navegação completa por teclado.
- Texto alternativo em imagens informativas.
- Labels em todos os campos de formulário.
- Ausência de conteúdo piscante acima de 3Hz.
- Idioma da página declarado.

---

## Critérios Recomendados

Práticas que elevam a acessibilidade para além do mínimo exigido:

- Atingir conformidade **WCAG 2.1 Nível AAA** nas funcionalidades principais.
- Testar com usuários reais com deficiência ao menos uma vez por ciclo de release.
- Incluir acessibilidade como critério nos testes automatizados (ex: axe-core, Lighthouse).
- Oferecer modo de alto contraste ou respeitar a preferência do sistema (`prefers-contrast`).
- Respeitar preferência de movimento reduzido (`prefers-reduced-motion`).
- Documentar decisões de acessibilidade não óbvias nos componentes afetados.
- Manter um log de issues de acessibilidade conhecidas com prazo de resolução.
