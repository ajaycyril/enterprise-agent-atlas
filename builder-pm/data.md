---
layout: default
title: "Data, retrieval and access"
permalink: /builder-pm/data.html
parent: "AI builder PM library"
---

# Data, retrieval and access

A policy assistant should cite the current cancellation rule for the caller’s account. This requires an authorized source, a version and a way to retire it. An embedding is a derived copy that needs its own lifecycle.

| Stage | Control | Failure to rehearse |
|---|---|---|
| Import | Capture document ID, owner, version, effective date, access groups and source pointer. Reject or quarantine records with missing ownership. | Two departments publish different rules with the same title. |
| Parse | Keep passage and page references. Check tables, exceptions and scanned documents with a human-labeled sample. | The fee survives extraction while its exemption disappears. |
| Retrieve | Scope by tenant and current permissions before content reaches the model. Recheck access when opening a citation. | A support agent loses a role while an answer is cached. |
| Answer | Cite the relevant authorized passage, flag conflicting policies and abstain on insufficient evidence. | A familiar question has no applicable policy for this tenant. |
| Retire | Invalidate cached answers, remove derived records and track exceptions such as time-limited backup retention. | A deleted source survives in the vector index or trace exporter. |

**Which component performed badly?** Label a small set of questions with relevant passages and acceptable answers. Run lexical search first. If the right passage never appears, test splitting or retrieval. If it appears and the answer is still wrong, inspect the prompt, conflicting context and evidence grading. Keep a separate slice for revoked and missing documents.

**Security review.** Draw the browser, application API, retrieval service, inference provider and storage boundary. Mark which fields each needs, region, retention, operator access and deletion owner. Treat imported text and model output as untrusted. Validate tool arguments and user authority in a service outside the model. Use workload identity or narrowly scoped secrets, redacted traces and a restoration exercise on synthetic data.

[Data inventory worksheet](worksheets/data-inventory.csv) · [Permission-aware RAG](../architectures/references/permission-aware-enterprise-rag.md) · [PostgreSQL row security](https://www.postgresql.org/docs/current/ddl-rowsecurity.html) · [OWASP ASVS](https://asvs.owasp.org/)
