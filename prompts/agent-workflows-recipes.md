---
layout: default
title: "Agent workflows prompts"
permalink: /prompts/agent-workflows-recipes.html
parent: "Prompt collection"
---

# Agent workflows prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Choose a bounded harness

**Claude**

```text
<project>
A knowledge assistant may need routing, tools, parallel reads and human approval.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a single-agent baseline, escalation triggers and a comparison of eve, LangGraph and a durable workflow owner. Start with the smallest viable loop and identify the first requirement that forces durable ownership.
</assignment>

<done_when>
One layer owns retry and resume per effect and each added specialist has an evaluation reason. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A knowledge assistant may need routing, tools, parallel reads and human approval.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a single-agent baseline, escalation triggers and a comparison of eve, LangGraph and a durable workflow owner. Choose one stack for the supplied team and list the conditions that would change that decision.

Acceptance condition: One layer owns retry and resume per effect and each added specialist has an evaluation reason. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Evaluate retrieval and citations

**Claude**

```text
<project>
An internal assistant answers questions from permission-scoped documents.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an evaluation design for retrieval recall, citation authorization, supported claims, cost and latency. Trace one answer from authorized source to citation before selecting retrieval metrics.
</assignment>

<done_when>
Include revoked documents, no-evidence queries, out-of-date revisions and a human-calibrated rubric. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: An internal assistant answers questions from permission-scoped documents.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an evaluation design for retrieval recall, citation authorization, supported claims, cost and latency. Return the held-out case categories, baseline, metrics and a practical model-change release decision.

Acceptance condition: Include revoked documents, no-evidence queries, out-of-date revisions and a human-calibrated rubric. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Control tool and model budgets

**Claude**

```text
<project>
A fan-out workflow risks repeated reads and unbounded model turns.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a per-run budget policy for tokens, money, duration, attempts and branch depth. Compare soft warnings with hard stops and explain how each interacts with already-running activities.
</assignment>

<done_when>
A budget breach emits an inspectable outcome and cannot initiate another side effect. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A fan-out workflow risks repeated reads and unbounded model turns.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a per-run budget policy for tokens, money, duration, attempts and branch depth. Give a budget ledger and two sample runs, one near limit and one interrupted during a write.

Acceptance condition: A budget breach emits an inspectable outcome and cannot initiate another side effect. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Evaluate prompts across models

**Claude**

```text
<project>
The same project brief can run in Claude, ChatGPT and API-backed agents.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a paired evaluation protocol with identical inputs, independent grading, cost and latency measurements. Distinguish model effort, input context and prompt wording; vary one at a time and include an ablation.
</assignment>

<done_when>
Do not claim a winner until held-out results, errors and relevant cohort slices are supplied. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: The same project brief can run in Claude, ChatGPT and API-backed agents.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a paired evaluation protocol with identical inputs, independent grading, cost and latency measurements. Return blank result tables plus a scored example clearly labeled hypothetical and a rule for choosing a default.

Acceptance condition: Do not claim a winner until held-out results, errors and relevant cohort slices are supplied. Distinguish observed facts, proposed decisions and tests that still need to run.
```
