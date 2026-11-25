---
layout: default
title: "Customer onboarding across channels"
permalink: /architectures/references/customer-onboarding-across-channels.html
parent: "Reference architectures"
---

# Customer onboarding across channels

**Design question.** A customer starts on mobile, uploads evidence later and finishes with assisted support.

## Components and information flow

A journey service holds progress, revision and customer-visible status. Object storage holds restricted evidence. A support adapter reads scoped context. A durable workflow owns reminders and expiry.

## Decision and tradeoff

A shared case reference reduces repeated questions. Persistent drafts introduce consent, deletion and expiry obligations.

## Failure case

A file uploads but validation fails after the user leaves. Keep a recoverable draft and send a contextual status update with a safe resume path.

## Acceptance exercise

Resume from another device after expiry, switch to assisted support and confirm staff can explain exactly what is outstanding.

## Reference designs

[GOV.UK Service Manual](https://www.gov.uk/service-manual) · [OWASP upload design](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
