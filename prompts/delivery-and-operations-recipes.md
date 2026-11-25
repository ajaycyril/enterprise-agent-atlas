---
layout: default
title: "Delivery and operations prompts"
permalink: /prompts/delivery-and-operations-recipes.html
parent: "Prompt collection"
---

# Delivery and operations prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Specify an enterprise release gate

**Claude**

```text
<project>
A small team is preparing to launch a multi-tenant agent workflow.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an evidence-backed release checklist covering accessibility, security, correctness, performance, cost and recovery. Rank gates by consequence of failure and identify what requires a human reviewer.
</assignment>

<done_when>
Every gate includes owner, test, artifact, pass condition, rollback action and unresolved dependency. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A small team is preparing to launch a multi-tenant agent workflow.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an evidence-backed release checklist covering accessibility, security, correctness, performance, cost and recovery. Return a concise go/hold table and a separate list of actual evidence still missing.

Acceptance condition: Every gate includes owner, test, artifact, pass condition, rollback action and unresolved dependency. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design a pilot and rollout

**Claude**

```text
<project>
A new workflow may shorten handling time but increase mistaken approvals.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an experiment with cohort, duration, comparison group, guardrails, stop conditions and rollback owner. Evaluate bias from early adopters and propose one cohort where results may differ.
</assignment>

<done_when>
Track customer resolution and unauthorized or duplicate effects alongside operator speed. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A new workflow may shorten handling time but increase mistaken approvals.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an experiment with cohort, duration, comparison group, guardrails, stop conditions and rollback owner. Provide pilot specification, adoption threshold and what to do when speed improves but customer outcomes worsen.

Acceptance condition: Track customer resolution and unauthorized or duplicate effects alongside operator speed. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Plan an incident and support handover

**Claude**

```text
<project>
A provider becomes unavailable while some customer cases await external receipts.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an incident timeline, paused capabilities, reconciliation queue, support update and restart criteria. Walk through containment, customer communication and recovery, with assumptions attached to each handoff.
</assignment>

<done_when>
An operator can separate confirmed, unknown and safe-to-retry cases from stored evidence. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A provider becomes unavailable while some customer cases await external receipts.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an incident timeline, paused capabilities, reconciliation queue, support update and restart criteria. Draft the runbook and two status messages. Quantify outstanding exposure without inventing incident data.

Acceptance condition: An operator can separate confirmed, unknown and safe-to-retry cases from stored evidence. Distinguish observed facts, proposed decisions and tests that still need to run.
```
