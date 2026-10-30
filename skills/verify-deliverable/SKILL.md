---
name: verify-deliverable
description: Verify an implemented analysis, script, API, web interface, or document against concrete requirements. Use after a meaningful implementation or before submission. Compare expected and observed results, record failures and unverified items, and rerun the same check after fixes.
---

# Verify a deliverable

Read the current task requirements, relevant decisions, and implementation.
Respect the environment's tool, network, and automation limits.

1. Map mandatory requirements to risk-prioritized checks. Reuse relevant existing tests.
2. Choose a small normal case and important boundary or failure cases. Avoid tests that merely repeat implementation logic.
3. Establish expected results independently where possible: a manual calculation, source data, a contract, or a known fixture.
4. Execute the relevant checks. Distinguish actual execution, code inspection, and manual checks still needed from the user.
5. For failure, preserve the reproducing input, expected result, observed result, and error. Investigate before editing.
6. Fix the demonstrated cause within the authorized scope, then rerun the same check and any affected essential regression.
7. Confirm actual output files, startup instructions, paths, and the agreement between documentation and implementation.
8. Report remaining limitations truthfully. Do not replace real integration with an unlabeled mock or claim tests not run.

Use the task's relevant checks:
- Data: key uniqueness, missing values, join cardinality, denominators, units, and aggregate reconciliation.
- Prediction: data leakage, evaluation split, baseline, and important failure groups.
- Web/API: actual requests and responses, validation, startup, and manual UI checks when required.
- Documents: file existence, readable output, source consistency, and meaningful layout checks.

Do not launch browser or desktop automation where prohibited. Ask the user to perform the specific manual action.

| Requirement | Input or action | Expected | Observed | Pass / Fail / Unverified |
|---|---|---|---|---|

Prioritize checks that could change correctness or required behavior. Stop redundant testing once relevant checks pass.
