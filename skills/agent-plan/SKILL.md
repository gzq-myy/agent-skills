---
name: agent-plan
description: Break work into small verifiable tasks with acceptance criteria and dependency ordering. Use when the user asks for agent-plan, @agent-plan, task breakdown, implementation plan, or planning from SPEC.md.
---

# Agent Plan

## Overview

Use the `planning-and-task-breakdown` skill. Break an existing spec into small, ordered, verifiable tasks, then save the plan to `tasks/plan.md` and the task list to `tasks/todo.md`.

## When to Use

- The user asks for `@agent-plan`, `agent-plan`, an implementation plan, task breakdown, or planning from a spec.
- A spec exists and needs ordered, verifiable tasks.
- Work needs checkpoints before implementation.

## Process

1. Use the `planning-and-task-breakdown` skill.
2. Read the existing spec from `SPEC.md`, `docs/SPEC.md`, or `spec/*`.
3. If no spec exists, stop and ask the user to run `@agent-spec` first or provide the spec path.
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
| "I can plan while coding." | `@agent-plan` is read-only planning before implementation. |
| "The tasks are obvious." | The command produces concrete task files with acceptance criteria and verification. |

## Red Flags

- Code changed during `@agent-plan`.
- Tasks lack verification steps.
- The plan ignores dependency order.
