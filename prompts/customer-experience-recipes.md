---
layout: default
title: "Customer experience prompts"
permalink: /prompts/customer-experience-recipes.html
parent: "Prompt collection"
---

# Customer experience prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Map a customer journey

**Claude**

```text
<project>
A customer reports a missed collection and needs a replacement or escalation.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a journey map covering trigger, action, expectation, friction, channel, owner and success signal. Separate documented customer evidence from internal assumptions and nominate the riskiest assumption.
</assignment>

<done_when>
Include before-service, exception and after-resolution stages and mark missing research. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A customer reports a missed collection and needs a replacement or escalation.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a journey map covering trigger, action, expectation, friction, channel, owner and success signal. Return a journey table and two high-impact experiments. Specify the metric and failure signal for each.

Acceptance condition: Include before-service, exception and after-resolution stages and mark missing research. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Create a service blueprint

**Claude**

```text
<project>
A digital request passes from a customer to support, agents, an approver and a field team.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a blueprint with customer, frontstage, backstage, system and owner lanes. Trace a normal case and one missed handoff through all lanes; expose the highest-cost dependency.
</assignment>

<done_when>
Every handoff has a receipt, timeout, accountable owner and customer update. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A digital request passes from a customer to support, agents, an approver and a field team.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a blueprint with customer, frontstage, backstage, system and owner lanes. Provide the blueprint, escalation sequence and a bounded service measure at each transition.

Acceptance condition: Every handoff has a receipt, timeout, accountable owner and customer update. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design onboarding to first value

**Claude**

```text
<project>
A new tenant must invite one user and complete one useful workflow.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an onboarding sequence with progressive setup, resumable state and first-value definition. Challenge each mandatory field and show how missing configuration is explained at the point of need.
</assignment>

<done_when>
Measure first successful business outcome alongside abandonment and support burden. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A new tenant must invite one user and complete one useful workflow.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an onboarding sequence with progressive setup, resumable state and first-value definition. Give a minimum first-session path, a follow-up path and a metric spec with denominator and time window.

Acceptance condition: Measure first successful business outcome alongside abandonment and support burden. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Connect self-service to a human

**Claude**

```text
<project>
The assistant cannot resolve a customer's evidence discrepancy.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an assisted handoff contract with identity checks, context, owner and next promised update. Identify what the customer should never have to repeat and where verification is still required.
</assignment>

<done_when>
The customer can resume with a reference and the receiving agent can see authorized prior context. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: The assistant cannot resolve a customer's evidence discrepancy.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an assisted handoff contract with identity checks, context, owner and next promised update. Write customer-facing copy, the support summary schema and a test for an unavailable receiving team.

Acceptance condition: The customer can resume with a reference and the receiving agent can see authorized prior context. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Recover from a broken promise

**Claude**

```text
<project>
A slot was offered but the external booking did not confirm before expiry.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a recovery flow, truthful status messages, escalation responsibility and remediation options. Trace how the service distinguishes an uncertain write from a confirmed failure and who resolves each.
</assignment>

<done_when>
The interface promises only confirmed outcomes and tracks repeat contact and reopening. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A slot was offered but the external booking did not confirm before expiry.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a recovery flow, truthful status messages, escalation responsibility and remediation options. Return a customer timeline and operational runbook. Include a scenario where a late receipt arrives.

Acceptance condition: The interface promises only confirmed outcomes and tracks repeat contact and reopening. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Measure experience without vanity metrics

**Claude**

```text
<project>
A team claims a redesigned funnel improved completion.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a goal/signal/metric map, cohort definitions, event schema, countermetrics and experiment decision rule. Use HEART as a lens and provide one competing explanation for any apparent gain.
</assignment>

<done_when>
Include missingness, support contact, reopened cases and changes in cohort mix. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A team claims a redesigned funnel improved completion.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a goal/signal/metric map, cohort definitions, event schema, countermetrics and experiment decision rule. Give the calculation for each measure, one example denominator and an explicit advance/hold decision rule.

Acceptance condition: Include missingness, support contact, reopened cases and changes in cohort mix. Distinguish observed facts, proposed decisions and tests that still need to run.
```
