---
name: spec
description: Create or update SPEC.md before implementation. Use when starting a feature, clarifying requirements, writing acceptance criteria, or when the user asks for spec, /spec, or @spec.
---

# Spec

## Overview

Codex entrypoint mirroring the Claude Code `/spec` command. This is a thin wrapper around `skills/spec-driven-development/SKILL.md`.

## When to Use

- The user asks for `@spec`, `/spec`, a spec, requirements, acceptance criteria, or a feature definition.
- A feature or significant change should be clarified before implementation.
- Requirements are ambiguous and need a written source of truth.

## Process

1. Follow `skills/spec-driven-development/SKILL.md`.
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
| "I'll just start coding." | This entrypoint exists to create the spec before implementation. |
| "The request is obvious." | Obvious requests still need success criteria and boundaries. |

## Red Flags

- Implementation files changed during `@spec`.
- Missing success criteria.
- Ambiguous requirements were guessed instead of listed as open questions.
