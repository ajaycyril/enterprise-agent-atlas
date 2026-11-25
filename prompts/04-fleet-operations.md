---
layout: default
title: "Fleet and robotics operations console"
permalink: /prompts/04-fleet-operations.html
parent: "Prompt collection"
---

# Fleet and robotics operations console

Build a browser-based fleet mission inspection console using Next.js, MapLibre GL JS and deck.gl for tracks, a TanStack Table mission queue, ECharts for telemetry, and React Flow for the planning and verification trace. Start with one grounded use case: an operator investigates a late delivery robot, reviews a route proposal and records an advisory decision. Use recorded or synthetic telemetry for the example. Preserve source timestamps, coordinate units, event age and provenance.

Synchronize selection across map, mission list, trace and time scrubber. Distinguish planned path, reported position and last known position with a legend plus text. Pause playback, inspect a node, compare two time windows, resume live and handle lost telemetry. Keep the map viewport when new records arrive. Provide mobile, reduced-motion, keyboard and low-GPU/table views.

Use a read-only mission adapter, a scoped telemetry summarizer and policy checker, a durable approval workflow, tenant isolation, bounded model budget and audited event stream. Any suggested physical action stays an advisory record in this app. Supply a fixture replay and a separately identified authorized telemetry adapter. Verify late/out-of-order messages, stale data, reconnect, missing GPS and tenant switching. Include original layouts, performance measurements and evidence for each interaction.
