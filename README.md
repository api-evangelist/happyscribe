# Happy Scribe (happyscribe)

Happy Scribe is a transcription, subtitling, and translation platform. Its REST API (base `https://www.happyscribe.com/api/v1`, Bearer-token auth) turns audio and video into text with automatic (machine) or professional (human) service, generates and translates subtitles/captions, and exports finished transcripts into 15+ formats (SRT, VTT, STL, DOCX, PDF, TXT, JSON, CSV, XLSX, plus editing-suite formats like Adobe Premiere XML, Final Cut Pro XML, EDL, and Avid DS). Work is organized under organizations and folders, files are ingested by URL or signed upload, and webhooks notify consumers when transcriptions complete.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/happyscribe/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/happyscribe/refs/heads/main/apis.yml)

## Access Model

Happy Scribe is a commercial SaaS; there is no open-source server component. API access is available to account holders and is keyed by a **Bearer API token** generated in your Happy Scribe account settings. API usage draws down the **same billing balance as the web app** — automatic (AI) work consumes per-minute AI credits from your subscription/top-ups, and professional (human) transcription or subtitling is billed separately per minute. Long-running work is **asynchronous**: create an order or export, then poll its state, or register a **webhook** to be notified when a transcription completes.

The developer documentation lives at [dev.happyscribe.com](https://dev.happyscribe.com). Endpoint paths, the auth scheme, and the resource set below are grounded in that public documentation. The request/response field schemas in `openapi/happyscribe-openapi.yml` are **honestly modeled** from the docs and may not enumerate every field — reconcile against the live reference before treating them as authoritative.

> **Note on "Shared Links":** Happy Scribe does **not** currently document a shared/public-links API resource. Exposing public share links through the API is an open, user-requested feature, not a shipped endpoint, so it is not modeled here. Sharing/collaboration exists in the product UI only.

## Tags

- Audio Transcription
- Transcription
- Speech-to-Text
- Subtitles
- Captions
- Translation

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Happy Scribe Transcriptions API

List, retrieve, update, and delete transcriptions, and fetch an AI-generated summary of a transcription. Each transcription carries its language, processing state, audio length, and cost. Creating transcriptions directly is deprecated in favor of the Orders API. Core audio-to-text / speech-to-text surface.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Audio Transcription
- Transcription
- Speech-to-Text

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [API Reference](https://dev.happyscribe.com/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Orders API

The preferred way to submit new work. Create transcription or subtitling orders from a media URL and create translation orders, choosing automatic (machine) or professional (human) service, then confirm and track order state through fulfillment. Replaces the deprecated direct transcription creation endpoint.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Transcription
- Subtitles
- Translation

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Exports API

Render finished transcripts into downloadable files across 15+ formats — subtitle/caption formats (SRT, VTT, STL), documents (DOCX, PDF, TXT, JSON, CSV, XLSX), and editing-suite formats (Adobe Premiere XML, Final Cut Pro XML, EDL, Avid DS). Create an export, then poll it for state and a download link.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Exports
- Subtitles
- Captions

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Organizations API

List the organizations (workspaces) the authenticated user belongs to, with role, member count, currency, and whether human transcription and translation are enabled. Organizations scope transcriptions, orders, and billing.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Organizations
- Workspaces

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Organization Memberships API

Manage who belongs to an organization — list memberships, add a member by email with a role, update a member's role, and remove a member. Enables programmatic workspace and seat administration.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Members
- Access Management

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Uploads API

Request a signed upload URL for a local media file, then PUT the file to that URL and pass the resulting temporary URL when creating a transcription or order. The ingestion path for files not already hosted at a public URL.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Uploads
- Files

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Happy Scribe Glossaries and Style Guides API

List the glossaries and style guides available in an organization so they can be attached to orders to improve transcription accuracy and enforce formatting conventions.

- **Human URL:** [https://dev.happyscribe.com/sections/product/](https://dev.happyscribe.com/sections/product/)
- **Base URL:** `https://www.happyscribe.com/api/v1`

#### Tags

- Glossaries
- Style Guides

#### Properties

- [Documentation](https://dev.happyscribe.com/sections/product/)
- [OpenAPI](openapi/happyscribe-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/happyscribe.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/happyscribe.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Authentication](authentication/happyscribe-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/happyscribe)
- [Website](https://www.happyscribe.com)
- [Documentation](https://dev.happyscribe.com)
- [Plans](plans/happyscribe-plans-pricing.yml)
- [Rate Limits](rate-limits/happyscribe-rate-limits.yml)
- [Fin Ops](finops/happyscribe-finops.yml)
- [Blog](https://www.happyscribe.com/blog)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
