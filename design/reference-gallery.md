---
layout: default
title: "Reference gallery for a live agent dashboard"
permalink: /design/reference-gallery.html
parent: "Agent interface design"
---

# Reference gallery for a live agent dashboard

Use these existing examples as visual or technical references in a build prompt. Each demonstrates a specific behavior. Pair the animation reference with the event or state change that should trigger it.

| What to study | Existing reference | What to borrow for a prompt |
|---|---|---|
| A message moving along a directed graph edge | [React Flow animated edges](https://reactflow.dev/examples/edges/animating-edges) | Move one labeled packet from Triage to Evidence on the recorded transfer. Keep an accessible text row for the same event. |
| Propagating typed data between nodes | [React Flow computing flows](https://reactflow.dev/learn/advanced-use/computing-flows) | Show which named input a specialist received, the output it produced and the downstream node that consumed it. |
| A structured fan-out / join layout | [React Flow ELK.js example](https://reactflow.dev/examples/layout/elkjs) | Keep parallel specialist nodes aligned. Relayout when topology changes and preserve the operator’s viewport during status updates. |
| State changes on an existing node | [React Flow update-node example](https://reactflow.dev/examples/nodes/update-node) | Preserve node identity while changing from running to retrying or completed. Inspecting one node should keep its position stable. |
| Sequencing the transfer, acknowledgement and inspector reveal | [Motion useAnimate](https://motion.dev/docs/react-use-animate) | Sequence the visual effects inside the component lifecycle and cancel them when the user seeks. |
| High-frequency visual updates without rerendering the entire interface | [Motion values](https://motion.dev/docs/react-motion-value) | Interpolate packet position outside React state. Update business state once per event. |
| Scrub, pause and seek across a recorded workflow | [GSAP Timeline](https://gsap.com/docs/v3/GSAP/Timeline/) and [MotionPathPlugin](https://gsap.com/docs/v3/Plugins/MotionPathPlugin/) | Put presentation labels at recorded event offsets. Reconstruct state first, then play the relevant segment. |
| A hand-authored SVG path | [Anime.js createMotionPath](https://animejs.com/documentation/svg/createmotionpath/) | Animate along a bespoke route between two stations on a fixed process diagram. |
| A waterfall explaining simultaneous tools and wait time | [Jaeger frontend UI](https://www.jaegertracing.io/docs/latest/frontend-ui/) and [OpenTelemetry spans](https://opentelemetry.io/docs/concepts/signals/traces/) | Represent each tool attempt as a time interval. Put waiting for approval on its own row; make it possible to inspect a specific span. |
| Dense particle traffic | [PixiJS particle example](https://pixijs.com/8.x/examples/basic/particle-container) | Sample transfer sprites under load, preserve counts and expose individual records through the inspector. |
| Reduced-motion presentation | [Motion reduced-motion hook](https://motion.dev/docs/react-use-reduced-motion) | Replace moving tokens with stationary arrows, sender/recipient names and a timestamped handoff list. |
| An operations-console composition | [AgentOps Control Center design reference](https://dribbble.com/shots/27727862-AgentOps-Control-Center-Platform-Design) | Reference the hierarchy of queue, workspace and detail. Describe the desired behavior independently and create an original layout. |

## Three prompts with the right vocabulary

**A live handoff**  
“On a durable handoff from Triage to Policy, traverse the React Flow Bézier edge once with a labeled request packet. Reveal the recipient, selected route, safe payload fields and evidence. Leave the other specialist running until its result arrives.”

**A decision the operator can inspect**  
“Pair the agent graph with a trace waterfall. Selecting the route opens the decision summary, evidence IDs, applicable policy and next action. Show tool attempts as child spans, and show the human approval wait as a separate interval.”

**A replay that explains concurrency**  
“Use a GSAP timeline keyed to stored event offsets. Let me pause while the evidence call retries, inspect the policy result that arrived first, then step into the join. Scrubbing changes the view only.”
