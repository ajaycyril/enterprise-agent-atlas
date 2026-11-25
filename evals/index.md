---
layout: default
title: "AI agent evals"
permalink: /evals/
nav_order: 6.5
description: "Evaluate enterprise AI agents with labeled cases, outcome and trace graders, repeat trials, tool comparisons and a release decision."
---

# AI agent evals

A booking assistant replies, “You’re confirmed for 4:30.” The provider timed out. A writing-quality judge might like the reply. A grader that compares the reply with the provider’s receipt should fail it. Decide what evidence proves the customer’s outcome before comparing prompts, agents or models.

[Download six labeled booking cases (CSV)](booking-cases.csv) · [Evaluation prompts for Claude and ChatGPT](#prompts-for-claude-and-chatgpt) · [Read the worked article on DigDeep Tech](https://digdeeptech.com/how-to-build-an-enterprise-app-with-ai/#agent-evals)

## Build a small evaluation set

Start with a task a person would recognize. Label the initial state, what the user said, acceptable outcomes, prohibited effects and the record that decides the result. A support lead can label the message a customer should receive. The booking owner can verify what happened to the reservation. Include ambiguity, interrupted work, missing evidence, changed permissions and the routine case. Split development and held-out examples by customer scenario or incident family. Near-duplicate wording in both sets can make a weak change look effective.

| Example | Correct behavior | Evidence to grade |
|---|---|---|
| “After school pickup” with no pickup time | Ask a clarifying question or make a conditional suggestion | User-visible reply and zero writes |
| Confirmation for an available slot | Show the exact slot and receipt | Provider record and customer message agree |
| Acknowledgement lost after a successful booking | Recover the existing receipt | One applied reservation across both attempts |
| Partner timeout with no receipt or lookup | Show pending, reference and follow-up route | Local request is pending and external state is unknown |
| Operator permission revoked | Explain the handoff | Denied write and appropriate disclosure |
| Two customers request the last slot | One receipt and fresh choices for the other customer | Capacity, privacy and both messages |

These synthetic cases illustrate the format. Build a separate, access-controlled holdout from representative, appropriately redacted cases before using results to make a release decision.

## Choose a grader and a denominator

| Question | How to score it |
|---|---|
| Did the customer get the correct outcome? | Passed cases / evaluated cases, broken down by scenario and language. Require both the system state and customer-visible result to satisfy the case. |
| Did the harness respect authority? | Count unauthorized effects, duplicate reservations and confirmations without receipts. Use deterministic assertions against the tool record and final state. Keep counts visible alongside aggregate scores. |
| Did the answer use the right evidence? | For retrieval, measure the fraction of labeled relevant items returned in the top k. Grade factual claims against authorized source passages. Grade empty-evidence cases separately for appropriate abstention. |
| Was the response understandable and actionable? | Ask two reviewers to grade a sample against explicit anchors. For a pending case, 0 means false confirmation or no usable status, 1 means pending with no next step, 2 means pending with a reference and follow-up. Calibrate a model judge on these labels and inspect disagreements. |
| Does the system behave consistently at an acceptable cost? | Repeat cases from identical clean fixtures. Report first-trial success and the fraction of cases passing every one of k trials. Report sample and trial counts, p95 latency and total spend across all attempts / successful outcomes. If no run succeeds, cost per success is undefined. |

Scores can depend on the path. Grade the final state first. Inspect tool calls and handoffs for policy violations or to diagnose a failure. Allow alternate valid paths unless the business process mandates a specific one. [Anthropic’s guide to agent evals](https://www.anthropic.com/research/demystifying-evals-for-ai-agents) · [OpenAI evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)

## Decide what ships

1. **Baseline.** Compare a simple workflow or the current release with the candidate on the same versioned cases. Reset fixtures between trials. Pin prompt, model, tool schema, judge and sampling settings. Vary one factor when attributing a change to a model or prompt.
2. **Review.** Show paired wins and losses, sample sizes, critical failures, latency and spend by slice. Read traces for changed outcomes. For small slices, label uncertainty and expand the sample before generalizing.
3. **Gate.** Agree thresholds with the product and risk owners before running the holdout. For this booking example, any observed false confirmation, unauthorized write or duplicate reservation blocks expansion. A clean seed set warrants a larger evaluation.
4. **Monitor.** In a limited rollout, sample redacted traces, reconcile receipts, track unresolved pending cases and repeated support contact. Roll back on the agreed trigger. Turn a reviewed production failure into a regression case and maintain a fresh holdout.

**Illustrative release decision.** Suppose both candidates pass five of six cases. Candidate A asks an extra question in the routine booking case. Candidate B confirms an unacknowledged reservation. Both score 83%, but B triggers the false-confirmation gate. The owner can review A’s friction separately. These numbers are an example of how to read a report.

## Pick a tool for the work

| Need | Starting point | What you supply |
|---|---|---|
| Regression checks on prompt or provider changes | [Promptfoo](https://www.promptfoo.dev/docs/intro/) | Versioned cases, assertions, spend limit and a CI failure rule |
| Connect a poor production outcome to a repeatable experiment | [Langfuse](https://langfuse.com/docs/evaluation/overview) | Trace redaction, dataset labels, scored observations and retention policy |
| Understand a retrieval failure | [Ragas](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/) | Questions, reference evidence and the inputs each selected metric requires |
| Prove the customer-facing screen agrees with the backend | [Playwright Trace Viewer](https://playwright.dev/docs/trace-viewer) plus service-side assertions | Browser trace, authorized booking fixture and authoritative receipt |

## Prompts for Claude and ChatGPT

The [paired prompt for comparing models](../prompts/agent-workflows-recipes.md#evaluate-prompts-across-models) specifies a controlled experiment. The [retrieval and citation prompt](../prompts/agent-workflows-recipes.md#evaluate-retrieval-and-citations) covers evidence quality. Use the following instructions with either when reviewing a booking workflow.

> Given the six booking cases and the baseline and candidate traces I attach, grade each run against its expected final state, customer message and prohibited effects. Cite the event or receipt behind each grade. Mark missing evidence as unverified. Produce paired wins and losses, a separate count of critical failures and a release recommendation. If I provide only the case definitions, return a blank scorecard and specify the evidence to collect.

[Model routing and evaluation architecture](../architectures/references/model-routing-and-evaluation-gateway.md) · [Release evidence and acceptance criteria](../operations/security-and-release.md#evaluation-design)
