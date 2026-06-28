---
name: webperf
description: Run a web performance audit for browser-facing applications. Use when the user asks for webperf, /webperf, @webperf, web performance, Lighthouse, Core Web Vitals, PageSpeed Insights, CrUX, or frontend performance review.
---

# Webperf

## Overview

Audit browser-facing performance only. Use Deep mode when Lighthouse, PageSpeed Insights, CrUX, DevTools trace, a live URL with browser tooling, or equivalent runtime metrics are available; otherwise use Quick mode and label findings as potential impact.

## When to Use

- The user asks for `@webperf`, `/webperf`, Lighthouse, Core Web Vitals, frontend performance, or web performance review.
- The target has browser-facing UI or pages.
- The user provides runtime performance artifacts or wants a source scan for likely issues.

## Process

1. Determine whether the target is browser-facing. If not, explain that `@webperf` is not the right workflow.
2. Use Deep mode when the user provides Lighthouse JSON, PageSpeed Insights JSON, CrUX data, a DevTools trace, a live URL with browser tooling, or equivalent runtime metrics.
3. Use Quick mode when runtime metrics are unavailable; label findings as potential impact.
4. Apply the `agents/web-performance-auditor.md` persona if available.
5. For browser runtime investigation, follow `skills/browser-testing-with-devtools/SKILL.md` when tooling is configured.
6. Return the full audit report without unnecessary synthesis.

## Verification

- The report states Quick or Deep mode.
- Sourced metrics are distinguished from source-code heuristics.
- Findings are ranked by expected impact.
- Missing runtime evidence is explicit.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "Source inspection is enough." | Runtime metrics are required for measured performance claims. |
| "Any app can use webperf." | This workflow is for browser-facing surfaces. |

## Red Flags

- Server-only or CLI code is audited as web performance.
- Potential impact is presented as measured impact.
- Missing Lighthouse, CrUX, or trace data is not disclosed.
