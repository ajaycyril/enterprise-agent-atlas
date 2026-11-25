---
layout: default
title: "Design a service customers can finish"
permalink: /experience/service-design.html
parent: "UI, UX and CX"
---

# Design a service customers can finish

An interface can succeed at form submission while the customer still misses an appointment. Start with the outcome the customer recognizes. For a replacement booking, success means an understandable confirmation for a usable slot, a way to change it and a support team that can see the same commitment. Use the journey map to understand that outcome, a service blueprint to assign operational work and a task flow to design each interaction. [Service blueprinting](https://www.nngroup.com/articles/service-blueprints-definition/) · [Journey mapping](https://www.nngroup.com/articles/journey-mapping-101/)

## From discovery to release

| Decision | Method and artifact | What makes the result usable |
|---|---|---|
| Whose problem deserves a solution? | Interview customers and frontline staff. Map their current workaround, trigger, outcome and constraint. | Label direct observations, interpretations and open questions. Include an infrequent or assisted-channel user. |
| Where does the current service break? | Map stages from discovering the need through resolution. Put process evidence and complaint themes beside each stage. | Each failure has an affected cohort, frequency estimate or “unknown,” owner and recovery path. |
| How will customers find the right action? | Card-sort ambiguous labels, then tree-test a realistic task without visual hints. | Compare findability, wrong turns and confidence. Include language people actually use. |
| Which interaction deserves prototyping? | Pick the highest-risk action. Use a low-fidelity prototype before styling. | Give a participant a goal and realistic data. Observe completion, hesitation, backtracking and support requests. |
| What can be learned from a rollout? | Define a goal, signals and measures before changing the interface. | Record denominator, baseline, window, segmentation, owner and what action a change would trigger. |

[18F Methods](https://guides.18f.org/methods/) · [GOV.UK user research](https://www.gov.uk/service-manual/user-research) · [HEART](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/)

## Worked service blueprint

An illustrative missed-collection case ties the customer's experience to the operator's agent dashboard.

| Stage | Customer and frontstage | Backstage responsibility | Failure and recovery | Observable measure |
|---|---|---|---|---|
| Report | Customer chooses the missed appointment, sees what information is needed and receives a reference. | Intake resolves account access and deduplicates retries. | Connection drops after submit. Reopening the reference shows the accepted request. | Unique accepted reports / attempted reports, with retries deduplicated. |
| Investigate | A status page explains which checks are underway and when to expect the next update. | Two scoped specialists independently check the service rule and carrier evidence. | Evidence is missing. An owner requests the specific document or takes over the case. | Time to first meaningful update and age of blocked cases. |
| Resolve | The customer sees the proposed slot, timezone and change/cancel options. | Reviewer checks the exact proposal; scheduling adapter verifies the reservation receipt. | The slot is lost during approval. Offer current alternatives without making a false promise. | Confirmed usable slots / approved proposals. |
| Follow through | Confirmation, reminders and assisted support all show the same reference and current status. | Support reads an authorized service timeline and owns unresolved exceptions. | Notification fails after reservation. Retry the notification independently and preserve the reservation. | Repeat contact per resolved case and successful delivery of confirmation. |

## Customer experience prompts worth making specific

- **Onboarding:** distinguish identity checks, task setup and first value. Ask for the fields genuinely required at each point. Measure first successful task and the support burden created by the change.
- **Customer communication:** write the status, what happened, what the customer can do and when a human will respond. Use an explicit timezone and avoid promising a resolution the backend has not confirmed.
- **Assisted service:** give a support agent the prior context, a verified identity boundary and a case owner. Give the customer a transfer reference, expected wait and a way to resume asynchronously.
- **Trust and consent:** place the explanation at the point of collection or consequential action. Show what the service needs, why, how to change the choice and which features depend on it.
- **Measurement:** completion rate can improve when difficult users leave earlier. Pair it with abandonment by stage, repeat contact, time to resolution, reopen rate and accessibility task success. Treat missing measures as research questions.

[Service measurement](https://www.gov.uk/service-manual/measuring-success) · [Inclusive design](https://inclusive.microsoft.design/) · [Experience prompt collection](../prompts/index.md)
