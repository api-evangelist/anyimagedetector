# AnyImageDetector (anyimagedetector)

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

**APIs.json:** [https://anyimagedetector.apievangelist.com/apis.yml](https://anyimagedetector.apievangelist.com/apis.yml)

## Tags

- AI image detection
- image analysis
- computer vision
- content moderation
- trust & safety
- fact-checking
- media verification
- developer tools
- synthetic media
- fraud prevention

## Timestamps

- **Created:** 2026-08-11
- **Modified:** 2026-08-11

## APIs

### AI Image Detector API

REST API with a single endpoint (POST /v1/image/detect) that detects whether an image is AI-generated. Accepts a multipart file upload (JPG, PNG or WebP, up to 8 MB) or a JSON body with a public image URL, and returns verdict, ai_score, confidence, and source_breakdown. Requires a paid account and Bearer/x-api-key authentication; one credit per successful detection; one request per second per API key.

- **Human URL:** [https://imagedetector.online/api](https://imagedetector.online/api)
- **Base URL:** `https://imagedetector.online/v1`

#### Tags

- AI image detection
- image analysis
- computer vision
- content moderation
- trust & safety
- fact-checking
- media verification
- developer tools

#### Properties

- [Documentation](https://imagedetector.online/docs)
- [API Reference](https://imagedetector.online/docs)
- [OpenAPI](openapi/anyimagedetector-ai-image-detector-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/anyimagedetector-ai-image-detector.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/anyimagedetector-ai-image-detector.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Data Model](data-model/anyimagedetector-data-model.yml)
- [Error Catalog](errors/anyimagedetector-problem-types.yml)

## Common Properties

- [M C P Server](mcp/anyimagedetector-mcp.yml)
- [Domain Security](security/anyimagedetector-domain-security.yml)
- [Developer Portal](https://imagedetector.online/api)
- [Documentation](https://imagedetector.online/docs)
- [API Reference](https://imagedetector.online/docs)
- [Support](mailto:support@imagedetector.online)
- [Blog](https://imagedetector.online/blog)
- [Pricing](https://imagedetector.online/pricing)
- [Sign Up](https://imagedetector.online/sign-up)
- [Login](https://imagedetector.online/sign-in)
- [Terms of Service](https://imagedetector.online/terms-of-service)
- [Privacy Policy](https://imagedetector.online/privacy-policy)
- [Methodology](https://imagedetector.online/methodology)
- [Limitations](https://imagedetector.online/accuracy-and-limitations)
- [About](https://imagedetector.online/about)
- [L L Ms Txt](llms/anyimagedetector-llms.txt)
- [Authentication](authentication/anyimagedetector-authentication.yml)
- [Error Catalog](errors/anyimagedetector-problem-types.yml)
- [Rate Limits](rate-limits/anyimagedetector-rate-limits.yml)
- [Plans](plans/anyimagedetector-plans-pricing.yml)
- [Conventions](conventions/anyimagedetector-conventions.yml)
- [Lifecycle](lifecycle/anyimagedetector-lifecycle.yml)
- [Conformance](conformance/anyimagedetector-conformance.yml)
- [Data Model](data-model/anyimagedetector-data-model.yml)
- [Agent Skill](skills/_index.yml)

## Maintainers

**FN:** imagedetector.online
**Email:** support@imagedetector.online
**URL:** https://imagedetector.online
