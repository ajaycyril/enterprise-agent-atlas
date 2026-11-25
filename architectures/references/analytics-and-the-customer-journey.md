---
layout: default
title: "Analytics and the customer journey"
permalink: /architectures/references/analytics-and-the-customer-journey.html
parent: "Reference architectures"
---

# Analytics and the customer journey

**Design question.** A product team wants to understand onboarding abandonment without leaking customer information into analytics.

## Components and information flow

Product events use a versioned minimal schema. A controlled ingestion path validates consent and deduplicates events. An analytical table feeds cohort reports, with access controlled by role.

## Decision and tradeoff

Preaggregated dashboards are fast but can hide sparse cohorts or upstream missing data. Retain governed evidence for metric reconciliation.

## Failure case

A renamed event makes completion appear to fall. Monitor schema drift and compare downstream totals with operational receipts before drawing a conclusion.

## Acceptance exercise

Compare two versions on a fixed cohort. Publish denominator, missingness, repeat contacts and the decision threshold before rollout.

## Reference designs

[Google HEART framework](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/) · [GOV.UK service measurement](https://www.gov.uk/service-manual/measuring-success)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
