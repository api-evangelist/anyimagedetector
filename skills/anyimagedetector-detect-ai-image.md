---
name: anyimagedetector-detect-ai-image
description: >-
  Check whether an image is AI-generated using the AnyImageDetector AI Image Detector API, and
  interpret the score correctly — including when to refuse to act on the result. Use when asked
  to verify an image's authenticity, screen marketplace or profile photos, or fact-check a
  picture before publication.
api: AI Image Detector API
provider: AnyImageDetector
base_url: https://imagedetector.online/v1
spec: openapi/anyimagedetector-ai-image-detector-openapi.yml
operations:
  - detectImage
generated: '2026-08-11'
method: generated
source: >-
  Grounded in openapi/anyimagedetector-ai-image-detector-openapi.yml plus the provider's
  published conventions (https://imagedetector.online/docs) and interpretation rules
  (https://imagedetector.online/methodology, /accuracy-and-limitations).
---

# Detect whether an image is AI-generated

One operation, one decision. The hard part is not the call — it is reading the answer honestly
and knowing what you are not allowed to conclude from it.

## Before you call

- **A paid plan is required.** Free accounts cannot create API keys or call `/v1` at all. A key
  on a free account returns `403 paid_plan_required`.
- **Get the key** from Settings → API Keys in the AnyImageDetector account UI. It is shown once
  at creation. It starts with `sk_`.
- **Every successful detection costs 1 credit**, drawn from the same balance the web tool uses.
  Do not call speculatively, and do not call in a loop to "confirm" a result — the API is
  deterministic enough that a repeat call spends a credit for no new information.

## Authenticate

Send exactly one of these headers, never both:

```
Authorization: Bearer sk_your_api_key
```
```
x-api-key: sk_your_api_key
```

Missing or invalid → `401 unauthorized`.

## Call `detectImage`

`POST /v1/image/detect`

Provide **exactly one** of `image` or `imageUrl`.

File upload — JPG, PNG or WebP, **max 8 MB**:

```
curl -X POST https://imagedetector.online/v1/image/detect \
  -H "Authorization: Bearer sk_your_api_key" \
  -F "image=@/path/to/photo.jpg"
```

Public URL — must be reachable over HTTP/HTTPS without credentials:

```
curl -X POST https://imagedetector.online/v1/image/detect \
  -H "Authorization: Bearer sk_your_api_key" \
  -H "Content-Type: application/json" \
  -d '{"imageUrl": "https://example.com/photo.jpg"}'
```

Sending both, sending neither, exceeding 8 MB, or passing a URL the service cannot fetch all
return `400 bad_request`.

## Read the response

```json
{ "verdict": "likely_ai", "ai_score": 0.87, "confidence": "high", "source_breakdown": [] }
```

`ai_score` is the primitive; `verdict` and `confidence` are labels the provider derives from it
using published bands:

| ai_score | verdict | confidence |
|---|---|---|
| 0.75–1.00 | likely_ai | high |
| 0.55–0.74 | likely_ai | medium |
| 0.46–0.54 | uncertain | low |
| 0.26–0.45 | likely_human | medium |
| 0.00–0.25 | likely_human | high |

`source_breakdown` is documented as permanently `[]` — it is reserved for future per-generator
scores. Do not write logic that expects entries in it, and do not report it as evidence.

## Report the result honestly

This is the part that matters most.

- **Never state that an image "is" or "is not" AI-generated.** Report the score, the verdict and
  the confidence, and say the result is probabilistic.
- **Treat `uncertain` as "no answer"**, not as a weak yes. It exists precisely to stop
  overconfident calls near the middle of the range.
- **Say what can break it**, when it is relevant: compression and screenshots, heavy cropping or
  retouching, newly released generators, hybrid images with an AI-edited region, human-made CGI
  and illustration, and low resolution all degrade accuracy in both directions.
- **The provider publishes no accuracy percentage** and says so deliberately. Do not invent,
  estimate, or repeat one from elsewhere as though it applied to this service.
- **Refuse to be the sole basis for a consequence.** The provider states outright that a single
  detector score must not drive disciplinary action, legal claims, payment refusal, account
  suspension, or public accusation. If asked to make such a call from this result alone, say no
  and recommend corroboration: request the original file, check C2PA content credentials
  (this API does not read them), compare metadata, run a reverse-image search, and get human
  review.

## Handle errors

Errors are `application/json`, shaped `{ "error": "...", "message": "..." }` — **not** RFC 9457
problem+json, so there is no `type` URI to dereference.

| Status | error | What to do |
|---|---|---|
| 400 | `bad_request` | Fix the input: one of image/imageUrl, JPG/PNG/WebP, ≤ 8 MB, public URL. Do not retry unchanged. |
| 401 | `unauthorized` | Key missing or invalid. Do not retry. |
| 402 | `insufficient_credits` | Out of credits. Stop; tell the user to upgrade. Do not retry. |
| 403 | `paid_plan_required` | Free account. Stop. |
| 429 | `too_many_requests` | Read the `Retry-After` header (seconds), wait, then retry with exponential backoff. |
| 500 | `detection_failed` | Transient upstream failure. Retry with backoff, then give up and report it. |
| 503 | `unavailable` | Upstream detection provider not configured. Retry later. There is no status page to check. |

## Rate limits and retries — read this before you build a loop

- **1 request per second per API key.** That is the published baseline for every plan; the Pro
  plan advertises a "higher rate limit" with no number attached.
- On `429`, honour `Retry-After` and back off exponentially. There are **no** `RateLimit-*` or
  `X-RateLimit-*` headers, so you cannot see remaining budget before you hit the wall — pace
  yourself to ≤ 1 rps rather than reacting.
- **There is no idempotency key.** If a request times out and you never saw the response, you
  cannot safely retry it: a retry may be billed as a second detection. Prefer to surface the
  ambiguity to the user over silently re-spending their credits.

## What this API does not do

No batch endpoint. No async job or webhook — detection is synchronous. No detection id, so you
cannot re-fetch or dispute a past result through the API. No history endpoint. No C2PA/Content
Credentials reading. No video, no audio, no text.
