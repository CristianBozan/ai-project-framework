# Como Contribuir

Obrigado pelo interesse em melhorar o AI Project Framework.

---

## O que contribuir

Contribuições bem-vindas:

- **Correções** — informação errada, link quebrado, instrução ambígua
- **Melhorias** — tornar um processo mais claro, mais prático ou mais conciso
- **Novas skills** — especialistas que fazem falta (ex: `security_reviewer`, `architect`)
- **Novos exemplos** — tipos de projeto ainda não cobertos
- **Padrões por linguagem** — `standards/languages/typescript.md`, `python.md`, etc.
- **Tradução** — versão em inglês dos arquivos principais

Não é o momento certo para contribuir:
- Adicionar ferramentas ou dependências de código
- Mudar o propósito do framework (é de governança, não de código)
- Propor mudanças de estilo sem impacto prático

---

## Como contribuir

### 1. Abrir uma issue primeiro

Antes de submeter um PR, abra uma issue descrevendo:
- O que está errado ou faltando
- Por que a mudança melhora o framework
- O que você propõe

Isso evita trabalho desnecessário se a mudança não se alinhar com a direção do projeto.

### 2. Fork e branch

```bash
git clone https://github.com/CristianBozan/ai-project-framework.git
cd ai-project-framework
git checkout -b minha-contribuicao
```

### 3. Fazer as mudanças

- Siga os padrões de escrita dos arquivos existentes
- Linguagem padrão: Português Brasileiro
- Markdown com títulos em hierarquia (H1 → H2 → H3)
- Sem emojis, sem enfeites — direto ao ponto

### 4. Atualizar o CHANGELOG.md

Adicione uma entrada na seção `[Não lançado]` no topo do CHANGELOG com o que mudou.

### 5. Abrir o Pull Request

Descreva no PR:
- O que foi mudado
- Por que melhora o framework
- Se há impacto em outros arquivos

---

## Padrões de escrita

| O que | Como |
|-------|------|
| Tom | Direto, sem rodeios, sem jargão desnecessário |
| Pessoa | Você (segunda pessoa) |
| Listas | Para enumerações sem ordem — usar `•` ou `-` |
| Tabelas | Para comparações e mapeamentos |
| Código | Para instruções que o usuário copia e cola |
| Negrito | Para termos importantes na primeira ocorrência |
| Itálico | Evitar — preferir negrito ou reescrita |

---

## Dúvidas

Abra uma issue com a tag `question`.
