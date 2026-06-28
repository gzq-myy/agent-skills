---
name: code-simplify
description: Simplify code for clarity and maintainability without changing behavior. Use when the user asks for code-simplify, /code-simplify, @code-simplify, simplify code, reduce complexity, or clean up recent changes.
---

# Code Simplify

## Overview

Use the `code-simplification` skill. Simplify recently changed code or the specified scope for clarity and maintainability while preserving exact behavior.

## When to Use

- The user asks for `@code-simplify`, `/code-simplify`, simplify code, reduce complexity, or clean up recent changes.
- Code works but is harder to read or maintain than necessary.
- The target scope is clear enough to preserve behavior.

## Process

1. Use the `code-simplification` skill.
2. Read project conventions before editing.
3. Identify the target scope from the user request, recent changes, or current diff.
4. Understand purpose, callers, edge cases, and test coverage before changing code.
5. Simplify incrementally while preserving exact behavior.
6. Run relevant tests or checks after simplification.
7. If a simplification breaks behavior, revert that simplification and reassess.

## Verification

- Behavior is preserved.
- Relevant tests and checks pass.
- The diff is smaller, clearer, or easier to maintain.
- Any unverified behavior is reported.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I'll refactor broadly while here." | `@code-simplify` stays inside the requested scope. |
| "This abstraction might help later." | Do not add abstractions without a current use. |

## Red Flags

- Behavior changes without explicit approval.
- New abstraction increases complexity.
- Tests fail after simplification.
