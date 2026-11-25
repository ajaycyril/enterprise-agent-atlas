---
layout: default
title: "Model routing and evaluation gateway"
permalink: /architectures/references/model-routing-and-evaluation-gateway.html
parent: "Reference architectures"
---

# Model routing and evaluation gateway

**Design question.** Several teams need provider choice, tenant budgets and a defensible rollout decision for a new model.

## Components and information flow

A gateway resolves data class, region and model eligibility. The harness supplies scoped context. Evaluation records model, prompt, tool and dataset revisions. A policy gate controls release cohorts.

## Decision and tradeoff

Fallback improves availability only if the substitute meets residency, capabilities, quality and budget constraints for that tenant.

## Failure case

A primary provider times out after a tool proposal was generated. Re-evaluate the proposal under the pinned policy and deduplicate any downstream effect.

## Acceptance exercise

Force a primary timeout in a controlled environment. Confirm the restricted tenant takes its approved fallback or an explicit degraded path.

## Reference designs

[AI Gateway](https://vercel.com/docs/ai-gateway) · [Langfuse evaluations](https://langfuse.com/docs/evaluation/overview)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
