---
layout: default
title: "Tenant-aware SaaS control plane"
permalink: /architectures/references/tenant-aware-saas-control-plane.html
parent: "Reference architectures"
---

# Tenant-aware SaaS control plane

**Design question.** A provider onboards customers across several products. Provisioning must survive a partial regional failure while users keep an accurate status.

## Components and information flow

Tenant registry owns identity-to-region mapping and desired state. API records a signed-in administrator's intent. Outbox dispatcher starts provisioning. A reconciler compares actual resources with desired state.

## Decision and tradeoff

Pooled data is cheaper to operate. Dedicated stamps give stronger isolation and impose migration, idle-capacity and support costs.

## Failure case

A retry after allocating storage can create a second environment. Persist a logical provision ID and look up existing resources before retrying.

## Acceptance exercise

Deactivate a tenant mid-provision, then verify that subsequent access and queued steps are rejected or safely canceled.

## Reference designs

[AWS tenant control plane](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/manage-tenants-across-multiple-saas-products-on-a-single-control-plane.html) · [AWS SaaS isolation](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/full-stack-isolation.html)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
