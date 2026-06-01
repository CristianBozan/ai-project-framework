# Exemplo: Projeto Acadêmico

> Demonstração de como o framework é aplicado a um projeto de TCC ou trabalho acadêmico.
> Adaptado para contexto universitário: prazo fixo, equipe pequena, entregáveis formais.

---

## Contexto do Projeto

**Nome:** SentinelEdu — Sistema de Detecção de Dificuldades de Aprendizagem
**Tipo:** Trabalho de Conclusão de Curso (TCC) — Ciência da Computação
**Instituição:** [Nome da Instituição]
**Fase:** Desenvolvimento | Mês 5 de 8
**Stack:** Python + FastAPI + PostgreSQL + React + scikit-learn
**Idioma:** Português Brasileiro

### Problema

Professores do ensino fundamental identificam dificuldades de aprendizagem dos alunos tarde demais — muitas vezes só ao fim do semestre, quando a intervenção precoce seria mais eficaz. Não há ferramenta acessível que processe os dados já existentes (notas, frequência, participação) para sinalizar alunos em risco de forma proativa.

### Solução

Sistema web que processa dados de desempenho dos alunos (notas, frequência, entrega de atividades) e aplica um modelo de machine learning para identificar, em tempo real, alunos com maior probabilidade de dificuldade de aprendizagem — gerando alertas para o professor e relatórios para a coordenação.

### Quem usa

| Perfil | Contexto | Necessidade |
|--------|---------|------------|
| Professor | Desktop, 2-3x por semana | Ver lista de alunos em risco e o que motivou o alerta |
| Coordenador pedagógico | Desktop, 1x por semana | Ver relatório consolidado da turma e histórico de intervenções |
| Pesquisador (banca) | Desktop, na defesa | Avaliar qualidade técnica e relevância do trabalho |

### Restrições

- **Prazo fixo:** Defesa em 2026-11-15 — sem prorrogação
- **Escopo acadêmico:** Foco em demonstração de viabilidade, não em produto pronto para produção
- **Dados sintéticos:** Por questões de privacidade (LGPD + regulamento da instituição), o sistema usará dataset sintético baseado em dados reais anonimizados
- **Equipe:** 1 desenvolvedor (autor do TCC) + orientador (revisão quinzenal)
- **Custo zero:** Sem serviços pagos — tudo open source ou tier gratuito

### Entregáveis formais

| Entregável | Prazo | Status |
|-----------|-------|--------|
| Proposta de TCC | 2026-02-28 | Entregue |
| Revisão bibliográfica | 2026-04-30 | Entregue |
| Protótipo funcional | 2026-08-31 | Em andamento |
| Texto completo do TCC | 2026-10-15 | Não iniciado |
| Defesa | 2026-11-15 | Não iniciado |

### Métricas de sucesso (acadêmico)

| Métrica | Meta | Por quê importa para a banca |
|---------|------|------------------------------|
| Acurácia do modelo (F1-score) | ≥ 0.75 | Valida a abordagem de ML escolhida |
| Recall (alunos em risco identificados) | ≥ 0.80 | Falso negativo é mais crítico que falso positivo |
| Tempo de processamento por turma | < 5 segundos | Demonstra viabilidade prática |
| Cobertura de testes do backend | ≥ 70% | Qualidade de código exigida pela banca |

---

## MVP — O Que Entra no Protótipo Funcional

O protótipo precisa demonstrar o ciclo completo: dado → modelo → alerta → interface.

### Entra no protótipo

**Pipeline de dados:**
- Upload de planilha CSV com dados de alunos (notas, frequência, atividades)
- Pré-processamento e feature engineering
- Predição com modelo treinado (Random Forest)
- Armazenamento dos resultados no PostgreSQL

**Interface web:**
- Login de professor e coordenador
- Dashboard da turma com lista de alunos e nível de risco (alto / médio / baixo)
- Página de aluno com explicabilidade da predição (features mais relevantes)
- Relatório PDF exportável por turma

**Modelo de ML:**
- Dataset sintético com 500 alunos e 3 anos de histórico
- Feature engineering documentado
- Validação cruzada e métricas de avaliação
- Comparação com 3 algoritmos (Regressão Logística, Random Forest, XGBoost)

### Fora do protótipo (mencionado como trabalhos futuros no TCC)

- Integração com sistemas acadêmicos reais (SIGA, Moodle)
- Dados em tempo real (sem upload manual)
- Modelo de deep learning
- App mobile para professores
- Análise de texto de redações

---

## Backlog

### Alta Prioridade (Meses 1-4 — Concluídos)

- [x] **BK-001** — Revisão bibliográfica sobre detecção de dificuldades de aprendizagem `[research]` — 2026-04-30
- [x] **BK-002** — Geração do dataset sintético com dados realistas `[research] [backend]` — 2026-04-10
- [x] **BK-003** — Análise exploratória dos dados (EDA) em Jupyter Notebook `[research]` — 2026-04-20
- [x] **BK-004** — Feature engineering e pré-processamento `[backend]` — 2026-04-28
- [x] **BK-005** — Treinamento e comparação de modelos (LogReg, RF, XGBoost) `[backend]` — 2026-05-10
- [x] **BK-006** — Setup da API FastAPI com estrutura base `[backend] [infra]` — 2026-05-05

### Alta Prioridade (Meses 5-6 — Em andamento)

- [ ] **BK-007** — Endpoint de upload e processamento de planilha CSV `[backend]`
  - **O quê:** API que recebe CSV, valida, processa, executa predição e armazena resultado
  - **Por quê:** Ponto de entrada de dados no sistema
  - **Critério:** Valida formato, trata erros de dado inválido, retorna resultado em < 5s para 100 alunos

- [ ] **BK-008** — Endpoint de predição com explicabilidade (SHAP values) `[backend]`
  - **O quê:** Retornar predição + features mais relevantes para cada aluno
  - **Por quê:** Explicabilidade é requisito acadêmico — caixa-preta não é aceitável para a banca
  - **Critério:** Top-5 features com direção de impacto retornadas para cada aluno

- [ ] **BK-009** — Frontend: Dashboard da turma `[frontend]`
  - **O quê:** Listagem de alunos com badge de risco (alto/médio/baixo) e filtros
  - **Por quê:** Interface principal do professor
  - **Critério:** Responsivo, acessível por teclado, carrega em < 2s para 100 alunos

- [ ] **BK-010** — Frontend: Página de aluno com explicação da predição `[frontend]`
  - **O quê:** Gráfico de barras das features mais relevantes (SHAP), histórico de notas, frequência
  - **Por quê:** Professor precisa entender POR QUE o aluno foi sinalizado
  - **Critério:** Gráfico legível, dados corretos, sem jargão de ML para o usuário final

### Alta Prioridade (Meses 6-7)

- [ ] **BK-011** — Autenticação de usuários (professor e coordenador) `[backend] [frontend]`
- [ ] **BK-012** — Exportação de relatório PDF por turma `[backend]`
- [ ] **BK-013** — Testes unitários do pipeline de ML (pré-processamento + predição) `[testing]`
- [ ] **BK-014** — Testes de integração da API `[testing]`
- [ ] **BK-015** — Documentação técnica do modelo (features, métricas, limitações) `[docs]`

### Média Prioridade (Mês 8 — Finalização)

- [ ] **BK-016** — Seção de metodologia do TCC (capítulo 3) `[docs]`
- [ ] **BK-017** — Seção de resultados do TCC com gráficos de métricas `[docs]`
- [ ] **BK-018** — Preparação da apresentação para defesa (slides) `[docs]`
- [ ] **BK-019** — Deploy do protótipo para demonstração na defesa (Railway ou Render) `[infra]`
- [ ] **BK-020** — Revisão do texto completo com orientador `[docs]`

---

## Estrutura de Pastas

```
sentineledu/
├── AI_PROJECT_PROTOCOL.md
├── README.md
├── project/
│   ├── PROJECT_CONTEXT.md
│   └── STATUS.md
│
├── docs/
│   ├── decisions/
│   │   ├── ADR-0001.md          ← Escolha do Random Forest como modelo principal
│   │   ├── ADR-0002.md          ← SHAP vs. LIME para explicabilidade
│   │   └── ADR-0003.md          ← Dataset sintético vs. dados reais anonimizados
│   ├── business/
│   │   ├── risk-classification.md  ← Critérios de classificação de risco (alto/médio/baixo)
│   │   └── feature-definitions.md  ← Definição de cada feature do modelo
│   ├── brainstorms/
│   │   └── 2026-03-15-feature-engineering.md
│   └── backlog.md
│
├── research/                    ← Notebooks Jupyter (exploração e experimentação)
│   ├── 01-eda.ipynb             ← Análise exploratória
│   ├── 02-feature-engineering.ipynb
│   ├── 03-model-comparison.ipynb
│   └── 04-shap-analysis.ipynb
│
├── data/
│   ├── raw/
│   │   └── synthetic_dataset.csv    ← Dataset sintético gerado
│   ├── processed/               ← Dados após pré-processamento (gitignored)
│   └── generator/
│       └── generate_dataset.py  ← Script de geração do dataset sintético
│
├── backend/                     ← FastAPI
│   ├── app/
│   │   ├── main.py
│   │   ├── api/
│   │   │   ├── predictions.py
│   │   │   ├── students.py
│   │   │   └── reports.py
│   │   ├── ml/
│   │   │   ├── model.py         ← Carregamento e predição
│   │   │   ├── preprocessor.py  ← Pré-processamento de dados
│   │   │   └── explainer.py     ← SHAP values
│   │   ├── db/
│   │   │   ├── models.py        ← SQLAlchemy models
│   │   │   └── migrations/
│   │   └── schemas/             ← Pydantic schemas
│   ├── models/
│   │   └── random_forest_v1.pkl ← Modelo serializado
│   ├── tests/
│   │   ├── test_predictions.py
│   │   ├── test_preprocessor.py
│   │   └── test_api.py
│   └── requirements.txt
│
├── frontend/                    ← React + Vite
│   └── src/
│       ├── pages/
│       │   ├── Dashboard.tsx    ← Lista de alunos com risco
│       │   ├── StudentDetail.tsx ← Página do aluno com SHAP
│       │   └── Login.tsx
│       ├── components/
│       │   ├── RiskBadge.tsx
│       │   └── ShapChart.tsx    ← Gráfico de barras SHAP
│       └── services/
│           └── api.ts
│
└── docker-compose.yml           ← PostgreSQL + FastAPI + Vite para dev
```

### Decisões técnicas registradas

| Decisão | Escolha | Motivo |
|---------|---------|--------|
| Modelo principal | Random Forest | Melhor F1-score nos experimentos; interpretável com SHAP |
| Explicabilidade | SHAP (TreeExplainer) | Método mais robusto e com suporte nativo ao Random Forest |
| Dataset | Sintético gerado com `faker` + distribuições realistas | LGPD + regulamento institucional impedem dados reais |
| Backend | FastAPI + Python | Stack natural para ML; documentação automática (OpenAPI) |
| Frontend | React + Vite | SPA simples; sem necessidade de SSR para protótipo |

### Cronograma de entregáveis

```
Fev 2026  │ Proposta ✓
Mar-Abr   │ Revisão bibliográfica + EDA + Feature engineering ✓
Mai       │ Treinamento e comparação de modelos ✓
Jun-Jul   │ API + Frontend (em andamento) ◄
Ago       │ Protótipo funcional completo
Set-Out   │ Texto do TCC
Nov       │ Defesa
```

### Riscos ativos

| Risco | Probabilidade | Impacto | Mitigação |
|-------|-------------|--------|----------|
| Dataset sintético não representativo — banca questiona validade | Média | Alto | Documentar metodologia de geração baseada em literatura; validar com orientador |
| F1-score abaixo de 0.75 com dados sintéticos | Baixa | Alto | Fallback: ajustar hiperparâmetros; usar ensemble; justificar na metodologia |
| Prazo da escrita do TCC subestimado | Alta | Alto | Começar rascunho dos capítulos teóricos durante o desenvolvimento |
| Deploy do protótipo falhar na semana da defesa | Baixa | Médio | Manter versão local funcional como fallback; fazer demo gravada como backup |
