# KYE Protocol™

**KYE™ — Know Your Entity™.** An open vocabulary and contract layer for proving *who acted, on whose behalf, with what authority, under what scope, with what evidence* — for **every** action your humans, services, AI agents, models, tools, and workflows take.

KYC tells you who a customer is. KYB tells you who a counterparty is. **KYE™ tells you who acted.** And it does so for every entity that can act, be acted upon, delegate, approve, invoke, or be audited — humans, organisations, workloads, services, AI agents, models, datasets, credentials, and workflows alike.

## What KYE™ does

KYE™ standardises how a system answers — for any governed action — these twelve questions, every time, in a portable form:

1. **Who is the actor?**
2. **On whose behalf is it acting?**
3. **By what authority?**
4. **With what credential or attestation?**
5. **What right is being exercised?**
6. **What scope bounds it?**
7. **What resource is targeted?**
8. **What policy decides?**
9. **What obligations attach?**
10. **What stop conditions apply?**
11. **What runtime event was emitted?**
12. **What proof exists, signed and replayable, that this happened?**

If your system can't answer those twelve questions for every action it takes, you don't have entity-level accountability — you have logs. KYE™ is the contract that turns logs into proof.

## How it works (one diagram)

```text
   Caller (human / agent / workload / service)
                     │
                     ▼
            ┌──────────────────┐
            │   KYE Gateway    │  ← runtime enforcement (PEP)
            │   resolves who   │
            │   verifies what  │
            └────────┬─────────┘
                     │
                     ▼
            ┌──────────────────┐
            │  PDP / sPDP      │  ← decision engine
            │  scope + signals │     (with sector overlays:
            │  + policy        │      Payments, Healthcare, …)
            └────────┬─────────┘
                     │
              decision + obligations
                     │
                     ▼
        ┌────────────────────────────────┐
        │  Append-only audit chain       │  ← evidence
        │  Proof bundle (signed)         │
        │  Transparency receipt          │
        └────────────────────────────────┘
```

Five planes in motion: **identity → authority → decision → execution → evidence**. KYE™ specifies the contracts at each plane. Implementations choose their cloud, language, database, and policy engine.

## Who uses KYE™ — and why

| You are… | KYE™ gives you… |
|---|---|
| **A platform building AI agents that act for customers** | A way to prove every agent action was authorised, scoped, recorded, and revocable — without inventing the wiring yourself. |
| **A regulated SaaS provider** (fintech, health, gov, defense) | A pre-built evidence layer that maps directly onto SOC 2, ISO 27001, PCI DSS, PSD2, DORA, GDPR, HIPAA, NIST 800-207, and EU AI Act controls. |
| **A bank, fintech, or payments company** running agentic workflows | Wallet-bound spend control, dual-approval, signed payment attestations, and replayable proof of every payment authorisation — without becoming a custodian or settlement system. |
| **A security or audit team** | An append-only, hash-linked, signed audit chain plus signed transparency receipts that prove integrity without the auditor having to trust your database. |
| **A standards-aware identity team** | A protocol that **composes** with what you already use (OAuth, OIDC, SPIFFE, EAT, VC, JOSE/COSE, SCITT, GNAP, OpenID SSF/CAEP, OpenID Authorization API, OpenTelemetry) instead of replacing it. |
| **An AI-governance team** | Per-entity autonomy levels, mandatory signal-driven stop / revoke / quarantine cascades, and policy-decision records that satisfy EU AI Act records-of-processing requirements. |

## Benefits at a glance

- **Stoppable agents.** Publish one signal; every Gateway, ePDP, and downstream PEP refuses the next call within seconds. No more "we revoked the API key, please wait 24 hours for the cache to expire".
- **Replayable decisions.** Any policy decision can be reconstructed at any future date from the append-only chain — and the reconstruction proves bit-identical, with a signed receipt to prove it didn't change.
- **Compliance evidence by construction.** The audit chain, proof bundles, and transparency receipts ARE the SOC 2 / ISO 27001 / PCI / DORA / HIPAA evidence. You don't generate evidence — it falls out of doing the work.
- **Acting-on-behalf-of as a first-class concept.** Delegations are explicit, scoped, time-bounded, revocable, and recorded. Not implied by a session token; not lost in a chain of hops.
- **AI-native.** Models, prompt templates, guardrails, tools, and memory stores are first-class entities with classifications, attestations, and stop conditions. Autonomy modes are explicit (advisory → human-in-the-loop → constrained → sandbox-only → blocked).
- **Payments-ready, without becoming the bank.** Wallets, payment authorities, intents, approvals, and rail adapters are governed entities; **balances, settlement, custody, and clearing stay in your existing payment stack**.
- **Standards-composing, not standards-replacing.** Bring your existing OAuth, OIDC, SPIFFE, VC, OpenAPI, OTEL pipelines. KYE™ defines the contracts you wrap them in.
- **Portable.** Cloud-agnostic, database-agnostic, language-agnostic. Same protocol on AWS, Azure, GCP, on-prem, sovereign cloud, or air-gapped.

## How users actually use it

There are three entry points, depending on your role.

### 1. Developer / platform team

You start by **adopting the vocabulary and the wire contracts**:

- Pull the [vocabulary](https://github.com/KYE-Protocol/vocabulary) — entity types, relationship types, action names, lifecycle states, obligations, data classes, reason codes
- Adopt the [ID format](https://github.com/KYE-Protocol/id-format) for every entity in your system
- Use the [examples](https://github.com/KYE-Protocol/examples) as starting templates for your KYE™ artefacts

You then **wire a KYE-compliant Gateway** (or use a hosted one once available) into your runtime, pointed at your existing IdP, your existing policy engine, and your existing audit/observability stack. Existing OAuth tokens, SPIFFE workload identities, and W3C VC credentials all plug in.

### 2. Compliance / security / audit team

You start with the **evidence story**:

- The append-only audit chain is your records-of-processing register (GDPR Art. 30 / SOX / SOC 2 CC8.1)
- Proof bundles are your incident artefacts and your annual-audit handoff
- Transparency receipts are your tamper-detection signal you can point external auditors at
- The control-mappings document maps each KYE™ artefact to specific SOC 2 / ISO 27001 / PCI / PSD2 / DORA / GDPR / HIPAA / NIST 800-207 / EU AI Act controls

You don't need to "instrument for compliance" — KYE™ artefacts are the compliance evidence.

### 3. Product / business team

You start with the **risk and unlock story**:

- "Can I let an AI agent act on a customer's behalf?" → with KYE™, yes, with explicit delegation, scope, attestation, and revocation
- "Can I let an agent move money?" → yes, under wallet-bound spend control, dual approval, and signed payment attestations
- "What if the agent goes rogue?" → publish a stop signal; the cascade quarantines the agent, invalidates active tokens, blocks pending workflows, and records the whole incident, all within seconds

## What's public, what's reserved

| Asset | License |
|---|---|
| Vocabulary, ID format, illustrative examples | **Apache 2.0** — use freely |
| Documentation prose | **CC BY 4.0** where indicated |
| Trademarks (KYE™, KYE Protocol™, KYE Gateway™, KYE Payments™, KYE Certified™) | reserved |
| Reference runtimes and SDKs | published under their own terms |
| Mechanism specifications (replay algorithm, cascade ordering, authority-chain proof, payment-authority binding, gateway enforcement, federation transfer) | **not** under any open-source licence — see Patent notice |

The Apache 2.0 grant **does not** include trademark rights. To indicate conformance, participate in the **KYE Certified™** program.

## Public repositories

| Repository | Contents |
|---|---|
| [`vocabulary`](https://github.com/KYE-Protocol/vocabulary) | Stable names: entity types, relationships, actions, lifecycle states, obligations, data classes, reason codes |
| [`id-format`](https://github.com/KYE-Protocol/id-format) | KYE™ URN identifier format |
| [`examples`](https://github.com/KYE-Protocol/examples) | Illustrative JSON example payloads (every public schema covered) |

These three repositories are sufficient to **discuss, name, and tool against** KYE™. Implementing a conformant runtime requires the normative specification, which is published on a separate track.

## Profile family

KYE™ is a family of profiles, not a monolith.

| Profile | Purpose |
|---|---|
| **KYE-Core™** | Entity model, lifecycle, delegation, scope, decision, audit, proof |
| **KYE-Gateway™** | Runtime enforcement (PEP) and interoperability |
| **KYE-Federation™** | Cross-domain trust + entity transfer |
| **KYE-Credentials™** | Credential / presentation packaging (VC + JOSE/COSE) |
| **KYE-Attestation™** | Workload + entity attestation (SPIFFE + EAT) |
| **KYE-Signals™** | Continuous risk / revocation signaling (SSF/CAEP-compatible) |
| **KYE-Transparency™** | Signed statements + inclusion-proof receipts (SCITT-style) |
| **KYE-Telemetry™** | Observability semantic conventions (OTEL) |
| **KYE-Conformance™** | Machine-testable rules + KYE Certified™ program |
| **KYE-Payments™** | Wallets, payment authorities, intents, approvals, rail adapters |
| **KYE-Treasury™** *(overlay)* | Spend programs, allocation, payout batches |
| **KYE-Custody™** *(overlay)* | Custody-provider binding + signing-policy + key ceremonies |
| **KYE-Healthcare™** *(overlay)* | HIPAA + HITECH (break-glass, patient consent, ePHI) |
| **KYE-Payments-EU™** *(overlay)* | PSD2 + EBA SCA RTS |
| **KYE-Payments-Card™** *(overlay)* | PCI DSS v4 |
| **KYE-Payments High-Assurance™** *(overlay)* | Maximum-strictness payments stack |

## Standards alignment

KYE™ coexists with — does not replace — the standards you already trust:

- **NIST SP 800-207 Zero Trust Architecture** — KYE™ is the resource-centric posture
- **OAuth 2.0 / OIDC / GNAP** — token issuance + delegated authorization
- **OpenID Authorization API** — PDP / PEP exchange compatible
- **OpenID Shared Signals Framework / CAEP** — signal interop
- **SPIFFE / SVID** — workload identity bridge
- **IETF EAT (RFC 9711)** — attestation claim format
- **W3C VC 2.0 + JOSE/COSE** — credential securing
- **SCITT** — transparency receipts
- **OpenTelemetry semantic conventions** — observability vocabulary

## What KYE™ is not

- not a SaaS product
- not a replacement for OAuth, OIDC, SPIFFE, EAT, VC, or SCITT
- not a custodian, processor, ledger, or settlement system
- not an opinionated cloud, database, language, or model

## Patent notice

KYE Protocol™ is the subject of pending patent applications covering specific technical mechanisms — **how** replay, stop cascades, authority-chain proof, payment-authority binding, gateway enforcement, and cross-domain federation transfer actually work. The public repositories deliberately publish only the **vocabulary, naming, and high-level structure**. Anyone interested in implementing a conformant runtime should contact the maintainers about the normative specification track and the **KYE Certified™** conformance program.

## Get involved

- **Use** the vocabulary, ID format, and examples in your own tooling under Apache 2.0
- **Discuss** naming and vocabulary in the issues of the relevant public repository
- **Conformance** — contact the maintainers about the **KYE Certified™** program
- **Specification access** — contact the maintainers about the normative specification track

For collaboration, conformance program participation, or normative specification access, contact the KYE Protocol™ maintainers.

---

KYE™, KYE Protocol™, KYE Passport™, KYE Gateway™, KYE Payments™, KYE Certified™, Know Your Entity™ and the KYE™ logo are trademarks of the KYE Protocol™ maintainers. Use of these marks to indicate conformance requires participation in the KYE Certified™ program.
