---
layout: default
title: "Live agent control room"
permalink: /prompts/01-control-room.html
parent: "Prompt collection"
---

# Live agent control room

Build a Vercel-hosted, browser-accessible missed-collection recovery desk for dispatch operators and shift supervisors. An operator opens a delayed case, sees two specialists evaluate evidence and policy, and approves a replacement-slot request. Use synthetic supplier references for examples.

Use Next.js App Router, TypeScript, shadcn/ui with Base UI, Tailwind design tokens, TanStack Table for the queue, React Flow 13 for the read-only run graph, and Motion for React for state transitions. Use eve for durable execution, a server-side AI SDK provider adapter, PostgreSQL for cases, events and effect receipts, and OIDC for identity. Resolve supported patch versions and lock compatible dependencies. Provide hosted web and worker configuration, environment-variable names, setup instructions and a labeled fixture replay that runs without provider credentials.

Start on a populated case workspace. On desktop reserve a narrow queue, a flexible execution canvas and an inspector. On mobile offer queue, run, detail navigation. Use an ink/neutral palette and semantic status colors, visible focus, readable time labels and reduced motion. Primary actions are select case, inspect handoff, open evidence, review, approve/decline, cancel, replay, step and return to live. Every control must work. Provide Arabic RTL and a text timeline for the visual graph.

The triage agent routes two real read-only specialists concurrently. Each returns schema-checked evidence references. A deterministic join checks required results before the planner proposes a typed action. Bind the review to an exact proposal digest, expiry and authorized actor. A write adapter executes once per logical effect, records the destination receipt and reconciles an uncertain acknowledgment. Scope tools and retrieval to tenant and principal. Bound steps, elapsed time, spend and fan-out.

Emit committed run events with runId, seq, eventId, stepId, agent, event type, safe summary and evidence references. Allocate per-run sequence in the store. Animate the specific edge on a handoff, update a tool node on start/result and hold at approval. Show a short routing reason and cited inputs. Support cursor reconnect, duplicates, gaps, worker restart and read-only replay. Keep actual provider execution distinct from fixture playback.

Deliver the complete vertical slice, migrations, API and event contracts, original responsive UI, source and reproducible tests. Exercise seeded tenants, both approval outcomes, concurrent review, provider timeouts, cancellation, worker restart and lost effect acknowledgment. Return a trace, screenshot set for desktop/mobile, reduced-motion test, cost per successful test case, actual test outcomes and any external prerequisite. Treat real credentials and deployments as external configuration. Do not portray unconfigured integrations as live.
