---
layout: default
title: "Shadow pilot and human recovery"
permalink: /architectures/references/shadow-pilot-human-recovery.html
parent: "Reference architectures"
---

# Shadow pilot and human recovery

How can the team compare a new agent against the current service without letting the experiment change a customer’s booking?

## Components and ownership

The admission service records the experiment assignment at tenant or case level. The production path retains sole ownership of live writes. The shadow runner receives scoped inputs and calls read-only or simulated tools. A comparison job joins both decisions to the observed outcome. When the authorized pilot expands, a separate support queue owns unknown results.

## Failure and recovery

| Condition | Expected behavior |
|---|---|
| Agent proposes a real write in shadow | The shadow adapter has no live write credentials. Retain the proposed action for grading. |
| Customer changes channel | Use the same case reference and original cohort assignment. |
| Provider times out after a live pilot write | Look up by original request key, mark pending and hand off on deadline. Do not start another independent booking. |

## Acceptance exercise

Run a complete shadow case and prove zero external changes. Then deliberately interrupt one authorized pilot case and ask support to recover it using only the case reference.

[Feature evaluation](https://openfeature.dev/docs/reference/intro/) · [Canary rollouts](https://sre.google/workbook/canarying-releases/) · [Pilot decision process](../../builder-pm/release.md)
