# my-fullstack-developer

> Um template que eu criei pra servir como base dos meus projetos fullstack.
> A ideia é ter tudo organizado desde o começo: arquitetura, documentação, padrões, workflows e integração com IA.

---

# Sobre o projeto

Esse repositório não é uma aplicação pronta.

Ele funciona como uma estrutura base pra iniciar projetos de forma mais profissional, organizada e escalável, tanto pra trabalho quanto pra estudo.

A proposta aqui é simples:

- evitar começar projeto do zero toda vez
- manter padrão entre diferentes stacks
- facilitar onboarding
- deixar os agentes de IA realmente úteis dentro do projeto
- documentar as decisões importantes
- acelerar desenvolvimento sem virar bagunça

A ideia é que qualquer pessoa (ou IA) consiga entrar no projeto, entender tudo rápido e começar a trabalhar sem ficar perdida.

---

# Objetivos

| Objetivo | Descrição |
|---|---|
| Organização | Estrutura padronizada desde o início |
| Escalabilidade | Base pensada pra crescer sem virar caos |
| DX | Melhor experiência possível pra desenvolvimento |
| IA-first | Projeto preparado pra trabalhar junto com IA |
| Velocidade | Menos tempo configurando e mais tempo construindo |
| Qualidade | Padrões mais profissionais desde o primeiro commit |

---

# Filosofia do repositório

Algumas coisas que eu considero essenciais:

- documentação não é opcional
- padrão explícito é melhor do que convenção escondida
- IA deve agir como parte do time
- segurança não é feature extra
- pequenas evoluções são melhores que refatorações gigantes
- código precisa ser legível antes de ser “inteligente”

---

# Estrutura do projeto

```bash
my-fullstack-developer/
│
├── README.md
├── CLAUDE.md
├── AGENTS.md
│
├── .claude/
│   ├── CLAUDE.md
│   ├── settings.json
│   ├── commands/
│   ├── skills/
│   └── rules/
│
├── docs/
│   ├── product/
│   ├── architecture/
│   ├── conventions/
│   ├── workflows/
│   ├── security/
│   ├── deployment/
│   ├── database/
│   ├── api/
│   ├── frontend/
│   ├── backend/
│   ├── ai/
│   └── adr/
│
├── templates/
├── scripts/
└── .github/
    └── workflows/
```

---

# Como eu uso isso

## Quando vou iniciar um projeto novo

1. Clono esse template
2. Renomeio o projeto
3. Ajusto o README
4. Leio os arquivos principais (`CLAUDE.md` e `AGENTS.md`)
5. Defino a stack do projeto
6. Adapto a documentação inicial
7. Começo a desenvolver usando os comandos e workflows

---

## Quando vou usar em um projeto existente

Se o projeto já existe e você quer plugar esse template nele, o fluxo é diferente.

O agente não conhece o código — então mandar ele trabalhar direto vai gerar resultados genéricos e inconsistentes com o que já está feito.

**O que você precisa copiar para o projeto existente:**

```bash
# Copie esses arquivos/pastas para a raiz do seu projeto
.claude/          # commands, skills e rules
CLAUDE.md         # regras de comportamento
AGENTS.md         # guia de onboarding para agentes
```

Nada do código da aplicação é alterado. São apenas arquivos de contexto e configuração.

**Depois, siga essas 3 etapas:**

**Etapa 1 — Mapear o código existente**

Rode o comando abaixo na raiz do projeto existente:

```
/analyze-codebase

Diretório raiz: .
Foco: geral
Objetivo: onboarding
```

O agente vai varrer o código, identificar a stack, arquitetura, módulos e padrões já em uso, e gerar um documento em `docs/architecture/overview.md`. **Ele não altera nada** — só documenta o que encontrou.

**Etapa 2 — Revisar e completar o contexto**

Com a análise feita, complete ou ajuste estes arquivos para refletir o projeto real:

| Arquivo | O que colocar |
|---|---|
| `README.md` | Descrição real do projeto |
| `docs/product/vision.md` | O que o sistema faz e para quem |
| `docs/architecture/overview.md` | Arquitetura real identificada |
| `.env.example` | Todas as variáveis de ambiente necessárias |
| `AGENTS.md` | Particularidades e contexto do seu projeto |

**Etapa 3 — Usar normalmente**

A partir daí, os comandos funcionam com contexto. Em cada sessão nova o agente lê os arquivos de contexto automaticamente e já sabe onde está, qual é a stack e quais padrões seguir.

```
# Criar uma nova feature
/create-feature

# Corrigir um bug
/fix-bug

# Criar um endpoint
/create-endpoint
```

> O passo de análise é feito uma vez. Nas sessões seguintes, o agente lê a documentação gerada — não o código inteiro — o que é muito mais rápido.

---

## Quando vou estudar alguma stack

Eu também uso isso pra estudo.

Exemplo:
- Laravel
- NestJS
- Next.js
- Docker
- arquitetura
- DevOps
- microsserviços

A vantagem é que eu mantenho o mesmo padrão em tudo.

---

# Como os agentes de IA devem trabalhar

Todo agente de IA que usar esse projeto deve:

1. Ler a documentação antes de sair criando código
2. Entender a stack atual
3. Seguir as regras da pasta `.claude/rules`
4. Planejar antes de alterar qualquer coisa
5. Trabalhar em pequenas etapas
6. Validar tudo antes de finalizar
7. Atualizar documentação quando necessário
8. Explicar claramente o que foi feito

A ideia aqui não é usar IA como autocomplete.
É usar IA como um desenvolvedor colaborando dentro do projeto.

---

# Comandos disponíveis

Os comandos ficam em `.claude/commands`.

Alguns exemplos:

| Comando | O que faz |
|---|---|
| `/init-project` | Inicializa um novo projeto |
| `/create-feature` | Cria uma feature completa |
| `/fix-bug` | Workflow de correção de bugs |
| `/review-code` | Revisão de código |
| `/create-endpoint` | Cria endpoint REST |
| `/create-page` | Cria página frontend |
| `/create-tests` | Cria testes |
| `/refactor` | Refatoração estruturada |
| `/security-audit` | Auditoria de segurança |
| `/deploy-checklist` | Checklist de deploy |
| `/dockerize-project` | Dockerização do projeto |
| `/production-debug` | Debug em produção |
| `/performance-review` | Revisão de performance |
| `/git-commit` | git add + commit com mensagem Conventional Commits + push |

---

# Skills disponíveis

As skills ficam em:

```bash
.claude/skills/
```

Cada uma é especializada em uma área específica.

Exemplos:

- backend-architecture
- frontend-architecture
- laravel-development
- nextjs-development
- node-development
- docker-devops
- database-design
- api-design
- testing-strategy
- security-review
- performance-optimization
- ai-agent-orchestration

---

# Convenções rápidas

## Código

- tudo relacionado a código fica em inglês
- documentação e explicações em PT-BR
- commits usando Conventional Commits
- branches padronizadas

---

## Qualidade

Algumas regras que eu sigo:

- código precisa ser legível
- evitar duplicação
- SOLID sempre que fizer sentido
- segurança desde o início
- documentação acompanhando evolução do projeto

---

# Sobre a pasta `/adr`

A pasta:

```bash
docs/adr/
```

serve pra armazenar os **Architecture Decision Records**.

Basicamente:
toda decisão técnica importante fica documentada ali.

Exemplos:

- por que escolhi PostgreSQL ao invés de MySQL
- por que usei monorepo
- por que escolhi Next.js
- por que decidi usar filas
- por que alterei arquitetura

Isso ajuda MUITO no futuro, principalmente em projetos grandes.

---

# Contribuição

Se alguém quiser melhorar a estrutura:

1. cria uma branch
2. faz as alterações
3. documenta mudanças importantes
4. abre PR

---

# Licença

Pode usar em projetos pessoais ou profissionais.

A ideia é justamente evoluir isso ao longo do tempo.

---

Desenvolvido por Gabriel Muller 🚀