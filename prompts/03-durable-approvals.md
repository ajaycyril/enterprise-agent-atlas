---
layout: default
title: "Multi-day approval and fulfillment"
permalink: /prompts/03-durable-approvals.html
parent: "Prompt collection"
---

# Multi-day approval and fulfillment

Build an enterprise service-change portal with requester, reviewer and auditor roles. A request spans a model-assisted classification, two team approvals, a downstream system change and verification. Use the existing identity provider via OIDC, a typed HTTP API, Postgres business read models, Temporal as the sole workflow owner, and a Next.js review queue. Run model calls, integrations and other I/O as activities with timeouts and bounded retries.

Implement an approval digest and version, expiry, separation of requester and reviewer where required, decision history, cancel and a receipt ledger. A timeout after an external write must trigger reconciliation against the stable effect key. If success cannot be confirmed safely, route the case to manual review. Bind policy, tenant and ownership checks to every tool action and replay operation.

Show a queue, fingerprinted proposal diff, audit timeline, assigned approver, expiry and current actionable step. Use a working keyboard path and an accessible nonvisual status update. Generate migration and worker versioning instructions, a recovery drill and browser tests. Demonstrate rejection, expired decision, two reviewers racing, worker crash after downstream success, and rollback with an old active workflow. Report the number of external mutations recorded for each scenario.
