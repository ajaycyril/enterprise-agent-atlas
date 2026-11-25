---
layout: default
title: "Security and release"
permalink: /operations/security-foundations.html
nav_order: 6
has_children: true
---

# Basic security architecture for an enterprise application

Start with a small tenant-scoped case system. A person signs in through the organization's identity provider, reads an authorized case and approves a proposed change. The same rules apply to a browser, a support console and an agent tool. The design must name an owner for authentication, resource authorization, data protection, action execution and audit. [OWASP ASVS](https://asvs.owasp.org/) · [NIST SP 800-207](https://csrc.nist.gov/pubs/sp/800/207/final)

## Three security reference architectures

| Architecture | Where trust is established | Where authority is enforced | Recovery and proof |
|---|---|---|---|
| Browser → BFF → business API → database | The identity provider authenticates the user. The BFF validates the callback and binds an opaque server-side session to the active principal. | The API authorizes the requested object and action. A least-privilege database role and tenant-aware policies add a second boundary. | Revoke membership during a session. Check protected reads, downloads and subsequent commands. Inspect redacted audit records. |
| Worker → service identity → scoped tool → destination | The workload authenticates using a short-lived identity. The job contains stable tenant, actor and run references. | The tool adapter resolves current policy, destination, approved parameters and allowed scopes. The receiver deduplicates the logical effect. | Rotate credentials, expire an approval and simulate a lost response. Confirm an uncertain write is reconciled using its receipt. |
| Admin console → elevated role → management plane | A named operator uses stronger authentication for sensitive administrative work. | Scope administration by tenant, operation and duration. Separate requester and approver where policy requires it. | Expire the elevated grant, review a break-glass action and verify the reason, approver and actual changes are reconstructible. |

[OWASP authentication](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) · [Authorization](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) · [Session management](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html) · [SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/)

## Threat-model worksheet

| Boundary | Questions to answer | Evidence to request |
|---|---|---|
| Login and recovery | Which issuer and audience are trusted? How are sessions created, rotated and revoked? What happens after a lost device? | Auth flow diagram, expected expiry and account-recovery test with a seeded user. |
| Tenant and role | How is tenant membership derived? Which relationships permit view, approve, export or administer? | Resource/action matrix and a pair of controlled tenants showing permitted and denied cases. |
| API and browser | Where are mutation authorization, schema validation, session protection and origin policy enforced? | An endpoint inventory with owner, required grant, expected denial, audit event and safe error message. |
| Secrets and storage | Which services may retrieve which secret? How are keys rotated and backups restored? | Workload identity mapping, rotation drill, per-data-class retention and restored access-control test. |
| File intake | Who may upload, scan, process and later retrieve an object? Where are untrusted files held? | Quarantine state, bounded type/size handling, safe preview and an authorized download path. |
| Agent tools | Can untrusted content alter grants or destinations? Which actions need human authority? | Narrow tool registry, data redaction rule, versioned proposal and receipt. Test with synthetic inert fixtures. |
| Delivery | Who can change source, approve a build or promote an artifact? | Locked inputs, limited build identity, provenance, SBOM, image digest and rollback evidence. |
| Operations | How will a team detect misuse, contain affected work and communicate service recovery? | Owner, detection coverage, retention, escalation, recovery target and a recorded tabletop exercise. |

[Upload guidance](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html) · [Secrets](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) · [Logging](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html) · [Release controls](security-and-release.md)

## A worked policy decision

A shift supervisor is allowed to approve a replacement slot for one service region. Resolve subject, tenant, case, service region, membership, proposal revision, expiry and action at the server. Record the policy version and decision before dispatch. If the carrier receives the update but its acknowledgment is lost, the case moves to reconciliation. An authorized operator retrieves the receipt using the stable effect ID. A repeat click returns the recorded decision. The browser can render the same history without calling the carrier.

For a design review, ask for the resource/action matrix, trust boundaries, failure behavior and one piece of test evidence for each control. This makes “secure by default” a specification that engineering, support and an auditor can all read.
