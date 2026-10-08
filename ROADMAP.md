# AEraLogIn — Public Development Roadmap

**Public snapshot: 8 October 2026 · Active development**

This is a curated summary of the internal AEraLogIn roadmap, whose statuses were reconciled against source code and phase reports on 6 October 2026. It is **not** a live production audit, security certification, or release-date commitment.

## Direction

**Human ownership → Agent → Runtime → Execution policy → Authorized action → Evidence**

AEraLogIn focuses on distinct identities, runtime-bound authority, accountable execution and interoperable agents. A2A is a primary interoperability path; other protocols are potential adapters, not substitutes for authorization.

## Status glossary

- **Implemented / internally tested**: documented functionality and tests exist within a stated scope, but live deployment assurance may remain outstanding.
- **Partial**: some building blocks exist; the end-to-end capability is incomplete.
- **Planned / release-gated**: not a claim of available functionality.

## Capability overview

| Workstream | Status | Scope and boundaries |
| --- | --- | --- |
| Runtime identity | Implemented / internally tested | Runtime-held Ed25519 keys, signature verification, active-key and request binding, revocation-aware checks; granular permissions remain incomplete. |
| Inbound A2A gateway | Implemented / internally tested | Agent Card, A2A endpoint, peer credentials, scopes, expiry, rotation/revocation, replay controls and rate limiting in documented scope. |
| A2A task lifecycle | Implemented / internally tested | Task persistence, get/list/cancel, SSE streaming, subscriptions and continuation; full cross-agent interoperability and release readiness are separate validations. |
| Execution evidence | Partial | Signed Runtime responses, correlation IDs and inbound audit data; independent receipts and standalone evidence verification are not yet delivered. |
| Capability authorization | Partial | Basic capabilities and peer/skill scopes; formal resource/tool rules, explicit deny semantics and granular decisions remain outstanding. |
| Human authentication | Partial | Wallet/SIWE plus implemented Google OIDC and GitHub OAuth flows; live-provider checks, production configuration, account linking and recovery remain incomplete. |
| Multi-agent delegation | Planned / release-gated | Scoped, revocable, cross-organization delegated execution and outbound task lifecycle still require security controls and interoperability testing. |
| MCP / ANP / PAP / DID / enterprise adapters | Planned | Evaluations and design work only; no conformance or availability claim. |

## Priorities

### P0 — Trust boundary hardening
- Complete authorization correctness, deny semantics and execution-time reauthorization.
- Strengthen runtime isolation, revocation enforcement and explicit destination/resource policy before enabling broad external side effects.
- Test adversarial and cross-boundary failure cases, including untrusted instructions and indirect tool access.
- Treat runtime signatures and logs as bounded evidence, not proof of independent execution assurance.

### P0 — A2A interoperability
- Maintain inbound A2A gateway behavior, protocol compatibility and conformance testing.
- Independently validate multi-agent interoperability before declaring it supported.
- Gate outbound multi-agent delegation on security, consent, isolation and verification requirements.

### P1 — Verifiable execution and delegated authority
- Design authorization evidence and independently verifiable execution receipts.
- Introduce least-privilege, expiring, revocable, task-bound grants with limits on onward delegation.
- Build understandable user approval, grant overview and revocation flows.
- Add data-flow restrictions, budgets and action-bound authorization for sensitive operations.

### P1 — Tool and control-plane assurance
- Preserve instruction provenance, including external content and memory.
- Verify tool/service identity and capability changes.
- Develop execution-profile controls, security event consistency and incident containment.

### P2 — Identity usability and protocol ecosystem
- Finish live-provider testing, account linking and recovery.
- Evaluate passkeys/smart accounts.
- Explore MCP, ANP, PAP, DID, and enterprise identity adapters behind shared authorization boundaries.
- Publish verified interoperability examples and compatibility reports.

## Security and publication principles

1. **Authentication does not imply authorization.**
2. **Protocol compatibility does not imply secure delegated execution.**
3. **Implemented does not mean production-certified.**
4. **Cryptographically signed runtime output is not independently observed proof of a real-world action.**
5. **Future adapters are not advertised as supported standards until implemented and verified.**
6. Deployment-specific security findings, credentials and exploit-ready details are not reproduced in this public roadmap.

## Collaboration

Technical discussions and architectural feedback are welcome. Source availability and contribution processes will be defined for each future public component.

[Organization](https://github.com/AEraLogIn) · [Website](https://aeralogin.com)

_This is a manually curated snapshot, not an automatically synchronized copy of the internal roadmap._
