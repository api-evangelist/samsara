# Samsara (samsara)

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

Samsara is a leading connected operations platform for physical operations industries including transportation, logistics, construction, field services, and energy. The Samsara REST API provides programmatic access to fleet telematics, driver safety, compliance (ELD/HOS), vehicle diagnostics, route management, industrial IoT sensors, and workforce management. With over two million connected devices, the platform offers real-time GPS tracking, AI-powered safety cameras, digital inspection forms (DVIRs), IFTA reporting, and data streaming via webhooks and Kafka. Base URL: https://api.samsara.com. Authentication uses Bearer tokens with OAuth 2.0 support.

**APIs.json:** [https://www.samsara.com/](https://www.samsara.com/)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Asset Tracking
- Connected Operations
- ELD
- Fleet Management
- GPS Tracking
- IoT
- Logistics
- Safety
- Telematics
- Transportation

## Timestamps

- **Created:** 2024-11-07
- **Modified:** 2026-05-02

## APIs

### Samsara API

The Samsara REST API provides comprehensive access to fleet and industrial IoT data including vehicles, drivers, assets, routes, compliance (ELD/HOS), safety events, sensor readings, DVIR inspections, documents, forms, addresses, tags, users, and messaging. Supports real-time data, historical queries, webhooks, and Kafka data streaming.

- **Human URL:** [https://developers.samsara.com/](https://developers.samsara.com/)
- **Base URL:** `https://api.samsara.com`

#### Tags

- Addresses
- Assets
- Compliance
- Documents
- Drivers
- DVIR
- ELD
- Fleet
- Forms
- Hours Of Service
- IoT
- Routes
- Safety
- Sensors
- Tags
- Telematics
- Users
- Vehicles
- Webhooks

#### Properties

- [Documentation](https://developers.samsara.com/docs/rest-api-overview)
- [OpenAPI](openapi/samsara-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GitHub Repository](https://github.com/samsarahq/api-docs)
- [Python S D K](https://github.com/samsarahq/samsara-python)
- [Java Script S D K](https://github.com/samsarahq/samsara-js)
- [S D K Documentation](https://developers.samsara.com/docs/sdks)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/samsara)
- [Documentation](https://developers.samsara.com/)
- [Documentation](https://developers.samsara.com/docs/getting-started)
- [GitHub Organization](https://github.com/samsarahq)
- [Authentication](https://developers.samsara.com/docs/authentication)
- [Spectral Rules](rules/samsara-rules.yml)
- [JSON Schema](json-schema/samsara-vehicle-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/samsara-driver-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/samsara-safety-event-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/samsara-vehicle-structure.json)
- [JSON Structure](json-structure/samsara-driver-structure.json)
- [J S O N L D Context](json-ld/samsara-context.jsonld)
- [Example](examples/samsara-list-vehicles-example.json)
- [Example](examples/samsara-list-safety-events-example.json)
- [Vocabulary](vocabulary/samsara-vocabulary.yml)
- [Integrations](https://www.samsara.com/resources/marketplace)
- [L L Ms Txt](https://developers.samsara.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
