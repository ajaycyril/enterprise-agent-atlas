---
layout: default
title: "Secure document intake"
permalink: /architectures/references/secure-document-intake.html
parent: "Reference architectures"
---

# Secure document intake

**Design question.** Multiple external parties submit large attachments that staff and AI workers later inspect.

## Components and information flow

Issue an object-specific short-lived upload grant. Hold the file in quarantine. A validation job records a decision and promotes approved content. Reauthorize downloads and derived previews.

## Decision and tradeoff

Direct uploads reduce API bandwidth. A quarantine pipeline adds asynchronous states that the interface must explain.

## Failure case

An interrupted upload or failed scanner leaves orphaned objects. Bound lifetime and keep attachments unavailable until a verified release decision.

## Acceptance exercise

Interrupt before and after scan completion. Verify no preview escapes quarantine and orphan cleanup preserves accepted files.

## Reference designs

[Azure valet key](https://learn.microsoft.com/en-us/azure/architecture/patterns/valet-key) · [OWASP file uploads](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
