---
layout: default
title: "Secure tool gateway and human approval"
permalink: /architectures/references/secure-tool-gateway-and-human-approval.html
parent: "Reference architectures"
---

# Secure tool gateway and human approval

**Design question.** Agents can propose a change to an external business system. A separately authorized human must decide whether it proceeds.

## Components and information flow

The model proposes structured arguments. A gateway validates schema and current grants. A reviewer sees the exact proposal digest. A scoped adapter performs the approved effect and records a receipt.

## Decision and tradeoff

A shared tool registry simplifies policy. Tight coupling across team tool schemas increases upgrade and compatibility risk.

## Failure case

After review, destination parameters change or the grant expires. Reject the stale decision and return a fresh proposal for the authorized reviewer.

## Acceptance exercise

Change a proposal field and revoke the reviewer role in controlled fixtures. Both paths must produce zero writes and a clear customer-visible status.

## Reference designs

[MCP architecture](https://modelcontextprotocol.io/docs/learn/architecture) · [Cedar policy language](https://docs.cedarpolicy.com/)

The component combination and acceptance exercise are an editorial design sketch derived from these references.
