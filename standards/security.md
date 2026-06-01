# Standard: Segurança

> Padrão universal de segurança aplicável a qualquer projeto que adote este framework.
> Todo código produzido deve ser verificado contra este padrão antes de ser considerado pronto.

---

## Objetivo

Garantir que o projeto não introduza vulnerabilidades conhecidas, proteja dados sensíveis, respeite o princípio do menor privilégio e esteja preparado para auditorias de segurança.

---

## Critérios Obrigatórios

### Autenticação e Autorização
- Toda rota ou recurso protegido deve verificar autenticação antes de processar a requisição.
- Autorização deve ser verificada no servidor — nunca apenas no cliente.
- Tokens e credenciais nunca são expostos em logs, respostas de erro ou URLs.
- Senhas nunca são armazenadas em texto plano — somente com hash seguro (bcrypt, argon2 ou equivalente).
- Sessões expiram após inatividade e após logout.

### Entrada de Dados
- Toda entrada proveniente do usuário, de APIs externas ou de arquivos é tratada como não confiável.
- Nunca construir queries SQL por concatenação de strings — usar prepared statements ou ORM.
- Nunca construir comandos shell a partir de input do usuário — evitar `exec`, `eval` e equivalentes.
- HTML gerado a partir de dados do usuário é sempre escapado (prevenção de XSS).
- Upload de arquivos valida tipo MIME no servidor, não apenas a extensão.

### Dados Sensíveis
- Credenciais, chaves de API e segredos nunca são commitados no repositório.
- Variáveis de ambiente são usadas para toda configuração sensível.
- `.env` e arquivos equivalentes estão no `.gitignore`.
- Dados pessoais (PII) são minimizados — coletar apenas o necessário.
- Comunicação com dados sensíveis ocorre exclusivamente via HTTPS/TLS.

### Dependências
- Dependências de terceiros são verificadas contra vulnerabilidades conhecidas antes de serem adicionadas.
- Versões de dependências são fixadas (lockfile) para garantir reprodutibilidade.
- Dependências não utilizadas são removidas.

### Tratamento de Erros
- Mensagens de erro exibidas ao usuário nunca expõem stack traces, queries ou estrutura interna.
- Erros são logados internamente com detalhe, mas retornados ao cliente de forma genérica.

---

## Checklist

Use antes de considerar qualquer feature ou PR como pronto.

### Autenticação e Autorização
- [ ] Todas as rotas protegidas verificam autenticação
- [ ] Autorização é validada no servidor
- [ ] Tokens não aparecem em logs ou URLs
- [ ] Senhas usam hash seguro
- [ ] Sessões têm expiração configurada

### Entrada de Dados
- [ ] Nenhuma query SQL é construída por concatenação
- [ ] Nenhum comando shell é construído a partir de input do usuário
- [ ] Output HTML é escapado antes de renderizar
- [ ] Upload de arquivo valida tipo MIME no servidor
- [ ] Toda entrada externa é validada e sanitizada

### Dados Sensíveis
- [ ] Nenhuma credencial no repositório
- [ ] Variáveis de ambiente usadas para segredos
- [ ] `.env` no `.gitignore`
- [ ] Comunicação sensível usa HTTPS/TLS
- [ ] PII minimizado

### Dependências
- [ ] Novas dependências verificadas contra CVEs conhecidos
- [ ] Lockfile atualizado e commitado
- [ ] Dependências não utilizadas removidas

### Erros
- [ ] Mensagens de erro ao usuário são genéricas
- [ ] Detalhes de erro logados internamente

---

## Critérios Mínimos Aceitáveis

Um código é considerado aceitável para produção quando:

- Nenhuma das vulnerabilidades OWASP Top 10 está presente.
- Nenhuma credencial está exposta no código ou histórico git.
- Toda entrada do usuário é validada antes de uso.
- Autenticação e autorização estão implementadas e funcionando.
- Erros não expõem informação interna ao cliente.

---

## Critérios Recomendados

Práticas que elevam a maturidade de segurança do projeto:

- Implementar rate limiting em endpoints públicos e de autenticação.
- Adotar política de Content Security Policy (CSP) em aplicações web.
- Implementar auditoria de ações sensíveis (logs de acesso, criação, exclusão).
- Realizar análise estática de segurança (SAST) no pipeline de CI.
- Verificar dependências automaticamente a cada build (ex: `npm audit`, `pip-audit`, `trivy`).
- Implementar rotação periódica de segredos e tokens.
- Adotar autenticação multifator (MFA) para acesso a sistemas críticos.
- Documentar o modelo de ameaças do sistema em `docs/security/threat-model.md`.
