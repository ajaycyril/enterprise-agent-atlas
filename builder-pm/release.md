---
layout: default
title: "Pilot, release and ownership"
permalink: /builder-pm/release.html
parent: "AI builder PM library"
---

# Pilot, release and ownership

A pilot needs someone who can close a customer case when the model stops responding. Name the person or team before launch. The same applies to spend, privacy, deployment and rollback.

| Role | Owns | Evidence before first live write |
|---|---|---|
| PM and operations lead | Eligible population, customer outcome and stop decision | Baseline, target, exclusion rules, support staffing and a review date |
| Service owner | Scope, transaction, idempotency and recovery | Two customers claiming one slot, lost receipt, worker restart |
| Security and data owner | Identity, tenant boundary, retention and credentials | Revocation, redaction and deletion checks with a second tenant |
| Evaluation owner | Versioned cases, labels and grader calibration | Paired outcomes, critical losses and unresolved disagreements |
| On-call lead | Alerts, feature switch, reconciliation and support escalation | Timed rehearsal with live writes disabled in a test tenant |

**A staged rollout.** Replay historical redacted cases against fixed fixtures. Run the candidate in shadow mode with writes disabled. After review, enable a small authorized tenant cohort with a named support owner. Compare equivalent case types across cohorts, include contact-center volume and watch for selection bias. Agree a minimum observation window and handling rules for unresolved cases.

**Rehearse stopping.** Turn off admission to new writes and let known operations reconcile safely. Inform the customer using the existing reference. Assign unknown outcomes to a queue with a deadline and human oversight. Restore the previous implementation and verify that older run records still open. Disabling a flag cannot undo an external booking.

[Pilot scorecard](worksheets/pilot-scorecard.csv) · [Six starter eval cases](../evals/booking-cases.csv) · [SRE guidance on canary releases](https://sre.google/workbook/canarying-releases/) · [Model and prompt comparisons](../prompts/model-guide.md)
