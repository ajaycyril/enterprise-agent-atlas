---
layout: default
title: "Document revision, access and deletion"
permalink: /architectures/references/policy-document-lifecycle.html
parent: "Reference architectures"
---

# Document revision, access and deletion

A partner revises its cancellation policy. How do you stop an assistant from quoting yesterday’s fee?

## Components and ownership

A source registry owns tenant, version, effective date and permissions. A parsing worker preserves passage IDs and revision metadata. The index publishes a verified version before the retrieval service switches its active pointer. The citation endpoint performs a fresh authorization check. Retire prior versions according to the retention policy and invalidate derived caches.

## Failure and recovery

| Condition | Expected behavior |
|---|---|
| Parsing drops a table footnote | Keep the current version active and flag the candidate for review. |
| Access revoked during a session | Recompute eligibility before displaying or reopening evidence. Invalidate affected cached results. |
| Partial deletion | Track completion by primary store, search index, answer cache and observability store. Record applicable backup expiry. |

## Acceptance exercise

Publish a revised fee with a new exception. Ask in two tenant contexts, then revoke one user's access. Inspect answer, citation, caches and the deletion record.

[Docling](https://docling-project.github.io/docling/) · [OpenLineage](https://openlineage.io/docs/) · [Permission-aware RAG](permission-aware-enterprise-rag.md)
