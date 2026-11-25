---
layout: default
title: "Research method"
permalink: /method.html
nav_order: 8
---

# How to use and maintain the research

**Scope.** The atlas surveys libraries, frameworks, standards, platforms, design systems and methods across the full application lifecycle. The catalog has one record per named entry. The separate pattern, architecture and prompt collections have their own units. Eighty model-specific prompts represent forty paired tasks. The seven original project briefs are counted separately.

**Selection.** Prefer upstream documentation, standards bodies and original design guidance. An entry must answer a recurring product or engineering decision, identify a material tradeoff and have a credible reference. References describe the upstream capability. Integration instructions, acceptance exercises, architecture combinations and model-specific prompts are editorial recommendations.

**Currency.** The research date is 25 November 2026. Exact version numbers appear where a dated release changes an implementation or model decision. Many docs links follow the current stable release. Recheck security advisories, maintenance status, licenses, hosted service regions, feature-specific editions and support agreements for the planned deployment.

**How to compare.** Evaluate fit for the product, team experience, interoperability, accessibility, operation and recovery, privacy boundaries, maintainability and total cost. Use the same realistic workload for competing options. Scope a claim about performance to the device, traffic profile, versions and measurement window. Grade model prompts against representative tasks and keep unmeasured results explicit.

**Data.** The library catalog is available as [JSON](catalog/tools.json) and [CSV](catalog/tools.csv). The [prompt JSON](prompts/recipes.json) contains the domain, task, two full prompts and an acceptance condition. The GitHub pages include human-readable equivalents and upstream references.

**Corrections.** When proposing a change, name the entry, link the official release or reference and describe how the change affects the design decision. A release date or a passing smoke test alone does not establish suitability for a specific enterprise. [Public source and issue tracker](https://github.com/ajaycyril/enterprise-agent-atlas/issues)
