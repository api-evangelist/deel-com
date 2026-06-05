# Deel (deel)

Deel is a global workforce platform combining payroll, Employer of Record (EOR), independent contractor management, HRIS, ATS, IT/device management, immigration, and background screenings across 150+ countries. The Deel Public API and SCIM API expose the full worker lifecycle — hire, onboard, pay, manage time off, run payroll, terminate — through a REST surface at api.letsdeel.com/rest/v2 with bearer-token and OAuth2 authentication, a sandbox at api-sandbox.demo.deel.com, HMAC-signed webhooks, a Deel App Store for partner apps, an Embedded "Deel as a Service" model, and a public MCP server for AI agent integration. Deel has compliantly processed over $20B in global payroll for 40,000+ companies.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/deel-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/deel-com/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- HR
- Payroll
- Global Payroll
- EOR
- Employer of Record
- Contractors
- HRIS
- ATS
- Workforce
- Compliance
- Immigration
- Background Checks
- Webhooks
- IT

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Deel Core API

Core organizational, contract, and people APIs covering organizations, legal entities, departments, groups, managers, cost centers, contracts (IC, EOR, COR, Global Payroll), invoice adjustments, lookups (countries, currencies, job titles, seniorities), magic links, tasks, and custom fields. Requires a bearer Organization or Personal API token (scoped permissions per endpoint).

- **Human URL:** [https://developer.deel.com/api/introduction](https://developer.deel.com/api/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- HR
- Workforce
- People
- Contracts
- Invoices

#### Properties

- [Documentation](https://developer.deel.com/api/introduction)
- [Getting Started](https://developer.deel.com/api/quickstart)
- [Authentication](https://developer.deel.com/api/authentication)
- [OpenAPI](openapi/deel-core-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-core-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-core-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/deel-contract-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/deel-person-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/deel-com-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Deel Employer of Record (EOR) API

Employer of Record APIs for compliantly hiring full-time employees in 100+ countries where the client lacks a local entity. Surfaces include EOR cost calculator, three-party EOR contract quote/sign flow, hiring guides by country, EOR amendments, terminations, offboarding, worker compliance/benefits/documents/banks/payslips, and country-specific benefits enrollment.

- **Human URL:** [https://developer.deel.com/api/employer-of-record/introduction](https://developer.deel.com/api/employer-of-record/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- HR
- EOR
- Employer of Record
- Hiring
- Compliance
- Workforce

#### Properties

- [Documentation](https://developer.deel.com/api/employer-of-record/introduction)
- [Documentation](https://developer.deel.com/api/employer-of-record/employment-cost-calculator)
- [Documentation](https://developer.deel.com/api/employer-of-record/hiring)
- [Documentation](https://developer.deel.com/api/employer-of-record/accept-quote)
- [OpenAPI](openapi/deel-eor-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-eor-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-eor-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/deel-eor-contract-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Deel Contractors API

Independent Contractor (IC), Pay-As-You-Go, Milestone, and COR (Contractor of Record) APIs covering IC contract creation, amendments, bulk signing, timesheets, milestones, IC invoicing taxes, off-cycle payments, bonuses, expense reimbursements, and contractor onboarding/offboarding.

- **Human URL:** [https://developer.deel.com/api/contractors/introduction](https://developer.deel.com/api/contractors/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- HR
- Contractors
- Independent Contractors
- Invoicing
- Timesheets
- Workforce

#### Properties

- [Documentation](https://developer.deel.com/api/contractors/introduction)
- [Documentation](https://developer.deel.com/api/contractors/invoice-adjustments)
- [Documentation](https://developer.deel.com/api/contractors/timesheets)
- [OpenAPI](openapi/deel-contractors-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-contractors-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-contractors-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Deel Global Payroll API

Global Payroll APIs for direct employees on the client's own legal entities across 120+ countries. Covers payroll events/cycles, gross-to-net adjustments (bonuses, deductions, one-time payments, expense reimbursements), time tracking shifts, payslips/paystubs, and Global Payroll hiring.

- **Human URL:** [https://developer.deel.com/api/global-payroll/introduction](https://developer.deel.com/api/global-payroll/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- Payroll
- Global Payroll
- HR
- Time Tracking
- Payslips
- Workforce

#### Properties

- [Documentation](https://developer.deel.com/api/global-payroll/introduction)
- [Documentation](https://developer.deel.com/api/global-payroll/time-tracking)
- [Documentation](https://developer.deel.com/api/global-payroll/adjustments)
- [OpenAPI](openapi/deel-global-payroll-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-global-payroll-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-global-payroll-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/deel-payroll-event-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Deel HRIS API

Unified HR Information System API covering all workers (IC, EOR, employee). Surfaces include people directory, working locations, time off (policies, requests, entitlements, events, work schedules), positions, employment information, departments, manager hierarchy, custom HR fields, and SCIM 2.0 user provisioning for Okta, Azure AD, and other IdPs.

- **Human URL:** [https://developer.deel.com/api/hris/introduction](https://developer.deel.com/api/hris/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- HRIS
- HR
- People
- Time Off
- SCIM
- Identity
- Workforce

#### Properties

- [Documentation](https://developer.deel.com/api/hris/introduction)
- [Documentation](https://developer.deel.com/api/scim-api/overview)
- [Documentation](https://developer.deel.com/api/hris-common-use-cases/sync-deel-users-to-identity-providers)
- [OpenAPI](openapi/deel-hris-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-hris-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-hris-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/deel-time-off-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Deel ATS API

Applicant Tracking System API for managing the full recruiting pipeline — jobs and job postings, candidates, applications, attachments, offers, departments, locations, email templates, hiring members, employment types, application sources, tags, and reasons. End-to-end flow candidate-to-contract via the Deel Hire handoff.

- **Human URL:** [https://developer.deel.com/api/ats-guides/introduction](https://developer.deel.com/api/ats-guides/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- ATS
- Recruiting
- Hiring
- Candidates
- Jobs
- HR

#### Properties

- [Documentation](https://developer.deel.com/api/ats-guides/introduction)
- [Documentation](https://developer.deel.com/api/ats-guides/getting-started)
- [Documentation](https://developer.deel.com/api/ats-guides/manage-jobs)
- [Documentation](https://developer.deel.com/api/ats-guides/manage-candidates-and-applications)
- [Documentation](https://developer.deel.com/api/ats-guides/webhooks)
- [OpenAPI](openapi/deel-ats-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-ats-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-ats-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Deel Webhooks API

Webhook management API and event catalog for real-time notifications across contracts, invoices, payroll, time off, EOR onboarding, ATS, and worker lifecycle events. Webhook payloads are HMAC-signed and can be simulated from the Developer Center without affecting production data.

- **Human URL:** [https://developer.deel.com/api/webhooks/introduction](https://developer.deel.com/api/webhooks/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- Webhooks
- Events
- Notifications
- HR
- Payroll

#### Properties

- [Documentation](https://developer.deel.com/api/webhooks/introduction)
- [Documentation](https://developer.deel.com/api/webhooks/quickstart)
- [Documentation](https://developer.deel.com/api/webhooks/events)
- [Documentation](https://developer.deel.com/api/webhooks/simulations)
- [OpenAPI](openapi/deel-webhooks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-webhooks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-webhooks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Deel Platform Extensions API

Specialized platform extensions covering background screenings (KYC/AML), immigration case management (visa types, business visa eligibility, work permits, right-to-work cases, document upload), and Deel IT (device provisioning, equipment assets, asset orders) for distributed workforce hardware management.

- **Human URL:** [https://developer.deel.com/api/platform/introduction](https://developer.deel.com/api/platform/introduction)
- **Base URL:** `https://api.letsdeel.com/rest/v2`

#### Tags

- Compliance
- Background Checks
- Immigration
- Visas
- Equipment
- IT
- Screenings

#### Properties

- [Documentation](https://developer.deel.com/api/platform/screenings)
- [Documentation](https://developer.deel.com/api/platform/immigration)
- [Documentation](https://developer.deel.com/api/deel-it/getting-started/introduction)
- [OpenAPI](openapi/deel-platform-extensions-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deel-platform-extensions-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deel-platform-extensions-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.deel.com)
- [Documentation](https://developer.deel.com/)
- [Documentation](https://developer.deel.com/reference)
- [Getting Started](https://developer.deel.com/api/quickstart)
- [Authentication](https://developer.deel.com/api/authentication)
- [Authentication](https://developer.deel.com/api/oauth)
- [Rate Limits](https://developer.deel.com/api/rate-limits)
- [Documentation](https://developer.deel.com/api/idempotency)
- [Best Practices](https://developer.deel.com/api/best-practices)
- [Versioning](https://developer.deel.com/api/api-versioning)
- [Sandbox](https://developer.deel.com/api/sandbox)
- [Webhooks](https://developer.deel.com/api/webhooks/introduction)
- [Webhooks](https://developer.deel.com/api/webhooks/events)
- [Partner](https://developer.deel.com/api/partners/introduction)
- [Embedded](https://developer.deel.com/api/embedded/introduction)
- [M C P](https://developer.deel.com/mcp/introduction)
- [Documentation](https://developer.deel.com/mcp/connecting-clients)
- [Documentation](https://developer.deel.com/mcp/reference/tools-reference)
- [Community](https://stack.deel.com)
- [Blog](https://www.deel.com/blog/)
- [Pricing](https://www.deel.com/pricing/)
- [Status Page](https://status.deel.com/)
- [Help Center](https://help.letsdeel.com/)
- [Contact Us](https://www.deel.com/contact-us/)
- [LinkedIn](https://www.linkedin.com/company/deel/)
- [X (Twitter)](https://x.com/deel)
- [GitHub Organization](https://github.com/deel)
- [Plans](plans/deel-com-plans-pricing.yml)
- [Rate Limits](rate-limits/deel-com-rate-limits.yml)
- [Fin Ops](finops/deel-com-finops.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
