# Skill: Database Specialist

> Especialista em modelagem de dados, queries, migrations e performance de banco de dados.
> Ativado quando a tarefa envolve schema, queries, índices, migrations ou integridade de dados.

---

## Objetivo

Garantir que os dados do sistema sejam armazenados de forma correta, consistente, segura e com performance adequada — com schema evolutivo e rastreável.

---

## Quando Utilizar

- Ao criar ou modificar o schema do banco de dados.
- Ao escrever ou otimizar queries complexas.
- Ao criar migrations (adição, remoção ou alteração de tabelas/colunas).
- Ao definir índices para padrões de acesso.
- Ao implementar relacionamentos entre entidades.
- Ao avaliar impacto de uma mudança em dados existentes.
- Ao investigar problemas de performance relacionados ao banco.
- Ao projetar estratégias de backup, particionamento ou archiving.

---

## Responsabilidades

- Projetar schema normalizado e adequado ao domínio do negócio.
- Criar migrations seguras, reversíveis e sem downtime quando possível.
- Definir índices baseados nos padrões de acesso reais (não hipotéticos).
- Garantir integridade referencial com constraints adequadas.
- Garantir que dados sensíveis estão protegidos (criptografados, mascarados ou com acesso controlado).
- Documentar o modelo de dados em `docs/` quando o schema não é autoexplicativo.
- Verificar queries com `EXPLAIN`/`EXPLAIN ANALYZE` antes de ir a produção.
- Garantir que migrations podem ser revertidas (down migration).

---

## Checklist

### Schema e Modelagem
- [ ] Entidades têm nomes no plural e em snake_case (ou conforme convenção do projeto)
- [ ] Chaves primárias definidas em todas as tabelas
- [ ] Chaves estrangeiras com constraint explícita (FK)
- [ ] Colunas NOT NULL onde o dado é obrigatório
- [ ] Tipos de dados adequados ao conteúdo (não `VARCHAR(255)` para tudo)
- [ ] Valores default definidos onde fazem sentido
- [ ] Sem redundância de dados sem justificativa documentada (normalização)

### Migrations
- [ ] Migration tem up e down implementados
- [ ] Migration é testada em banco de desenvolvimento antes de aplicar
- [ ] Migration não bloqueia tabelas em produção por tempo indeterminado
- [ ] Dados existentes são migrados corretamente (se aplicável)
- [ ] Migration é reversível sem perda de dados (ou perda documentada e aceita)
- [ ] Nome do arquivo segue convenção do projeto com timestamp

### Índices e Performance
- [ ] Colunas usadas em WHERE, JOIN e ORDER BY têm índice avaliado
- [ ] Índices compostos ordenados da coluna mais seletiva para menos seletiva
- [ ] Sem índices duplicados ou desnecessários
- [ ] Queries críticas analisadas com `EXPLAIN` / `EXPLAIN ANALYZE`
- [ ] Sem query N+1 nos fluxos de leitura

### Integridade e Segurança
- [ ] Constraints de unicidade onde necessário (UNIQUE)
- [ ] Constraints de check onde regras de negócio se aplicam
- [ ] Dados sensíveis identificados e com proteção adequada
- [ ] Acesso ao banco segue princípio do menor privilégio
- [ ] Sem queries construídas por concatenação de strings

---

## Perguntas Obrigatórias

Antes de criar ou modificar schema/queries:

1. **Qual é o volume esperado de dados?** Quantos registros hoje? Em 1 ano?
2. **Quais são os padrões de acesso?** O que é lido com mais frequência? O que é escrito?
3. **Há dados que não podem ser deletados?** Soft delete ou hard delete?
4. **Dados sensíveis estão envolvidos?** Como serão protegidos?
5. **Esta migration pode rodar sem downtime?** Qual é o impacto em produção?
6. **A migration é reversível?** O que acontece se precisar fazer rollback?
7. **Há dados existentes que precisam ser transformados?** Qual é a estratégia de backfill?
8. **Qual é a estratégia de backup para estes dados?** Com que frequência? Quanto tempo de retenção?

---

## Critérios de Validação

O trabalho do Database Specialist está completo quando:

- Schema reflete o modelo de domínio sem redundância não justificada.
- Todas as migrations têm up e down implementados e testados.
- Queries críticas foram analisadas com `EXPLAIN` e estão dentro dos SLOs de `standards/performance.md`.
- Constraints garantem integridade dos dados no nível do banco.
- Dados sensíveis têm proteção adequada definida.
- Nenhuma query é construída por concatenação de strings.
- Migration pode ser aplicada em produção sem downtime inesperado (ou downtime documentado e aceito).
- Índices existem para os padrões de acesso identificados.
