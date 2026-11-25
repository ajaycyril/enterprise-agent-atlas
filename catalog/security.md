---
layout: default
title: "Security references"
permalink: /catalog/security.html
parent: "Library catalog"
---

# Security

32 entries · Reviewed 25 November 2026. Each entry includes a use case, the main tradeoff, a prompt fragment and its original reference.

## Identity & access

### OpenID Connect

**Default.** Federated identity for enterprise login through the organization's identity provider.

**Tradeoff.** Identity alone does not authorize access to a tenant's records.

> Validate issuer and audience, map tenant membership server-side, and renew the session on sensitive decisions.

[Official reference](https://openid.net/developers/how-connect-works/)

### Keycloak

**Alternative.** Self-managed identity and federation for teams with the operational capacity.

**Tradeoff.** Owning the IdP adds patching, availability and recovery obligations.

> Integrate a separate test realm and exercise role withdrawal, session expiry and logout propagation.

[Official reference](https://www.keycloak.org/)

### OpenFGA

**Alternative.** Relationship-based checks for shared cases, delegated reviewers and hierarchical access.

**Tradeoff.** Relationship writes and caching introduce consistency questions at revocation.

> Represent reviewer and viewer relationships on cases. Recheck write permission immediately before execution.

[Official reference](https://openfga.dev/docs/concepts)

### Open Policy Agent

**Alternative.** Contextual policy decisions outside model prompts and application conditionals.

**Tradeoff.** Policy distribution, decision logging and fail-closed behavior need owners.

> Gate tool invocation using subject, tenant, action, resource and approval state. Persist the policy version.

[Official reference](https://www.openpolicyagent.org/docs)

### Vault

**Alternative.** Central secrets management where teams need scoped credentials and rotation.

**Tradeoff.** Plan how workloads authenticate, renew leases and behave during an outage.

> Use workload identity to retrieve scoped secrets. Never pass raw secrets through prompts or user traces.

[Official reference](https://www.hashicorp.com/en/products/vault)

## Verification & supply chain

### OWASP ASVS

**Default.** Verification requirements for prioritizing application security controls and tests.

**Tradeoff.** A checklist needs traceable evidence, applicability and ownership.

> Map applicable requirements to tests, evidence links and accountable owners for this app.

[Official reference](https://owasp.org/www-project-application-security-verification-standard/)

### OWASP agentic and GenAI guidance

**Default.** Threat categories for agent tools, autonomy, identities and delegated work.

**Tradeoff.** Pair threat descriptions with preventive controls and release evidence.

> Threat-model untrusted retrieved content, excessive agency and over-scoped access. Test the intended denial paths.

[Official reference](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)

### Semgrep

**Alternative.** Static analysis for unsafe patterns in generated and handwritten source.

**Tradeoff.** Rules need tuning and owners to prevent high-noise gates.

> Review new high-confidence findings on changed code and record time-limited, owned exceptions.

[Official reference](https://semgrep.dev/docs/)

### Trivy

**Alternative.** Scan built artifacts and infrastructure configuration for known issues.

**Tradeoff.** Scan results depend on advisory freshness, artifact scope and configuration.

> Scan the release image digest and IaC, record the scanner database time and triage actionable findings.

[Official reference](https://github.com/aquasecurity/trivy)

### CycloneDX

**Alternative.** Standard bill-of-materials format for dependencies and shipped artifacts.

**Tradeoff.** Generating an SBOM does not prove the release came from the trusted build.

> Attach an SBOM to the release digest and verify it identifies the dependencies actually shipped.

[Official reference](https://cyclonedx.org/)

### Sigstore Cosign

**Alternative.** Sign and verify artifact identity and attestations in the release pipeline.

**Tradeoff.** A valid signature still needs a trusted issuer and expected signing identity.

> At deployment verify the artifact digest, expected workflow identity and issuer before promotion.

[Official reference](https://docs.sigstore.dev/cosign/verifying/verify/)

### SLSA

**Alternative.** Supply-chain framework for evaluating build provenance and integrity.

**Tradeoff.** Choose a target level and verify its actual requirements before making assurance claims.

> Record source revision, builder identity and provenance verification alongside each release.

[Official reference](https://slsa.dev/spec/)

## Identity & sessions

### OAuth 2.0 Security BCP

**Default.** A current baseline for evaluating delegated authorization flows and client behavior.

**Tradeoff.** Map the recommendations to your client type, identity provider and supported flows.

> Document redirect validation, token audience, PKCE and token storage for the selected client.

[Official reference](https://www.rfc-editor.org/rfc/rfc9700)

### WebAuthn

**Alternative.** Public-key credentials for user authentication, including passkey-capable journeys.

**Tradeoff.** Enrollment, recovery, device availability and accessibility affect adoption.

> Design registration, sign-in, lost-device recovery and fallback ownership as one journey.

[Official reference](https://www.w3.org/TR/webauthn-3/)

### SCIM

**Specialist.** Tenant provisioning and deprovisioning between an enterprise IdP and SaaS.

**Tradeoff.** Sync lag and group mappings complicate immediate access revocation.

> Show how disabling a directory account revokes active access and queued approvals.

[Official reference](https://www.rfc-editor.org/rfc/rfc7644)

## Workload identity

### SPIFFE

**Specialist.** Portable workload identity across service boundaries.

**Tradeoff.** A trust domain and attestation policy require an operating owner.

> Name each worker identity and verify the audience and trust domain before granting a tool.

[Official reference](https://spiffe.io/docs/latest/spiffe-about/overview/)

### SPIRE

**Specialist.** Issuing and rotating identities for attested workloads in a SPIFFE deployment.

**Tradeoff.** Trust bootstrap and agent availability are infrastructure dependencies.

> Define node and workload attestation plus the behavior when identity renewal is unavailable.

[Official reference](https://spiffe.io/docs/latest/spire-about/)

## Authorization

### Cedar

**Alternative.** Policy-as-code decisions using principals, actions, resources and context.

**Tradeoff.** The application must supply correct entities and enforce every decision.

> Evaluate a reviewer action against tenant, case, role and proposal revision immediately before the write.

[Official reference](https://docs.cedarpolicy.com/)

### Zanzibar model

**Alternative.** A reference design for relationship-based authorization at significant scale.

**Tradeoff.** Consistency after permission changes matters as much as relationship modeling.

> Explain revocation freshness and how nested membership is bounded and tested.

[Official reference](https://research.google/pubs/zanzibar-googles-consistent-global-authorization-system/)

## Secrets

### OpenBao

**Alternative.** Self-managed secret storage, dynamic credentials and leases where operational control is needed.

**Tradeoff.** Recovery, unsealing, availability and rotation require a named team.

> Describe workload login, scoped lease lifetime, revocation and an outage drill.

[Official reference](https://openbao.org/docs/)

## Policy enforcement

### Kyverno

**Alternative.** Kubernetes admission and policy enforcement for cluster workloads.

**Tradeoff.** An overly broad policy can block legitimate deployments or create noisy exceptions.

> Start with an owned policy report, test known workloads and explicitly approve enforcement scope.

[Official reference](https://kyverno.io/docs/)

## Runtime detection

### Falco

**Specialist.** Runtime event detection for containerized workloads and operating-system activity.

**Tradeoff.** High-volume alerts need tuning, correlation and an investigation owner.

> Map one approved detection to an incident runbook and measure false positives on normal batch jobs.

[Official reference](https://falco.org/docs/)

## Supply chain

### Syft

**Alternative.** Software bill of materials generation for built packages and images.

**Tradeoff.** Source and final-image inventories can differ.

> Generate an SBOM for the release digest and associate the artifact and build metadata.

[Official reference](https://github.com/anchore/syft)

### OSV-Scanner

**Alternative.** Dependency vulnerability screening against machine-readable advisories.

**Tradeoff.** Reachability and business exposure still require triage.

> Record affected package, shipped artifact, advisory revision and the owner of a remediation decision.

[Official reference](https://google.github.io/osv-scanner/)

### OpenSSF Scorecard

**Alternative.** Comparing observable repository security practices before adopting a dependency.

**Tradeoff.** Scores can lag or misrepresent project context and are insufficient on their own.

> Review the underlying checks, maintainer activity, provenance and unresolved findings.

[Official reference](https://scorecard.dev/)

## Security architecture

### NIST Zero Trust Architecture

**Alternative.** A reference for resource-centric access decisions across users, devices and workloads.

**Tradeoff.** A design principle requires an inventory of resources, policy points and actual enforcement.

> Mark policy decision, enforcement, identity evidence and audit boundaries on the architecture diagram.

[Official reference](https://csrc.nist.gov/pubs/sp/800/207/final)

### OWASP Cheat Sheet Series

**Default.** Practical defensive reference material for sessions, authorization, uploads and logging.

**Tradeoff.** Select guidance relevant to your stack and threat model.

> Map three concrete controls to their enforcement location and a non-destructive acceptance check.

[Official reference](https://cheatsheetseries.owasp.org/)

## Security governance

### OWASP SAMM

**Alternative.** Assessing maturity and prioritizing improvements to a software security program.

**Tradeoff.** Maturity levels measure practices and require evidence from teams.

> Select an improvement under design, implementation or verification with owner, evidence and target date.

[Official reference](https://owaspsamm.org/model/)

## Privacy and release evidence

### Microsoft Presidio

**Alternative.** Identify and anonymize selected sensitive fields in text before secondary use.

**Tradeoff.** Recognition varies by language and entity. Test local names and account formats with synthetic fixtures.

> Compare missed and unnecessary redactions on approved Arabic and English examples.

[Official reference](https://microsoft.github.io/presidio/)

### TruffleHog

**Alternative.** Check authorized repositories and build inputs for exposed secrets as part of release hygiene.

**Tradeoff.** Treat findings as sensitive and establish who can rotate affected credentials.

> Specify a release gate and the incident owner for a seeded test credential without printing the value.

[Official reference](https://github.com/trufflesecurity/trufflehog)

### OWASP Threat Dragon

**Alternative.** Document system data flows, trust boundaries and defensive controls during design.

**Tradeoff.** A diagram goes stale as tools and data sources change. Review it alongside the deployment diff.

> Trace a customer lookup and an approval through the system and identify the enforcement point on each boundary.

[Official reference](https://owasp.org/www-project-threat-dragon/)

### in-toto

**Specialist.** Record and verify attestations about how software artifacts were produced.

**Tradeoff.** An attestation is only useful when deployment verifies trusted identities and the intended artifact digest.

> Describe which release evidence the deployment checks before admitting a worker image.

[Official reference](https://in-toto.io/)
