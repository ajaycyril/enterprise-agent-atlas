---
layout: default
title: "System architecture prompts"
permalink: /prompts/system-architecture-recipes.html
parent: "Prompt collection"
---

# System architecture prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Choose monolith or services

**Claude**

```text
<project>
A team of six ships a case product with three domain modules and a volatile integration.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an ADR comparing deployment, ownership, data consistency, release cadence and failure isolation. Stress-test the recommendation against a failed integration and a team ownership change.
</assignment>

<done_when>
The decision names a measurable trigger for splitting one module later. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A team of six ships a case product with three domain modules and a volatile integration.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an ADR comparing deployment, ownership, data consistency, release cadence and failure isolation. Lead with the deployment decision, draw a boundary diagram and provide a reversible migration seam.

Acceptance condition: The decision names a measurable trigger for splitting one module later. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Estimate capacity and cost

**Claude**

```text
<project>
A service admits runs at a stated peak, each with variable fan-out and retries.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a sizing worksheet for execution, events, storage, concurrency and cost per successful case. Check dimensional consistency and evaluate two growth cases before recommending capacity.
</assignment>

<done_when>
State units, traffic distribution, assumptions, retry amplification and sensitivity to the slowest tool. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A service admits runs at a stated peak, each with variable fan-out and retries.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a sizing worksheet for execution, events, storage, concurrency and cost per successful case. Show equations and one worked peak-period calculation. Mark the input that most affects the bill.

Acceptance condition: State units, traffic distribution, assumptions, retry amplification and sensitivity to the slowest tool. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design multi-tenant data access

**Claude**

```text
<project>
One service supports pooled small customers and isolated enterprise customers.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a tenant placement ADR, access controls, routing, migration plan and tenant restore procedure. Compare pooled, siloed and mixed isolation with explicit operating costs and consistency risks.
</assignment>

<done_when>
A tenant move preserves grant checks, case continuity and effect deduplication. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: One service supports pooled small customers and isolated enterprise customers.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a tenant placement ADR, access controls, routing, migration plan and tenant restore procedure. Return the decision matrix, routing rules and a rehearsal for one partially migrated tenant.

Acceptance condition: A tenant move preserves grant checks, case continuity and effect deduplication. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Define the event contract

**Claude**

```text
<project>
Several clients need durable run progress, live tokens and replay after disconnect.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a versioned business envelope, ordering rule, snapshot policy and compatibility contract. Review one legacy consumer and one reconnecting consumer using the same case history.
</assignment>

<done_when>
The client handles duplicates, missing events and an old schema without dispatching side effects. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Several clients need durable run progress, live tokens and replay after disconnect.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a versioned business envelope, ordering rule, snapshot policy and compatibility contract. Provide two specimen events, a reducer invariant and expected results for gaps and duplicates.

Acceptance condition: The client handles duplicates, missing events and an old schema without dispatching side effects. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design disaster recovery

**Claude**

```text
<project>
The app stores cases, workflow checkpoints, evidence and external effect receipts.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a recovery sequence, dependencies, business-agreed RPO/RTO and a restore drill. Trace a partial restore and identify the earliest safe point at which writes may resume.
</assignment>

<done_when>
Measure actual restore time and hold writes if external receipts have not reconciled. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: The app stores cases, workflow checkpoints, evidence and external effect receipts.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a recovery sequence, dependencies, business-agreed RPO/RTO and a restore drill. Give an ordered runbook, decision owner at each gate and how an operator recognizes an unsafe promotion.

Acceptance condition: Measure actual restore time and hold writes if external receipts have not reconciled. Distinguish observed facts, proposed decisions and tests that still need to run.
```
