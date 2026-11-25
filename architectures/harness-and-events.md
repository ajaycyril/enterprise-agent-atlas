---
layout: default
title: "The agent harness and its public trace"
permalink: /architectures/harness-and-events.html
parent: "Reference architectures"
---

# The agent harness and its public trace

An agent harness owns the loop around the model. It assembles context, chooses allowed tools, validates requests, executes approved work, records outcomes and decides when to stop. Orchestration defines how components hand work to each other. A durable runtime remembers progress through restarts and long waits. Name who owns each responsibility before choosing libraries. [LangGraph overview](https://docs.langchain.com/oss/python/langgraph/overview) · [AgentCore harness and runtime](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/harness-vs-runtime.html)

## One case from intake to receipt

A supplier reports a missed collection. The operator needs to know what happened and whether a replacement slot can be requested. The triage agent routes reads to an evidence specialist and a policy specialist. They operate independently and have no write tool. The proposal names the slot, the applicable policy and source records. An authorized reviewer can approve or decline it. An action adapter applies the approved change and records the external receipt.

| Step | Owner and input | Output the UI may show | Failure path |
|---|---|---|---|
| Admit | API resolves tenant and subject from session, validates business input and idempotency key | Run ID, queued state, first cursor | Prior matching command returns the original run. Same key with different input returns a conflict. |
| Route | Triage receives scoped case summary and a fixed tool catalog | Route code, brief decision summary and cited evidence references | Unrecognized route goes to manual triage. |
| Delegate | Harness budgets two parallel read-only branches | Parent step, receiving agent, start time, correlation ID | Timeout returns a typed outcome. Only the failing read retries within its budget. |
| Join | Deterministic join verifies evidence and policy results belong to the same run and revision | Two received artifacts, completeness and missing items | Missing required evidence blocks proposal and identifies a responsible operator. |
| Propose | Planner returns a schema-valid action; server resolves resource, scope and parameters | Redacted diff, evidence IDs, approval policy and expiry | Reject fields outside schema or user authority. |
| Review | Server checks reviewer role, tenant, version, expiry, action hash and current policy | Approved, declined, already resolved or expired | Compare-and-swap resolves races. An edited proposal requires a new review. |
| Act | Adapter uses scoped workload identity and a stable effect key | Attempt number, duration, receipt reference or uncertain state | Reconcile after timeout. Check for a confirmed receipt before another write. |
| Close | Harness verifies required receipts and terminal outcome | Completion reason, final summary, cost, duration and replay | Unknown external outcome keeps the case in reconciliation. |

Each specialist publishes inspectable inputs, outputs, source references and a short decision summary. Keep private model reasoning and raw prompts out of the operator feed. Audit, developer diagnostics and the user-facing timeline have different readers and retention needs. [Sensitive telemetry](https://opentelemetry.io/docs/security/handling-sensitive-data/) · [Logging](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)

## Runtime contract

| Capability | Implement this behavior |
|---|---|
| State | Track tenant, case, run, workflow revision, attempt and checkpoint. Pin a running workflow to a compatible revision. |
| Context | Fetch only ACL-visible evidence. Tag source, revision, timestamps and expiry. Compact long threads into scoped summaries; keep canonical evidence intact. |
| Routing | Define route names and permitted transitions. A deterministic controller validates each proposed next step. |
| Tool registry | Store name, input and output schema, required grant, effect type, timeout, allowed destinations, policy and owner. Recheck grants on invocation. |
| Memory | Short-term state belongs to a run. Cross-run memory needs a scoped namespace, purpose, expiry, deletion path and provenance. |
| Budgets | Enforce step, token or currency, deadline, branch fan-out, retry and concurrency caps server-side. Exceeding a cap emits a terminal or manual-review event. |
| Cancellation | Stop scheduling new work, propagate cooperative cancellation and reconcile any remote action already in flight. |
| Transport | HTTP commands express intent. The browser receives scrubbed events by SSE and sends the last accepted sequence on reconnect. |
| Authentication | Authorize the run, tenant and event stream. A cursor or trace ID is an identifier. Revalidate permissions on reconnect and sensitive events. |
| Observability | Attach run and step correlation to spans, store model and policy versions in audit records, aggregate bounded metric dimensions. |
| Evaluation | Compare route, allowed tools, evidence support, durable recovery and business outcome. Record time, cost and approval correctness. |

[OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/) · [MCP architecture](https://modelcontextprotocol.io/docs/learn/architecture) · [SSE](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)

## Five orchestration patterns

| Pattern | Natural use | Cost or failure to budget for |
|---|---|---|
| Bounded single-agent loop | One assistant with a small read-only tool catalog | Set step limit and verify evidence before answering. |
| Router and specialist | Billing versus scheduling need different grants and data | Evaluate route confusion, define a fallback and carry the user scope through handoff. |
| Parallel fan-out and join | Evidence lookup and policy lookup can run independently | Bound parallelism, set a join deadline and declare required versus optional results. |
| Proposer and verifier | A consequential proposal needs an independent check | Use objective business rules or labeled evaluation. A second model may repeat the same mistake. |
| Long-lived approval or saga | Cross-system changes, human wait and partial failures | Persist the exact proposal revision. Track completed effects, compensation eligibility and unresolved cases. |

## Browser projection

For the public trace, identify the tenant, run, step, event, sender, recipient, timestamp, event type, safe payload summary and evidence references. Events are committed with a monotonically increasing per-run sequence allocated by the store. Enforce uniqueness for both (tenant, run, seq) and event ID. Persist the event and its domain transition atomically where they share a database. For a separate workflow engine, record a durable delivery intent, publish idempotently and reconcile lagging projections.

1. Load a snapshot plus its high-water sequence. Open the authorized stream after that cursor.
2. Ignore a duplicate event. On a gap, pause projection, fetch missing records and resume in order. If history expired, fetch a new snapshot.
3. Render views through a pure reducer. Replay consumes the same stored events and has no side-effect adapter.
4. Keep transient token deltas separate from durable transitions. Batch text updates and write final summaries. New browser tabs reconstruct the same business state.
5. A frontend timer may interpolate elapsed time or playback speed. Only persisted state transitions advance the business workflow.

For AG-UI clients, add a translation boundary from your durable envelope to supported protocol events. MCP connects tools and resources; A2A helps independently deployed agents exchange tasks; A2UI and json-render concern declarative presentation. Select each only when that boundary exists. [AG-UI](https://docs.ag-ui.com/introduction) · [MCP](https://modelcontextprotocol.io/docs/learn/architecture) · [A2A](https://a2a-protocol.org/latest/) · [A2UI](https://a2ui.org/) · [json-render](https://json-render.dev/)
