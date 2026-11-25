---
layout: default
title: "Start here"
permalink: /
nav_order: 1
description: "Choose enterprise libraries, reference architectures, UX and security methods, and prompts for Claude and ChatGPT."
---

# Enterprise Agent Atlas

A public field guide for people building enterprise software with AI. Choose a library, inspect a reference architecture, and adapt a prompt to a real project. Reviewed **25 November 2026**.

| What are you deciding? | Start here |
|---|---|
| Which library fits this task? | [198 catalog entries](catalog/index.md), with tradeoffs, official references and prompt fragments. [CSV](catalog/tools.csv) · [JSON](catalog/tools.json) |
| Which architecture should own state, identity and recovery? | [12 workload reference architectures](architectures/reference-index.md), [three execution-stack blueprints](architectures/choose-a-stack.md) and [24 system design patterns](architectures/pattern-library.md) |
| How should an agent look while it works? | [Motion library comparison](design/agent-animation.md), [12 direct design references](design/reference-gallery.md) and [frontend playbook](design/frontend-playbook.md) |
| What would the customer actually experience? | [UI, UX and service design](experience/index.md), including a worked cross-channel service blueprint |
| What security belongs in the first design? | [Basic security architectures](operations/security-foundations.md), followed by [release evidence and evaluation](operations/security-and-release.md) |
| What should I ask Claude or ChatGPT? | [40 task pairs and seven full-project briefs](prompts/index.md), [current model guide](prompts/model-guide.md) and [prompt data](prompts/recipes.json) |

## A useful first pass

Suppose a customer needs a replacement booking. Start with the [customer journey](experience/service-design.md) to define a successful outcome. Use the [secure approval architecture](architectures/references/secure-tool-gateway-and-human-approval.md) to decide who may authorize a change. Use the [handoff reference](design/agent-animation.md) to show what the operator can inspect. Finish with a [security prompt](prompts/security-foundations-recipes.md) that asks what happens when two people approve at once. The same business decision connects the interface, the backend and the acceptance test.

[Research method and source policy](method.md) · [Release landmarks](catalog/release-notes.md) · [Public repository](https://github.com/ajaycyril/enterprise-agent-atlas)
