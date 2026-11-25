---
layout: default
title: "UI and visual design prompts"
permalink: /prompts/ui-and-visual-design-recipes.html
parent: "Prompt collection"
---

# UI and visual design prompts

Choose the task, supply the bracketed project inputs and copy the version for your model. Each pair asks for the same outcome with a different briefing style. [Model selection and evaluation](model-guide.md)

## Choose a component foundation

**Claude**

```text
<project>
An enterprise app needs bilingual forms, dialogs and dense lists, with a small design team.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a decision record comparing shadcn/Base UI, React Aria and an established enterprise kit. Use the actual team's skills and existing components to decide which migration cost matters most.
</assignment>

<done_when>
Keyboard use, RTL layout, maintenance ownership and paid feature needs appear in the decision. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: An enterprise app needs bilingual forms, dialogs and dense lists, with a small design team.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a decision record comparing shadcn/Base UI, React Aria and an established enterprise kit. Recommend one primary kit, document its tradeoff and specify a two-screen proof to decide between close options.

Acceptance condition: Keyboard use, RTL layout, maintenance ownership and paid feature needs appear in the decision. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Specify tokens and visual hierarchy

**Claude**

```text
<project>
A product has an analyst desktop, an executive readout and a mobile service form.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare semantic tokens, typography roles, density rules and examples for the three contexts. Map every visual choice to the operator task; identify where a single token cannot safely encode both status and selection.
</assignment>

<done_when>
Changing one status token remains legible in light, dark and high-contrast states. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A product has an analyst desktop, an executive readout and a mobile service form.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver semantic tokens, typography roles, density rules and examples for the three contexts. Return a token table and a before/after description for a blocked case. Include a non-color cue.

Acceptance condition: Changing one status token remains legible in light, dark and high-contrast states. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design a dense data grid

**Claude**

```text
<project>
Analysts compare 30 columns, filter 100,000 records and export approved results.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a grid decision, column plan, server query contract and keyboard interaction model. Compare the cost of building headless interactions with licensing a grid that already supplies them.
</assignment>

<done_when>
Selection survives sorting and the exported row set matches the authorized filters. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: Analysts compare 30 columns, filter 100,000 records and export approved results.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a grid decision, column plan, server query contract and keyboard interaction model. Give the decision, a keyboard acceptance script and a performance experiment with explicit device and workload.

Acceptance condition: Selection survives sorting and the exported row set matches the authorized filters. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design an accessible form

**Claude**

```text
<project>
A long service request can be saved, resumed and corrected after server validation.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare field groups, save policy, inline errors, summary links and focus behavior. Draft the recovery wording alongside the form structure and account for a stale draft version.
</assignment>

<done_when>
The user corrects two invalid fields without losing valid data or leaving the keyboard. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A long service request can be saved, resumed and corrected after server validation.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver field groups, save policy, inline errors, summary links and focus behavior. Return a field/state table and the exact messages for expired session, invalid date and conflicting edit.

Acceptance condition: The user corrects two invalid fields without losing valid data or leaving the keyboard. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Plan an Arabic and English interface

**Claude**

```text
<project>
An approval screen mixes Arabic names, English identifiers, dates and currency.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a bilingual layout specification with logical positioning, bidi isolation and formatting rules. Use the supplied translated content and identify mixed-direction tokens that must preserve their internal order.
</assignment>

<done_when>
The same decision is reachable with a keyboard at 390 px and 200% zoom in both languages. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: An approval screen mixes Arabic names, English identifiers, dates and currency.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a bilingual layout specification with logical positioning, bidi isolation and formatting rules. Describe desktop and narrow layouts and provide a fixture list covering long names, numeric IDs and ambiguous dates.

Acceptance condition: The same decision is reachable with a keyboard at 390 px and 200% zoom in both languages. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Select meaningful dashboard motion

**Claude**

```text
<project>
A triage agent delegates to two specialists and a human reviews their results.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare a component-to-event mapping for React Flow, Motion and an accessible timeline. Read the event fixture first. Explain which movements communicate new facts and which would merely suggest activity.
</assignment>

<done_when>
A duplicate event creates no new transfer; reduced motion conveys the same state and direction. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A triage agent delegates to two specialists and a human reviews their results.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver a component-to-event mapping for React Flow, Motion and an accessible timeline. Return a six-row motion score plus a pause, seek and reconnect test. Assign one owner to each animated property.

Acceptance condition: A duplicate event creates no new transfer; reduced motion conveys the same state and direction. Distinguish observed facts, proposed decisions and tests that still need to run.
```

## Design charts for decisions

**Claude**

```text
<project>
A supervisor must distinguish system slowness from time waiting for a human.
Project-specific inputs: [paste your environment, constraints and evidence here].
</project>

<assignment>
Prepare chart selection, axes, units, denominator and drill-down for queue wait, model time and review time. Compare an aggregated latency chart with a parallel span waterfall for the same investigated case.
</assignment>

<done_when>
A telemetry gap is visible, and the data table reproduces the selected values. Label missing evidence and complete the requested artifact using explicit assumptions where possible.
</done_when>
```

**ChatGPT**

```text
Goal: A supervisor must distinguish system slowness from time waiting for a human.
My inputs: [attach the relevant brief, screenshots, records or constraints].

Deliver chart selection, axes, units, denominator and drill-down for queue wait, model time and review time. Draw the chart brief in words and list three misleading encodings to catch in review, each tied to the supplied metrics.

Acceptance condition: A telemetry gap is visible, and the data table reproduces the selected values. Distinguish observed facts, proposed decisions and tests that still need to run.
```
