---
layout: default
title: "Event-driven ingestion and audit"
permalink: /architectures/references/event-driven-ingestion-and-audit.html
parent: "Reference architectures"
---

# Event-driven ingestion and audit

**Design question.** Many business systems produce events that feed independent audit, reporting and search consumers.

## Components and information flow

The domain transaction writes a state change plus outbox record. A publisher transfers it to a broker. Consumers checkpoint independently and project by aggregate ID and revision.

## Decision and tradeoff

An outbox limits dual-write failure. CDC can preserve source change order but increases coupling to the database schema.

## Failure case

A publisher dies after broker acknowledgment. The consumer receives a duplicate and must recognize the logical event before modifying its view.

## Acceptance exercise

Reprocess a day of events and compare item counts, audit results and per-aggregate state before and after replay.

## Reference designs

[AWS transactional outbox](https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/transactional-outbox.html) · [Debezium architecture](https://debezium.io/documentation/reference/stable/architecture.html)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
