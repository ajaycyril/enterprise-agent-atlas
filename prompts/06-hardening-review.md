---
layout: default
title: "Enterprise release review"
permalink: /prompts/06-hardening-review.html
parent: "Prompt collection"
---

# Enterprise release review

Review the generated app and apply fixes in scope. Begin with its real entry points and deployed topology. Produce a table with requirement, implementation location, evidence, failure mode and owner. Inspect authentication, per-tenant data isolation, tool grants, CSRF, secrets, untrusted content handling, audit redaction, hosted dependencies and software supply chain.

Trace one run through API admission, state persistence, model call, tool invocation, approval, external effect, receipt and replay. Check retry ownership, idempotency, approval expiry, cancellation, deadline, budget, duplicate events, subscriber reconnect and deletion. Distinguish a rendered fixture from an executed backend transition. Run non-destructive tests against controlled fixtures and approved test systems.

Record what you executed, the actual results, open blockers, runtime limits, vendor-plan assumptions, measured accessibility and performance, rollback steps and the next release decision. Return the changed implementation and small repro fixtures for the identified regressions.
