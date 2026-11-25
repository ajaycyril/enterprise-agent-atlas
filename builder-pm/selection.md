---
layout: default
title: "Architecture and procurement"
permalink: /builder-pm/selection.html
parent: "AI builder PM library"
---

# Architecture and procurement

Put the smallest viable option in the comparison. For a booking assistant this might be a form, a server and a lookup endpoint. Compare candidates using the same supported languages, concurrency, corpus, team skills and failure scenario.

| Dependency | Sensible starting point | Reason to change | Who owns the exit? |
|---|---|---|---|
| Frontend | Existing design system and accessible native controls | A bespoke component needs tested focus, selection and localization behavior | Frontend team owns tokens, interaction contract and screenshots |
| Model integration | One bounded model call or tool loop behind an adapter | Multiple providers, residency rules or evaluated routing benefit | Platform owner retains task cases and typed tool definitions |
| Long-running work | One service and database for short, local work | A human or partner can pause the process longer than a worker lifetime | Workflow owner demonstrates restart, export and a runbook |
| Knowledge search | Metadata filters and lexical search | Semantic misses persist on a labeled corpus | Data owner can rebuild indexes from canonical documents |
| Purchased SaaS | Managed service that satisfies existing controls | Contract, region, operational cost or export restrictions conflict with tenant needs | Procurement and engineering jointly run the exit drill |

**Make gates explicit.** Treat mandatory regional processing, audit export, customer deletion and authority checks as pass, fail or unknown. A high weighted score cannot compensate for a failed gate. On surviving candidates, compare staff time, integration and expected 12-month spend. Ask vendors for the exact edition, version, evidence date and contract terms supporting each claim.

**Try the migration before approving the purchase.** Export one run with its tool schema, prompt version and receipt. Rebuild the case in a second environment. Can support still identify what happened? What customer data remains at the old provider, where, and for how long? Record contractual exceptions, costs and owners. A missing answer stays open.

[Vendor comparison worksheet](worksheets/vendor-review.csv) · [Cloud SaaS design questions](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/welcome.html) · [NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/)
