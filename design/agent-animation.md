---
layout: default
title: "Agent interface design"
permalink: /design/agent-animation.html
nav_order: 4
has_children: true
---

# Animate an agent at work

## The stack I would specify

For a browser-based agent console with dozens of visible nodes, choose **React Flow 13 + Motion for React + an ordered run-event stream**. React Flow owns topology, viewport, selection and edge geometry. Motion owns a short, interruptible transition when a concrete event arrives. The worker or workflow owns run state. A message can arrive late, fail or be retried without the canvas inventing a successful handoff. Add ELK only when topology needs automatic layout. [React Flow animated edges](https://reactflow.dev/examples/edges/animating-edges) · [Motion](https://motion.dev/docs/react) · [ELK.js](https://github.com/kieler/elkjs)

## Which engine for which job?

| Pick | Choose it for | Concrete prompt phrase | Tradeoff / adoption trigger |
|---|---|---|---|
| React Flow 13 + Motion | Interactive operator graph, branching, hover/click inspection, tool lifecycle | “Use custom React Flow edges. Advance one SVG packet along the actual Bézier path on message delivery. Use Motion for enter/exit and lifecycle cleanup.” | Best first choice for a React dashboard. Keep topology stable, subscribe narrowly and profile on the target hardware. [Example](https://reactflow.dev/examples/edges/animating-edges) · [Motion values](https://motion.dev/docs/react-motion-value) |
| GSAP Timeline + MotionPathPlugin | A curated replay, long timeline, synchronized camera and packet paths | “Label the timeline with event IDs. Pause, seek and restore state from the event log. Bind the packet to the route path.” | Strong when authoring and scrubbing are central. Give GSAP sole control of its animated elements and retain a separate business reducer. [Timeline](https://gsap.com/docs/v3/GSAP/Timeline/) · [MotionPath](https://gsap.com/docs/v3/Plugins/MotionPathPlugin/) |
| Anime.js SVG utilities | Custom SVG decision tree, paths that draw or morph as a plan changes | “Draw a new branch only when the plan revision introduces it. Move its envelope once on delivery.” | Lighter conceptual fit for a hand-drawn bespoke diagram. You own graph layout, keyboard controls and inspection. [SVG utilities](https://animejs.com/documentation/svg/) |
| Native Web Animations API | Modest transitions in an existing UI where extra dependencies are undesirable | “Use element.animate for the acknowledgement flash. Store its handle and cancel on unmount or seek.” | Good for a handful of cues. A sophisticated replay requires your own orchestration and cleanup. [API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API) |
| D3 transitions | Span waterfall, event-rate chart, p95 latency bands and changing chart geometry | “Key spans by ID, scale bar width by actual duration and preserve rows as new spans arrive.” | Use inside a dedicated chart subtree. A chart animator alone gives you no interactive graph editor. [Transitions](https://d3js.org/d3-transition) |
| PixiJS | Many simultaneous moving packets over a canvas, fleet or network | “Profile SVG first. If the target workload misses budget, batch visible packet sprites, sample counts and expose the precise ledger beside the canvas.” | Extra renderer, hit testing, coordinate mapping and accessibility work. Measure before switching. [Particle container](https://pixijs.com/8.x/guides/components/scene-objects/particle-container) |
| Sigma.js | Very large relationship networks where graph overview is itself the task | “Use WebGL for network overview. Drill into the selected run for its precise events and artifacts.” | Choose when relational exploration dominates. Retain a separate accessible inspector. [Sigma.js](https://www.sigmajs.org/) |
| Rive / dotLottie | Authored robot, device or agent illustrations with a small state vocabulary | “Bind the device illustration to idle, active or error. Put evidence, recipient and action in adjacent text.” | Useful for authored assets. You still need data, layout and transport for real exchanges. [Rive](https://rive.app/docs/runtimes/web/web-js) · [dotLottie](https://developers.lottiefiles.com/docs/dotlottie-player/dotlottie-web/) |

## Agent events as an animation score

| Runtime fact | Show it | Click or focus reveals |
|---|---|---|
| Triage selects a route | Selected edge gains contrast, active agent and destination receive names. One directional packet travels from sender to recipient. | Decision code, concise explanation grounded in visible inputs, policy revision and source record IDs. |
| Two reads run concurrently | Both branches stay active until their own results return. Lay out related branches at the same rank. | Distinct input envelope, agent identity, start time and tool scope for each branch. |
| A specialist sends data | Show payload *type* on the edge and short-lived direction cue. Keep payload details in the inspector. | Safe field names, selected values, sender, recipient, evidence ID, event sequence and attempt. |
| A tool call stalls or retries | Node remains running, then shows retry with attempt count. Give failure an icon and label. | Last error category, elapsed time and remaining budget. A timeout after a write shows an uncertain state. |
| A branch finishes early | Its node changes to completed. The join still displays “1 of 2 results”. | Actual receipt and which result is still missing. |
| A decision requires a human | Hold the workflow, surface the proposed change and focusable review action. Stop continuous decorative motion. | Exact proposal, evidence, required grant and expiry. Show competing decisions as already resolved. |
| A model streams an explanation | Batch incremental public response text. Display a short, sourced decision summary once validated. | Supporting artifact or policy. Privileged reasoning, credentials and raw tool outputs stay outside this feed. |
| The user seeks or reconnects | Recompute persistent states through the cursor. Suppress historical transfer effects during a jump and avoid repeat announcements. | Sequence, cursor position, stream health and a link back to the current run. |

## Production adaptation

- **Arrival and rendering clocks.** A server event establishes order. The animation clock just draws the transition. A burst can produce forty valid transfers in one frame. Aggregate visual pulses by edge and show “×40”; preserve every logical event in the ledger.
- **Replay.** Store snapshots and event offsets. Play at the chosen rate, step exactly one event, seek to a sequence, then resume. Replay performs no tool calls. For a historical waterfall, use measured timestamps; show clock uncertainty if workers have different clocks.
- **Inspection.** Keep an operator's selected edge pinned while live events continue. Add an explicit “follow latest” action. Hide sensitive fields before events leave the server. A decorative pulse must never be the only way to discover a handoff.
- **Motion accessibility.** Respect prefers-reduced-motion and an explicit motion switch. Replace travelling packets with a persistent directional highlight and readable event row. Announce phase changes only. Provide keyboard access to every event and inspector.
- **Scale test.** Proposed test loads: 25/100/500 visible nodes, 5/25/100 delivered events per second, plus a 3-second burst. Use representative mobile and operator devices. Record input responsiveness, long frames, DOM nodes, dropped visual cues, end-to-end event lag and ledger completeness. Escalate to canvas/WebGL only on measured evidence.
- **Transport.** Adapt documented SDK events to your versioned business envelope. Surface `route.selected`, `step.handoff`, `tool.retry`, `step.completed`, `approval.requested`, and `effect.confirmed` as concepts; adopt the exact names your schema supports. Capture shared references to run, step, sender, recipient, safe payload summary and evidence. Distinguish a requested tool call from its verified result.

[Motion reduced motion](https://motion.dev/docs/react-use-reduced-motion) · [React Flow Bézier paths](https://reactflow.dev/api-reference/utils/get-bezier-path) · [SSE](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events) · [Agent tracing](https://openai.github.io/openai-agents-python/tracing/)

## Build-brief fragment

> On the first screen, show the active case and the agent performing work. Implement React Flow 13 custom nodes and edges and Motion for React. Drive a one-shot packet along each actual sender-to-recipient path on a committed transfer event. Two concurrently active specialists must be independently selectable. Each exchange reveals a sanitized payload, routing reason, source artifacts and outcome. Include retry, partial join, approval wait and receipt states. Add pause, one-event step, seek, follow-latest and reduced motion. Verify that repeating the same event ID never animates twice during live delivery, an early result never completes a pending join, and reopening a historical run never dispatches a tool.
