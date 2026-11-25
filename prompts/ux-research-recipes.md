---
layout: default
title: "UX research prompts"
permalink: /prompts/ux-research-recipes.html
parent: "Prompt collection"
---

# UX research prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Turn a problem into a research plan

**Claude**

```text
<project>
Customers abandon a replacement-booking process before confirmation.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a research question, recruitment matrix, interview guide and evidence-to-decision rule. Distinguish direct observations from hypotheses; design one method to disconfirm the preferred explanation.
</assignment>

<done_when>
Questions elicit past behavior and include users who needed assisted service. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Customers abandon a replacement-booking process before confirmation.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a research question, recruitment matrix, interview guide and evidence-to-decision rule. Deliver a one-week research plan with participants, tasks, synthesis method and the decision it will unblock.

Acceptance condition: Questions elicit past behavior and include users who needed assisted service. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Test information architecture

**Claude**

```text
<project>
Customers confuse reported issues, open cases and booked appointments.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a tree-test protocol with realistic goals, candidate labels and an analysis plan. Use the language in the supplied interview notes to draft multiple labels and identify ambiguous terms.
</assignment>

<done_when>
The test records first choice, completion, wrong turns and confidence. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Customers confuse reported issues, open cases and booked appointments.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a tree-test protocol with realistic goals, candidate labels and an analysis plan. Write five unprompted tasks and a scoring sheet. Show how the results could change the navigation.

Acceptance condition: The test records first choice, completion, wrong turns and confidence. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Run a usability study

**Claude**

```text
<project>
A new operator must identify a blocked case, inspect evidence and approve or decline.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a moderated script, realistic fixture, observer sheet and prioritized findings template. Identify where moderator wording could reveal the answer and replace it with neutral language.
</assignment>

<done_when>
Distinct tasks measure discoverability, understanding and execution without leading the participant. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A new operator must identify a blocked case, inspect evidence and approve or decline.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a moderated script, realistic fixture, observer sheet and prioritized findings template. Return the exact moderator script, rubric, task ordering and post-task questions.

Acceptance condition: Distinct tasks measure discoverability, understanding and execution without leading the participant. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Audit accessibility by journey

**Claude**

```text
<project>
A case reviewer uses keyboard navigation, zoom and a screen reader.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a task-based review plan mapped to applicable WCAG and ARIA patterns. Prioritize issues by task impact and identify which findings need assistive-technology testing.
</assignment>

<done_when>
The full critical decision is reachable without the graph or pointer, with focus restored after errors. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A case reviewer uses keyboard navigation, zoom and a screen reader.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a task-based review plan mapped to applicable WCAG and ARIA patterns. Create a manual checklist, automated checks and an evidence table. Label any untested platform.

Acceptance condition: The full critical decision is reachable without the graph or pointer, with focus restored after errors. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Review product copy and errors

**Claude**

```text
<project>
Users see an ambiguous failure after reserving a slot.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare plain-language copy for pending, retrying, denied, uncertain and confirmed states. Compare candidate wording against the actual backend state and identify any false promise.
</assignment>

<done_when>
Each message says what happened, what is known and what the customer can do next. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Users see an ambiguous failure after reserving a slot.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver plain-language copy for pending, retrying, denied, uncertain and confirmed states. Provide short UI copy and longer support wording for each state. Preserve all actual time and action constraints.

Acceptance condition: Each message says what happened, what is known and what the customer can do next. Distinguish observed facts, proposed decisions and tests that still need to run.
```
