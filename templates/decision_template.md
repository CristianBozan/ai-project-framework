# ADR-XXXX — [Título da Decisão]

> Architecture Decision Record (ADR): registro de uma decisão técnica ou de produto relevante.
> Criado quando a decisão tem impacto duradouro, pode ser questionada no futuro ou representa uma troca consciente.
> Baseado no formato MADR (Markdown Architectural Decision Records).

---

## Metadados

| Campo | Valor |
|-------|-------|
| **ID** | ADR-XXXX |
| **Data** | YYYY-MM-DD |
| **Status** | [Proposto \| Aceito \| Deprecado \| Substituído por ADR-XXXX] |
| **Decisores** | [Nome(s) ou papel(is) que tomaram a decisão] |
| **Área** | [Arquitetura \| Banco de dados \| Infraestrutura \| Frontend \| Backend \| Processo \| Produto] |

---

## Contexto

> Qual é a situação atual? Qual problema ou necessidade levou a esta decisão?
> Descreva os fatos, restrições e forças em jogo — sem mencionar a decisão ainda.
> Seja concreto: quem está sendo impactado, qual é a escala, quais são os limites.

[Ex: O sistema precisa autenticar usuários. Hoje não há autenticação implementada. O prazo para o MVP é de 6 semanas. A equipe tem experiência com JWT mas não com OAuth. O sistema não prevê integração com provedores externos por enquanto.]

---

## Problema

> Uma frase direta descrevendo o que precisa ser decidido.

[Ex: Qual mecanismo de autenticação adotar para o MVP, considerando prazo e expertise da equipe?]

---

## Opções Consideradas

### Opção 1: [Nome da opção]

> Descrição objetiva do que esta opção envolve.

[Ex: JWT stateless com refresh tokens armazenados no servidor]

**Prós:**
- [Pro 1]
- [Pro 2]

**Contras:**
- [Contra 1]
- [Contra 2]

---

### Opção 2: [Nome da opção]

[Descrição]

**Prós:**
- [Pro 1]

**Contras:**
- [Contra 1]

---

### Opção 3: [Nome da opção] (se aplicável)

[Descrição]

**Prós:**
- [Pro 1]

**Contras:**
- [Contra 1]

---

## Decisão

> O que foi escolhido e por quê — de forma direta e sem ambiguidade.
> Explique a lógica da escolha, não apenas o resultado.

[Ex: Escolhemos JWT com refresh tokens (Opção 1) porque a equipe já tem domínio da tecnologia, reduzindo risco técnico no prazo de 6 semanas. A ausência de integração externa no MVP torna OAuth desnecessariamente complexo agora.]

---

## Consequências

### O que muda

- [Ex: Toda rota protegida verificará o JWT no header Authorization]
- [Ex: Refresh tokens serão armazenados no banco — tabela `refresh_tokens`]

### O que fica mais fácil

- [Ex: Implementação simples e bibliotecas maduras disponíveis]
- [Ex: Equipe familiar com o padrão — menos curva de aprendizado]

### O que fica mais difícil ou implica dívida

- [Ex: Invalidação imediata de tokens antes da expiração requer blacklist]
- [Ex: Se no futuro precisar de OAuth, haverá refatoração]

### Revisão necessária quando

- [Ex: Se a integração com provedores externos for adicionada ao roadmap]
- [Ex: Se o volume de usuários exigir escala horizontal da autenticação]

---

## Links e Referências

- [Link para discussão ou PR onde a decisão foi tomada]
- [Link para documentação de referência]
- [ADR relacionado: ADR-XXXX — Título]
