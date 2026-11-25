---
layout: default
title: "Security, evaluations and release evidence"
permalink: /operations/security-and-release.html
parent: "Security and release"
---

# Security, evaluations and release evidence

The word “enterprise” becomes actionable when a reviewer can point to a control, its owner and a reproducible test. These are design and acceptance proposals for an agent-operated case desk. Align targets, data regions, edition terms and retention periods with the organization that will operate it.

## Defensive controls

| Risk / boundary | Control to implement | Evidence to require |
|---|---|---|
| Tenant or object access | Enterprise OIDC, server-side tenant selection, object authorization at API, stream, download and tool. Use least-privilege DB roles and RLS. | Two seeded tenants and roles. Attempts to read another tenant’s seeded test case return a denial across all four surfaces. Verify DB policy with the application role. |
| Agent receives untrusted documents | Treat retrieved text and tool output as data, isolate instructions, grant only eligible tools and validate arguments and intended destination outside the model. | A synthetic document with irrelevant instructions cannot change the allowed tool list, approval requirement or destination. |
| Unauthorized or stale action | Bind approval to tenant, actor, action, proposed parameters, version, expiration and policy. Check permissions immediately before the effect. | Expired, modified, wrong-role and double-submitted decisions produce zero unauthorized effects. |
| Cross-run memory or retrieval spill | Namespace memory by tenant and principal/use case, enforce ACLs at retrieval and recheck cited artifacts. | Access revocation removes evidence and memory from subsequent authorized reads; document cache expiry. |
| Generated UI or Markdown | Validate a closed component/action catalog. Encode untrusted output, restrict link schemes and signed capabilities. | Unknown widget and action produce a safe fallback. A frontend click still reaches backend authorization. |
| Secrets or regulated data in telemetry | Workload identity, secret manager and rotation. Redact before export; omit full prompts and raw tool arguments by default. | Seed a synthetic sensitive marker. Verify it is absent from logs, spans, analytics and browser events. Record who can access audit storage. |
| Unnecessary runtime privileges | Run generated code only if required in isolated, short-lived compute with explicit resource and egress limits. | Worker has no production credentials. Output artifacts pass the product's validation policy before release. |
| Web session and browser boundary | Secure session cookies, appropriate SameSite and CSRF protection for mutations, explicit allowed origins, CSP compatible with chosen components. | Expired sessions and invalid origins cannot mutate state. Inspect CSP in the built deployment, including third-party assets. |
| Supply chain | Lock dependencies, review provenance and licenses, scan source/images, generate SBOM, sign approved artifacts and verify issuer and identity at deployment. | Retain digest, SBOM, scan output, signing identity and a signed rollback artifact. Document dated exceptions. |
| Denial of service and cost | Per-tenant admission, bounded tool calls, branch budgets, timeout, cancellation, concurrency limit and safe fallback. | One synthetic tenant at quota cannot consume another tenant's reserved capacity. Measured costs stay inside the defined run budget. |
| Audit and deletion | Separate security audit from debug traces. Specify retention by data class, evidence access and deletion across derived stores. | Run a sample deletion through event payloads, blobs, memory, traces and backup lifecycle. Record mandatory audit exceptions. |

[ASVS](https://asvs.owasp.org/) · [OWASP agentic risks](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) · [Prompt injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) · [Secret management](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) · [Telemetry redaction](https://opentelemetry.io/docs/security/handling-sensitive-data/) · [Cosign verification](https://docs.sigstore.dev/cosign/verifying/verify/)

## Evaluation design

Version the case set, rubric, model identifier, provider, policy, prompts and tool schemas together. Start with human-labeled cases covering common outcomes and high-consequence boundaries. A release dataset needs enough examples per route and tenant context to expose failures.

| Measure | Calculation or test | Example acceptance criterion for a pilot |
|---|---|---|
| Route quality | Per-route precision/recall, confusion matrix and human-review rate | Compare with the existing classifier or a single-agent baseline on the same held-out cases. Review failures for each rare route. |
| Evidence support | Human-labeled supported claims / assessed claims, plus citation resolution and ACL checks | Every cited artifact resolves and is visible to the active user. Set claim-support threshold with domain reviewers. |
| Action integrity | Unauthorized writes and duplicate applied effects on deterministic scenario tests | Zero across the specified test cases, including lost acknowledgments. |
| Durability | Restart at every side-effect boundary, reload UI, duplicate decisions, replay out-of-order and duplicate messages | Final business state and effect count agree with the expected fixture. |
| Budget / performance | p95 admission and update lag, cost per successful case, max steps and wall time | Example pilot targets: p95 admission <1 s and p95 persisted-event-to-visible <2 s on the stated workload. Report actual measurements. |
| Operator usability | Time to identify active agent, reason, evidence and next action; keyboard and reduced-motion runs | A reviewer can complete the required action without the graph or a mouse. |
| Drift | Compare old and new prompt/model/adapter against identical cases; version judge prompts and calibrate with humans | Review paired regressions, high-risk slices and spend changes before expanding a canary. |

[Promptfoo](https://www.promptfoo.dev/docs/intro/) · [Langfuse evaluations](https://langfuse.com/docs/evaluation/overview) · [Playwright](https://playwright.dev/docs/intro) · [Browser accessibility tests](https://playwright.dev/docs/accessibility-testing) · [k6](https://grafana.com/docs/k6/latest/)

## Release sequence

1. Verify lockfile, supported runtime and signed build inputs. Keep preview features behind a flag with an owner and fallback. Run typed contract, migration and scope checks.
2. Run deterministic tool fakes in CI. Compare pinned model/prompt candidates in a controlled evaluation environment using approved data and a spend cap.
3. In staging, use a real provider and a test integration tenant. Rehearse worker restart, signal loss, expired approval, uncertain write, budget exhaustion and rollback. A demo backed only by fixtures should identify itself in the interface.
4. Canary by tenant cohort. Monitor outcomes, spend, provider fallback, event lag, reconciliation backlog and denial rates. Keep the previous worker version available for active workflows.
5. On incident, stop admission or writes as appropriate, retain receipts, drain or suspend affected runs, reconcile external state and re-enable after an accountable review. Measure restore against agreed RPO/RTO and attach the outcome to the release record.

[OpenFeature](https://openfeature.dev/docs/reference/intro/) · [Temporal activity lifecycle](https://docs.temporal.io/activity-definition) · [OpenTelemetry](https://opentelemetry.io/docs/concepts/signals/)
