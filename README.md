# Deel (deel-com)
Deel is a global workforce platform combining payroll, Employer of Record (EOR), independent contractor management, HRIS, ATS, IT/device management, immigration, and background screenings across 150+ countries. The Deel Public API and SCIM API expose the full worker lifecycle — hire, onboard, pay, manage time off, run payroll, terminate — through a REST surface at `api.letsdeel.com/rest/v2` with bearer-token and OAuth2 authentication, a sandbox at `api-sandbox.demo.deel.com`, HMAC-signed webhooks, a Deel App Store for partner apps, an Embedded "Deel as a Service" model, and a public MCP server for AI agent integration. Deel has compliantly processed over $20B in global payroll for 40,000+ companies.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/deel-com/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - HR, Payroll, Global Payroll, EOR, Employer of Record, Contractors, HRIS, ATS, Workforce, Compliance, Immigration, Background Checks, Webhooks, IT

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Pricing Snapshot

| Product | Tier | Per-Worker / Month (USD) |
|---|---|---|
| Contractors | Standard | $49 |
| Contractor of Record | Standard | $325 |
| Employer of Record | Standard | $599 |
| Employer of Record | Enterprise | $899 |
| US PEO | Standard | $125 |
| Global Payroll (Managed Global) | Standard | $29 |
| Global Payroll (Managed US) | Standard | $29 |
| Deel HR — Core HR | Standard | $5 |
| Deel HR — Recruit | Standard | $14 |
| Deel HR — Develop | Standard | $22 |
| Deel HR — Full HR | Bundle | $56 |
| Deel IT | Platform | $10 |
| Deel IT | Starter | $45 |
| Deel IT | Growth | $125 |
| Deel IT | Scale | $133 |

## APIs

### Deel Core API
Core organizational, contract, and people APIs covering organizations, legal entities, departments, groups, managers, cost centers, contracts (IC, EOR, COR, Global Payroll), invoice adjustments, lookups (countries, currencies, job titles, seniorities), magic links, tasks, and custom fields.

**Human URL:** [https://developer.deel.com/api/introduction](https://developer.deel.com/api/introduction)

- [Documentation](https://developer.deel.com/api/introduction)
- [Getting Started](https://developer.deel.com/api/quickstart)
- [Authentication](https://developer.deel.com/api/authentication)
- [OpenAPI](openapi/deel-core-api-openapi.yml)
- [JSON Schema — Contract](json-schema/deel-contract-schema.json)
- [JSON Schema — Person](json-schema/deel-person-schema.json)
- [JSON-LD](json-ld/deel-com-context.jsonld)
- [Naftiko Capability — Contracts](capabilities/core-contracts.yaml)
- [Naftiko Capability — People](capabilities/core-people.yaml)
- [Naftiko Capability — Invoice Adjustments](capabilities/core-invoice-adjustments.yaml)

### Deel Employer of Record (EOR) API
Employer of Record APIs for compliantly hiring full-time employees in 100+ countries where the client lacks a local entity. Surfaces include EOR cost calculator, three-party contract quote/sign flow, hiring guides by country, amendments, terminations, and worker compliance/benefits/documents/payslips.

**Human URL:** [https://developer.deel.com/api/employer-of-record/introduction](https://developer.deel.com/api/employer-of-record/introduction)

- [OpenAPI](openapi/deel-eor-api-openapi.yml)
- [JSON Schema — EOR Contract](json-schema/deel-eor-contract-schema.json)
- [Naftiko Capability — EOR Hiring](capabilities/eor-hiring.yaml)
- [Naftiko Capability — EOR Cost Calculator](capabilities/eor-cost-calculator.yaml)
- [Naftiko Capability — EOR Worker Information](capabilities/eor-worker-information.yaml)

### Deel Contractors API
IC, Pay-As-You-Go, Milestone, and Contractor of Record (COR) APIs covering IC contract creation, amendments, bulk signing, timesheets, milestones, IC invoicing taxes, off-cycle payments, bonuses, and expense reimbursements.

**Human URL:** [https://developer.deel.com/api/contractors/introduction](https://developer.deel.com/api/contractors/introduction)

- [OpenAPI](openapi/deel-contractors-api-openapi.yml)
- [Naftiko Capability — IC Contracts](capabilities/contractors-contracts.yaml)
- [Naftiko Capability — Timesheets](capabilities/contractors-timesheets.yaml)

### Deel Global Payroll API
Global Payroll APIs for direct employees on client-owned legal entities across 120+ countries. Covers payroll events/cycles, gross-to-net adjustments (bonuses, deductions, reimbursements), time-tracking shifts, payslips/paystubs, and Global Payroll hiring.

**Human URL:** [https://developer.deel.com/api/global-payroll/introduction](https://developer.deel.com/api/global-payroll/introduction)

- [OpenAPI](openapi/deel-global-payroll-api-openapi.yml)
- [JSON Schema — Payroll Event](json-schema/deel-payroll-event-schema.json)
- [Naftiko Capability — Payroll Events](capabilities/payroll-events.yaml)
- [Naftiko Capability — Payroll Adjustments](capabilities/payroll-adjustments.yaml)

### Deel HRIS API
Unified HRIS across all worker types: people directory, working locations, time off (policies, requests, entitlements, events, work schedules), positions, employment information, departments, manager hierarchy, custom HR fields, and SCIM 2.0 user provisioning for Okta, Azure AD, and other IdPs.

**Human URL:** [https://developer.deel.com/api/hris/introduction](https://developer.deel.com/api/hris/introduction)

- [OpenAPI](openapi/deel-hris-api-openapi.yml)
- [JSON Schema — Time Off](json-schema/deel-time-off-schema.json)
- [SCIM Overview](https://developer.deel.com/api/scim-api/overview)
- [Naftiko Capability — People](capabilities/hris-people.yaml)
- [Naftiko Capability — Time Off](capabilities/hris-time-off.yaml)
- [Naftiko Capability — SCIM](capabilities/hris-scim.yaml)

### Deel ATS API
Applicant Tracking System API for the full recruiting pipeline — jobs and job postings, candidates, applications, attachments, offers, departments, locations, email templates, hiring members, employment types, application sources, tags, and reasons — with an end-to-end candidate-to-contract flow.

**Human URL:** [https://developer.deel.com/api/ats-guides/introduction](https://developer.deel.com/api/ats-guides/introduction)

- [OpenAPI](openapi/deel-ats-api-openapi.yml)
- [Naftiko Capability — Jobs](capabilities/ats-jobs.yaml)
- [Naftiko Capability — Candidates](capabilities/ats-candidates.yaml)
- [Naftiko Capability — Applications](capabilities/ats-applications.yaml)

### Deel Webhooks API
Webhook management API and event catalog for real-time notifications across contracts, invoices, payroll, time off, EOR onboarding, ATS, and worker lifecycle events. Webhook payloads are HMAC-SHA256 signed and can be simulated from the Developer Center.

**Human URL:** [https://developer.deel.com/api/webhooks/introduction](https://developer.deel.com/api/webhooks/introduction)

- [OpenAPI](openapi/deel-webhooks-api-openapi.yml)
- [Event Catalog](https://developer.deel.com/api/webhooks/events)
- [Simulations](https://developer.deel.com/api/webhooks/simulations)
- [Naftiko Capability — Webhooks](capabilities/webhooks-webhooks.yaml)

### Deel Platform Extensions API
Specialized platform extensions covering background screenings (KYC/AML), immigration case management (visa types, business visa eligibility, work permits, right-to-work cases, document upload), and Deel IT (device provisioning, equipment assets, asset orders).

**Human URL:** [https://developer.deel.com/api/platform/introduction](https://developer.deel.com/api/platform/introduction)

- [OpenAPI](openapi/deel-platform-extensions-api-openapi.yml)
- [Screenings](https://developer.deel.com/api/platform/screenings)
- [Immigration](https://developer.deel.com/api/platform/immigration)
- [Deel IT](https://developer.deel.com/api/deel-it/getting-started/introduction)
- [Naftiko Capability — Immigration](capabilities/platform-immigration.yaml)
- [Naftiko Capability — Screenings](capabilities/platform-screenings.yaml)
- [Naftiko Capability — Deel IT](capabilities/platform-deel-it.yaml)

## Common Properties

- [Portal](https://www.deel.com)
- [Documentation](https://developer.deel.com/)
- [API Reference](https://developer.deel.com/reference)
- [Getting Started](https://developer.deel.com/api/quickstart)
- [Authentication](https://developer.deel.com/api/authentication)
- [OAuth2](https://developer.deel.com/api/oauth)
- [Rate Limits](https://developer.deel.com/api/rate-limits)
- [Idempotency](https://developer.deel.com/api/idempotency)
- [Best Practices](https://developer.deel.com/api/best-practices)
- [Versioning](https://developer.deel.com/api/api-versioning)
- [Sandbox](https://developer.deel.com/api/sandbox)
- [Webhooks](https://developer.deel.com/api/webhooks/introduction)
- [Webhook Events Catalog](https://developer.deel.com/api/webhooks/events)
- [Deel App Store / Partners](https://developer.deel.com/api/partners/introduction)
- [Deel as a Service (Embedded)](https://developer.deel.com/api/embedded/introduction)
- [Deel MCP Server](https://developer.deel.com/mcp/introduction)
- [MCP Connecting Clients](https://developer.deel.com/mcp/connecting-clients)
- [MCP Tools Reference](https://developer.deel.com/mcp/reference/tools-reference)
- [Stack by Deel (community)](https://stack.deel.com)
- [Blog](https://www.deel.com/blog/)
- [Pricing](https://www.deel.com/pricing/)
- [Status Page](https://status.deel.com/)
- [Help Center](https://help.letsdeel.com/)
- [Contact Us](https://www.deel.com/contact-us/)
- [LinkedIn](https://www.linkedin.com/company/deel/)
- [X](https://x.com/deel)
- [GitHub Organization](https://github.com/deel)
- [Plans](plans/deel-com-plans-pricing.yml)
- [Rate Limits](rate-limits/deel-com-rate-limits.yml)
- [FinOps](finops/deel-com-finops.yml)

## Maintainers

| Name | Email | Twitter | URL |
|---|---|---|---|
| Kin Lane | info@apievangelist.com | apievangelist | [apievangelist.com](https://apievangelist.com) |
