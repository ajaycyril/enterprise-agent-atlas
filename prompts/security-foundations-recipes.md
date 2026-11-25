---
layout: default
title: "Security foundations prompts"
permalink: /prompts/security-foundations-recipes.html
parent: "Prompt collection"
---

# Security foundations prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Draw the first trust boundary

**Claude**

```text
<project>
A tenant-scoped case app has a browser, BFF, database, worker and external case service.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a context diagram and a boundary table with identity, data class, enforcement point and owner. Mark every trust assumption that could change the design; use the two traces to check the table for unguarded crossings.
</assignment>

<done_when>
Trace one read and one consequential write through all five components. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A tenant-scoped case app has a browser, BFF, database, worker and external case service.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a context diagram and a boundary table with identity, data class, enforcement point and owner. Return the diagram, then the smallest control set that covers both traces. Finish with three verifiable acceptance cases.

Acceptance condition: Trace one read and one consequential write through all five components. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design enterprise login and recovery

**Claude**

```text
<project>
Employees sign in through an enterprise IdP and can lose a device or leave the organization.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a sequence for sign-in, logout, session expiry, account recovery and deprovisioning. Contrast browser session ownership with token audience and show the recovery path's weakest assumption.
</assignment>

<done_when>
A disabled test user loses protected access within an explicitly stated bound. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Employees sign in through an enterprise IdP and can lose a device or leave the organization.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a sequence for sign-in, logout, session expiry, account recovery and deprovisioning. List each state, who can move it forward and which user-facing recovery message appears. Flag any IdP-dependent behavior.

Acceptance condition: A disabled test user loses protected access within an explicitly stated bound. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Map roles to resources

**Claude**

```text
<project>
Viewers, case reviewers and tenant admins have different rights on cases, evidence and exports.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a subject × action × resource policy matrix with conditions, defaults and enforcement locations. Work from the resource relationships in the input and identify ambiguous inherited access.
</assignment>

<done_when>
A reviewer in tenant B cannot view, approve or export a seeded case in tenant A. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Viewers, case reviewers and tenant admins have different rights on cases, evidence and exports.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a subject × action × resource policy matrix with conditions, defaults and enforcement locations. Produce the matrix plus a minimal positive/negative test set; distinguish hidden UI actions from server authorization.

Acceptance condition: A reviewer in tenant B cannot view, approve or export a seeded case in tenant A. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Review secrets and key rotation

**Claude**

```text
<project>
A job calls a model provider, an evidence store and a scheduling partner.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a workload identity map, secret inventory, rotation sequence and outage behavior. Trace each credential from issuance through revocation and challenge any shared access.
</assignment>

<done_when>
One credential can rotate while unrelated workloads continue and raw values stay out of logs. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A job calls a model provider, an evidence store and a scheduling partner.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a workload identity map, secret inventory, rotation sequence and outage behavior. Use a table by service and a timeline for one rotation. State what happens to in-flight work when renewal fails.

Acceptance condition: One credential can rotate while unrelated workloads continue and raw values stay out of logs. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Threat-model document intake

**Claude**

```text
<project>
Customers upload case evidence and operators can later preview it.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an upload flow with authorization, quarantine, validation, promotion, preview and expiry. Trace a benign incomplete upload and a delayed validation result. Identify which component owns each state.
</assignment>

<done_when>
Unvalidated or expired objects cannot be retrieved through either app or worker. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Customers upload case evidence and operators can later preview it.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an upload flow with authorization, quarantine, validation, promotion, preview and expiry. Return a before-and-after state table, a safe customer message and acceptance checks using harmless fixtures.

Acceptance condition: Unvalidated or expired objects cannot be retrieved through either app or worker. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Specify a safe approval gate

**Claude**

```text
<project>
An agent proposes changing a reservation after a supervisor reviews the evidence.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a proposal schema, authority check, expiry rule, idempotency strategy and receipt policy. Compare approval time with execution time; explain how the exact proposal remains bound to the decision.
</assignment>

<done_when>
Editing a proposal or revoking a reviewer prevents a subsequent write. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: An agent proposes changing a reservation after a supervisor reviews the evidence.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a proposal schema, authority check, expiry rule, idempotency strategy and receipt policy. Provide the sequence, a concurrent-review scenario and the expected external mutation count.

Acceptance condition: Editing a proposal or revoking a reviewer prevents a subsequent write. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Protect customer data in telemetry

**Claude**

```text
<project>
Operators need traces that include tool names, costs, timing and evidence references.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a field-level policy for persist, redact, hash, restrict or omit, with retention owners. Separate operational diagnosis, user-visible progress and security audit by audience and purpose.
</assignment>

<done_when>
A synthetic marker stays out of the browser stream and general telemetry exporter. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Operators need traces that include tool names, costs, timing and evidence references.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a field-level policy for persist, redact, hash, restrict or omit, with retention owners. Give an example safe event and a field-by-field review table. Name one useful diagnostic still possible after redaction.

Acceptance condition: A synthetic marker stays out of the browser stream and general telemetry exporter. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Review release provenance

**Claude**

```text
<project>
A team builds a container in CI and deploys it to production.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a chain from source revision through dependency lock, SBOM, artifact digest, signing identity and deployment verification. Use the supplied pipeline definition to identify where trust is established and where it can drift.
</assignment>

<done_when>
Production accepts the intended artifact from the approved builder and the prior version is recoverable. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A team builds a container in CI and deploys it to production.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a chain from source revision through dependency lock, SBOM, artifact digest, signing identity and deployment verification. Return release evidence, missing checks and a rollback rehearsal. Mark any unverifiable pipeline steps.

Acceptance condition: Production accepts the intended artifact from the approved builder and the prior version is recoverable. Distinguish observed facts, proposed decisions and tests that still need to run.
```
