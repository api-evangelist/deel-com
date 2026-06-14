# Deel GraphQL Schema

## Overview

Deel is a global workforce platform combining payroll, Employer of Record (EOR), independent contractor management, HRIS, ATS, IT/device management, immigration, and background screenings across 150+ countries. This GraphQL schema models the full Deel domain covering global payroll, compliance, contracts, workers, and payments.

## Schema Source

This schema was derived from Deel's public REST API surface (https://developer.deel.com/api/introduction), product documentation, and the OpenAPI specifications published under this repository. It models the same data domain exposed by the Deel Core API, EOR API, Contractors API, Global Payroll API, HRIS API, and ATS API.

## Types

### Core Organization Types

- **Organization** — top-level tenant representing a Deel customer company with legal entities, departments, and cost centers
- **LegalEntity** — a registered business entity within an organization tied to a specific country
- **Department** — organizational grouping for workers and cost centers
- **CostCenter** — financial grouping for payroll allocation
- **Group** — custom worker grouping for management and reporting
- **Manager** — person with supervisory authority and reporting relationships

### Worker / People Types

- **Worker** — unified person record spanning contractors, EOR employees, and direct employees
- **WorkerProfile** — extended biographical and contact information for a worker
- **WorkerEmploymentInfo** — employment classification, start date, seniority, job title, and work location
- **WorkerDocument** — identity and compliance documents uploaded by or for a worker
- **WorkerBank** — bank account details for payment disbursement
- **WorkerPayslip** — payslip/paystub document for a completed pay period
- **WorkerBenefit** — enrolled benefit plan (health, dental, vision, pension) for an EOR employee
- **WorkerCompliance** — compliance status and required document checklists per country

### Contract Types

- **Contract** — polymorphic base contract covering IC, EOR, COR, and Global Payroll contract types
- **ICContract** — Independent Contractor fixed-rate or pay-as-you-go contract
- **EORContract** — Employer of Record full-time employment contract
- **CORContract** — Contractor of Record (employer-of-record for contractors) contract
- **GlobalPayrollContract** — direct employee payroll contract on the client's own legal entity
- **ContractAmendment** — modification to an existing contract (salary change, role change, scope change)
- **ContractTermination** — structured record of an offboarding/termination event with reason and effective date
- **MagicLink** — short-lived signing URL for worker onboarding or contract acceptance

### Payroll Types

- **PayrollCycle** — a single payroll run covering a period, legal entity, and set of workers
- **PayrollEvent** — individual gross-to-net computation event within a payroll cycle
- **PayrollAdjustment** — bonus, deduction, one-time payment, or expense reimbursement attached to a cycle
- **PayslipDocument** — generated PDF payslip artifact for worker download
- **GrossToNetBreakdown** — itemized breakdown of gross pay, taxes, deductions, and net pay
- **TaxWithholding** — country-specific tax withholding line item on a payroll event

### Invoice / Payment Types

- **Invoice** — worker-submitted invoice for contractor payment
- **InvoiceAdjustment** — modification to a submitted invoice (add line item, correct amount)
- **InvoiceTax** — applicable tax line items on a contractor invoice
- **Payment** — disbursement record linking an invoice or payroll event to a bank or crypto transfer
- **PaymentMethod** — stored payment method (bank account, crypto wallet, card) for a worker
- **Withdrawal** — worker-initiated transfer from Deel balance to an external account

### Time and Leave Types

- **TimeOffPolicy** — leave policy defining accrual rules, carry-over limits, and eligible worker classes
- **TimeOffRequest** — individual leave request with dates, type, status, and approval chain
- **TimeOffEntitlement** — worker's current balance and accrued hours/days under a policy
- **TimeOffEvent** — historical event log for accruals, expirations, and manual adjustments
- **WorkSchedule** — defined weekly work pattern (days, hours) for a worker or department
- **TimeTrackingShift** — clock-in/clock-out record for hourly workers on Global Payroll or PAGR contracts
- **Timesheet** — aggregated weekly or bi-weekly collection of shifts for payroll input

### Compliance and Background Check Types

- **BackgroundScreening** — KYC/AML screening record with provider, status, and findings
- **ScreeningReport** — detailed findings from a completed background screening
- **ImmigrationCase** — visa or work permit case with country, visa type, and document requirements
- **VisaType** — reference data for visa categories by country
- **RightToWork** — right-to-work verification record for EOR employees
- **ComplianceDocument** — country-required compliance document with upload status and expiry

### ATS Types

- **Job** — open position with title, department, location, employment type, and status
- **JobPosting** — published job board listing linked to a Job record
- **Candidate** — applicant record with contact info, resume, and source attribution
- **Application** — a Candidate's progression through a Job pipeline with stage and status
- **ApplicationAttachment** — resume, cover letter, or other file attached to an Application
- **Offer** — formal employment or contract offer extended to a Candidate
- **HiringMember** — recruiter or hiring manager assigned to a Job
- **InterviewStage** — a named stage in a hiring pipeline (screening, technical, offer)

### IT / Device Types

- **ITAsset** — device record (laptop, phone, tablet) with serial number, OS, and assignment
- **AssetOrder** — procurement order for a new device or peripheral
- **MDMEnrollment** — mobile device management enrollment status for an ITAsset

### Webhook Types

- **WebhookSubscription** — registered webhook endpoint with event filters and HMAC secret
- **WebhookEvent** — fired event record with payload, delivery status, and retry history
- **WebhookSimulation** — test event triggered in sandbox without production side-effects

### Reference / Lookup Types

- **Country** — ISO 3166-1 alpha-2 country record with supported Deel product availability
- **Currency** — ISO 4217 currency with exchange rate and supported payment method flags
- **JobTitle** — standardized job title from Deel's taxonomy
- **Seniority** — seniority level enum (Junior, Mid, Senior, Lead, Principal, Director, VP, C-Level)
- **EmploymentType** — classification enum (Employee, Contractor, EOR, COR, GlobalPayroll)

### Custom Field Types

- **CustomField** — organization-defined metadata field with name, type, and applicable worker classes
- **CustomFieldValue** — worker-level value for a CustomField

## Queries

The schema exposes read operations for all major entities:

- `organization`, `legalEntities`, `departments`, `costCenters`, `groups`
- `workers`, `worker`, `workerProfile`, `workerDocuments`, `workerBanks`, `workerPayslips`, `workerBenefits`
- `contracts`, `contract`, `icContracts`, `eorContracts`, `globalPayrollContracts`
- `payrollCycles`, `payrollCycle`, `payrollEvents`, `payrollAdjustments`
- `invoices`, `invoice`, `payments`
- `timeOffPolicies`, `timeOffRequests`, `timeOffEntitlements`, `worksheets`, `shifts`
- `jobs`, `job`, `candidates`, `candidate`, `applications`, `application`, `offers`
- `backgroundScreenings`, `immigrationCases`
- `itAssets`, `assetOrders`
- `webhookSubscriptions`, `webhookEvents`
- `countries`, `currencies`, `jobTitles`, `seniorities`

## Mutations

The schema exposes write operations including:

- `createContract`, `amendContract`, `terminateContract`, `signContract`
- `createInvoice`, `submitInvoice`, `adjustInvoice`, `approveInvoice`
- `createPayrollAdjustment`, `updatePayrollAdjustment`, `deletePayrollAdjustment`
- `requestTimeOff`, `approveTimeOff`, `declineTimeOff`, `cancelTimeOff`
- `createTimeTrackingShift`, `updateTimeTrackingShift`, `submitTimesheet`
- `createJob`, `updateJob`, `createCandidate`, `createApplication`, `updateApplicationStage`, `createOffer`
- `createWebhookSubscription`, `updateWebhookSubscription`, `deleteWebhookSubscription`, `simulateWebhookEvent`
- `createImmigrationCase`, `uploadComplianceDocument`
- `createAssetOrder`, `assignITAsset`
- `createCustomField`, `setCustomFieldValue`

## References

- Deel Developer Portal: https://developer.deel.com/
- Deel Core API Reference: https://developer.deel.com/reference
- Deel GraphQL (internal): https://api.letsdeel.com/graphql
- OpenAPI Specifications: see `openapi/` directory in this repository
