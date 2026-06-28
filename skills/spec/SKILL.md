---
name: spec
description: Start spec-driven development by writing a structured specification before code. Use when the user asks for spec, /spec, @spec, requirements, acceptance criteria, or feature definition.
---

# Spec

## Overview

Use the `spec-driven-development` skill. Write a structured spec before implementation by clarifying the user's objective, target users, core features, acceptance criteria, tech stack constraints, and boundaries, then create or update `SPEC.md`.

## When to Use

- The user asks for `@spec`, `/spec`, a spec, requirements, acceptance criteria, or a feature definition.
- A feature or significant change should be clarified before implementation.
- Requirements need a written source of truth before planning or code changes.

## Process

1. Use the `spec-driven-development` skill.
2. Understand the objective, target users, core features, acceptance criteria, tech stack constraints, and boundaries.
3. Ask clarifying questions when requirements are ambiguous.
4. Create or update `SPEC.md` in the project root unless the user requests another path.
5. Do not implement code during this workflow.
6. Stop after writing the spec and ask for review before planning or implementation.

## Verification

- `SPEC.md` exists or was updated.
- The spec covers objective, commands, project structure, code style, testing strategy, and boundaries.
- Success criteria are concrete.
- Open questions are listed instead of guessed.
- No implementation files were changed.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I'll start coding and write the spec later." | `@spec` means define the work before implementation. |
| "The request is obvious." | The spec still needs explicit acceptance criteria and boundaries. |

## Red Flags

- Implementation files changed during `@spec`.
- Missing success criteria.
- Ambiguous requirements were guessed instead of listed as open questions.
