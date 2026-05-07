# AI Prompts Repository

[English](#-en-us) | [Português](#-pt-br)

---

# EN-US

## Overview

Central repository for **versioned, reusable, and production-grade prompts** used to orchestrate LLM-based agents.

This project treats prompts as **first-class engineering artifacts**:

* versioned
* testable
* modular
* reusable across systems

---

## Philosophy

Prompts are not text.
They are:

> **deterministic execution interfaces for AI agents**

This repository enforces:

* structure over improvisation
* reproducibility over creativity
* minimal token usage over verbosity

---

## Repository Structure

```
prompts/
├── skills/        # Full agent definitions (production-ready)
├── templates/     # Reusable prompt templates
├── fragments/     # Small modular building blocks
└── schemas/       # Output format definitions

examples/          # Usage examples
tests/             # Prompt validation tests
```

---

## Prompt Types

### Skills

Full agents with defined behavior and execution flow.

Example:

```
tdd_executor_low_token_v1
```

---

### Templates

Reusable prompts for common tasks:

* code review
* debugging
* analysis

---

### Fragments

Composable building blocks:

* token rules
* TDD rules
* output constraints

---

### Schemas

Standardized output formats for consistency and parsing.

---

## Naming Convention

```
<type>_<function>_<optimization>_v<version>
```

Examples:

* `tdd_executor_low_token_v1`
* `planner_agent_v1`
* `code_reviewer_strict_v2`

---

## Versioning

Semantic versioning:

* **v1** → stable baseline
* **v1.1** → small improvements
* **v2** → breaking changes

Track versions in:

```
VERSION.md
```

---

## Usage

### Basic

```
Use skill: tdd_executor_low_token_v1
```

---

### With Context

```
Use skill: tdd_executor_low_token_v1

Execute next task from PLAN.md in fiap-ml-workbench
```

---

## Design Principles

* Deterministic execution
* Single-task focus
* Explicit constraints
* Minimal output
* No hidden assumptions

---

## Token Optimization Rules

* No explanations unless required
* No verbosity
* No repeated context
* Short structured outputs
* Prefer lists over paragraphs

---

## Testing Prompts

Prompts must be testable.

Example:

```yaml
- name: should_return_structured_output
  input: "Execute next task"
  expected:
    contains:
      - "TASK:"
      - "STATUS:"
    max_lines: 10
```

---

## Integration

### Option 1 — Git Submodule

```
git submodule add https://github.com/your-user/ai-prompts prompts
```

---

### Option 2 — Direct Load

```
Load prompt from:
prompts/skills/tdd_executor_low_token_v1.yaml
```

---

### Option 3 — API / Automation

Use prompts as:

* agent configs
* system messages
* pipeline steps

---

## Best Practices

* Keep prompts small and focused
* Avoid multi-task execution
* Prefer iteration over complexity
* Reuse fragments whenever possible
* Always define output schema

---

## Anti-Patterns

* ❌ Unstructured prompts
* ❌ Mixing responsibilities
* ❌ Verbose outputs
* ❌ Hidden assumptions
* ❌ No versioning

---

## Roadmap

* Prompt linting (validation rules)
* CLI runner (`prompt run <skill>`)
* Multi-agent orchestration
* CI integration for prompt testing
* Observability (logs + metrics)

---

# PT-BR

## Visão Geral

Repositório central para **prompts versionados, reutilizáveis e prontos para produção**.

Este projeto trata prompts como:

* artefatos de engenharia
* reutilizáveis
* testáveis
* versionados

---

## Filosofia

Prompt não é texto.

É:

> **interface determinística de execução de agentes de IA**

Princípios:

* estrutura > improviso
* previsibilidade > criatividade
* eficiência de tokens > verbosidade

---

## Estrutura do Repositório

```
prompts/
├── skills/        # Agentes completos
├── templates/     # Prompts reutilizáveis
├── fragments/     # Blocos modulares
└── schemas/       # Formatos de saída

examples/          # Exemplos de uso
tests/             # Testes de prompt
```

---

## Tipos de Prompt

### Skills

Agentes completos com fluxo definido.

Exemplo:

```
tdd_executor_low_token_v1
```

---

### Templates

Prompts reutilizáveis para tarefas comuns:

* revisão de código
* debug
* análise

---

### Fragments

Blocos reutilizáveis:

* regras de token
* regras de TDD
* restrições

---

### Schemas

Padronização de saída.

---

## Convenção de Nomes

```
<tipo>_<função>_<otimização>_v<versão>
```

Exemplos:

* `tdd_executor_low_token_v1`
* `planner_agent_v1`

---

## Versionamento

Versionamento semântico:

* **v1** → estável
* **v1.1** → melhorias pequenas
* **v2** → mudanças grandes

Arquivo:

```
VERSION.md
```

---

## Uso

### Básico

```
Use skill: tdd_executor_low_token_v1
```

---

### Com contexto

```
Execute próxima tarefa do PLAN.md
```

---

## Princípios de Design

* Execução determinística
* Uma tarefa por vez
* Restrições explícitas
* Saída mínima
* Sem suposições

---

## Regras de Economia de Tokens

* Sem explicações desnecessárias
* Sem repetição
* Saídas curtas
* Estrutura > texto

---

## Testes de Prompt

Exemplo:

```yaml
- name: deve_retornar_formato
  input: "Executar tarefa"
  expected:
    contains:
      - "TASK:"
      - "STATUS:"
```

---

## Integração

### Submodule

```
git submodule add https://github.com/seu-user/ai-prompts prompts
```

---

### Carregamento direto

```
Load prompt from:
prompts/skills/tdd_executor_low_token_v1.yaml
```

---

## Boas Práticas

* Prompts pequenos
* Evitar múltiplas tarefas
* Reutilizar blocos
* Definir schema sempre

---

## Anti-padrões

* ❌ Prompt solto
* ❌ Sem estrutura
* ❌ Verbosidade
* ❌ Sem versionamento

---

## Roadmap

* Validação automática de prompts
* CLI de execução
* Multi-agentes
* Integração com CI/CD
* Observabilidade

---
