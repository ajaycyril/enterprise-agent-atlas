---
layout: default
title: "Evidence-backed enterprise copilot"
permalink: /prompts/05-enterprise-copilot.html
parent: "Prompt collection"
---

# Evidence-backed enterprise copilot

Build a read-only enterprise knowledge assistant. Choose Next.js with assistant-ui or AI Elements, a bounded server-side model loop, Postgres with pgvector when semantic retrieval is justified, document ACLs, and evidence storage. Use one assistant until a measured evaluation shows a specialist improves outcomes. Choose the accessible UI primitives already used by the host app.

Include seeded tenants, scoped indexed documents, source revision, retrieval timestamp and citations that open the exact authorized record. The user can ask, interrupt a response, inspect citations, switch tenant and see a clear answer when evidence is insufficient. Treat retrieved text as untrusted content. Enforce access at retrieval and again before citation download. Keep raw content out of general logs.

Build a labeled evaluation set with answerable, ambiguous, revoked-access and no-evidence cases. Compare retrieval with and without vectors, report recall at k, supported-claim rate, p95 time to first useful output and cost per supported answer. Deliver a reproducible import, an index refresh and a deletion test that covers derived embeddings and cached results.
