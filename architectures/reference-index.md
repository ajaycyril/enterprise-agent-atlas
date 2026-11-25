---
layout: default
title: "Reference architectures"
permalink: /architectures/reference-index.html
nav_order: 3
has_children: true
---

# Reference architectures

Start with the workload and compare its state owner, trust boundary and failure case. The linked designs are editorial examples with upstream references.

| Reference architecture | Design question |
|---|---|
| [Tenant-aware SaaS control plane](references/tenant-aware-saas-control-plane.md) | A provider onboards customers across several products. Provisioning must survive a partial regional failure while users keep an accurate status. |
| [Permission-aware enterprise RAG](references/permission-aware-enterprise-rag.md) | An employee needs a source-grounded answer across documents with different permissions and revisions. |
| [Live agent operations console](references/live-agent-operations-console.md) | Operators need to understand concurrent specialist activity, receipt of evidence and human decisions while a browser disconnects and reconnects. |
| [Event-driven ingestion and audit](references/event-driven-ingestion-and-audit.md) | Many business systems produce events that feed independent audit, reporting and search consumers. |
| [Customer onboarding across channels](references/customer-onboarding-across-channels.md) | A customer starts on mobile, uploads evidence later and finishes with assisted support. |
| [Secure document intake](references/secure-document-intake.md) | Multiple external parties submit large attachments that staff and AI workers later inspect. |
| [Fleet telemetry and incident replay](references/fleet-telemetry-and-incident-replay.md) | A dispatcher investigates a late delivery from irregular device observations, mission plans and prior service actions. |
| [Model routing and evaluation gateway](references/model-routing-and-evaluation-gateway.md) | Several teams need provider choice, tenant budgets and a defensible rollout decision for a new model. |
| [Regional recovery and residency](references/regional-recovery-and-residency.md) | A regional outage affects tenants whose data residency rules and recovery targets differ. |
| [Progressive delivery for a shared platform](references/progressive-delivery-for-a-shared-platform.md) | A platform team must ship schema and workflow revisions while active cases continue. |
| [Analytics and the customer journey](references/analytics-and-the-customer-journey.md) | A product team wants to understand onboarding abandonment without leaking customer information into analytics. |
| [Secure tool gateway and human approval](references/secure-tool-gateway-and-human-approval.md) | Agents can propose a change to an external business system. A separately authorized human must decide whether it proceeds. |

[Three execution-stack blueprints](choose-a-stack.md) · [24 reusable system patterns](pattern-library.md) · [Three basic security architectures](../operations/security-foundations.md)
