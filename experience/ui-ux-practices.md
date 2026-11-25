---
layout: default
title: "UI and UX decisions for enterprise products"
permalink: /experience/ui-ux-practices.html
parent: "UI, UX and CX"
---

# UI and UX decisions for enterprise products

| Design decision | Concrete direction for a build brief | How to review it |
|---|---|---|
| Information architecture | Name the user's task, the object they act on and the next action. Design a stable queue → case → evidence hierarchy with shareable links. | Ask a first-time operator to find a blocked case using only the visible navigation. |
| Visual hierarchy | Use typography, alignment, whitespace and a single dominant task per region. Reserve high-salience color for state and consequence. | At a glance, identify the active case, current owner, current status and available decision. |
| Density | Offer compact rows on desktop, a readable default and detail on demand. Preserve the selected row when filters change. | At 200% zoom and a narrow width, critical actions and evidence remain reachable. |
| Tokens | Name semantic colors, type, spacing, elevation and motion durations. Define light, dark, high-contrast and reduced-motion behavior. | Change a semantic token once and inspect buttons, graph, overlays and charts together. |
| Navigation and input | Choose data grids for cell-level work and semantic tables for reading. Define focus order, arrow keys, exit, selection and touch alternatives. | Complete the critical workflow without a pointer. Verify a screen reader announces names, states and errors. |
| Forms and validation | Group fields by decision, preserve entered data, show a summary linked to fields and validate server-side. | Trigger multiple errors and finish the correction without reentering valid information. |
| Content | Use action verbs with a clear object. State what happened and how to recover. Translate business codes into language customers understand. | Compare “Submit” with “Confirm replacement slot” in context. Test the translated version with native speakers. |
| States | Specify first-use, loading, partial, stale, denied, empty, no-results, offline, failed, complete and undoable actions. | Each state identifies what is known, the next action and what the system is waiting for. |
| Accessible motion | Animate routing, changes of ownership or confirmed progress. Provide text alternatives and permit pause, replay and reduced motion. | A reviewer can reconstruct the same event order without viewing or interpreting motion. |
| Multilingual and RTL | Mirror navigation where appropriate and use logical layout properties. Isolate embedded IDs, phone numbers and mixed-direction text. | Use real translated strings, text expansion, mixed Arabic/English, localized dates and 24-hour times. |
| Consequential actions | Show the exact proposed change and affected resources, provide recovery/undo when feasible and show a receipt. | An expired or already resolved decision explains the current state and offers the appropriate next action. |
| Handoff to engineering | Attach component states, data contracts, interaction rules, breakpoints, tokens, keyboard paths and test cases to the design. | The implemented screen can be reviewed against actual states and sample data, including errors. |

[WCAG 2.2](https://www.w3.org/TR/WCAG22/) · [ARIA patterns](https://www.w3.org/WAI/ARIA/apg/patterns/) · [WAI forms tutorials](https://www.w3.org/WAI/tutorials/forms/) · [GOV.UK error summary](https://design-system.service.gov.uk/components/error-summary/) · [W3C internationalization](https://www.w3.org/International/techniques/authoring-html) · [Heuristic evaluation principles](https://www.nngroup.com/articles/ten-usability-heuristics/)

## A short acceptance script

A supervisor receives a link to a case. Have them explain the current state, verify why the evidence branch retried and identify the proposed replacement. Let a second reviewer resolve the case before the first submits. Observe whether the supervisor understands the conflict and can confirm the final receipt. Repeat with keyboard only, reduced motion and the smallest supported viewport. Record task outcome, time, hesitations, wording problems and the consequence of any mistake.

Use these observations to prioritize by customer impact and recoverability. Visual inconsistency and a confusing action that changes a real booking deserve different severities. Report what the participant actually did separately from the team's interpretation.
