# Security policy

## Supported versions

| Component | Version | Status |
|---|---|---|
| KYE Protocol™ Core | v1.0.x | Supported |
| Reference Gateway | latest main | Supported (illustrative) |
| TS / Python / Go SDKs | v0.x | Supported |
| Sectoral profiles (Payments, Federation, Credentials, Attestation, Signals, Transparency) | v1.0.x | Supported |

## Reporting a vulnerability

**Do not open a public issue or discussion for security vulnerabilities.**

Send a private report through one of:

1. **GitHub Security Advisories** — preferred. Open a draft advisory on the affected repository.
2. **Email** — use the contact path in the [org profile README](https://github.com/KYE-Protocol/.github/blob/main/profile/README.md). PGP key fingerprint is published there.

Include:

- A description of the issue and the affected component / version
- Steps to reproduce, ideally with a minimal proof-of-concept
- Your assessment of impact (confidentiality, integrity, availability)
- Whether you intend to publish (and any timeline pressure on your end)

## What to expect

- Acknowledgement within **3 business days**.
- Initial triage and severity assessment within **7 business days**.
- A fix or mitigation plan within **30 business days** for high/critical issues; longer for low/medium with explanation.
- Coordinated disclosure: we publish the advisory and the fix at the same time, and credit reporters who want credit.

## Out-of-scope

- Issues in third-party dependencies should be reported upstream first.
- Bugs in vendor-specific KYA implementations (Visa, Skyfire, Persona, Sumsub, Trulioo) should be reported to the vendor.
- Misconfiguration of a deployment that's not in the reference Gateway code.

## Security architecture

For the threat model and explicit mitigations (replay protection, audit-chain integrity, cascade atomicity, credential signature verification, approval timeout handling), see Section 8 of the [whitepaper](https://kye-protocol.github.io/whitepaper.html#security).
