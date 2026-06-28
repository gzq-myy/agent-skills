---
name: plan
description: Break an existing spec into tasks/plan.md and tasks/todo.md. Use when the user asks for plan, /plan, @plan, task breakdown, implementation plan, or planning from SPEC.md.
---

# Plan

## Overview

Codex entrypoint mirroring the Claude Code `/plan` command. This is a thin wrapper around `skills/planning-and-task-breakdown/SKILL.md`.

## When to Use

- The user asks for `@plan`, `/plan`, an implementation plan, task breakdown, or planning from a spec.
- A spec exists and needs ordered, verifiable tasks.
- Work needs checkpoints before implementation.

## Process

1. Follow `skills/planning-and-task-breakdown/SKILL.md`.
2. Read the existing spec from `SPEC.md`, `docs/SPEC.md`, or `spec/*`.
3. If no spec exists, stop and ask the user to run `@spec` first or provide the spec path.
4. Read only during planning; do not implement code.
5. Identify dependencies, slice work vertically, and define verification for each task.
6. Save the implementation plan to `tasks/plan.md`.
7. Save the task checklist to `tasks/todo.md`.
8. Present the plan for human review before implementation.

## Verification

- `tasks/plan.md` exists or was updated.
- `tasks/todo.md` exists or was updated.
- Every task has acceptance criteria and verification.
- Dependencies and checkpoints are clear.
- No implementation files were changed.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I can plan while coding." | Planning should happen before implementation so dependencies and verification are explicit. |
| "The tasks are obvious." | Write them down so progress and review are concrete. |

## Red Flags

- Code changed during `@plan`.
- Tasks lack verification steps.
- The plan ignores dependency order.
