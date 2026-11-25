---
layout: default
title: "Product and delivery tools"
permalink: /catalog/product-delivery.html
parent: "Library catalog"
---

# Product and delivery tools

12 entries · Reviewed 25 November 2026. Select a service, tool or framework according to the decision you need to make.

## Product analytics

### PostHog

**Default.** Connect invitation, first useful action and repeat use in an event funnel.

**Tradeoff.** Session replay can collect sensitive screen content. Decide which events the product needs and disable unnecessary capture.

> Draft an event dictionary for the booking funnel, including the server event that proves success.

[Official reference](https://posthog.com/docs/product-analytics)

### Amplitude

**Alternative.** Investigate activation and retention across cohorts with a managed analytics platform.

**Tradeoff.** A change in event definitions can look like a change in customer behavior. Version definitions and compare both for an overlap period.

> Compare repeat bookings for two onboarding cohorts using a fixed inclusion rule.

[Official reference](https://amplitude.com/docs/analytics)

## Experimentation

### GrowthBook

**Alternative.** Evaluate variants and analyze product experiments against warehouse data.

**Tradeoff.** Randomizing by user can mix experiences inside a shared customer account. Define the unit of assignment first.

> Design a tenant-level experiment with a primary outcome, guardrail and plan for small cohorts.

[Official reference](https://docs.growthbook.io/)

### Unleash

**Alternative.** Roll a capability out to defined cohorts with centrally managed feature flags.

**Tradeoff.** Long-lived flags create untested combinations. Give each flag a removal date and an owner.

> Describe how to disable new booking proposals while settling existing ones.

[Official reference](https://docs.getunleash.io/)

### LaunchDarkly

**Alternative.** Manage targeted releases and flag evaluation across multiple services.

**Tradeoff.** Plan for stale or unavailable configuration and confirm which controls your contract covers.

> Provide safe defaults for a new tenant and an unavailable flag service.

[Official reference](https://launchdarkly.com/docs/home)

## Metering and unit cost

### OpenMeter

**Alternative.** Meter usage against a product dimension such as completed operations per account.

**Tradeoff.** Usage records need stable subjects and event IDs. A technical retry should not become a second billable outcome.

> Model two tool attempts, one final receipt and the resulting usage record.

[Official reference](https://openmeter.io/docs)

### FinOps FOCUS

**Specialist.** Normalize supported billing data when comparing infrastructure or provider spend.

**Tradeoff.** A common cost schema cannot assign an invoice line to a customer outcome without an allocation key.

> Map eligible invoice fields to tenant and workload, and put unallocated cost in a visible bucket.

[Official reference](https://focus.finops.org/focus-specification/)

### FinOps unit economics

**Default.** Define the business unit when reviewing model, infrastructure and human handling costs.

**Tradeoff.** A cheap completed call can belong to a case that never resolves. Count eligible cases and final outcomes separately.

> Compute cost per verified resolution for the baseline and the proposed pilot.

[Official reference](https://www.finops.org/framework/capabilities/unit-economics/)

## Service and rollout review

### GOV.UK Service Standard

**Default.** Review whether a service solves a whole problem across channels and can be operated reliably.

**Tradeoff.** Applying the standard still requires user research and evidence from people operating the service.

> Trace a failed online booking into assisted support and back to a single case record.

[Official reference](https://www.gov.uk/service-manual/service-standard)

### Google SRE Workbook on SLOs

**Default.** Translate a customer promise into a measurable service-level objective and error budget.

**Tradeoff.** A fast API response can hide a long wait for the actual service outcome.

> Define good and eligible events for timely booking confirmation, and name the owner when the budget is exhausted.

[Official reference](https://sre.google/workbook/implementing-slos/)

### NIST AI RMF Playbook

**Alternative.** Organize model-risk decisions, measurement and accountability across product stakeholders.

**Tradeoff.** The playbook supplies guidance. Approval, evidence and treatment of residual risk remain organizational decisions.

> Assign an accountable owner and measurable outcome to the three largest risks in the pilot.

[Official reference](https://airc.nist.gov/airmf-resources/playbook/)

### AWS SaaS Lens

**Alternative.** Review tenant onboarding, isolation and tenant-aware operations in a SaaS architecture.

**Tradeoff.** Map the advice to your deployment and customer contracts, including where evidence lives.

> Walk a noisy tenant, a revoked tenant and a tenant export through the proposed service.

[Official reference](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/welcome.html)
