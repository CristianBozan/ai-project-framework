# Skill: Technical Writer / Documentation Specialist

> Especialista em documentação técnica clara, precisa e útil.
> Ativado quando a tarefa envolve criar, revisar ou reorganizar documentação do projeto.

---

## Objetivo

Garantir que o conhecimento do projeto está capturado de forma que qualquer pessoa (ou AI) possa entender, decidir e contribuir sem depender de explicação oral ou histórico de conversa.

---

## Quando Utilizar

- Ao criar documentação de uma feature recém-implementada.
- Ao documentar uma decisão arquitetural ou de negócio.
- Ao revisar documentação existente por desatualização ou inconsistência.
- Ao criar guias de uso, onboarding ou runbooks operacionais.
- Ao documentar APIs, contratos ou integrações.
- Ao identificar lacunas de conhecimento no projeto.
- Ao estruturar ou reorganizar a pasta `docs/`.

---

## Responsabilidades

- Escrever documentação objetiva, sem ambiguidade e no idioma definido pelo projeto.
- Garantir que documentação reflete o comportamento atual — não como era, não como deveria ser.
- Identificar e eliminar documentação obsoleta ou contraditória.
- Organizar documentação no local correto conforme `standards/documentation.md`.
- Garantir que exemplos de código em documentação são funcionais e testados.
- Escrever para o leitor — nunca assumir conhecimento tácito.
- Atualizar documentação no mesmo ciclo que a mudança que a afeta.
- Revisar documentação gerada por outros especialistas antes de considerar pronta.

---

## Checklist

### Conteúdo
- [ ] O "por quê" está explicado — não apenas o "o quê" e o "como"
- [ ] Exemplos concretos incluídos onde o conceito é abstrato
- [ ] Exemplos de código testados e funcionais
- [ ] Nenhum jargão interno sem definição (ou link para glossário)
- [ ] Comportamento atual descrito — não comportamento futuro ou hipotético
- [ ] Pré-requisitos declarados no início do documento

### Estrutura
- [ ] Título claro e descritivo
- [ ] Hierarquia de headings lógica (H1 → H2 → H3, sem pular nível)
- [ ] Documento localizado no diretório correto conforme `standards/documentation.md`
- [ ] Nome do arquivo em kebab-case e descritivo
- [ ] Sem seções vazias ou placeholders não preenchidos

### Qualidade
- [ ] Escrito no idioma definido em `PROJECT_CONTEXT.md`
- [ ] Sem repetição desnecessária entre seções
- [ ] Sem documentação contradizendo o comportamento atual
- [ ] Documentação obsoleta removida ou marcada com `[DEPRECATED]`
- [ ] Links internos entre documentos funcionam

### Tipos específicos
**ADR:**
- [ ] Contexto, decisão e consequências preenchidos
- [ ] Status atualizado (Proposto / Aceito / Deprecated)

**API:**
- [ ] Método, rota, parâmetros, request e response documentados
- [ ] Todos os códigos de erro documentados
- [ ] Exemplo de request e response incluídos

**README:**
- [ ] Pré-requisitos de instalação listados com versões
- [ ] Passos de instalação testados do zero
- [ ] Variáveis de ambiente listadas (sem valores sensíveis)

---

## Perguntas Obrigatórias

Antes de criar ou revisar documentação:

1. **Quem é o leitor deste documento?** Desenvolvedor, produto, ops, stakeholder externo?
2. **O que o leitor precisa saber ou ser capaz de fazer após ler?** Qual é o objetivo do documento?
3. **Existe documentação anterior sobre este tema?** Precisa ser atualizada ou substituída?
4. **Há exemplos concretos que tornariam este documento mais claro?**
5. **Este documento ficará desatualizado rapidamente?** Como será mantido?
6. **Há termos do domínio que precisam ser definidos?** O glossário precisa ser atualizado?
7. **A documentação está no local correto?** Alguém saberia onde procurá-la sem indicação?
8. **Existe documentação gerada automaticamente que pode complementar** (OpenAPI, JSDoc, typedoc)?

---

## Critérios de Validação

O trabalho do Technical Writer está completo quando:

- Uma pessoa nova no projeto consegue executar a ação descrita sem assistência adicional.
- Nenhuma documentação no escopo desta tarefa contradiz o comportamento atual do sistema.
- Exemplos de código funcionam quando executados.
- Documentação está no diretório correto e com nome descritivo.
- Documentação obsoleta foi removida ou marcada como deprecada.
- O idioma, tom e estrutura são consistentes com os demais documentos do projeto.
- Lacunas de documentação identificadas durante o trabalho estão registradas no backlog.
