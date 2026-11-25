---
layout: default
title: "Permission-aware enterprise RAG"
permalink: /architectures/references/permission-aware-enterprise-rag.html
parent: "Reference architectures"
---

# Permission-aware enterprise RAG

**Design question.** An employee needs a source-grounded answer across documents with different permissions and revisions.

## Components and information flow

Ingestion retains source revision and access metadata. Retrieval filters by current grants. A model receives permitted passages. Citation downloads reauthorize the exact artifact.

## Decision and tradeoff

Relational/vector colocation simplifies ownership. A dedicated search service offers more tuning at the cost of synchronization and deletion complexity.

## Failure case

A revoked document can survive in an embedding index or cached answer. Propagate revocation and revalidate before disclosure.

## Acceptance exercise

Seed two workspaces, revoke a shared document, and inspect retrieval, answer citations, cache and subsequent downloads.

## Reference designs

[Microsoft RAG design and evaluation](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/rag/rag-solution-design-and-evaluation-guide) · [Postgres row security](https://www.postgresql.org/docs/current/ddl-rowsecurity.html)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
