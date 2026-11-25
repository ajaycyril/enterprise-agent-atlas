---
layout: default
title: "Live handoffs and agent decisions"
permalink: /prompts/00-live-agent-motion.html
parent: "Prompt collection"
---

# Live handoffs and agent decisions

Build an event-driven operator console for an AI agent investigating a missed service pickup. Make the agent at work the first screen. Present a case queue, interactive graph, chronological text timeline and exchange inspector. Use React Flow 13 for topology and edge geometry, Motion for React for one-shot state transitions, and shadcn/ui on Base UI for the surrounding application. Use automatic ELK layout only on topology changes. Keep the operator's viewport and inspection selection stable as events arrive.

Implement actual server-side execution in the configured environment. Use one harness, eve for a TypeScript/Vercel app or LangGraph with a persistent checkpointer for Python. Name the chosen runtime and do not stack both. Register an evidence lookup and policy check as distinct, read-only specialist tools. Triage chooses a route and delegates. Both workers can be active simultaneously. Persist their actual tool inputs, scrubbed output references, timestamps, attempts and outcome. Verify the join before proposing a scoped action. If model credentials are missing, expose a separately labeled fixture replay or local worker demonstration.

Implement typed business events. A handoff identifies the sender, recipient, reason code, safe payload fields and evidence references. A completed read carries its result, elapsed time and attempt. An approval event carries the proposed change, revision, expiry and reviewer grant. An effect is complete only after a verified receipt. Show concise decision summaries and the evidence that led to a route. Keep raw private reasoning and unredacted tool arguments outside the UI.

Implement custom SVG edges in React Flow. On a new handoff event, use Motion to move a single packet along the real Bézier edge. Highlight the recipient and expose the payload type in the inspector. Completed branches retain their outcome while the join waits. Approvals stop the moving packets. A retry shows the same logical step with its new attempt. A timeout after a write enters reconciliation. A disconnected stream shows its cursor and recovers gaps. On bursts, coalesce visual pulses while retaining every ledger event.

Deliver play, pause, seek, single-step, replay, follow latest, source drill-down, approval and rejection. Reduced motion uses a stationary arrow, plain-text status and chronological events. Keyboard and mobile users must be able to inspect any transfer and take the same decision. Add tests for two parallel workers, denied review, duplicated/late events, restart during approval, no effects during replay and a recorded receipt after an approved action. Demonstrate the complete browser journey and return actual outcomes, unsupported integrations and measured frame performance under a stated workload.
