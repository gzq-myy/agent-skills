---
name: build
description: Implement planned tasks incrementally. Use when the user asks for build, /build, @build, build auto, implement the next task, or run the approved plan.
---

# Build

## Overview

Codex entrypoint mirroring the Claude Code `/build` command. This wrapper orchestrates `skills/incremental-implementation/SKILL.md` and `skills/test-driven-development/SKILL.md`.

## When to Use

- The user asks for `@build`, `/build`, implementation, the next task, or `build auto`.
- A spec and plan exist and the user wants code changes.
- The user wants incremental, verified task execution.

## Modes

- `@build` implements the next pending task and then stops.
- `@build auto` or `@build all` plans if needed, gets one explicit approval, then implements every task in dependency order.

## Default: One Task

1. Read the next pending task from `tasks/todo.md` or `tasks/plan.md`.
2. If no plan exists, stop and ask the user to run `@plan` first.
3. Follow `skills/incremental-implementation/SKILL.md`.
4. Follow `skills/test-driven-development/SKILL.md`.
5. Read the task's acceptance criteria.
6. Load only the relevant context and existing patterns.
7. Write or update tests first when behavior changes.
8. Implement the minimum code needed for the task.
9. Run the task's verification, plus relevant regression checks.
10. Mark the task complete and stop.

## Auto: Whole Plan

1. Require a spec at `SPEC.md`, `docs/SPEC.md`, or `spec/*`. If none exists, stop and ask the user to run `@spec` first.
2. Run `git status --porcelain`.
3. If unrelated local changes exist outside expected planning artifacts, ask how to proceed before editing.
4. If `tasks/plan.md` does not exist, follow `skills/planning-and-task-breakdown/SKILL.md` and create it.
5. Present the full plan and wait for explicit approval such as "approve", "go", or "yes".
6. After approval, execute every task in dependency order.
7. For each task, run the default loop: test, implement, verify, update task status.
8. Commit per task when appropriate, staging only files touched by that task plus task-status updates.
9. Stop and ask the user if tests cannot be fixed, the spec is ambiguous, or the task is high-risk or irreversible.

## Verification

- Completed tasks are marked in `tasks/todo.md` or `tasks/plan.md`.
- Relevant tests and checks were run.
- The summary lists files changed, checks run, tasks completed, and remaining work.
- Any blocker or skipped verification is explicit.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I'll implement several tasks at once." | Build one task at a time unless `@build auto` was explicitly approved. |
| "I'll test at the end." | Each task needs its own verification before moving on. |
| "I'll include this small cleanup." | Keep each task scoped and separately reviewable. |

## Red Flags

- No spec or plan exists.
- Unrelated local changes are folded into task work.
- Tests or checks are skipped without being reported.
- Multiple independent tasks are mixed in one change.
