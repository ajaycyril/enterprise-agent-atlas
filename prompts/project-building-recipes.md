---
layout: default
title: "Project building prompts"
permalink: /prompts/project-building-recipes.html
parent: "Prompt collection"
---

# Project building prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Write the smallest credible project brief

**Claude**

```text
<project>
A builder has a promising idea, two references and one week for a first vertical slice.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a one-page brief with user, job, outcome, inputs, scope, failure path, constraints and acceptance evidence. Use the reference material as context, surface conflicting assumptions and state the narrowest useful first slice.
</assignment>

<done_when>
One customer can complete a real outcome end to end; each reference is tied to a named behavior. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A builder has a promising idea, two references and one week for a first vertical slice.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a one-page brief with user, job, outcome, inputs, scope, failure path, constraints and acceptance evidence. Lead with the outcome. Give the brief, one worked fixture and an evidence checklist; defer only decisions that materially block it.

Acceptance condition: One customer can complete a real outcome end to end; each reference is tied to a named behavior. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Choose references for a coding model

**Claude**

```text
<project>
A builder has screenshots, component docs and a system diagram but little time to explain them.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare an annotated reference pack with behavior to borrow, ownership boundary, adaptation and test. Compare what each source demonstrates with what the builder merely infers, then fill gaps with explicit requirements.
</assignment>

<done_when>
Every reference answers a project decision; include manual checks for any visual claim. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A builder has screenshots, component docs and a system diagram but little time to explain them.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver an annotated reference pack with behavior to borrow, ownership boundary, adaptation and test. Give a three-reference starter pack, a prompt fragment for each and a check that the result fits the actual task.

Acceptance condition: Every reference answers a project decision; include manual checks for any visual claim. Distinguish observed facts, proposed decisions and tests that still need to run.
```
