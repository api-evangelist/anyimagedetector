# AnyImageDetector

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

AnyImageDetector (imagedetector.online) is a single-purpose AI-image-detection service for individuals, trust-and-safety reviewers, journalists and developers. Its AI Image Detector API exposes one REST endpoint, POST /v1/image/detect, that accepts a JPG/PNG/WebP file up to 8 MB or a public image URL and returns a verdict (likely_ai, likely_human or uncertain), an ai_score from 0 to 1, a confidence label, and a source_breakdown array reserved for future per-generator scores. The provider publishes the exact score bands that map ai_score to verdict and confidence, and deliberately declines to publish a single accuracy percentage, stating that one number would hide differences between generators, image styles, resolutions and editing conditions. Authentication is a static sk_ API key sent as a Bearer token or an x-api-key header; API access requires a paid plan and each successful detection consumes one credit from the same balance as the web tool. Requests are limited to one per second per key, with Retry-After returned on 429.

**Areas:** AI image detection · Image Analysis · Computer Vision · Content Moderation · Trust and Safety · Fact Checking · media verification · Developer Tools · Synthetic Media · Fraud Prevention

## AnyImageDetector on APIs.io

Everything profiled for AnyImageDetector is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/anyimagedetector/](https://apis.io/providers/anyimagedetector/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [AnyImageDetector Detection API](https://apis.io/apis/anyimagedetector/anyimagedetector-detection-api/) — Analyze an image and report whether it is AI-generated.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [anyimagedetector-mcp.yml](https://apis.io/servers/anyimagedetector/anyimagedetector-mcp-yml/)

#### Collections (1)

Postman and Open Collection request collections.

- [AI Image Detector API](https://apis.io/collections/anyimagedetector/open-anyimagedetector-ai-image-detector/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Anyimagedetector Authentication](https://apis.io/security/anyimagedetector/anyimagedetector-authentication/)
- [Anyimagedetector Domain Security](https://apis.io/security/anyimagedetector/anyimagedetector-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Anyimagedetector Plans Pricing](https://apis.io/plans/anyimagedetector/anyimagedetector-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Anyimagedetector Rate Limits](https://apis.io/rate-limits/anyimagedetector/anyimagedetector-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.imagedetector.online/)
- [Documentation](https://imagedetector.online/docs)
- [API reference](https://imagedetector.online/docs)
- [Pricing](https://imagedetector.online/pricing)
- [Sign up](https://imagedetector.online/sign-up)
- [Blog](https://imagedetector.online/blog)
- [Terms of service](https://imagedetector.online/terms-of-service)
- [Privacy policy](https://imagedetector.online/privacy-policy)

## API Evangelist rating

**Kin Score 39.0** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 15.0 |
| Contract governance | 4.5 |
| Operational transparency | 21.1 |
| Developer ergonomics | 47.0 |
| Access clarity | 76.3 |

**Agent readiness 32.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 22.7** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/anyimagedetector/](https://apis.io/providers/anyimagedetector/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for AnyImageDetector: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/anyimagedetector/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
