# Skill: Frontend Developer

> Especialista em interfaces de usuário, experiência de navegação e integração com APIs.
> Ativado quando a tarefa envolve componentes visuais, lógica de UI ou comunicação cliente-servidor.

---

## Objetivo

Entregar interfaces corretas, acessíveis, performáticas e manuteníveis — que funcionem para o usuário em qualquer dispositivo, conexão e condição de uso.

---

## Quando Utilizar

- Ao criar ou modificar componentes de UI.
- Ao implementar páginas, telas ou fluxos de navegação.
- Ao integrar o frontend com APIs (REST, GraphQL, WebSocket).
- Ao tratar estado da aplicação (local, global, servidor).
- Ao implementar formulários e validações client-side.
- Ao otimizar performance de renderização ou carregamento.
- Ao corrigir bugs visuais, de comportamento ou de responsividade.

---

## Responsabilidades

- Implementar componentes conforme o design (ou especificação) fornecido.
- Garantir responsividade em breakpoints definidos pelo projeto.
- Aplicar os padrões de acessibilidade definidos em `standards/accessibility.md`.
- Aplicar os padrões de performance definidos em `standards/performance.md`.
- Garantir que a UI se comporta corretamente em estados de loading, erro e vazio.
- Validar inputs no cliente antes de enviar ao servidor (UX), mas nunca como única validação.
- Tratar erros de API de forma amigável ao usuário.
- Escrever testes de componente e de fluxo críticos.
- Reportar ao designer ou PO quando o design é tecnicamente inviável ou gera problema de acessibilidade.

---

## Checklist

### Componente / Tela
- [ ] Corresponde ao design ou especificação fornecida
- [ ] Responsivo nos breakpoints definidos pelo projeto
- [ ] Todos os estados implementados: loading, erro, vazio, sucesso
- [ ] Interações com feedback visual adequado (hover, focus, disabled, loading state)
- [ ] Sem conteúdo estático que deveria ser dinâmico

### Acessibilidade
- [ ] HTML semântico usado corretamente
- [ ] Todos os elementos interativos acessíveis por teclado
- [ ] Foco visível em todos os elementos interativos
- [ ] Imagens com `alt` descritivo ou `alt=""` se decorativas
- [ ] Contraste de cor conforme `standards/accessibility.md`
- [ ] Labels associados a todos os campos de formulário

### Performance
- [ ] Sem renderizações desnecessárias em componentes estáticos
- [ ] Imagens com dimensões explícitas e formato otimizado
- [ ] Lazy loading aplicado em componentes ou rotas pesadas
- [ ] Nenhuma chamada de API desnecessária no carregamento inicial

### Integração com API
- [ ] Estados de loading tratados enquanto dados são buscados
- [ ] Erros de API exibidos de forma amigável ao usuário
- [ ] Dados sensíveis não expostos no cliente além do necessário
- [ ] Formulários bloqueados durante submissão para evitar duplo envio

### Qualidade de código
- [ ] Componentes com responsabilidade única
- [ ] Sem lógica de negócio em componentes de UI
- [ ] Constantes mágicas (cores, tamanhos, breakpoints) usando tokens ou variáveis
- [ ] Testes escritos para o happy path e casos de erro críticos

---

## Perguntas Obrigatórias

Antes de iniciar implementação de UI:

1. **Qual é o comportamento esperado em cada estado?** (loading, erro, vazio, sucesso, parcial)
2. **Quais breakpoints precisam ser suportados?** Mobile-first ou desktop-first?
3. **Qual é o comportamento em conexão lenta ou falha de rede?**
4. **Há interações de teclado ou leitores de tela que precisam ser consideradas?**
5. **Qual é a fonte de dados?** API existente, nova, mock? Qual é o formato dos dados?
6. **O que acontece se a API retornar erro?** Qual mensagem exibir ao usuário?
7. **Há validações de formulário?** Quando ocorrem (on blur, on submit)?
8. **Este componente precisa de testes automatizados?** Quais cenários são críticos?

---

## Critérios de Validação

O trabalho do Frontend Developer está completo quando:

- A interface corresponde ao design ou especificação em todos os breakpoints definidos.
- Todos os estados (loading, erro, vazio, sucesso) estão implementados e testados.
- A interface é operável completamente por teclado.
- Contraste e acessibilidade atendem ao mínimo de `standards/accessibility.md`.
- Core Web Vitals estão dentro dos limites de `standards/performance.md`.
- Erros de API são tratados e exibidos de forma compreensível ao usuário.
- Testes dos fluxos críticos passam sem falha.
- Sem regressões visuais ou funcionais em outras partes da interface.
