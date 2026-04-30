# Contributing to KYE Protocol™

Thanks for your interest. KYE Protocol™ is an open vocabulary and contract layer; the most valuable contributions are the ones that improve clarity, correctness, and conformance.

## Where to file what

| You want to… | Path |
|---|---|
| Ask a question, propose a profile, share an integration | [Discussions](https://github.com/KYE-Protocol/Discussions/discussions) |
| File a vocabulary error / new term proposal | Issue against [`vocabulary`](https://github.com/KYE-Protocol/vocabulary) |
| Fix a URN format edge case | Issue / PR against [`id-format`](https://github.com/KYE-Protocol/id-format) |
| Add or correct an example payload | PR against [`examples`](https://github.com/KYE-Protocol/examples) |
| Report a security vulnerability | **Do not open a public issue.** See [SECURITY.md](SECURITY.md) |
| Suggest a sectoral profile (Treasury, Custody, Healthcare, …) | RFC discussion in [Discussions / RFCs](https://github.com/KYE-Protocol/Discussions/discussions/categories/rfcs) |
| Improve the landing page or whitepaper | PR against [`kye-protocol.github.io`](https://github.com/KYE-Protocol/kye-protocol.github.io) |

## Pull request workflow

1. Open a discussion first if the change is non-trivial — vocabulary additions, schema changes, profile RFCs.
2. Fork, branch, commit. Keep commits small and descriptive.
3. Run the relevant lint / test commands locally before pushing.
4. Open the PR with a one-paragraph rationale and a link to the discussion (if any).
5. CI must pass.

## Style

- **Vocabulary**: lower_snake_case for terms; one term per concept; no synonyms.
- **Schemas**: JSON Schema 2020-12 with absolute `$id` URIs under `https://schemas.kye.dev/`.
- **OpenAPI**: redocly-clean.
- **Markdown**: markdownlint-clean. One H1 per file.
- **Code**: TypeScript / Python / Go formatted by their respective canonical tools.

## Inbound = outbound

By contributing, you agree to license your contribution under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) — the same licence as the project. No CLA is required.

## Trademarks

KYE™, KYE Protocol™, and Know Your Entity™ are trademarks of the KYE Protocol™ project. Do not use them in your fork's name or marketing — see [legal](https://kye-protocol.github.io/legal.html).

## Conduct

Be kind. Cite specifics. Assume good faith. Conduct violations are handled per the [Code of Conduct](CODE_OF_CONDUCT.md).
