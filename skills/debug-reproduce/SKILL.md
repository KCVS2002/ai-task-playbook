---
name: debug-reproduce
description: Diagnose a reproducible error or repeated failed implementation in a local task. Use when execution fails, calculated results differ, or a service does not respond. Isolate the cause, make a scoped correction, and verify with the same reproduction; do not alter platform controls.
---

# Reproduce and correct a failure

Follow higher-priority instructions and preserve the user's source data and existing work.

1. Classify the state: awaiting approval, legitimately running, execution failure, incorrect result, or platform/connection failure.
2. Capture a minimal relevant command or input, expected result, actual result, and sanitized error. Never print secrets.
3. Reproduce once where possible; do not repeatedly install packages or resend the same request without new evidence.
4. Narrow the cause using the smallest useful inspection. Check execution path, dependency version, input shape, and environment.
5. For web preview, check server output, running state, actual port, required bind address, and path. Do not invent tunnels or bypass restrictions.
6. Propose and apply a small correction within scope. Preserve required behavior and explain any changed assumption.
7. Rerun the original reproduction, then the essential affected check.
8. If the cause is a blocked tool, provider failure, or platform issue, record time and symptom and use the provided support route. Do not disable or restart management, security, or monitoring processes.
9. If time is low, offer a reduced valid scope rather than hiding a failure behind a mock.

Report: symptom, evidence, cause or remaining hypothesis, change, rerun result, and remaining limitation.
Do not claim a root cause until evidence supports it.
