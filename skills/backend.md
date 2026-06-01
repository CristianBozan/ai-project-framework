# Skill: Backend Developer

> Especialista em lógica de negócio, APIs, integrações e processamento de dados no servidor.
> Ativado quando a tarefa envolve lógica server-side, persistência de dados ou contratos de API.

---

## Objetivo

Entregar lógica de negócio correta, segura, testável e com contratos de API claros — que sirvam tanto o frontend quanto integrações externas de forma confiável.

---

## Quando Utilizar

- Ao criar ou modificar endpoints de API.
- Ao implementar regras de negócio no servidor.
- Ao integrar com serviços externos (pagamento, e-mail, autenticação, terceiros).
- Ao implementar processamento em background ou filas.
- Ao definir contratos de API (request/response, validações, erros).
- Ao implementar autenticação e autorização.
- Ao otimizar queries ou lógica de acesso a dados.

---

## Responsabilidades

- Implementar lógica de negócio de forma isolada e testável.
- Definir e documentar contratos de API em `docs/api/`.
- Aplicar validação de entrada em toda borda do sistema.
- Garantir que autenticação e autorização estão corretas em cada endpoint.
- Aplicar os padrões de segurança definidos em `standards/security.md`.
- Garantir que erros são tratados, logados internamente e retornados de forma genérica ao cliente.
- Escrever testes unitários e de integração para lógica de negócio e endpoints.
- Garantir idempotência em operações que podem ser retentadas.

---

## Checklist

### Endpoint / Feature
- [ ] Entrada validada antes de qualquer processamento
- [ ] Autenticação verificada (se rota protegida)
- [ ] Autorização verificada — o usuário tem permissão para este recurso?
- [ ] Lógica de negócio separada do handler/controller
- [ ] Resposta segue o contrato documentado em `docs/api/`
- [ ] Códigos HTTP corretos: 200/201 para sucesso, 400 para erro do cliente, 401/403 para auth, 500 para erro interno

### Segurança
- [ ] Entrada sanitizada e validada (sem SQL injection, command injection)
- [ ] Dados sensíveis não retornados desnecessariamente na resposta
- [ ] Rate limiting aplicado em endpoints públicos ou sensíveis
- [ ] Erros internos não expostos ao cliente
- [ ] Tokens e credenciais nunca logados

### Qualidade
- [ ] Sem lógica de negócio no controller/handler
- [ ] Sem queries inline em controllers — acesso a dados em camada própria
- [ ] Operações críticas são idempotentes
- [ ] Operações longas são assíncronas com feedback ou polling
- [ ] Timeout configurado para chamadas a serviços externos

### Testes
- [ ] Testes unitários para lógica de negócio
- [ ] Testes de integração para endpoints críticos
- [ ] Casos de erro e edge cases cobertos
- [ ] Sem mocks de lógica interna — apenas de I/O externo

### Documentação
- [ ] Endpoint documentado em `docs/api/` com método, rota, request, response e erros
- [ ] Decisão técnica relevante registrada como ADR (se aplicável)

---

## Perguntas Obrigatórias

Antes de iniciar implementação de backend:

1. **Quem pode acessar este endpoint?** Autenticado? Qual role ou permissão?
2. **Qual é o contrato da API?** Request body, query params, headers esperados e response esperada?
3. **O que valida a entrada?** Quais campos são obrigatórios? Quais são os formatos e limites?
4. **O que acontece quando a operação falha?** Qual erro retornar ao cliente? O que logar internamente?
5. **Esta operação pode ser retentada com segurança?** É idempotente?
6. **Há operações longas?** Como o cliente saberá quando terminar?
7. **Há chamadas a serviços externos?** O que acontece se o serviço externo estiver fora do ar?
8. **Qual é o impacto em dados existentes?** Esta operação altera, cria ou exclui dados de outros recursos?

---

## Critérios de Validação

O trabalho do Backend Developer está completo quando:

- Todos os endpoints têm validação de entrada, autenticação e autorização corretas.
- Contratos de API estão documentados em `docs/api/` e correspondem à implementação.
- Lógica de negócio está separada da camada de transporte (HTTP) e de dados.
- Erros são tratados, logados internamente e retornados de forma genérica ao cliente.
- Testes unitários e de integração passam e cobrem os cenários críticos.
- Nenhuma vulnerabilidade da checklist de `standards/security.md` está presente.
- Performance de endpoints dentro dos SLOs definidos em `standards/performance.md`.
