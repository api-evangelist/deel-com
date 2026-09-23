# Deel GraphQL Schema

## Overview

This conceptual GraphQL schema covers the Deel global payroll, HR, and contractor management platform. Deel supports workers and contractors in 150+ countries through a unified API surface spanning contracts, payroll, invoices, expenses, EOR, compliance, onboarding, and integrations.

The schema is derived from the Deel REST API documented at https://developer.deel.com/ and represents the domain model as a GraphQL type system for tooling, documentation, and integration reference purposes.

## Schema Source

- Provider: Deel
- API Reference: https://developer.deel.com/reference
- Documentation: https://developer.deel.com/
- Schema File: deel-schema.graphql
- Type: Conceptual (not an officially published Deel GraphQL endpoint)

## Domain Coverage

### Workers and People

Types covering the worker lifecycle from onboarding through offboarding across contractor and employee engagement models:

- `Worker` — top-level person node combining contractor and employee profiles
- `WorkerDetails` — extended personal and employment metadata
- `WorkerType` — enumeration of engagement types (contractor, EOR employee, GP employee, PEO employee)
- `ContractorProfile` — contractor-specific profile fields (entity type, tax identification, payment preferences)
- `EmployeeProfile` — EOR and global payroll employee profile data

### Contracts and Agreements

Types representing the legal structures that govern each working relationship:

- `Contract` — active or historical contract record
- `ContractDetails` — full contract body including compensation, scope, term, and jurisdiction
- `ContractStatus` — lifecycle state (draft, pending signature, active, terminated, amended)
- `ContractTerms` — financial and scope terms embedded in a contract
- `ContractType` — engagement category (fixed rate, pay-as-you-go, milestone, EOR, GP)
- `Agreement` — signed document record
- `AgreementDetails` — agreement metadata including PDF URL, signing timestamps, and signatories

### Payments and Payouts

- `Payment` — a disbursement record to a worker or contractor
- `PaymentDetails` — breakdown including gross, net, fees, and FX conversion
- `PaymentStatus` — lifecycle state (pending, processing, completed, failed, reversed)
- `PaymentMethod` — stored bank account or payment rail (SWIFT, ACH, Wise, Payoneer, crypto)
- `PayoutDetails` — scheduled and settled payout metadata

### Invoices

- `Invoice` — contractor invoice submitted for payment
- `InvoiceDetails` — full invoice with line items, totals, currency, and approval chain
- `InvoiceStatus` — state (draft, submitted, approved, rejected, paid)
- `InvoiceItem` — individual line item on an invoice (task, expense, milestone, adjustment)

### Milestones

- `Milestone` — deliverable checkpoint on a milestone-based contract
- `MilestoneDetails` — description, due date, amount, and approval status
- `MilestoneStatus` — state (pending, submitted, approved, paid)

### Payroll

- `Payroll` — payroll record for an employee or payroll run
- `PayrollDetails` — gross-to-net breakdown, contributions, and statutory deductions
- `PayrollStatus` — state (open, processing, finalized, paid)
- `PayrollCycle` — configured pay frequency and cut-off dates (monthly, bi-weekly, weekly)
- `PayrollRun` — execution record for a payroll cycle across all employees in scope
- `PayslipDetails` — individual employee pay statement with PDF reference
- `Deduction` — statutory or voluntary deduction line item
- `Benefit` — employee benefit enrollment record (health, dental, vision, pension)
- `BenefitDetails` — plan details, provider, cost, and coverage dates

### Equity

- `Equity` — equity grant record (options, RSUs, shares)
- `EquityDetails` — grant date, vesting schedule, cliff, and strike price

### Compliance

- `Compliance` — compliance standing record for a worker or entity
- `ComplianceDetails` — jurisdiction-specific requirement status
- `ComplianceType` — category (tax registration, KYC, right-to-work, background check)

### Legal Entities and Countries

- `Entity` — Deel legal entity or client legal entity record
- `EntityDetails` — registration number, address, tax ID, and incorporation country
- `EntityCountry` — country-level entity presence
- `LegalEntity` — employer of record legal entity used in EOR engagements
- `Country` — country reference with ISO codes, currency, and supported Deel products
- `CountryCompliance` — compliance requirements and mandatory documents per country

### Adjustments and Expenses

- `Adjustment` — payroll or invoice adjustment (bonus, deduction, correction)
- `Expense` — single expense submission with category, amount, and receipt
- `ExpenseReport` — grouped set of expenses submitted together for approval

### Tax

- `Tax` — tax record associated with a worker or engagement
- `TaxDetails` — withholding rates, jurisdiction, and classification
- `TaxForm` — generated tax document (W-8BEN, W-9, 1099, local equivalents)

### Organization and Teams

- `Organization` — top-level client organization on Deel
- `OrganizationDetails` — billing info, seat counts, subscription tier, and settings
- `Team` — department or team grouping within an organization
- `TeamDetails` — team name, parent, cost center, and member list
- `Manager` — manager record with approval authority
- `ManagerDetails` — manager profile with direct reports and delegation settings

### Onboarding and Offboarding

- `Onboarding` — onboarding task list and progress for a new worker
- `OnboardingStatus` — completion state (invited, in progress, completed, blocked)
- `Offboarding` — offboarding record with termination reason, final pay, and equipment return

### Authentication and Integrations

- `APIKey` — API key credential record
- `Token` — OAuth2 access or refresh token
- `Webhook` — registered webhook endpoint configuration
- `WebhookEvent` — delivered event payload record
- `Integration` — third-party integration connection (accounting, ATS, HRIS, SCIM)

## Query Patterns

The schema supports the following primary access patterns:

- Fetch a worker with their active contract, payment method, and onboarding status
- List all payroll runs for an organization within a date range
- Retrieve invoices by contractor filtered by status and period
- Look up country compliance requirements before hiring
- Query milestones by contract with approval chain
- Fetch expense reports pending approval for a team

## Notes

- This is a conceptual schema derived from the Deel REST API surface. Deel does not publish an official public GraphQL endpoint as of mid-2026.
- All 65 named types in `deel-schema.graphql` correspond to real Deel domain objects documented in the REST reference.
- Enum values reflect states observed in the REST API response bodies.
