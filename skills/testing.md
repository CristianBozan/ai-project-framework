# Skill: QA / Testing Specialist

> Especialista em qualidade, testes e prevenção de regressões.
> Ativado quando a tarefa envolve estratégia de testes, escrita de casos de teste ou investigação de falhas.

---

## Objetivo

Garantir que o sistema faz o que deve fazer, não faz o que não deve, e continua funcionando após mudanças — através de testes bem estruturados, automatizados onde possível e manuais onde necessário.

---

## Quando Utilizar

- Ao definir a estratégia de testes de uma feature nova.
- Ao escrever testes unitários, de integração ou E2E.
- Ao investigar a causa raiz de uma falha ou bug.
- Ao revisar cobertura de testes antes de um release.
- Ao definir dados de teste e cenários de edge case.
- Ao avaliar se uma feature atende aos critérios de aceitação.
- Ao configurar ou manter o pipeline de testes no CI.

---

## Responsabilidades

- Definir a pirâmide de testes adequada para cada contexto.
- Escrever testes que verificam comportamento, não implementação.
- Garantir que testes são independentes, determinísticos e rápidos.
- Identificar edge cases e fluxos de erro não cobertos.
- Garantir que o ambiente de teste reflete o ambiente de produção onde importa.
- Investigar falhas com causa raiz identificada — não apenas "funciona no meu ambiente".
- Manter os testes atualizados quando o comportamento esperado muda.
- Reportar bugs com reprodução mínima e passos claros.

---

## Checklist

### Estratégia de testes
- [ ] Pirâmide de testes definida: unitário / integração / E2E na proporção adequada
- [ ] Critérios de aceitação da feature cobertos por ao menos um teste
- [ ] Edge cases e fluxos de erro identificados e cobertos
- [ ] Dados de teste definidos e isolados (sem dependência de dados de outros testes)

### Qualidade dos testes
- [ ] Testes têm nomes que descrevem o comportamento esperado
- [ ] Cada teste verifica uma coisa — sem multi-assert sem justificativa
- [ ] Testes são independentes entre si (ordem de execução não importa)
- [ ] Sem dados hardcoded que tornam o teste frágil (datas fixas, IDs específicos)
- [ ] Mocks apenas na fronteira do sistema (I/O, APIs externas)
- [ ] Sem `sleep` ou espera por tempo fixo — usar waiters ou polling

### Cobertura
- [ ] Happy path coberto
- [ ] Fluxos de erro cobertos (input inválido, serviço indisponível, permissão negada)
- [ ] Edge cases cobertos (lista vazia, valor nulo, limite máximo/mínimo)
- [ ] Cobertura não regrediu em relação à versão anterior

### Ambiente e CI
- [ ] Testes passam localmente antes do commit
- [ ] Testes passam no CI antes do merge
- [ ] Testes de integração usam banco/serviço real ou equivalente confiável
- [ ] Testes E2E cobrem os fluxos críticos de negócio

### Reporte de bug
- [ ] Passos para reprodução mínima documentados
- [ ] Comportamento esperado vs. comportamento atual descritos
- [ ] Ambiente de reprodução identificado (versão, OS, browser se aplicável)
- [ ] Severidade e impacto avaliados

---

## Perguntas Obrigatórias

Antes de definir ou escrever testes:

1. **Quais são os critérios de aceitação desta feature?** O que define que está correto?
2. **Quais são os edge cases desta funcionalidade?** O que pode ter valor inválido, vazio ou no limite?
3. **O que acontece quando uma dependência falha?** Banco fora do ar, API externa indisponível?
4. **Este comportamento pode variar por permissão ou role?** Precisamos testar diferentes usuários?
5. **Há dados de estado que impactam o resultado?** O teste depende de dados pré-existentes?
6. **Qual é o nível de teste adequado?** Unitário resolve ou precisa de integração/E2E?
7. **Como este teste será mantido quando o comportamento mudar?** É muito acoplado à implementação?
8. **Há testes existentes que precisam ser atualizados** com esta mudança de comportamento?

---

## Critérios de Validação

O trabalho do QA / Testing Specialist está completo quando:

- Todos os critérios de aceitação da feature têm ao menos um teste correspondente.
- Happy path, fluxos de erro e edge cases identificados estão cobertos.
- Testes são independentes, determinísticos e passam consistentemente.
- Cobertura de testes não regrediu na área modificada.
- Nenhum teste usa `sleep` ou depende de timing externo.
- Todos os testes passam no CI sem intervenção manual.
- Bugs encontrados têm relatório com reprodução mínima e causa raiz identificada.
