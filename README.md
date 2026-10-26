# Happy Scribe (happyscribe)

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
