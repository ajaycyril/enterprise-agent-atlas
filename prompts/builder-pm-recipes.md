---
layout: default
title: "Builder PM decision prompts"
permalink: /prompts/builder-pm-recipes.html
parent: "Prompt collection"
---

# Builder PM decision prompts

Use these with the [builder PM guides and worked examples](../builder-pm/index.md). Paste actual approved inputs. An answer with no observed results can still be a good plan, but it cannot establish that a pilot passed.

## Decide whether to fund a pilot

**Claude**

```text
<inputs>
Current journey, representative tickets, current costs and intended users. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Take the service owner’s perspective. Compare a form change, a rules change and a bounded agent. Identify the single most consequential assumption and design a cheap test that could reject the agent option.
</task>

<acceptance>
A reader can choose an option and identify the evidence that would reverse it. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Return a one-page investment note with the three options, evidence for and against each, smallest reversible experiment, explicit exclusions and a stop rule.

Inputs: Current journey, representative tickets, current costs and intended users. Use the supplied evidence and identify any missing inputs.

Acceptance: A reader can choose an option and identify the evidence that would reverse it. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Define a measurable customer promise

**Claude**

```text
<inputs>
Case events, customer messages, partner receipts and support resolution policy. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Follow one case from entry to confirmed service outcome. Mark where channels disagree, identify a denominator that includes abandonment, and explain which event proves success.
</task>

<acceptance>
A support-assisted success and a false confirmation are classified correctly using the same rule. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Produce a metric contract with eligibility, numerator, denominator, source of truth, attribution window, late events and examples that must be excluded.

Inputs: Case events, customer messages, partner receipts and support resolution policy. Use the supplied evidence and identify any missing inputs.

Acceptance: A support-assisted success and a false confirmation are classified correctly using the same rule. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Write a vendor evaluation the team can run

**Claude**

```text
<inputs>
Two vendor options, contractual requirements, permitted data classes and a pilot workload. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Evaluate mandatory gates first. For each remaining option specify a proof request, a failure drill, an exit test and the person responsible for reviewing it.
</task>

<acceptance>
Unknown residency or deletion evidence cannot be averaged into a passing score. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Deliver a procurement scorecard with pass, fail or unknown for each mandatory condition. Compare qualified options on total cost and demonstrated fit. List contract items for human review.

Inputs: Two vendor options, contractual requirements, permitted data classes and a pilot workload. Use the supplied evidence and identify any missing inputs.

Acceptance: Unknown residency or deletion evidence cannot be averaged into a passing score. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Calculate cost per verified outcome

**Claude**

```text
<inputs>
Invoice components, eligible cases, authoritative receipts, handling minutes, reattempts and support rate. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Reconcile costs to outcomes. Work the arithmetic with units, expose shared cost allocation and test one sensitivity in human workload. Distinguish freed capacity from cash savings.
</task>

<acceptance>
The arithmetic reconciles to totals and zero verified outcomes returns an undefined unit cost. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Build a baseline-versus-pilot cost table showing attempts, successful cases, spend on all cases, cost per verified case and break-even handling minutes. Mark missing inputs and unpriced work.

Inputs: Invoice components, eligible cases, authoritative receipts, handling minutes, reattempts and support rate. Use the supplied evidence and identify any missing inputs.

Acceptance: The arithmetic reconciles to totals and zero verified outcomes returns an undefined unit cost. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Design a trusted document lifecycle

**Claude**

```text
<inputs>
Two versions of a policy, tenant access grants, ingestion route, cache and backup policy. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Trace one revised fee, one removed exemption and one revoked role from source through citation. Assign owners for each derivative, fallback and expiry.
</task>

<acceptance>
A reviewer can prove which policy a tenant could see at the time of a recommendation. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Return a document lifecycle diagram, field inventory and acceptance tests for revision, revocation and deletion, including a partial failure and a retained-backup exception.

Inputs: Two versions of a policy, tenant access grants, ingestion route, cache and backup policy. Use the supplied evidence and identify any missing inputs.

Acceptance: A reviewer can prove which policy a tenant could see at the time of a recommendation. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Build an accessible live operator brief

**Claude**

```text
<inputs>
Run events with retries and duplicates, operator task, mobile screenshot and supported languages. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Map every visible transition to an observed event. Specify keyboard, reduced-motion and Arabic behavior. Show what reconnect changes while a reviewer is reading history.
</task>

<acceptance>
An operator can recover who acted, what evidence arrived and what needs approval without animation. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Give a state table for customer, operator and screen reader plus acceptance checks for delayed delivery, replay, right-to-left layout and interrupted focus.

Inputs: Run events with retries and duplicates, operator task, mobile screenshot and supported languages. Use the supplied evidence and identify any missing inputs.

Acceptance: An operator can recover who acted, what evidence arrived and what needs approval without animation. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Choose a retrieval investment

**Claude**

```text
<inputs>
Labeled questions, eligible passages, current lexical results, candidate semantic results and cost. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Trace misses by source availability, access, chunking, ranking and answer formation. Compare lexical and hybrid retrieval on identical authorized evidence.
</task>

<acceptance>
Every counted relevant passage is authorized, current and uniquely identified. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Return a paired case table with recall at the chosen k, supported-claim rate, correct abstention, latency and cost. Include the simplest change worth testing next.

Inputs: Labeled questions, eligible passages, current lexical results, candidate semantic results and cost. Use the supplied evidence and identify any missing inputs.

Acceptance: Every counted relevant passage is authorized, current and uniquely identified. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Design a regional pilot and fallback

**Claude**

```text
<inputs>
Permitted regions, provider capabilities, outage scenario, live-action policy and latency budget. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Track where prompts, caches, backups, traces and support access go. Rehearse the primary provider timing out after an action has been proposed.
</task>

<acceptance>
No forbidden region receives data and a fallback cannot cause a duplicate business effect. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Produce a decision table for allowed primary and fallback routes. Give a degraded user-facing response, reconciliation owner and recovery check for each blocked route.

Inputs: Permitted regions, provider capabilities, outage scenario, live-action policy and latency budget. Use the supplied evidence and identify any missing inputs.

Acceptance: No forbidden region receives data and a fallback cannot cause a duplicate business effect. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Prepare the support handoff

**Claude**

```text
<inputs>
A pending case, three messages already sent, roles and the actual support search fields. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Role-play a support agent receiving a customer from another channel. Find the minimal case record, permissions and statement that correctly explains the next step.
</task>

<acceptance>
The second operator can continue from the correct state without re-collecting sensitive context. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Write the customer message, support view, escalation contract and a test in which a second operator opens the case after access changes.

Inputs: A pending case, three messages already sent, roles and the actual support search fields. Use the supplied evidence and identify any missing inputs.

Acceptance: The second operator can continue from the correct state without re-collecting sensitive context. Link each material conclusion to an input or an explicitly labeled assumption.
```

## Review a canary and decide whether to expand

**Claude**

```text
<inputs>
Baseline and pilot counts by cohort, critical failures, spend, sample sizes and operator reports. Paste approved project evidence here. Mark absent evidence explicitly.
</inputs>

<task>
Compare like cohorts, identify selection effects, read changed cases and distinguish reversible friction from release blockers. Explain whether more observations could alter the decision.
</task>

<acceptance>
A reviewer can reproduce the decision and explain what will happen to a pending external write. Separate observed results from proposed tests.
</acceptance>
```

**ChatGPT**

```text
Return a release decision with paired regressions, uncertainty by slice, rollback trigger, treatment of in-flight cases and the accountable owner.

Inputs: Baseline and pilot counts by cohort, critical failures, spend, sample sizes and operator reports. Use the supplied evidence and identify any missing inputs.

Acceptance: A reviewer can reproduce the decision and explain what will happen to a pending external write. Link each material conclusion to an input or an explicitly labeled assumption.
```
