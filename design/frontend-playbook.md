---
layout: default
title: "Frontend patterns you can name in a prompt"
permalink: /design/frontend-playbook.html
parent: "Agent interface design"
---

# Frontend patterns you can name in a prompt

For an operations product, the first screen should answer three questions. Which case needs attention? What is the agent doing? What can the operator do next? Start with a case in progress, a selectable decision and an evidence record. Reserve aggregate metrics for the reporting screen.

## Choose the component foundation

| Product context | Starting point | What changes your choice |
|---|---|---|
| Distinctive React product with a small design team | shadcn/ui + Base UI + Tailwind tokens | Maintain an existing Radix foundation if the app already depends on its composition and focus conventions. [shadcn changelog](https://ui.shadcn.com/docs/changelog/2026-07-base-ui-default) |
| Internationalized forms and complex keyboard-selectable collections | React Aria Components with the team's theme | Budget time for styling and manual assistive-technology testing across locales. [React Aria](https://react-aria.adobe.com/) |
| Internal platform with established enterprise conventions | Carbon or Material UI, chosen to match the organization | Adopt one system's density, overlay and navigation conventions per product. [Carbon](https://carbondesignsystem.com/) · [Material UI](https://mui.com/material-ui/getting-started/) |
| Analyst grid with pivot, grouping or Excel export | AG Grid with the relevant edition | For a branded queue and simple server filters, TanStack Table gives more control over rendering. [AG Grid editions](https://www.ag-grid.com/react-data-grid/community-vs-enterprise/) · [TanStack Table](https://tanstack.com/table/latest) |

## An agent control room

| Surface | Implementation vocabulary | Observable acceptance test |
|---|---|---|
| Case queue | TanStack Table, URL-backed filters, stable case IDs, cursor pagination, persistent selected row | Select a run, change a filter, navigate back. The previous selection and filters are restored. |
| Run canvas | React Flow custom nodes and labeled edges. Use ELK for topology layout, Motion for active transitions. Persist the user's viewport. | Two specialist branches are simultaneously active. A new event updates one node without resetting pan or zoom. |
| Decision inspector | shadcn Sheet or inline detail pane with reason code, evidence, policy version, actor and timestamps | Selecting an edge opens the decision that produced it. Escape returns focus to that edge or its equivalent timeline row. |
| Tool activity | AI Elements tool card or your component kit's disclosure. Include duration, attempt, status and scrubbed result. | A retry appears as attempt two on the same logical invocation. Expanding the first attempt still shows its outcome. |
| Approval | Dialog with requested change, scope, evidence and expiry. Recheck policy server-side on submit. | Two reviewers act concurrently. Only one decision applies, and both screens converge on the recorded outcome. |
| Trace and replay | Ordered, virtualized timeline for long runs. Play, pause, step, seek and return to live. Render from the same event reducer. | Pausing replay freezes the cursor while new events accumulate. Returning to live catches up without resubmitting a tool call. |
| Operational chart | ECharts duration distribution and queue wait series with units, date ranges and missing-data state | A gap stays visible when telemetry is unavailable. The accessible table gives the numbers plotted. |
| Fleet map | MapLibre base map, deck.gl path or scatter layers, list linked by asset ID | Selecting a site on either surface opens the same run. A user can complete the task with the map closed. |
| Copilot | assistant-ui or AI Elements thread scoped to the selected case, evidence links into the inspector | Switching tenants clears the previous thread. An unavailable citation is explained and the answer remains readable. |
| Responsive/RTL | Desktop split panes; on small screens queue → run → inspector navigation; logical CSS and bidi-safe identifiers | At 390 px and 200% zoom approval and cancel remain reachable. Arabic layout mirrors navigation while IDs and timestamps remain legible. |

Sources for implementation patterns: [graph examples](https://reactflow.dev/examples), [motion examples](https://motion.dev/examples), [AI Elements](https://elements.ai-sdk.dev/), [virtualization](https://tanstack.com/virtual/latest), [accessibility guidance](https://www.w3.org/WAI/standards-guidelines/wcag/).

## Motion direction for the build brief

| Trigger | Proposed behavior | Reduced motion or impairment fallback |
|---|---|---|
| Run accepted | A queued label becomes running when the worker starts. Keep the same node dimensions. | Update the status word and icon. Announce the phase once. |
| Specialist handoff | On the persisted handoff event, trace the source-to-target edge once over roughly 300 ms. Target shows the receiving specialist. | Static directional arrow and a timestamped “Triage assigned Policy” row. |
| Fan-out and join | Start each branch from its own event. Keep the join waiting until its required results arrive. | List completed/required branches. A failed branch shows the retry or terminate action. |
| Tool progress | Show the actual elapsed time. Use determinate progress only when the tool reports a denominator. | Text with start time, elapsed time and status. |
| Approval pending | Hold the selected node and expose its action; stop motion while waiting. | Focusable review action with owner, expiry and proposed change. |
| Drawer or insertion | Use transform and opacity for a short 160–220 ms transition. Preserve reading position as rows arrive. | Skip travel. Preserve focus and the user's scroll anchor. |

Timings are proposed design values. Profile them on a target device. Use Motion for state transitions, GSAP for a separately authored scroll explainer, and Rive for a designed interactive illustration. Persisted timestamps determine ordering in a replay. [Motion](https://motion.dev/docs/react) · [GSAP](https://gsap.com/docs/v3/Plugins/ScrollTrigger/) · [Rive](https://rive.app/docs/runtimes/web/web-js)

## Visual references worth pointing a coding agent to

| Specific reference | Borrow this pattern | State the constraint |
|---|---|---|
| [AgentOps Control Center concept](https://dribbble.com/shots/27727862-AgentOps-Control-Center-Platform-Design) | Composition inspiration for an operator workspace | Design an original screen. A concept image provides no runtime, accessibility or failure behavior. |
| [Carbon patterns](https://carbondesignsystem.com/patterns/overview/) | Table action hierarchy, progressive disclosure and status language | Put the most common operator action in context. |
| [GitLab Pajamas](https://design.gitlab.com/) | Dense developer workflows and consistent status semantics | Carry one status vocabulary through list, graph and history. |
| [GOV.UK patterns](https://design-system.service.gov.uk/patterns/) | Check answers, errors and confirmation in high-consequence forms | Explain the proposed change in plain language before commit. |
| [shadcn blocks](https://ui.shadcn.com/blocks) | Working shell and sidebar implementation | Define the navigation around real tasks and keep only working controls. |
| [React Flow examples](https://reactflow.dev/examples) | Custom nodes, edges, layout, interaction and controls | Supply an ordered event fixture and equivalent keyboard-accessible timeline. |
| [Motion examples](https://motion.dev/examples) | Layout transitions and coordinated appearances | Attach each movement to a named interaction or persisted event. |
| [AG Grid example](https://www.ag-grid.com/example/) | Spreadsheet interaction, selection, tool panels and density | Select only the column operations the role needs. Verify edition rights. |

## Copy this frontend direction

> Build a three-pane case workspace using shadcn/ui on Base UI, TanStack Table and React Flow 13. The selected case shows a triage agent delegating evidence and policy checks in parallel. Each edge animates once on a recorded handoff. Selecting it opens the scrubbed decision summary and supporting evidence. Keep a text timeline beside the graph. Show retry, denied, expired approval, reconnect and replay states. On mobile, move the inspector into a sheet. Demonstrate the same journey using keyboard controls, Arabic layout and reduced motion. Return browser-test evidence and the component-to-event mapping.
