---
layout: default
title: "Python evidence and policy workflow"
permalink: /prompts/02-python-casework.html
parent: "Prompt collection"
---

# Python evidence and policy workflow

Build the same case-recovery journey for an enterprise with an existing Python service. Use a Next.js/React Flow front end, FastAPI admission API, durable dispatcher, LangGraph with a persistent Postgres checkpointer, Pydantic tool schemas and an authorized evidence store. Put the Python worker in a managed worker service. Keep the browser independent of local runtimes.

Implement triage → concurrent evidence and policy branches → strict join → proposed action → human interrupt → scoped effect or closure. Give each branch only its required tools and a budget. Reuse a stable thread ID for resume. Keep each effect behind an idempotent adapter. Create the run and outbox atomically, preserve tenant scope on every read, and store external receipts. Return a safe summary, reason code and source artifact for each visible decision.

Produce C4 container and workflow diagrams, schema migrations, a versioned event contract, live server-sent events and a replay view. Include initial intake, denied, missing evidence, worker restart during approval, duplicate approval and concurrent runs on two tenants. Compare the graph against a single-agent baseline using the same held-out cases, cost per successful resolution and p95 completion time. Report the actual scorecard and any unmeasured items.
