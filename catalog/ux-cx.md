---
layout: default
title: "Experience methods"
permalink: /catalog/ux-cx.html
parent: "Library catalog"
---

# UX & customer experience

10 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## Accessibility

### WCAG 2.2

**Default.** Designing and evaluating accessible web content against defined success criteria.

**Tradeoff.** Conformance requires evaluation of actual journeys, components and supported technology.

> Specify keyboard completion, visible focus, input assistance, zoom and motion alternatives for the core task.

[Official reference](https://www.w3.org/TR/WCAG22/)

### ARIA APG

**Default.** Established keyboard interaction and semantics for widgets such as dialogs, tabs and grids.

**Tradeoff.** Applying a role without its expected behavior can worsen accessibility.

> Compare the custom dialog against the APG keyboard and focus pattern with real assistive technology.

[Official reference](https://www.w3.org/WAI/ARIA/apg/patterns/)

### WAI Easy Checks

**Alternative.** An introductory review of headings, contrast, text alternatives and keyboard behavior.

**Tradeoff.** Preliminary checks cover only part of an accessibility evaluation.

> Use the easy checks for triage, then schedule deeper manual coverage of the critical task.

[Official reference](https://www.w3.org/WAI/test-evaluate/preliminary/)

## Service design

### GOV.UK Service Manual

**Default.** Researching, designing, operating and measuring end-to-end transactional services.

**Tradeoff.** Adapt service ownership and channel assumptions to your organization.

> Map the customer's goal, assisted channel, operational dependency and service outcome.

[Official reference](https://www.gov.uk/service-manual)

### Service blueprinting

**Default.** Connecting customer actions to frontstage responses, backstage work and support systems.

**Tradeoff.** A blueprint needs owners and recovery paths at cross-team handoffs.

> Trace a missed appointment from customer notification through agent review to confirmed resolution.

[Official reference](https://www.nngroup.com/articles/service-blueprints-definition/)

## UX research

### 18F Methods

**Alternative.** Practical methods for discovery, synthesis, prototyping and evaluation.

**Tradeoff.** Choose the method around a decision and the evidence you need.

> Write a research question, recruitment criteria, session protocol and how the findings change a decision.

[Official reference](https://guides.18f.org/methods/)

## Experience measurement

### HEART framework

**Default.** Translating product goals into experience signals and metrics.

**Tradeoff.** A broad framework still needs a baseline, denominator and action threshold.

> Map onboarding success to observable task completion, repeat use and a countermetric for support burden.

[Official reference](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/)

## Usability review

### Nielsen usability heuristics

**Alternative.** A structured expert review of visibility, control, errors and consistency.

**Tradeoff.** An expert critique cannot establish how frequently real users fail.

> Attach a screen, user task, severity rationale and a proposed validation method to every issue.

[Official reference](https://www.nngroup.com/articles/ten-usability-heuristics/)

## Localization

### W3C internationalization

**Alternative.** Guidance for language metadata, directionality, multilingual layout and text handling.

**Tradeoff.** Translation alone cannot establish bidirectional or locale behavior.

> Verify mixed Arabic text, Latin case IDs, numbers, dates and keyboard navigation in context.

[Official reference](https://www.w3.org/International/techniques/authoring-html)

## Inclusive design

### Microsoft Inclusive Design

**Alternative.** Identifying mismatches between human abilities, context and product assumptions.

**Tradeoff.** The method works best with participation from people experiencing the exclusion.

> Recruit across permanent, temporary and situational constraints and retest the highest-friction task.

[Official reference](https://inclusive.microsoft.design/)
