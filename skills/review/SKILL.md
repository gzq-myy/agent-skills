---
name: review
description: Conduct a five-axis code review across correctness, readability, architecture, security, and performance. Use when the user asks for review, /review, @review, code review, or pre-merge review.
---

# Review

## Overview

Use the `code-review-and-quality` skill. Review the current changes across correctness, readability, architecture, security, and performance, then return prioritized findings with file and line references.

## When to Use

- The user asks for `@review`, `/review`, code review, pre-merge review, or current diff review.
- A change needs quality, correctness, security, or performance review.
- The user wants findings before a summary.

## Process

1. Use the `code-review-and-quality` skill.
2. Review staged changes, unstaged changes, or recent commits as requested.
3. Check correctness, readability, architecture, security, and performance.
4. Use the `security-and-hardening` skill for security-sensitive changes.
5. Use the `performance-optimization` skill for performance-sensitive changes.
6. Prioritize findings by severity and include file and line references.

## Output

Report findings first, then open questions or assumptions, then a short summary. If there are no issues, say so clearly and mention remaining risk or test gaps.

## Verification

- Findings include specific file and line references where possible.
- Severity is clear.
- Missing tests or unverified behavior are called out.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I'll summarize first." | `@review` should lead with findings so risks are visible. |
| "This is just style." | Correctness, risk, and missing tests come before style. |

## Red Flags

- Findings do not include file or line references when available.
- The review focuses on summaries instead of actionable risks.
- Test gaps are omitted.
