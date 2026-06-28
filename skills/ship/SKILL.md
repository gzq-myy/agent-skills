---
name: ship
description: Run the pre-launch checklist with specialist review and a go/no-go decision. Use when the user asks for ship, /ship, @ship, release readiness, launch review, rollback planning, or go/no-go.
---

# Ship

## Overview

Run the pre-launch review. Invoke `skills/shipping-and-launch/SKILL.md`, fan out to the quality, security, and test perspectives when appropriate, then synthesize blockers, recommended fixes, acknowledged risks, a rollback plan, and a `GO` or `NO-GO` decision.

## When to Use

- The user asks for `@ship`, `/ship`, launch review, release readiness, or go/no-go.
- A change is ready for production-bound review.
- The user needs rollback, quality, security, and test readiness checked together.

## Process

1. Follow `skills/shipping-and-launch/SKILL.md`.
2. Review the current change, staged diff, or release candidate.
3. Run or emulate the three specialist reviews:
   - `agents/code-reviewer.md` for code quality.
   - `agents/security-auditor.md` for security and threat modeling.
   - `agents/test-engineer.md` for coverage and test gaps.
4. If a subagent tool is available, run the reviews independently and merge their reports. If not, apply each persona sequentially and treat the outputs as independent reports.
5. Verify accessibility, infrastructure, documentation, monitoring, migrations, feature flags, and rollback readiness directly.
6. Produce a single `GO` or `NO-GO` decision.

## Output

Include blockers, recommended fixes, acknowledged risks, rollback plan, and specialist reports or summaries.

## Verification

- Any Critical or High-risk issue blocks shipping unless the user explicitly accepts the risk.
- A rollback plan is included before any `GO` decision.
- Test, security, and operational gaps are explicit.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "The diff is small, so it can ship." | Small diffs can still affect security, data, or operations. |
| "Rollback is obvious." | A GO decision needs an explicit rollback plan. |

## Red Flags

- GO decision without rollback steps.
- Critical findings are treated as non-blocking without user acceptance.
- Security or test coverage is not checked.
