# KYE Protocol™

**KYE™ — Know Your Entity™.** An open vocabulary for identifying, authorizing, constraining, auditing, and proving every entity that can act, be acted upon, delegate, approve, invoke, or be audited.

KYE Protocol™ extends entity-level identity, authority, and accountability across humans, organizations, workloads, services, AI agents, models, tools, datasets, credentials, and workflows.

Every governed action is representable as:

> Actor **A** (immutable entity ID **B**) acts on behalf of subject **C**, under authority **D**, using credential or attestation **E**, with right **F**, inside scope **G**, on resource **I**, under policy **J**, in context **K**, producing decision **L**, runtime event **M**, audit chain **N**, and portable proof **O**.

## Public repositories

| Repository | Contents |
|---|---|
| [`vocabulary`](https://github.com/KYE-Protocol/vocabulary) | Entity types, relationships, actions, lifecycle states, obligations, data classes, reason codes |
| [`id-format`](https://github.com/KYE-Protocol/id-format) | KYE™ URN identifier format |
| [`examples`](https://github.com/KYE-Protocol/examples) | Illustrative JSON example payloads |

These are the **patent-safe public surface** of the protocol. They define names, structure, and shape so the protocol can be discussed, named, and tooled against — without disclosing the patentable mechanisms.

## What KYE™ is

A protocol family. Planned profiles include:

- **KYE-Core™** — entity model, lifecycle, delegation, scope, policy decision, audit, proof contracts
- **KYE-Gateway™** — runtime enforcement and interoperability
- **KYE-Federation™** — cross-domain trust
- **KYE-Credentials™** — credential / presentation packaging
- **KYE-Attestation™** — workload and entity attestation
- **KYE-Signals™** — continuous access and risk signaling
- **KYE-Transparency™** — signed statements and receipts
- **KYE-Conformance™** — machine-testable rules
- **KYE-Payments™** — wallets, payment authorities, spend scopes, approvals *(separate profile)*
- **KYE-Treasury™** — treasury allocation and payout governance *(separate profile)*
- **KYE-Custody™** — custody-provider binding and signing policy *(separate profile)*

Profile mechanism specifications and reference implementations are released on a separate track.

## What KYE™ is not

- not a SaaS product
- not a replacement for OAuth, OIDC, SPIFFE, EAT, VC, or SCITT
- not a custodian, processor, ledger, or settlement system
- not a mandated cloud, database, language, or model

KYE coexists with established standards (zero-trust resource-centric enforcement, workload identity, verifiable credentials, attestation, continuous access signals, transparency receipts).

## Standards alignment

KYE artifacts can be packaged or carried using:

- W3C Verifiable Credentials Data Model
- JOSE / COSE secured credentials
- SPIFFE workload identity
- IETF EAT entity attestation
- OpenID Shared Signals Framework / CAEP
- SCITT-style transparency
- OpenID Authorization API for PDP/PEP exchange
- GNAP-style delegated authorization artifacts
- OpenTelemetry semantic conventions
- NIST SP 800-207 zero-trust architecture

## Patent notice

KYE Protocol™ is the subject of pending patent applications covering specific technical mechanisms. The public repositories deliberately publish only the **vocabulary, naming, and high-level structure** of the protocol. They do not publish:

- specific replay or audit-chain reconstruction algorithms
- specific stop, revocation, or attenuation propagation algorithms
- specific authority-chain verification or compression methods
- specific payment authority and wallet-bound spend control mechanisms
- specific gateway enforcement methods for normalizing agent and tool calls
- specific cross-domain federation transfer methods

Anyone interested in implementing a conformant runtime should contact the maintainers about the normative specification track and the **KYE Certified™** conformance program.

## Trademarks

KYE™, KYE Protocol™, KYE Passport™, KYE Gateway™, KYE Payments™, KYE Certified™, and the KYE™ logo are trademarks of the KYE Protocol™ maintainers. Use of these marks to indicate conformance requires participation in the KYE Certified™ program.

## Licensing

| Asset | License |
|---|---|
| Vocabulary, ID format, examples | **Apache License 2.0** |
| Documentation prose | **CC BY 4.0** where indicated |
| Trademarks | reserved |
| Reference implementations | published separately under their own licenses |
| Mechanism specifications and runtime designs | not released under any open-source license |

## Get involved

- **Use** the vocabulary, ID format, and examples in your own tooling under Apache 2.0
- **Discuss** naming and vocabulary in the issues of the relevant public repository
- **Conformance** — contact the maintainers about the **KYE Certified™** program
- **Specification access** — contact the maintainers about the normative specification track

For conformance program participation or normative specification access, contact the KYE Protocol™ maintainers.
