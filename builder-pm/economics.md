---
layout: default
title: "Unit economics for an AI pilot"
permalink: /builder-pm/economics.html
parent: "AI builder PM library"
---

# Unit economics for an AI pilot

Count verified outcomes and every cost incurred to produce them. Mixing successful calls with resolved cases is an easy way to make a weak pilot look cheap.

Both illustrative cohorts below have 1,000 eligible cases and the same observation window. A verified resolution requires a valid reservation receipt. The pilot counts assisted and unassisted resolutions together. Keep that split in your own report.

| Item in AED | Current service | Assisted pilot |
|---|---:|---:|
| Model and tool charges including repeated attempts | 0 | 400 |
| Allocated platform cost | 100 | 150 |
| Human follow-up at AED 2 per minute | 600 minutes × 2 = 1,200 | 300 minutes × 2 = 600 |
| Total delivery cost | 1,300 | 1,150 |
| Verified resolutions | 800 | 850 |
| Cost per verified resolution | 1.625 | 1.353 |

On these assumptions, 50 more cases resolve, 300 handling minutes are released and delivery cost drops AED 150 per 1,000 eligible cases. Saved handling time only becomes cash savings if staffing spend actually changes. Track capacity released separately. At a fixed 850 pilot resolutions and AED 550 of non-human cost, approximately **416 human minutes** would bring the pilot back to the baseline cost per resolution. An increase in escalation time can erase the apparent advantage.

**Include before you scale.** Add implementation and migration costs, on-call, review of errors, idle capacity and commitments where relevant. If a cost is omitted, name it. For a pilot decision, distinguish marginal cost on current capacity from fully loaded cost at target volume. Report volume, peak concurrency, failures and human time with every estimate. If zero cases resolve, report the total spend and mark cost per success undefined.

[Worked cost data](worksheets/unit-economics.csv) · [FinOps unit economics](https://www.finops.org/framework/capabilities/unit-economics/) · [FOCUS billing specification](https://focus.finops.org/focus-specification/)
