---
layout: default
title: "Interface and service acceptance"
permalink: /builder-pm/experience.html
parent: "AI builder PM library"
---

# Interface and service acceptance

An operator needs enough evidence to act while a customer needs to know whether their appointment moved. Sketch those two views separately before asking a coding assistant for the UI.

| Runtime event | What the customer sees | What the operator can inspect |
|---|---|---|
| Proposal created | Proposed slot, expiry and a chance to change it | Source, permitted action and proposal revision |
| Approval saved | Request submitted and reference number | Approver, bound revision, effective permissions check |
| Provider times out | Pending and a follow-up route | Attempt, deadline, retry owner and lookup status |
| Receipt reconciled | Confirmed time and retrievable receipt | Provider reference and reconciliation time |
| Slot is gone | Existing choices retained and available alternatives | Business conflict, next action and ownership |

For a small operator graph, start with React Flow and Motion. Animate an actual handoff when the receiver records it. A customer screen usually needs a text status. An event sequence or cursor lets a reconnected browser recover from a persisted snapshot and show what it missed. Distinguish an interrupted connection from a failed booking.

**Run the acceptance review with real constraints.** Give a reviewer the keyboard, switch motion off, increase text size and change to Arabic. Ask them to find the current state, inspect evidence and decline an expired proposal without a mouse. Trigger a delayed confirmation after navigation. Check whether focus stayed stable and whether the support agent can retrieve the same case without a transcript.

[Interaction references](../design/agent-animation.md) · [Accessible component patterns](https://www.w3.org/WAI/ARIA/apg/) · [WCAG 2.2](https://www.w3.org/TR/WCAG22/) · [GOV.UK check answers](https://design-system.service.gov.uk/patterns/check-answers/)
