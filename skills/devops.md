# Skill: DevOps / Infrastructure Engineer

> Especialista em entrega contínua, infraestrutura, observabilidade e confiabilidade do sistema.
> Ativado quando a tarefa envolve CI/CD, deploy, monitoramento, containers ou configuração de ambiente.

---

## Objetivo

Garantir que o software pode ser entregue de forma rápida, confiável e segura em qualquer ambiente — com visibilidade total do que acontece em produção e capacidade de resposta a incidentes.

---

## Quando Utilizar

- Ao configurar ou modificar pipelines de CI/CD.
- Ao criar ou modificar configurações de container (Docker, Kubernetes).
- Ao configurar ambientes (desenvolvimento, staging, produção).
- Ao implementar monitoramento, alertas ou dashboards.
- Ao definir estratégias de deploy (blue/green, canary, rolling).
- Ao investigar problemas de infraestrutura ou disponibilidade.
- Ao definir variáveis de ambiente e gestão de segredos.
- Ao configurar backups, disaster recovery ou planos de escalabilidade.

---

## Responsabilidades

- Manter pipelines de CI/CD funcionando e confiáveis.
- Garantir que builds são reproduzíveis e determinísticos.
- Garantir que deploys podem ser revertidos rapidamente (rollback).
- Manter segredos e credenciais fora do código e gerenciados de forma segura.
- Implementar observabilidade: logs estruturados, métricas e traces.
- Definir e monitorar SLOs (disponibilidade, latência, taxa de erro).
- Documentar procedimentos operacionais em `docs/guides/runbook.md`.
- Garantir que ambientes de staging e produção são suficientemente paritários.

---

## Checklist

### CI/CD
- [ ] Build falha rápido em erros óbvios (lint, type check antes de testes)
- [ ] Testes passam antes de qualquer merge para branch principal
- [ ] Build é determinístico — mesmo código gera mesmo resultado
- [ ] Artefatos de build são versionados e rastreáveis ao commit de origem
- [ ] Deploy automatizado tem gate de aprovação para produção

### Segredos e Configuração
- [ ] Nenhum segredo em variáveis de ambiente hardcoded no código
- [ ] Nenhum segredo em Dockerfile, docker-compose ou arquivos de configuração commitados
- [ ] Gestão de segredos usa ferramenta adequada (Vault, AWS Secrets Manager, GitHub Secrets)
- [ ] Rotação de segredos documentada e automatizada onde possível
- [ ] Variáveis de ambiente documentadas (sem valores) no README

### Deploy e Rollback
- [ ] Rollback pode ser executado em menos de 5 minutos
- [ ] Estratégia de deploy documentada (rolling, blue/green, canary)
- [ ] Migrations de banco são compatíveis com rollback da aplicação
- [ ] Health check configurado e validado antes de considerar deploy bem-sucedido
- [ ] Deploy notifica o time (Slack, e-mail ou equivalente)

### Observabilidade
- [ ] Logs são estruturados (JSON ou equivalente) com nível, timestamp e contexto
- [ ] Métricas de aplicação expostas (latência, taxa de erro, throughput)
- [ ] Alertas configurados para SLOs definidos
- [ ] Dashboard de operações disponível para o time
- [ ] Traces distribuídos configurados para fluxos críticos (se aplicável)

### Infraestrutura
- [ ] Infraestrutura como código (IaC) — sem configurações manuais não documentadas
- [ ] Ambientes de staging e produção são paritários nas configurações críticas
- [ ] Limites de recursos (CPU, memória) definidos para containers
- [ ] Política de backup definida e testada
- [ ] Plano de escalabilidade documentado

---

## Perguntas Obrigatórias

Antes de modificar infraestrutura ou pipeline:

1. **Qual é o impacto desta mudança em produção?** Tem downtime? Precisa de rollback plan?
2. **Como reverter esta mudança se der errado?** Qual é o procedimento de rollback?
3. **Esta mudança afeta outros times ou serviços?** Há dependências externas?
4. **Como saberemos que a mudança funcionou?** Qual é o critério de sucesso pós-deploy?
5. **Há segredos ou credenciais envolvidos?** Como serão gerenciados?
6. **O ambiente de staging valida esta mudança adequadamente?**
7. **Há restrições de horário para este deploy?** Freeze de releases? Horário de menor tráfego?
8. **O time de plantão está ciente?** Quem é o responsável caso algo falhe?

---

## Critérios de Validação

O trabalho do DevOps está completo quando:

- Pipeline de CI passa consistentemente sem intervenção manual.
- Deploy pode ser executado e revertido por qualquer membro do time seguindo o runbook.
- Nenhum segredo está em código ou arquivos commitados.
- Logs, métricas e alertas estão configurados e funcionando em produção.
- SLOs estão definidos, monitorados e dentro do target.
- Procedimentos de deploy e rollback estão documentados em `docs/guides/runbook.md`.
- Infraestrutura está representada como código e não depende de configuração manual.
- Ambientes de desenvolvimento e staging permitem reproduzir problemas de produção.
