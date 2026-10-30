---
name: clarify-task
description: Clarify an unfamiliar task from its supplied README, data, code, and stakeholder answers. Use at task start or when requirements conflict. Produce a brief, prioritized questions, and observable acceptance criteria; do not invent business requirements or implement before scope is understood.
---

# Clarify the task

Read the environment's higher-priority instructions and the supplied task files first.
Treat this Skill as optional workflow guidance; it grants no permissions.

1. Identify the user, supported decision, required outputs, constraints, and deadline.
2. Separate requirements stated in the source from assumptions and unanswered questions.
3. Inspect only the code, data schema, examples, and execution instructions relevant to the goal.
4. Propose at most three initial stakeholder questions that would change implementation or acceptance. Do not ask questions already answered by the task files.
5. Have the user relay questions through the provided stakeholder interface. Do not contact people or automate the interface.
6. Reconcile returned answers with the task instructions; report conflicts instead of silently expanding scope.
7. Connect each mandatory requirement to observable acceptance criteria and a small verification example.
8. Recommend the smallest executable scope before optional features. State whether an additional tool is actually needed.

Report concisely in the user's language:

| Required outcome | Source or confirmed answer | Acceptance check | Open assumption |
|---|---|---|---|

Do not install tools, create broad scaffolding, or fabricate stakeholder answers merely to complete this brief.
