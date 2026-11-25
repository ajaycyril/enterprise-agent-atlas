---
layout: default
title: "Metered AI service and tenant budgets"
permalink: /architectures/references/metered-ai-service.html
parent: "Reference architectures"
---

# Metered AI service and tenant budgets

An AI supplier bills per attempt. Your customer pays per completed case. How do you reconcile those units without billing twice?

## Components and ownership

The request API resolves the tenant and checks its admission budget. The worker records attempts under a stable case ID. A receipt verifier writes a single billable outcome to a ledger with a uniqueness rule for the contracted unit. An asynchronous export feeds the billing service. Finance reconciles provider spend, credits and final outcomes separately. An idempotency key identifies the command and a receipt identifies the outcome.

## Failure and recovery

| Condition | Expected behavior |
|---|---|
| Duplicate provider callback | Record receipt once. Replayed delivery leaves the amount unchanged. |
| Budget reached mid-run | Stop new optional calls and route an unresolved case to the owed follow-up. Preserve the existing receipt lookup. |
| Late credit or cancellation | Record an adjustment linked to the original entry. Preserve the audit history and expose the customer-visible total. |

## Acceptance exercise

Give Finance two attempts, one receipt and a later credit. It should be possible to explain the invoice, model spend and customer outcome without joining raw prompts.

[OpenMeter](https://openmeter.io/docs) · [FinOps unit economics](https://www.finops.org/framework/capabilities/unit-economics/) · [Worked cost model](../../builder-pm/economics.md)
