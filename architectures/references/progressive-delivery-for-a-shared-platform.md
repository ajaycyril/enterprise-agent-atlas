---
layout: default
title: "Progressive delivery for a shared platform"
permalink: /architectures/references/progressive-delivery-for-a-shared-platform.html
parent: "Reference architectures"
---

# Progressive delivery for a shared platform

**Design question.** A platform team must ship schema and workflow revisions while active cases continue.

## Components and information flow

CI builds one immutable artifact. Deployment policy verifies identity and digest. Cohort flags choose a revision on admission. Workers drain old workflows and compatibility gates protect events.

## Decision and tradeoff

Canaries reduce exposure. Parallel worker versions and backward-compatible schemas demand operating capacity.

## Failure case

The new worker fails on an old approval. Route the existing run to a compatible worker and stop admission for the new revision.

## Acceptance exercise

Exercise rollback with active runs. Verify the old worker completes them and monitoring distinguishes cohorts by release.

## Reference designs

[Argo CD](https://argo-cd.readthedocs.io/en/stable/) · [OpenFeature](https://openfeature.dev/docs/reference/intro/)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
