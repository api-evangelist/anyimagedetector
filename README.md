# AnyImageDetector (anyimagedetector)

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
