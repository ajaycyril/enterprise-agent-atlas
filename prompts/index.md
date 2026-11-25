---
layout: default
title: "Prompt collection"
permalink: /prompts/index.html
nav_order: 7
has_children: true
---

# Prompt collection

**50 task pairs, 100 model-specific prompts and seven original full-project briefs.** Each pair includes a Claude version and a ChatGPT version. The two versions share a concrete output and an acceptance condition.

[Which Claude or ChatGPT model should I use?](model-guide.md) · [Download the paired prompts as JSON](recipes.json)

| Topic | Tasks | Examples |
|---|---:|---|
| [Security foundations](security-foundations-recipes.md) | 8 | Draw the first trust boundary, Design enterprise login and recovery, Map roles to resources |
| [UI and visual design](ui-and-visual-design-recipes.md) | 7 | Choose a component foundation, Specify tokens and visual hierarchy, Design a dense data grid |
| [UX research](ux-research-recipes.md) | 5 | Turn a problem into a research plan, Test information architecture, Run a usability study |
| [Customer experience](customer-experience-recipes.md) | 6 | Map a customer journey, Create a service blueprint, Design onboarding to first value |
| [System architecture](system-architecture-recipes.md) | 5 | Choose monolith or services, Estimate capacity and cost, Design multi-tenant data access |
| [Agent workflows](agent-workflows-recipes.md) | 4 | Choose a bounded harness, Evaluate retrieval and citations, Control tool and model budgets |
| [Delivery and operations](delivery-and-operations-recipes.md) | 3 | Specify an enterprise release gate, Design a pilot and rollout, Plan an incident and support handover |
| [Project building](project-building-recipes.md) | 2 | Write the smallest credible project brief, Choose references for a coding model |
| [Builder PM decisions](builder-pm-recipes.md) | 10 | Fund a pilot, evaluate vendors, track verified outcome cost, govern data, recover customer cases |

## Evaluation prompts

Use the [agent evals guide and six-case dataset](../evals/index.md), [paired model-comparison prompt](agent-workflows-recipes.md#evaluate-prompts-across-models) and [retrieval and citation prompt](agent-workflows-recipes.md#evaluate-retrieval-and-citations) to design the experiment and grade its results.

## Full-project briefs

- [Live handoffs and agent decisions](00-live-agent-motion.md)
- [Live agent control room](01-control-room.md)
- [Python evidence and policy workflow](02-python-casework.md)
- [Multi-day approval and fulfillment](03-durable-approvals.md)
- [Fleet and robotics operations console](04-fleet-operations.md)
- [Evidence-backed enterprise copilot](05-enterprise-copilot.md)
- [Enterprise release review](06-hardening-review.md)
