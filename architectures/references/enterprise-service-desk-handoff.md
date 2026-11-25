---
layout: default
title: "AI assistant and service-desk handoff"
permalink: /architectures/references/enterprise-service-desk-handoff.html
parent: "Reference architectures"
---

# AI assistant and service-desk handoff

A user hands a failed digital interaction to a call-center agent. What is the smallest record that lets the conversation continue?

## Components and ownership

The customer UI creates an opaque case reference. A case service links it to tenant, booking revision, user-visible status and recovery owner. A support adapter creates or updates one ticket for that case. The operator authenticates to see scoped evidence and can execute only the policy-approved next step. Receipt reconciliation updates the same case across channels.

## Failure and recovery

| Condition | Expected behavior |
|---|---|
| Support ticket creation times out | Persist handoff intent, retry by case key and reconcile ticket identity. |
| Operator changes team mid-case | Recheck access on open and at any subsequent write. |
| Two operators handle the same exception | Use a case version and conditional transition. Give the losing operator current state and a safe next action. |

## Acceptance exercise

Switch from an Arabic mobile session to a support call while a receipt is pending. The reviewer must find the current status without copying conversation history, resolve one case and prove which message the customer received.

[GOV.UK Service Standard](https://www.gov.uk/service-manual/service-standard) · [OpenFGA modeling](https://openfga.dev/docs/modeling/getting-started) · [Service blueprint](../../experience/service-design.md)
