---
layout: default
title: "Discovery and baseline"
permalink: /builder-pm/discovery.html
parent: "AI builder PM library"
---

# Discovery and baseline

Interview someone who recently missed a booking, someone who successfully rebooked, and the support team that inherited an exception. Ask each to walk through the last real case. Record where they waited, repeated information or believed the task had finished. Use appropriately redacted evidence.

| Discovery question | Booking example | Decision it changes |
|---|---|---|
| Who has the problem and how often? | Identify eligible missed appointments, including callers who never opened the app. | Which population belongs in the denominator |
| Can a simpler change solve it? | Try a clear link to current slots and a receipt lookup. | Whether a model is needed |
| Where could reasoning help? | Interpret “after school pickup” and ask for the missing time. | Narrow tool scope and when to clarify |
| What is costly when wrong? | A false confirmation sends somebody to a slot they do not have. | A separate release blocker |
| What would convince you to stop? | The existing form resolves as many cases with less handling time. | Whether to keep investing |

**Write the baseline before the brief.** Define an eligible case, the observation window, what counts as verified resolution and how to join a provider receipt to a support case. Include abandoned cases and assisted completions. If you cannot measure a baseline, use a time-boxed manual sample, document the exclusions and give the instrumentation gap an owner.

**Decision record.** “For customers rebooking a missed appointment, we expect the assisted flow to increase verified replacements per eligible case within the agreed window. Start with one partner and one support team. Booking Ops owns reconciliation. Stop expansion after any false confirmation.” Numeric thresholds and sample sizes belong to the team running the pilot.

[Service discovery](https://www.gov.uk/service-manual/agile-delivery/how-the-discovery-phase-works) · [Service Standard](https://www.gov.uk/service-manual/service-standard) · [Journey and service blueprint](../experience/service-design.md)
