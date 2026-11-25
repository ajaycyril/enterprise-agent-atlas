---
layout: default
title: "System design tools"
permalink: /catalog/system-design.html
parent: "Library catalog"
---

# System design

37 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## APIs & modeling

### FastAPI

**Default.** Typed HTTP boundary for a Python agent or retrieval service.

**Tradeoff.** Long work in a request handler consumes capacity and is vulnerable to disconnects.

> Return 202 with a run ID, validate scope, enqueue durably, and expose a cursor-based event endpoint.

[Official reference](https://fastapi.tiangolo.com/)

### NestJS

**Alternative.** Structured Node API with modules and dependency injection for larger backend teams.

**Tradeoff.** A separate API service adds deployment and tracing overhead.

> Organize by case, approval and execution modules and validate inputs at each external boundary.

[Official reference](https://docs.nestjs.com/)

### OpenAPI

**Default.** Describe HTTP endpoints and generate consistent clients for UI and integrations.

**Tradeoff.** Breaking response changes need compatibility and contract tests.

> Specify Run, Evidence, Approval and Problem responses. Include 403, 409 and idempotent retry examples.

[Official reference](https://www.openapis.org/what-is-openapi)

### AsyncAPI

**Specialist.** Document event channels, payloads and producer/consumer contracts across teams.

**Tradeoff.** A specification cannot enforce delivery order or deduplication.

> Publish event versions, delivery guarantees and per-run ordering. Reject unknown breaking versions.

[Official reference](https://www.asyncapi.com/docs/concepts/asyncapi-document)

### C4 model

**Default.** Architecture notation for context, containers and component ownership.

**Tradeoff.** Dense component diagrams obscure operational boundaries.

> Draw browser, BFF, worker, database, IdP and model boundary. Label the owner and protocol of each crossing.

[Official reference](https://c4model.com/)

## Data & messaging

### PostgreSQL

**Default.** System of record for tenants, runs, approvals, events and effect receipts with row-level policies.

**Tradeoff.** Table owners and BYPASSRLS roles can bypass policies. Model worker privileges explicitly.

> Enable tenant policies and use scoped roles. Test cross-tenant access on the API, event stream and evidence.

[Official reference](https://www.postgresql.org/docs/current/ddl-rowsecurity.html)

### Drizzle ORM

**Alternative.** Typed SQL access and migrations for a TypeScript/Postgres application.

**Tradeoff.** Migration lock time and RLS behavior still need database-level testing.

> Use reviewed migrations and verify a least-privilege application role on a restored production-sized database.

[Official reference](https://orm.drizzle.team/docs/overview)

### pgvector

**Specialist.** Vector retrieval beside relational metadata when Postgres already stores your knowledge base.

**Tradeoff.** Approximate retrieval under restrictive filters can hurt recall. Evaluate tenant-specific queries.

> Apply document ACLs and tenant filters, measure recall at k and cite stable chunk IDs.

[Official reference](https://github.com/pgvector/pgvector)

### NATS JetStream

**Specialist.** Persistent streams when several workers or independent consumers must replay domain events.

**Tradeoff.** At-least-once scenarios require consumer deduplication and capacity planning.

> Set explicit retention, ack policy and consumer lag alarms. Keep the authoritative run sequence in the store.

[Official reference](https://docs.nats.io/nats-concepts/jetstream)

### Amazon S3

**Alternative.** Object storage for large evidence files and exported artifacts.

**Tradeoff.** Signed URLs are bearer access. Decide expiry, retention, region and versioning.

> Store opaque object references in events and mint short-lived downloads after authorization.

[Official reference](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

### Transactional outbox

**Default.** Commit a domain change and its pending message in the same database transaction.

**Tradeoff.** Dispatch can deliver duplicates. Consumers must tolerate retries.

> Insert the run and outbox record atomically, publish after commit, and reconcile unacknowledged messages.

[Official reference](https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/transactional-outbox.html)

### Server-sent events

**Default.** One-way browser delivery of ordered run updates alongside ordinary HTTP commands.

**Tradeoff.** Connection limits, proxy buffering and cursor gaps vary by host.

> Send event IDs, heartbeat, resume cursor and snapshot fallback. Recheck authorization on reconnect.

[Official reference](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)

## Delivery

### OpenTofu

**Alternative.** Versioned infrastructure for repeatable private-network or enterprise deployments.

**Tradeoff.** Remote state is sensitive and needs restricted access and locking.

> Provision separate stage and production with encrypted state and reviewed plans.

[Official reference](https://opentofu.org/docs/intro/)

### GitHub Actions OIDC

**Default.** Short-lived cloud credentials for build and deployment jobs.

**Tradeoff.** Overbroad trust conditions can grant credentials to unintended jobs.

> Restrict trust to the correct repository, workflow/environment and audience. Pin third-party actions.

[Official reference](https://docs.github.com/en/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect)

### OpenFeature

**Alternative.** Vendor-neutral flag evaluation for progressive rollout and a circuit-breaking product switch.

**Tradeoff.** Flag evaluation must have a safe default when the provider fails.

> Gate the new harness version by tenant cohort, record the variant on every run, and support rollback.

[Official reference](https://openfeature.dev/docs/reference/intro/)

## Events & integration

### Kafka

**Alternative.** A durable event backbone for independent consumers and replayable streams.

**Tradeoff.** Partitioning defines ordering scope; slow consumers and schema drift require operational tooling.

> Key events by aggregate ID, version payloads and expose consumer lag and replay controls.

[Official reference](https://kafka.apache.org/intro)

### RabbitMQ

**Alternative.** Work queues and routing where acknowledgment and delivery behavior are explicit.

**Tradeoff.** A retry can redeliver work already applied at the destination.

> Declare queue ownership, retry deadlines, dead-letter routing and an idempotent consumer.

[Official reference](https://www.rabbitmq.com/docs)

### Apache Flink

**Specialist.** Stateful stream processing for time-windowed telemetry and late events.

**Tradeoff.** State size, watermark strategy and checkpoint recovery need load tests.

> Define event time, allowed lateness and the correction rule for an updated metric.

[Official reference](https://github.com/apache/flink)

### Debezium

**Alternative.** Change-data capture for downstream projections and integration feeds.

**Tradeoff.** Schema evolution, initial snapshots and retained transaction logs require ownership.

> Specify a bootstrap snapshot, durable offsets and recovery when a consumer falls behind retention.

[Official reference](https://debezium.io/documentation/reference/stable/architecture.html)

## Storage & retrieval

### Redis

**Alternative.** Low-latency cache and short-lived counters for an existing application.

**Tradeoff.** Eviction, failover and stale authorization can change business behavior.

> Scope cache keys to tenant and permission version. Test eviction and database fallback.

[Official reference](https://redis.io/docs/latest/develop/)

### Valkey

**Specialist.** An open-source key-value service where a managed or self-hosted deployment is needed.

**Tradeoff.** Verify client, command and service compatibility with the workload.

> Set TTL and memory policy per use case and test read behavior during failover.

[Official reference](https://valkey.io/)

### ClickHouse

**Alternative.** Analytical scans across append-heavy events, traces or telemetry.

**Tradeoff.** Table order and ingestion shape drive query cost and correction behavior.

> Model the primary time and tenant filters and benchmark the p95 dashboard query on production-shaped data.

[Official reference](https://clickhouse.com/docs/intro)

### DuckDB

**Alternative.** Embedded analytics over columnar files for reproducible investigations.

**Tradeoff.** Concurrency and memory budgets differ from a shared analytical service.

> Analyze a versioned Parquet snapshot and report sampling, filters and query time.

[Official reference](https://duckdb.org/docs/stable/)

### OpenSearch

**Alternative.** Search across indexed enterprise documents with filters and aggregations.

**Tradeoff.** Index freshness and authorization propagation need explicit service objectives.

> Apply tenant and document grants, record source revisions and test revoked-document search.

[Official reference](https://docs.opensearch.org/latest/)

### Qdrant

**Alternative.** A dedicated vector retrieval service for filtered semantic search.

**Tradeoff.** Choosing an index, embedding revision and filter strategy requires a labeled retrieval set.

> Benchmark recall and latency with restrictive tenant filters and realistic deletion frequency.

[Official reference](https://qdrant.tech/documentation/)

### Apache Iceberg

**Alternative.** Large analytical tables that need snapshot history and schema evolution.

**Tradeoff.** Catalog maintenance, compaction and expired snapshot cleanup have a cost.

> Version the event schema and define the retention and compaction policy for archived runs.

[Official reference](https://iceberg.apache.org/docs/latest/)

## Contracts & APIs

### gRPC

**Alternative.** Typed internal service calls and streaming across service boundaries.

**Tradeoff.** Browser and proxy compatibility need a deliberate gateway or transport choice.

> Set deadlines and cancellation, version protobuf fields compatibly and test service degradation.

[Official reference](https://grpc.io/docs/what-is-grpc/introduction/)

### GraphQL

**Alternative.** Multiple clients need different shapes of a shared domain graph.

**Tradeoff.** Resolver authorization, query cost and per-field fan-out need controls.

> Cap complexity and verify field-level authorization on sensitive case relationships.

[Official reference](https://graphql.org/learn/)

### CloudEvents

**Alternative.** A common envelope across event producers and transport adapters.

**Tradeoff.** Domain schemas, delivery guarantees and tenant permissions remain application decisions.

> Keep source, type, ID and payload schema stable across broker and HTTP transports.

[Official reference](https://cloudevents.io/)

### JSON Schema

**Default.** Validating data at HTTP, workflow, tool and event boundaries.

**Tradeoff.** Draft support and allowed keywords vary across validators and model providers.

> Pin the dialect and reject unknown action types before a tool receives arguments.

[Official reference](https://json-schema.org/overview/what-is-jsonschema)

### OpenAPI Generator

**Alternative.** Repeatable client generation for multiple API consumers.

**Tradeoff.** Generator changes and hand edits create drift.

> Pin the generator and schema revision and verify an older client against the new server.

[Official reference](https://openapi-generator.tech/docs/usage/)

## Infrastructure & delivery

### Kubernetes

**Alternative.** A platform team needs scheduling, rollout and isolation controls for many services.

**Tradeoff.** Operational overhead is substantial for a small service or simple website.

> Specify resource requests, disruption budgets and worker drain behavior before choosing the cluster shape.

[Official reference](https://kubernetes.io/docs/concepts/overview/)

### Argo CD

**Alternative.** Declarative application delivery from Git for Kubernetes environments.

**Tradeoff.** Separately authorize repository writes, deployment promotion and secret access.

> Show drift, require production promotion review and rehearse rollback of a worker revision.

[Official reference](https://argo-cd.readthedocs.io/en/stable/)

### Helm

**Alternative.** Packaging and configuring versioned Kubernetes applications.

**Tradeoff.** Template complexity can hide environment-specific mistakes.

> Render and check the production values in CI and document data migration dependencies.

[Official reference](https://helm.sh/docs/)

### Envoy

**Alternative.** Consistent edge or service-proxy behavior across a polyglot estate.

**Tradeoff.** Timeout and retry policies can amplify work when also configured upstream.

> Assign retry ownership and measure the effective end-to-end request deadline.

[Official reference](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

### Dapr

**Alternative.** Common building blocks for services across different language runtimes.

**Tradeoff.** Sidecar dependencies introduce another version, latency and recovery boundary.

> Specify which pub/sub or state component is used and test its actual delivery semantics.

[Official reference](https://docs.dapr.io/)

### Backstage

**Alternative.** A developer portal for service ownership, documentation and templates.

**Tradeoff.** Catalog accuracy needs integration with engineering ownership practices.

> Expose the team's runbook, service owner, SLO and escalation path on one catalog record.

[Official reference](https://backstage.io/docs/overview/what-is-backstage/)
