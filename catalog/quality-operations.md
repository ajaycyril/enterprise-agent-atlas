---
layout: default
title: "Quality and operations"
permalink: /catalog/quality-operations.html
parent: "Library catalog"
---

# Quality & operations

22 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## Testing

### Storybook

**Default.** Isolated component states, interaction stories and design review.

**Tradeoff.** A story can hide backend and reconnect failures. Pair it with a browser integration test.

> Create an approval story for pending, expired, rejected and already handled states.

[Official reference](https://storybook.js.org/docs)

### Playwright

**Default.** Browser verification across run creation, review and reconnection.

**Tradeoff.** Time-based sleeps make event-driven tests brittle.

> Wait for event-derived UI states and assert the same run after reload. Capture traces on failure.

[Official reference](https://playwright.dev/docs/intro)

### axe-core for Playwright

**Default.** Automated accessibility checks within exercised screens.

**Tradeoff.** Manual keyboard, screen reader, zoom and RTL testing remain necessary.

> Check the dialog open state and completed trace, then manually verify focus return and a nonvisual handoff.

[Official reference](https://playwright.dev/docs/accessibility-testing)

### Grafana k6

**Alternative.** Load testing APIs, streams and queues against explicit workload assumptions.

**Tradeoff.** Synthetic throughput without a representative tenant mix is misleading.

> Test bursts from one tenant while measuring another tenant's admission latency and run completion.

[Official reference](https://grafana.com/docs/k6/latest/)

### Vitest

**Alternative.** Fast unit and component-level checks for Vite-oriented applications.

**Tradeoff.** Mocked tests alone cannot verify browser semantics or actual deployments.

> Test the event reducer against duplicates, gaps, terminal transitions and cursor rewind.

[Official reference](https://vitest.dev/guide/)

### Testing Library

**Alternative.** User-oriented component tests written against accessible roles and names.

**Tradeoff.** An accessible query passing still leaves full keyboard and screen-reader journeys to verify.

> Select by role, submit an invalid field and verify the visible recovery message.

[Official reference](https://testing-library.com/docs/)

### Mock Service Worker

**Alternative.** Reproducible request-level behavior for integration tests and component stories.

**Tradeoff.** Keep mocks synchronized with the real API contract.

> Model delayed responses, a denied decision and a stale version using the published schema.

[Official reference](https://mswjs.io/docs/)

### Pact

**Alternative.** Consumer-driven integration contracts between independently released services.

**Tradeoff.** A contract test covers interactions represented by the consumer and provider suites.

> Verify both last production consumer and next consumer contracts before promoting the provider.

[Official reference](https://docs.pact.io/)

## Observability & evals

### OpenTelemetry

**Default.** Correlated traces, metrics and logs across BFF, workflow and model gateway.

**Tradeoff.** Avoid tenant IDs in unbounded metric labels and scrub sensitive span attributes.

> Propagate trace context across queues. Record wait, tool time and model time as separate spans.

[Official reference](https://opentelemetry.io/docs/concepts/signals/)

### Langfuse

**Alternative.** Agent traces, prompt versions, datasets and evaluation results.

**Tradeoff.** Model inputs, outputs and traces can be sensitive. Configure sampling, redaction and retention.

> Tag each result with workflow, prompt, model and dataset version. Compare cost per successful case.

[Official reference](https://langfuse.com/docs)

### Promptfoo

**Default.** Repeatable evaluation suites comparing prompts, providers and application outcomes.

**Tradeoff.** Model-judged scores need human calibration. Keep deterministic controls separate.

> Evaluate route, tool allowlist and evidence correctness against labeled cases and output a CI report.

[Official reference](https://www.promptfoo.dev/docs/intro/)

## Performance & accessibility

### Lighthouse

**Alternative.** Repeatable lab audits of representative pages and constrained device profiles.

**Tradeoff.** A one-off lab score cannot stand in for field measurements or manual accessibility review.

> Run the same authenticated task on every candidate and investigate the largest regression.

[Official reference](https://developer.chrome.com/docs/lighthouse/overview/)

### web-vitals

**Alternative.** Measuring user-centric performance in real browser sessions.

**Tradeoff.** Sampling and device mix can hide regressions for an important cohort.

> Compare p75 responsiveness by route, device class and release cohort with privacy-safe labels.

[Official reference](https://github.com/GoogleChrome/web-vitals)

## Observability

### Jaeger

**Alternative.** Distributed trace exploration for causality, overlapping spans and service latency.

**Tradeoff.** Sampled traces leave gaps in authoritative business history.

> Link a run to its trace and distinguish active tool time, queue delay and human wait.

[Official reference](https://www.jaegertracing.io/docs/latest/)

### Prometheus

**Alternative.** Time-series monitoring and alerts for capacity, rates and saturation.

**Tradeoff.** High-cardinality identifiers multiply storage and query cost.

> Track bounded dimensions on admission, queue age and outcomes. Keep per-case IDs in traces.

[Official reference](https://prometheus.io/docs/introduction/overview/)

### Grafana Tempo

**Alternative.** A trace backend integrated with dashboards and telemetry pipelines.

**Tradeoff.** Storage, sampling and sensitive attributes require deliberate governance.

> Find a slow run from a metric exemplar and inspect linked tool and worker spans.

[Official reference](https://grafana.com/docs/tempo/latest/)

### Sentry

**Alternative.** Application errors, release regressions and related performance symptoms.

**Tradeoff.** Configure scrubbing and consent before collecting sensitive context or replay.

> Attach a safe release tag and route name to an error, then verify source maps and redaction.

[Official reference](https://docs.sentry.io/)

### OpenLLMetry

**Alternative.** LLM-specific instrumentation layered onto OpenTelemetry export pipelines.

**Tradeoff.** Instrumentation can capture sensitive request or response content if left unchecked.

> Define the content capture policy and verify a synthetic sensitive marker never reaches the exporter.

[Official reference](https://github.com/traceloop/openllmetry)

## Model evaluations

### Arize Phoenix

**Alternative.** Open-source tracing and evaluation for LLM and retrieval workflows.

**Tradeoff.** Trace visibility requires privacy controls and calibrated human labels.

> Compare groundedness and tool success by model, dataset version and retrieval strategy.

[Official reference](https://arize.com/docs/phoenix)

### Ragas

**Alternative.** Evaluations of retrieval-augmented answers and evidence quality.

**Tradeoff.** Judge-model scores can be biased or unstable across upgrades.

> Hold evidence fixed, calibrate against human labels and report disagreement on hard examples.

[Official reference](https://docs.ragas.io/en/stable/)

## Data validation

### Great Expectations

**Specialist.** Checking batch or analytical data assumptions before dependent workflows consume it.

**Tradeoff.** Freshness, business validity and expectation ownership still need agreement.

> Quarantine an invalid batch, record the failing expectation and preserve last-known-good data.

[Official reference](https://docs.greatexpectations.io/docs/core/introduction/)

## Reliability

### OpenSLO

**Alternative.** A portable way to express service-level objectives and their indicators.

**Tradeoff.** Backend capabilities and alert translation need testing in the actual monitoring system.

> Define admission latency and successful completion as separate SLIs with agreed measurement windows.

[Official reference](https://openslo.com/)
