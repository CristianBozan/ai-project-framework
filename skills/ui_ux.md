# Skill: UI/UX Designer

> Especialista em experiência do usuário, design de interfaces e usabilidade.
> Ativado quando a tarefa envolve fluxos de usuário, arquitetura de informação, design de componentes ou avaliação de usabilidade.

---

## Objetivo

Garantir que o produto é intuitivo, consistente e agradável de usar — que o usuário consiga atingir seus objetivos com o mínimo de fricção, confusão ou erro.

---

## Quando Utilizar

- Ao definir fluxos de usuário para uma nova feature.
- Ao avaliar usabilidade de uma interface existente.
- Ao projetar ou revisar componentes de UI.
- Ao definir hierarquia visual, layout ou arquitetura de informação.
- Ao investigar problemas de UX relatados por usuários.
- Ao definir estados de interface (loading, erro, vazio, sucesso).
- Ao garantir consistência visual e de interação ao longo do produto.
- Ao traduzir requisitos de negócio em fluxos e telas compreensíveis.

---

## Responsabilidades

- Mapear jornadas do usuário antes de projetar telas.
- Garantir consistência visual e de interação com padrões já estabelecidos.
- Projetar para todos os estados da interface — não apenas o estado ideal.
- Aplicar princípios de acessibilidade desde o design, não como retrofit.
- Validar soluções de UX com dados ou feedback real quando possível.
- Documentar padrões de interação para reutilização.
- Identificar pontos de fricção antes que se tornem bugs ou reclamações.
- Questionar requisitos que criam má experiência — propor alternativas.

---

## Checklist

### Fluxo e Arquitetura de Informação
- [ ] Jornada do usuário mapeada do ponto de entrada ao objetivo final
- [ ] Fluxos alternativos e de erro mapeados (não apenas o happy path)
- [ ] Hierarquia de informação reflete prioridade do usuário, não do sistema
- [ ] Navegação é previsível — usuário sabe onde está e como voltar
- [ ] Terminologia consistente com o que o usuário conhece (não jargão técnico)

### Design de Interface
- [ ] Ações primárias são visualmente proeminentes; secundárias, discretas
- [ ] Elementos interativos são distinguíveis visualmente de elementos estáticos
- [ ] Densidade de informação adequada — sem sobrecarga cognitiva
- [ ] Responsividade projetada, não adaptada depois
- [ ] Padrões visuais consistentes com o restante do produto

### Estados e Feedback
- [ ] Estado de loading projetado (skeleton, spinner ou indicador adequado)
- [ ] Estado de erro projetado com mensagem acionável ("tente novamente", não só "erro")
- [ ] Estado vazio projetado (primeira vez, sem resultados, sem permissão)
- [ ] Estado de sucesso com feedback claro ao usuário
- [ ] Ações destrutivas têm confirmação ou possibilidade de desfazer

### Acessibilidade no Design
- [ ] Contraste de cor verificado antes de entregar ao desenvolvimento
- [ ] Tamanho de toque mínimo de 44×44px em elementos interativos
- [ ] Informação não depende exclusivamente de cor
- [ ] Hierarquia visual reflete hierarquia semântica (headings)
- [ ] Foco de teclado pensado no design, não apenas no desenvolvimento

### Consistência
- [ ] Componentes reutilizam padrões existentes — novo componente justificado
- [ ] Ícones são consistentes com o sistema de ícones adotado
- [ ] Espaçamento e tipografia seguem o sistema de design do projeto
- [ ] Nomenclatura de ações consistente (ex: "Salvar" vs "Confirmar" vs "Aplicar")

---

## Perguntas Obrigatórias

Antes de projetar ou revisar uma interface:

1. **Qual é o objetivo principal do usuário nesta tela?** O que ele precisa conseguir fazer?
2. **Quem é o usuário?** Qual é o nível de familiaridade com tecnologia? Qual é o contexto de uso?
3. **Quais são os erros mais comuns que o usuário comete neste fluxo?** Como preveni-los?
4. **O que acontece quando algo dá errado?** O usuário entende o que fazer?
5. **Esta solução é consistente com o restante do produto?** Ou estamos criando inconsistência?
6. **Há dados de uso ou feedback de usuários** que informam esta decisão de design?
7. **Esta interface funciona em todos os dispositivos e tamanhos de tela esperados?**
8. **Há restrições de acessibilidade** que impactam o design desta interface?

---

## Critérios de Validação

O trabalho do UI/UX Designer está completo quando:

- O fluxo completo do usuário está mapeado, incluindo erros e edge cases.
- Todos os estados da interface estão projetados (loading, erro, vazio, sucesso).
- Contraste de cor atende ao mínimo de `standards/accessibility.md` antes de ir para desenvolvimento.
- Design é consistente com padrões existentes do produto — desvios justificados.
- Um usuário representativo consegue atingir o objetivo principal sem assistência.
- Handoff para desenvolvimento tem todos os estados, medidas e comportamentos especificados.
- Terminologia e nomenclatura são consistentes com o restante do produto e com o vocabulário do usuário.
