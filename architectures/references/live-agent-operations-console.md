---
layout: default
title: "Live agent operations console"
permalink: /architectures/references/live-agent-operations-console.html
parent: "Reference architectures"
---

# Live agent operations console

**Design question.** Operators need to understand concurrent specialist activity, receipt of evidence and human decisions while a browser disconnects and reconnects.

## Components and information flow

The harness owns checkpoints. The business store owns authorized events and per-run sequence. The BFF projects a safe cursor stream. React Flow and Motion render selected changes.

## Decision and tradeoff

SSE plus HTTP commands suits one-way updates. A bidirectional protocol earns its place when collaborative editing or frequent upstream signals are required.

## Failure case

An interrupted connection delivers a repeated handoff or a gap. Deduplicate by event ID, recover from cursor, then render the authoritative projection.

## Acceptance exercise

Reconnect between branch completion and approval. Compare the timeline and final receipt with a complete, uninterrupted run.

## Reference designs

[LangGraph durable execution](https://docs.langchain.com/oss/python/langgraph/durable-execution) · [React Flow animated edges](https://reactflow.dev/examples/edges/animating-edges)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
