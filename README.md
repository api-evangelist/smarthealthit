# SMART Health IT (smarthealthit)

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

SMART Health IT is not a commercial API vendor - it is the open standards and open source project run by the Computational Health Informatics Program at Boston Children's Hospital and Harvard Medical School that defines **SMART on FHIR**: the OAuth 2.0-based SMART App Launch framework that lets patient-facing and clinician-facing apps plug into any EHR and read clinical records over FHIR. The SMART App Launch specification is published through HL7, is required for certified EHRs under the 21st Century Cures Act, and powers integrations like Apple Health Records and CMS Blue Button 2.0. Alongside the specifications (SMART App Launch, FHIR Bulk Data Access, CDS Hooks, SMART Health Cards and Links), the project operates genuinely public, free sandboxes: an open FHIR R4 server full of synthetic patient records, the SMART App Launcher for simulating EHR and patient portal launches without client registration, and a reference Bulk Data server for testing `$export`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/smarthealthit/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/smarthealthit/refs/heads/main/apis.yml)

## Tags

- SMART on FHIR
- FHIR
- Health IT
- EHR Integration
- Clinical Data
- Clinical Records
- Patient Facing
- Open Standards
- Interoperability

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### SMART Sandbox FHIR R4 API

Free, fully open FHIR R4 server loaded with synthetic patient records for app development and testing. No registration or authentication is required - read, search, create, update, and delete clinical resources such as Patient, Observation, Condition, MedicationRequest, Encounter, Immunization, and AllergyIntolerance over plain FHIR REST. Companion open endpoints exist for DSTU2 (`r2.smarthealthit.org`) and STU3 (`r3.smarthealthit.org`).

- **Human URL:** [https://r4.smarthealthit.org](https://r4.smarthealthit.org)
- **Base URL:** `https://r4.smarthealthit.org`

#### Tags

- FHIR R4
- Clinical Records
- Sandbox
- Synthetic Patients

#### Properties

- [Documentation](https://docs.smarthealthit.org/)
- [API Reference](https://r4.smarthealthit.org/metadata)
- [OpenAPI](openapi/smarthealthit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/smarthealthit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smarthealthit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SMART App Launch Authorization API

The SMART App Launcher simulates EHR launches, patient portal launches, and standalone launches against a SMART-protected FHIR R4 proxy, with no client registration required. It implements the HL7 SMART App Launch specification (OAuth 2.0 authorization code with PKCE, launch context, clinical scopes, and token introspection) at `/v/r4/auth/authorize`, `/v/r4/auth/token`, and `/v/r4/auth/introspect`, with the protected FHIR surface at `/v/r4/fhir`.

- **Human URL:** [https://launch.smarthealthit.org](https://launch.smarthealthit.org)
- **Base URL:** `https://launch.smarthealthit.org/v/r4`

#### Tags

- SMART App Launch
- OAuth 2.0
- EHR Launch
- Patient Portal

#### Properties

- [Documentation](https://hl7.org/fhir/smart-app-launch/)
- [API Reference](https://launch.smarthealthit.org/v/r4/fhir/metadata)
- [OpenAPI](openapi/smarthealthit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/smarthealthit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smarthealthit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SMART Bulk Data Export API

Reference implementation of the HL7 FHIR Bulk Data Access specification for testing population-level export. Kick off system, Patient, and Group `$export` operations, poll the async status endpoint, and download NDJSON files. Authenticates with SMART Backend Services (client_credentials with a signed JWT assertion using ES384 or RS384 keys), with a configurable simulated database of up to one million synthetic patients and built-in error simulation.

- **Human URL:** [https://bulk-data.smarthealthit.org](https://bulk-data.smarthealthit.org)
- **Base URL:** `https://bulk-data.smarthealthit.org/fhir`

#### Tags

- Bulk Data
- FHIR Export
- Backend Services
- Population Health

#### Properties

- [Documentation](https://docs.smarthealthit.org/)
- [API Reference](https://bulk-data.smarthealthit.org/)
- [OpenAPI](openapi/smarthealthit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/smarthealthit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smarthealthit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SMART Health Cards Framework

Specification for issuing and verifying tamper-evident clinical records - vaccination history, lab results, and insurance cards - as signed JWS payloads carried in QR codes or files. Issuers expose the FHIR `$health-cards-issue` operation; verifiers validate signatures against published issuer keys. SMART Health Links extend the model to shareable links over richer clinical data. Maintained with the Verifiable Clinical Information (VCI) coalition.

- **Human URL:** [https://smarthealth.cards](https://smarthealth.cards)
- **Base URL:** `https://spec.smarthealth.cards`

#### Tags

- Health Cards
- Verifiable Credentials
- Immunization Records
- Health Links

#### Properties

- [Documentation](https://spec.smarthealth.cards/)

## Common Properties

- [Website](https://smarthealthit.org)
- [Documentation](https://docs.smarthealthit.org)
- [GitHub Organization](https://github.com/smart-on-fhir)
- [Specification](https://hl7.org/fhir/smart-app-launch/)
- [Plans](plans/smarthealthit-plans-pricing.yml)
- [Rate Limits](rate-limits/smarthealthit-rate-limits.yml)
- [Fin Ops](finops/smarthealthit-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
