---
layout: default
title: "Prompting Claude and ChatGPT for project work"
permalink: /prompts/model-guide.html
parent: "Prompt collection"
---

# Prompting Claude and ChatGPT for project work

Reviewed 25 November 2026. The [50 task pairs](index.md) are written for the model families below. They are informed by the vendors’ prompting guidance. Comparative quality, cost and latency have to be measured on your own tasks.

| Surface | Model choice for this collection | How to adapt the prompt |
|---|---|---|
| Claude chat or Claude Code, subject to your account's access | Start with Opus 5.5 for substantial implementation and architecture work. Consider Fable 5.2 for more demanding long-horizon analysis. Sonnet 5.5 is a candidate for iteration and Haiku 5.5 for bounded routing or extraction. | Put project context, source material, the requested artifact and completion conditions in distinct sections. For a long brief, identify the evidence the answer should use and give a concrete stopping condition. |
| ChatGPT | GPT-6.2 was announced for rollout in the chat tab on 23 November. Availability varies by plan and rollout. | Put the decision and deliverable first. Attach the actual screenshot, spec or data if you have it. Specify which details need live verification and what a completed answer must contain. |
| OpenAI API | Use `gpt-6.2-astra` as a candidate for demanding design or coding decisions and `gpt-6.2-sol` for repeatable, lower-cost work. | Put persistent project guidance in the documented developer-message location. Use the Responses API for tool calling with these two models. Validate each tool request and return the actual outcome. |
| Claude API | The documented IDs are `claude-fable-5-2`, `claude-opus-5-5`, `claude-sonnet-5-5` and `claude-haiku-5-5`. Verify current availability on your chosen provider. | Tune effort alongside prompt wording on a fixed evaluation set. The same named effort setting can behave differently after a model change. Check the relevant model-specific page. |

[Claude model overview](https://platform.claude.com/docs/en/models/overview) · [Fable 5.2 prompting](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2) · [Opus 5.5 prompting](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5-5) · [ChatGPT release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) · [OpenAI model guide](https://developers.openai.com/api/docs/guides/latest-model) · [OpenAI API changelog](https://developers.openai.com/api/docs/changelog)

## Give each model the same real problem

Suppose two supervisors open the same replacement proposal. One accepts it while the other is reading. Supply both models the proposal revision, the two intended roles, the current database contract, a screenshot of the decision panel and the desired outcome. A one-line “make this enterprise grade” request leaves the most consequential decisions unspecified.

**Claude brief.** Put the screenshot description and existing API contract in a context block. Ask for the expected browser, server and downstream state before and after the race. Finish with a requirement for both user-visible messages and a test proving exactly one external reservation. This structure works especially well when several source documents have similar terminology.

**ChatGPT brief.** Lead with “Return an architecture decision, UX copy for both reviewers, and four acceptance tests.” Supply the same fixture and constraints. Ask the model to distinguish assumptions from observed system behavior. If it has repository tools, ask it to cite the files it inspected and report checks it actually ran. For a design-only task, explicitly request a written specification.

Both sets of prompts work as ordinary chat messages. API parameters belong in API requests, and a chat interface can expose a different set of controls. Attach only material you are authorized to share with the selected service.

## Evaluate optimization

| Hold constant | Change one variable | Record |
|---|---|---|
| Identical problem, artifacts, tool permissions and output rubric | Prompt revision | Did the result answer the decision, preserve facts and cover the rare failure? |
| Same model revision and reference material | Effort setting, when available | Task completion, latency, tokens and cost per accepted answer |
| Same task, tools and rubric | Candidate model | Critical omissions, unnecessary implementation, tool failures and time to a usable artifact |
| Same checklist and reviewer training | Judge or scorer | Agreement with independent human review and examples of disagreements |

Suggested rubric: award 0, 1 or 2 points each for source fidelity, correct architecture, customer recovery, security boundaries and testable acceptance criteria. Record a separate critical failure for unauthorized access, duplicate irreversible effects or fabricated results. A candidate that scores 9/10 with a critical failure still needs review. Compare common cases and difficult slices separately. These are editorial evaluation criteria; the collection reports no head-to-head model benchmark.
