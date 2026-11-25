---
layout: default
title: "Regional recovery and residency"
permalink: /architectures/references/regional-recovery-and-residency.html
parent: "Reference architectures"
---

# Regional recovery and residency

**Design question.** A regional outage affects tenants whose data residency rules and recovery targets differ.

## Components and information flow

A tenant registry selects permitted cells. Each cell owns app, queue, data and evidence boundaries. Replication and backups follow data class. Routing changes only after integrity checks.

## Decision and tradeoff

Active-active reduces some recovery delay while increasing write-conflict and replication complexity. Active-passive needs a tested promotion sequence.

## Failure case

Promotion can restore the database before recent external receipts. Hold writes until the ledger and receiver state reconcile.

## Acceptance exercise

Restore a representative tenant, measure actual RPO/RTO and show the blocked fallback for a prohibited region.

## Reference designs

[Google disaster recovery planning](https://cloud.google.com/architecture/dr-scenarios-planning-guide) · [Azure regional cells](https://learn.microsoft.com/en-us/azure/architecture/patterns/geodes)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
