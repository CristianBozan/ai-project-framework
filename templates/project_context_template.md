# Project Context — [Nome do Projeto]

> Fonte de verdade do projeto. Lida pelo AI no início de cada sessão.
> Responde ao "por que" e "o quê" — nunca ao "como" (isso vai no código e nos ADRs).
> Última atualização: YYYY-MM-DD

---

## 1. Visão Geral

**Nome do projeto:** [Nome]
**Versão atual:** [Ex: 0.1.0 | MVP | Beta]
**Responsável principal:** [Nome ou equipe]
**Idioma do projeto:** [Ex: Português Brasileiro]

### Problema que este projeto resolve

> Descreva o problema real que existe hoje, sem mencionar a solução ainda.
> Exemplo: "Equipes de suporte perdem em média 2 horas/dia buscando informações espalhadas em 4 sistemas diferentes."

[Descreva o problema aqui]

### Solução proposta

> Descreva o que está sendo construído e por que esta abordagem resolve o problema.

[Descreva a solução aqui]

### Quem usa este sistema

| Perfil de usuário | Contexto de uso | Necessidade principal |
|------------------|----------------|----------------------|
| [Ex: Analista de suporte] | [Ex: Desktop, durante atendimento] | [Ex: Acesso rápido ao histórico do cliente] |
| | | |

---

## 2. Objetivos

### Objetivo principal

> Uma frase. O que este projeto precisa entregar para ser considerado bem-sucedido?

[Objetivo principal aqui]

### Objetivos secundários

- [Objetivo 2]
- [Objetivo 3]

### O que este projeto explicitamente NÃO é

> Delimitar o que está fora do escopo evita expectativas erradas e scope creep.

- [Ex: Não é um sistema de CRM — não gerencia relacionamento com clientes]
- [Ex: Não substitui o sistema X — integra com ele]

---

## 3. Métricas de Sucesso

> Como saberemos que o projeto foi bem-sucedido? Métricas mensuráveis.

| Métrica | Situação atual | Meta |
|---------|---------------|------|
| [Ex: Tempo médio para encontrar histórico] | [Ex: 8 minutos] | [Ex: < 1 minuto] |
| | | |

---

## 4. Restrições e Premissas

### Restrições

> Limites não negociáveis que impactam decisões técnicas e de produto.

- **Prazo:** [Ex: MVP até 2026-09-01]
- **Orçamento:** [Ex: Sem custo de infraestrutura adicional]
- **Tecnologia:** [Ex: Deve rodar na infraestrutura AWS existente]
- **Compliance:** [Ex: Dados de usuários sob LGPD — armazenados no Brasil]
- **Integrações obrigatórias:** [Ex: Deve integrar com sistema ERP legado via API REST]

### Premissas

> O que estamos assumindo como verdadeiro. Se uma premissa mudar, o projeto precisa ser revisado.

- [Ex: A equipe de suporte tem acesso a internet estável durante o uso]
- [Ex: O sistema ERP legado permanecerá disponível durante a migração]

---

## 5. Decisões Técnicas Vigentes

> Resumo das principais decisões arquiteturais já tomadas. ADRs detalhados em `docs/decisions/`.

| Decisão | Escolha | ADR |
|---------|---------|-----|
| [Ex: Linguagem backend] | [Ex: TypeScript + Node.js] | [ADR-0001] |
| [Ex: Banco de dados] | [Ex: PostgreSQL] | [ADR-0002] |
| [Ex: Hospedagem] | [Ex: AWS ECS] | [ADR-0003] |

---

## 6. Arquitetura de Alto Nível

> Diagrama ou descrição da estrutura do sistema. Detalhe técnico vai em `docs/`.

```
[Diagrama em ASCII ou descrição em texto]

Ex:
[Browser] → [Next.js Frontend] → [Node.js API] → [PostgreSQL]
                                       ↓
                                 [Redis Cache]
                                       ↓
                               [ERP Legado (REST)]
```

---

## 7. Stack Tecnológica

| Camada | Tecnologia | Versão mínima |
|--------|-----------|--------------|
| [Ex: Frontend] | [Ex: React + Next.js] | [Ex: Next.js 15] |
| [Ex: Backend] | [Ex: Node.js + Express] | [Ex: Node 20 LTS] |
| [Ex: Banco de dados] | [Ex: PostgreSQL] | [Ex: 16] |
| [Ex: Infraestrutura] | [Ex: Docker + AWS ECS] | — |
| [Ex: CI/CD] | [Ex: GitHub Actions] | — |

---

## 8. Equipe e Responsabilidades

| Papel | Nome / Contato | Responsabilidade |
|-------|--------------|-----------------|
| [Ex: Product Owner] | [Nome] | [Ex: Priorização e aceite de requisitos] |
| [Ex: Tech Lead] | [Nome] | [Ex: Decisões técnicas e revisão de código] |
| [Ex: Dev Backend] | [Nome] | [Ex: APIs e integrações] |

---

## 9. Dependências Externas

| Sistema / Serviço | Criticidade | Responsável | Contato |
|------------------|------------|------------|--------|
| [Ex: ERP Legado] | [Alta] | [Time de TI] | [email] |
| [Ex: Provedor de e-mail] | [Média] | [DevOps] | — |

---

## 10. Glossário do Domínio

> Termos específicos do negócio ou do projeto que precisam de definição clara.

| Termo | Definição |
|-------|----------|
| [Termo] | [Definição objetiva, sem ambiguidade] |
| | |

---

## 11. Histórico de Mudanças neste Documento

| Data | Mudança | Motivo |
|------|---------|--------|
| YYYY-MM-DD | Criação inicial | Setup do projeto |
| | | |
