# 2C2P

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

2C2P is a Singapore-headquartered payments platform serving merchants across Southeast Asia and beyond. Its Payment Gateway (PGW) API - currently Payment v4.3 - lets merchants accept cards, e-wallets, QR, installments, and alternative payment methods via a server-to-server REST interface where every request and response body is a JWT (JWS) signed with the merchant's secret key. The platform covers hosted-page and Secure Fields (direct) card capture, tokenization and recurring payments, transaction inquiry and status, void/cancel and refund maintenance, currency exchange, and backend (server-to-server) payment notifications. 2C2P is part of Ant International.

**Areas:** Payments · Payment Gateway · Southeast Asia · Singapore · Thailand · Cards · Digital Wallet · Payment Token · Cross-Border · Fintech

## 2C2P on APIs.io

Everything profiled for 2C2P is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/2c2p/](https://apis.io/providers/2c2p/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [2C2P Secure Fields](https://apis.io/apis/2c2p/2c2p-secure-fields-api/) — Browser-side card capture that loads 2C2P-hosted input elements into the merchant's own checkout page, returning an encryptedCardInfo / securePayToken that…
- [2C2P Do Payment API](https://apis.io/apis/2c2p/2c2p-do-payment-api/) — Execute a payment against a paymentToken.
- [2C2P Exchange Rate API](https://apis.io/apis/2c2p/2c2p-exchange-rate-api/) — Currency exchange rates for DCC / cross-border.
- [2C2P Inquiry API](https://apis.io/apis/2c2p/2c2p-inquiry-api/) — Query transaction result and status.
- [2C2P Maintenance API](https://apis.io/apis/2c2p/2c2p-maintenance-api/) — Void / cancel, refund, and settle operations.
- [2C2P Payment Option API](https://apis.io/apis/2c2p/2c2p-payment-option-api/) — Retrieve available payment options and channel details.
- [2C2P Payment Token API](https://apis.io/apis/2c2p/2c2p-payment-token-api/) — Initialize a payment and obtain a paymentToken.
- [2C2P Tokens API](https://apis.io/apis/2c2p/2c2p-tokens-api/) — Card token and installment plan information.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [2C2P Agentic Access](https://apis.io/agentic-access/2c2p/2c2p-agentic-access/)

#### Collections (8)

Postman and Open Collection request collections.

- [2C2P Payment Gateway API (PGW v4.3)](https://apis.io/collections/2c2p/open-2c2p/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment API](https://apis.io/collections/2c2p/open-2c2p-do-payment-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Exchange Rate API](https://apis.io/collections/2c2p/open-2c2p-exchange-rate-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Inquiry API](https://apis.io/collections/2c2p/open-2c2p-inquiry-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Maintenance API](https://apis.io/collections/2c2p/open-2c2p-maintenance-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Payment Option API](https://apis.io/collections/2c2p/open-2c2p-payment-option-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Payment Token API](https://apis.io/collections/2c2p/open-2c2p-payment-token-api/)
- [2C2P Payment Gateway API (PGW v4.3) Do Payment Tokens API](https://apis.io/collections/2c2p/open-2c2p-tokens-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [2C2P Authentication](https://apis.io/security/2c2p/2c2p-authentication/)
- [2C2P Domain Security](https://apis.io/security/2c2p/2c2p-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [2C2P Plans Pricing](https://apis.io/plans/2c2p/2c2p-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [2C2P Rate Limits](https://apis.io/rate-limits/2c2p/2c2p-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [2C2P Finops](https://apis.io/finops/2c2p/2c2p-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.2c2p.com)
- [Documentation](https://developer.2c2p.com)
- [Blog](https://2c2p.com/news/)

## API Evangelist rating

**Kin Score 24.3** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 43.5 |
| Contract governance | 0.0 |
| Operational transparency | 7.9 |
| Developer ergonomics | 31.0 |
| Access clarity | 7.9 |

**Agent readiness 19.6** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 10.7** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/2c2p/](https://apis.io/providers/2c2p/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for 2C2P: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/2c2p/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
