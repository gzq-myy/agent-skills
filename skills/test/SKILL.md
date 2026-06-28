---
name: test
description: Run a TDD workflow by writing failing tests, implementing, and verifying. Use when the user asks for test, /test, @test, TDD, regression tests, bug reproduction, or the Prove-It pattern.
---

# Test

## Overview

Run the test-driven workflow. Invoke `skills/test-driven-development/SKILL.md`; for new features, write failing tests for expected behavior before implementation, and for bugs, reproduce the failure first with the Prove-It pattern.

## When to Use

- The user asks for `@test`, `/test`, TDD, regression tests, test coverage, or bug reproduction.
- New behavior needs proof through tests.
- A bug should be reproduced before fixing.

## Process

1. Follow `skills/test-driven-development/SKILL.md`.
2. For new behavior, write tests that describe the expected outcome and confirm they fail before implementation.
3. For bugs, write a test that reproduces the bug and confirm it fails.
4. Implement the minimum code needed to pass.
5. Refactor only while tests stay green.
6. For browser-facing issues, also follow `skills/browser-testing-with-devtools/SKILL.md` when runtime verification is needed.

## Verification

- New or changed tests cover the behavior.
- The failure was observed first when using TDD or bug reproduction.
- Relevant test commands pass.
- Any unverified coverage or skipped test is reported.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "The fix is simple, no test needed." | Tests are the proof that behavior is correct and guarded. |
| "I'll write tests after the code." | This workflow starts with the failing test when behavior changes. |

## Red Flags

- A bug fix starts without a reproducing test.
- A test passes before the behavior exists and is treated as proof.
- Relevant regression tests are not run or not reported.
