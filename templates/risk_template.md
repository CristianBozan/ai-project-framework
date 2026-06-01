# Registro de Riscos — [Nome do Projeto]

> Documento vivo. Revisado em cada revisão periódica do projeto.
> Riscos resolvidos ou descartados são movidos para o histórico.
> Última atualização: YYYY-MM-DD

---

## Como usar este documento

**Probabilidade:** Alta (>70%) | Média (30-70%) | Baixa (<30%)
**Impacto:** Alto (bloqueia entrega ou causa perda significativa) | Médio (atrasa ou degrada) | Baixo (inconveniente gerenciável)
**Prioridade = Probabilidade × Impacto** — riscos de alta prioridade têm plano de mitigação obrigatório.

---

## Riscos Ativos

### RISCO-001 — [Título curto e descritivo]

| Campo | Valor |
|-------|-------|
| **Categoria** | [Técnico / Negócio / Externo / Pessoas / Compliance] |
| **Probabilidade** | [Alta / Média / Baixa] |
| **Impacto** | [Alto / Médio / Baixo] |
| **Prioridade** | [Alta / Média / Baixa] |
| **Identificado em** | YYYY-MM-DD |
| **Dono** | [Nome ou papel responsável por monitorar] |

**Descrição:**
> O que pode acontecer de errado e por quê.

[Ex: O sistema ERP legado pode estar indisponível durante a janela de migração, impedindo a sincronização inicial de dados.]

**Impacto se materializar:**
> O que acontece concretamente se o risco virar realidade.

[Ex: Atraso de 2 a 4 semanas no lançamento; dados precisariam ser migrados manualmente.]

**Plano de mitigação:**
> O que faremos para reduzir a probabilidade ou o impacto antes que aconteça.

- [Ex: Agendar janela de migração com 2 semanas de antecedência com o time de TI]
- [Ex: Criar script de migração manual como fallback]
- [Ex: Testar integração em ambiente de homologação antes da janela de produção]

**Plano de contingência:**
> O que faremos se o risco se materializar mesmo com a mitigação.

[Ex: Pausar migração, executar script manual, reagendar janela com time de TI.]

**Status:** [Monitorando | Mitigação em andamento | Aceito sem ação | Escalado]

---

### RISCO-002 — [Título]

| Campo | Valor |
|-------|-------|
| **Categoria** | [Técnico / Negócio / Externo / Pessoas / Compliance] |
| **Probabilidade** | [Alta / Média / Baixa] |
| **Impacto** | [Alto / Médio / Baixo] |
| **Prioridade** | [Alta / Média / Baixa] |
| **Identificado em** | YYYY-MM-DD |
| **Dono** | [Nome ou papel] |

**Descrição:**
[Descrição do risco]

**Impacto se materializar:**
[Consequências concretas]

**Plano de mitigação:**
- [Ação 1]
- [Ação 2]

**Plano de contingência:**
[O que fazer se acontecer]

**Status:** [Monitorando | Mitigação em andamento | Aceito sem ação | Escalado]

---

## Riscos Resolvidos

> Riscos que foram mitigados, que não se materializaram ou que deixaram de ser relevantes.

| ID | Título | Resolução | Data |
|----|--------|----------|------|
| RISCO-000 | [Exemplo: Indisponibilidade de API de terceiro] | [API foi estabilizada pelo fornecedor] | YYYY-MM-DD |

---

## Riscos Descartados

> Riscos avaliados e deliberadamente não tratados, com justificativa.

| ID | Título | Motivo do descarte | Data |
|----|--------|-------------------|------|
| — | — | — | — |

---

## Resumo por Prioridade

> Gerado na revisão periódica. Atualizar manualmente após cada revisão.

| Prioridade | Quantidade | IDs |
|-----------|-----------|-----|
| Alta | [N] | [RISCO-001, ...] |
| Média | [N] | [...] |
| Baixa | [N] | [...] |
