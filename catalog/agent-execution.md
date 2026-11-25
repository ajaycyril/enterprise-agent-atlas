---
layout: default
title: "Agent execution tools"
permalink: /catalog/agent-execution.html
parent: "Library catalog"
---

# Agent execution

33 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## Harnesses

### eve

**Default.** Integrated TypeScript harness for Vercel-first apps with durable runs, subagents and approvals.

**Tradeoff.** Recently reached 1.0. Validate region, export, run retention, sandbox limits and your recovery path.

> Use eve as the sole run owner. Map its tool, approval and completion transitions to a durable public event log.

[Official reference](https://eve.dev/)

### LangGraph

**Default.** Explicit state graphs for conditional routing, parallel branches, joins and human review.

**Tradeoff.** You own state schemas, checkpoint storage, tool idempotency and schema migrations.

> Use a persistent checkpointer, stable thread IDs and explicit branch joins. Resume an interrupted run after a worker restart.

[Official reference](https://docs.langchain.com/oss/python/langgraph/overview)

### Deep Agents

**Alternative.** A higher-level harness on LangGraph for planning, context offload and subagent delegation.

**Tradeoff.** File tools and shared memory widen the permissions surface.

> Give the research specialist a run-scoped workspace, read-only tools and bounded delegation.

[Official reference](https://docs.langchain.com/oss/python/deepagents/overview)

### OpenAI Agents SDK

**Alternative.** Lightweight agents, handoffs, tools and tracing for teams already using OpenAI integrations.

**Tradeoff.** Choose durable storage and an execution recovery strategy for long business processes.

> Define triage and specialist handoffs, narrow tool grants and a typed final output. Test provider timeout and replay.

[Official reference](https://openai.github.io/openai-agents-python/)

### Vercel AI SDK

**Default.** TypeScript model calls, tools and streaming for a bounded application agent.

**Tradeoff.** A tool loop still needs persistence, retry ownership and an explicit stopping policy.

> Use an allowlisted provider/model and typed tools. Bound steps, elapsed time and spend.

[Official reference](https://ai-sdk.dev/docs/agents/overview)

### Mastra

**Alternative.** Integrated TypeScript agents and explicit workflows for a Node team.

**Tradeoff.** Evaluate the hosting adapter, persistence and upgrade path together.

> Define a typed workflow with an evidence step and suspended review, then prove resume after redeploy.

[Official reference](https://mastra.ai/docs)

### Pydantic AI

**Alternative.** Typed Python dependencies and outputs for model-assisted domain workflows.

**Tradeoff.** Structured output can still be factually wrong. Track outcome quality on real examples.

> Return a typed recommendation with evidence IDs, verify those IDs and score support for each claim.

[Official reference](https://ai.pydantic.dev/)

### Microsoft Agent Framework

**Alternative.** .NET and Python agent workflows for Microsoft-platform teams and existing Semantic Kernel or AutoGen estates.

**Tradeoff.** Migration and feature support differ by language and connector.

> Use the supported workflow primitives in one language. Pin connector versions and test checkpoint recovery.

[Official reference](https://learn.microsoft.com/en-us/agent-framework/overview/)

### Google ADK

**Alternative.** Agents, tools and workflow composition for teams using the Google agent ecosystem.

**Tradeoff.** Check session persistence, identity propagation and host-specific behavior.

> Give each specialist a bounded toolset and persist sessions in the approved regional service.

[Official reference](https://google.github.io/adk-docs/)

### Claude Agent SDK

**Alternative.** Tool-capable Claude agents for research, document work and controlled coding workflows.

**Tradeoff.** Permission mode, tool allowlists, execution environment and credentials need deliberate ownership.

> Give one worker an isolated workspace and approved read tools. Capture artifact references and redact traces.

[Official reference](https://platform.claude.com/docs/en/agent-sdk/overview)

### Amazon Bedrock AgentCore

**Alternative.** Choose a managed agent harness or host your own agent code in AgentCore Runtime.

**Tradeoff.** The managed harness and runtime expose different control points. Check regional availability by service.

> Document which layer owns the loop, where sessions live and how tool calls inherit scoped identity.

[Official reference](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/harness-vs-runtime.html)

### CrewAI

**Alternative.** Role-based multi-agent coordination with explicit tasks and process choices.

**Tradeoff.** More roles can add repeated work and compound cost.

> Compare two specialists against a single-agent baseline and cap delegation depth.

[Official reference](https://docs.crewai.com/)

### Strands Agents

**Alternative.** Model-driven agents with composable tools for teams working in the AWS ecosystem.

**Tradeoff.** Model-directed tools still need scoped credentials and explicit stop conditions.

> Document the agent loop, model boundary, permitted tools and receipt requirements.

[Official reference](https://strandsagents.com/latest/documentation/docs/)

### Semantic Kernel

**Specialist.** An installed Microsoft agent or plugin estate requiring maintenance or migration analysis.

**Tradeoff.** Review the Microsoft Agent Framework migration path for new investment.

> Inventory existing plugins, memory and workflows and test the target equivalent on representative cases.

[Official reference](https://learn.microsoft.com/en-us/semantic-kernel/overview/)

## Protocols & tools

### MCP

**Specialist.** Standard interface for tool and resource servers shared across clients.

**Tradeoff.** Protocol compatibility and tool discovery do not establish tenant or action authority.

> Pin a protocol revision, verify server identity, allowlist tools, and bind credentials to the tenant.

[Official reference](https://modelcontextprotocol.io/docs/learn/architecture)

### A2A

**Specialist.** Interoperability between independently deployed agents with task lifecycles.

**Tradeoff.** In-process specialists rarely justify protocol negotiation or remote identity overhead.

> Use it only across a real service boundary. Validate agent identity, capabilities, timeouts and artifacts.

[Official reference](https://a2a-protocol.org/latest/)

## Model access

### Vercel AI Gateway

**Alternative.** Managed routing across model providers behind one gateway.

**Tradeoff.** Fallback can change region, data policy, model behavior and cost.

> Allowlist eligible fallback providers per data class and record the actual provider and model per call.

[Official reference](https://vercel.com/docs/ai-gateway)

### LiteLLM

**Alternative.** Gateway/proxy with a common model interface for a team operating its own routing layer.

**Tradeoff.** You own the proxy's availability, upgrades, keys and policy.

> Assign virtual credentials by application and tenant. Reject unapproved fallbacks and log attributed spend.

[Official reference](https://docs.litellm.ai/docs/)

### OpenAI Responses API

**Alternative.** Applications using OpenAI tools, structured responses and multi-step interactions.

**Tradeoff.** Available tools and retention controls depend on model, account and configuration.

> Map tool call and result identifiers to the business run without exposing provider secrets.

[Official reference](https://developers.openai.com/api/docs/guides/migrate-to-responses)

### Claude Messages API

**Alternative.** Applications invoking Claude with typed content blocks and tools.

**Tradeoff.** The client has to handle tool responses, continuation, failures and output validation.

> Record the stop reason, validate each tool request and return a scoped tool result.

[Official reference](https://platform.claude.com/docs/en/api/messages/create)

## Execution isolation

### Vercel Sandbox

**Specialist.** Isolated compute for an agent that genuinely needs to execute generated code.

**Tradeoff.** Bound network, lifetime, artifacts and credential exposure per execution.

> Start a short-lived sandbox with scoped inputs. Copy approved artifacts out, then expire the environment.

[Official reference](https://vercel.com/docs/vercel-sandbox)

### E2B

**Alternative.** Independent sandbox service for model-generated code or data analysis.

**Tradeoff.** Evaluate image lineage, region, egress controls and session cleanup.

> Use a prepared image, minimal file mounts, bounded time and an audited artifact-export path.

[Official reference](https://e2b.dev/docs)

## Durability

### Temporal

**Default.** Durable business workflows spanning outages, external systems and long human waits.

**Tradeoff.** Deterministic workflow code, activity idempotency and worker versioning are operational commitments.

> Make Temporal the workflow owner. Put all network and model calls into bounded activities.

[Official reference](https://docs.temporal.io/)

### Inngest

**Alternative.** Event-triggered durable steps and background work for application teams.

**Tradeoff.** Choose a single retry owner per side effect. Test event re-delivery and concurrency limits.

> Give each step a stable name and each logical effect a deduplication key. Exercise a duplicate trigger.

[Official reference](https://www.inngest.com/docs)

### Workflow SDK

**Alternative.** Durable TypeScript functions and steps, including the execution substrate used by eve.

**Tradeoff.** Check upgrade, retention and deployment adapter behavior for the chosen host.

> Persist run references and use durable waits for review. If using eve, keep approvals in its owning workflow.

[Official reference](https://workflow-sdk.dev/)

### Cloudflare Workflows

**Alternative.** Durable execution aligned with a Workers deployment.

**Tradeoff.** Review current step limits, retention and supported runtimes.

> Suspend the workflow at a human wait and prove a worker redeploy preserves the pending decision.

[Official reference](https://developers.cloudflare.com/workflows/)

### AWS Step Functions

**Alternative.** AWS-native state machines coordinating managed services and business activities.

**Tradeoff.** Choose workflow type and cost model for the actual duration and volume.

> Model retries, timeouts, explicit compensation and correlation to the business case.

[Official reference](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)

### Azure Durable Functions

**Alternative.** Durable orchestration and external events in an Azure Functions estate.

**Tradeoff.** Orchestrator replay constrains code and requires careful versioning.

> Put non-deterministic I/O in activities and test an old approval after a new deployment.

[Official reference](https://learn.microsoft.com/en-us/azure/azure-functions/durable/durable-functions-overview)

### Restate

**Alternative.** Durable service invocation and stateful workflows with explicit service boundaries.

**Tradeoff.** Service-side durability does not make a non-idempotent external action safe.

> Use a stable logical effect ID and reconcile destination receipts across retries.

[Official reference](https://docs.restate.dev/)

## Retrieval & knowledge

### LlamaIndex

**Alternative.** Ingestion and retrieval components for evidence-backed domain assistants.

**Tradeoff.** A retrieval pipeline needs independent ACL enforcement and citation evaluation.

> Link every returned chunk to its authorized source revision and measure recall.

[Official reference](https://developers.llamaindex.ai/python/framework/)

### Haystack

**Alternative.** Explicit search and generation pipelines with swappable components.

**Tradeoff.** Pipeline flexibility can complicate component-level performance attribution.

> Benchmark retrieval, reranking and generation independently against a fixed query set.

[Official reference](https://docs.haystack.deepset.ai/docs/intro)

## Optimization & evaluation

### DSPy

**Specialist.** Optimizing typed language-model programs against a defined metric and examples.

**Tradeoff.** An optimizer can improve a proxy metric while worsening a business outcome.

> Use separate training and held-out sets and inspect failure slices before promoting the candidate.

[Official reference](https://dspy.ai/)

## Agent interfaces

### Model Context Protocol Apps

**Specialist.** Interactive resources served from a tool experience to a compatible host.

**Tradeoff.** Host support, isolation, authentication and renderer behavior need verification.

> Define allowed UI actions and a text-only fallback for clients without the extension.

[Official reference](https://modelcontextprotocol.io/extensions/apps/overview)
