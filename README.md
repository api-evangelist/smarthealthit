# SMART Health IT (smarthealthit)

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
