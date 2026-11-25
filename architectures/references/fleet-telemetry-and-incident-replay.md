---
layout: default
title: "Fleet telemetry and incident replay"
permalink: /architectures/references/fleet-telemetry-and-incident-replay.html
parent: "Reference architectures"
---

# Fleet telemetry and incident replay

**Design question.** A dispatcher investigates a late delivery from irregular device observations, mission plans and prior service actions.

## Components and information flow

Ingestion records device time, arrival time, sequence and asset identity. A stream processor handles lateness. A historical store powers map and trace projections. Recommendations remain advisory.

## Decision and tradeoff

A fast live projection may be revised by late records. Historical reconstruction needs a declared event-time policy.

## Failure case

A delayed GPS ping appears newer than the last known location in arrival order. Display observation age and handle corrections by device time and revision.

## Acceptance exercise

Replay an out-of-order mission with a telemetry gap. A map selection and the textual ledger must identify the same observation and uncertainty.

## Reference designs

[Apache Flink](https://github.com/apache/flink) · [MapLibre GL JS](https://maplibre.org/maplibre-gl-js/docs/)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
