---
layout: default
title: "System design worksheet"
permalink: /architectures/system-design.html
parent: "Reference architectures"
---

# System design worksheet

## Start with a workload

Example sizing assumptions for an internal case desk: 1,000 concurrent open consoles, 10 new runs/s at peak, 24 durable events per run and two model calls per run. These are planning inputs for a load test. They imply roughly 240 new durable events/s and 20 model calls/s at steady peak before retries or fan-out. Four-second average model service time implies about 80 in-flight model calls at that rate. Token streaming and multiple subscribers increase outgoing traffic independently. Use actual arrival rates, service times, payload sizes and retry distributions when sizing a deployment.

| Boundary | Initial choice | Split or change when |
|---|---|---|
| Web / BFF | Next.js server routes authenticate and return tenant-scoped DTOs. Keep one deployable web application initially. | Separate the API when multiple independent clients, runtime constraints or release ownership require it. |
| Command admission | Unique tenant + command key, request hash, transaction creating run and outbox, HTTP 202 + Location | Add admission limits per tenant and return retry guidance when provider or worker quotas saturate. |
| Business store | PostgreSQL with tenant-scoped indexes and limited application roles | Partition high-volume event history by measured retention/query needs. Keep current snapshots cheap to load. |
| Async work | One durable owner and a dispatcher. Atomic outbox, bounded retries, dead-letter review and reconciliation | Add NATS JetStream if several independent consumers need durable subscriptions and replay. |
| Browser stream | SSE for one-way updates; HTTP commands for review/cancel. Compare cursor polling for low-frequency or restricted clients. | Use a bidirectional channel for simultaneous editing or frequent client signals. Verify reconnect and host support. |
| Evidence | Object storage with short-lived authorized download; metadata and ACLs in the DB | Add vector search when semantic retrieval improves a labeled search task. Filter ACLs before returning results. |
| Caching | Cache public assets broadly; cache tenant reads only under a full tenant + policy + resource key | Add shared caching after measuring expensive queries. Define TTL, revocation and invalidation behavior. |
| Release | Expand schema, release compatible readers/writers, backfill, verify, contract old fields | Version event envelopes and workflow definitions when old in-flight runs can outlive a deploy. |

[Outbox pattern](https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/transactional-outbox.html) · [Postgres RLS](https://www.postgresql.org/docs/current/ddl-rowsecurity.html) · [JetStream](https://docs.nats.io/concepts/jetstream) · [Vercel limits](https://vercel.com/docs/functions/limitations)

## Contracts a coding agent can implement

| Endpoint | Required semantics |
|---|---|
| POST /runs | Verify tenant grant, validate case and idempotency key, return 202 for accepted work. Retries with the same body return the same reference. |
| GET /runs/{id} | Authorize membership, return snapshot and last durable sequence from a consistent read. |
| GET /runs/{id}/events?after=N | Authorize every reconnect, send ordered events after N, handle expired cursors, cap open streams and heartbeat idle clients. |
| POST /runs/{id}/approvals/{approvalId}/decision | Require decision, proposal digest, expected version and command key. Compare and swap. Prevent expired approvals and repeat writes. |
| POST /runs/{id}/cancel | Mark cancellation requested; surface in-flight effects that still need reconciliation. An idempotent repeat returns current state. |
| GET /runs/{id}/artifacts/{artifactId} | Verify tenant, run and artifact relation, issue short-lived scoped retrieval, audit access to sensitive evidence. |

Minimum relational model: tenant memberships, cases, runs, per-run events, proposals, approvals, logical effects, receipts, artifact metadata and outbox. Foreign keys include tenant scope where appropriate. Unique constraints enforce one command per idempotency key within scope and one logical effect per approved proposal/action. Keep an append-only audit decision record independently of sampled traces. [OpenAPI](https://openapis.org/what-is-openapi/) · [AsyncAPI](https://www.asyncapi.com/docs/concepts/asyncapi-document)

## Capacity, continuity and cost

- Budget latency separately for admission, queue wait, time to first meaningful update, model latency, tool calls and human wait. Publish separate histograms. Measure p95 with realistic concurrency.
- Bound queue age, model concurrency and per-tenant budget. Shed low-priority work first. Back off transient errors with jitter. Reconcile uncertain writes. Use a circuit breaker around a failing dependency with a named fallback state.
- Agree an RPO and RTO with the business. As a sample target, RPO 15 minutes and RTO 2 hours require a restore drill that includes the event log, evidence references, effect ledger, identities and workflow recovery. Record actual recovery and outstanding gaps.
- Compute cost per successful case as total attributable model, execution, storage, trace and egress spend divided by successfully completed cases. Track retry and fallback rates and the cost of retained traces.
- Record deployment region for each database, model endpoint, gateway fallback, traces, blobs, backups and support export. Test failover with the same data constraints.

[Postgres recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) · [Circuit breaker](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) · [Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

## Architecture decision record

Copy this into the target project. Record the context and workload; chosen component and edition; considered alternatives; reason for selection; owner of state and retries; identity boundary; expected cost driver; recovery path; acceptance test; next review date. A vendor SLA, residency term or paid feature should link to the actual plan or agreement used by the enterprise.
