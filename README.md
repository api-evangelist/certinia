# Certinia (certinia)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Certinia (formerly **FinancialForce**) is a Salesforce-native ERP, Professional Services Automation (PSA), and revenue-management suite delivered as managed packages that run inside a customer's Salesforce org. Its programmatic surface is **not** a standalone public REST product - it is a set of global **Apex service classes** (and legacy SOAP APIs) invoked on the Salesforce Platform against Certinia managed-package objects, covering Revenue Management, Billing Central, PSA, Accounting/ERP, Supply Chain, and Services CPQ. Certinia automates revenue recognition to **ASC 606** and **IFRS 15**, subscription billing, project and resource management, and accounting.

> **Access model (honest note):** Certinia's APIs are **gated**. Using them requires (1) a licensed Salesforce org, (2) the relevant Certinia managed package installed and configured, and (3) an assigned permission set or profile. Authentication and transport are provided by the **Salesforce Platform** (OAuth 2.0 / SOAP session), not by a separate Certinia system. There is no self-serve public developer signup and no Certinia-hosted public HTTP base URL. The API entries here are **modeled from Certinia's public Apex developer references** (`endpointsModeled: true`) - they describe real, documented service classes but are not called against a public, unauthenticated endpoint.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/certinia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/certinia/refs/heads/main/apis.yml)

## Tags

- Revenue Recognition
- ASC 606
- ERP
- Professional Services Automation
- PSA
- Billing
- Accounting
- Salesforce
- FinancialForce
- Finance

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Certinia Revenue Management API

Global Apex service classes for automating revenue recognition to **ASC 606** and **IFRS 15**. `RevenueContractService` creates and updates revenue contracts, generates performance obligations, allocates revenue, and produces recognition schedules. `RevenueRecognitionService`, `RevenueScheduleService`, and `RevenueScheduleAutomationService` recognize revenue and cost against schedules, and `ForecastService` supports revenue forecasting. Invoked as Apex within a Salesforce org (class names use a namespace prefix, e.g. `CODAAPI`); endpoints modeled from the public developer reference.

- **Human URL:** [Revenue Management Apex API Developer Reference](https://help.certinia.com/TechnicalReference/2024.2/RevenueManagement/Apex/GenericAPI.htm)

#### Tags

- Revenue Recognition
- ASC 606
- IFRS 15
- Revenue Contracts
- Deferred Revenue

#### Properties

- [Documentation](https://help.certinia.com/TechnicalReference/2024.2/RevenueManagement/Apex/GenericAPI.htm)
- [API Reference - Creating Revenue Contracts Using the API](https://help.certinia.com/main/2024.1/Content/RevenueManagement/Features/RevenueContracts/CreateRevContractUsingAPI.htm)

### Certinia Billing Central API

Global Apex service classes for subscription and usage billing. `BillingService`, `BillingDocumentsService`, `BillingSchedulesService`, and `ContractsService` generate billing documents and schedules, manage contracts, pricing, discounts, products, and tax codes, and drive the bill-to-cash process. Invoked as Apex within a Salesforce org against Billing Central managed-package objects; endpoints modeled from the public developer reference.

- **Human URL:** [Billing Central Apex API Developer Reference](https://help.certinia.com/ffbc-api/3X/GenericAPI.htm)

#### Tags

- Billing
- Subscription Billing
- Invoicing
- Billing Documents

#### Properties

- [Documentation](https://help.certinia.com/ffbc-api/3X/GenericAPI.htm)

### Certinia Professional Services Automation (PSA) API

Domain-oriented Apex service classes for Professional Services Automation - projects, resource requests and assignments, milestones, timecards, expenses, and billing events. Runs against PSA managed-package objects (namespace prefix `pse`) inside a Salesforce org and supports SOAP development environments; not a generic public REST CRUD layer. Endpoints modeled from the public developer reference.

- **Human URL:** [PSA Apex API Developer Reference](https://help.certinia.com/TechnicalReference/2024.2/ProfessionalServicesAutomation/Apex/GenericAPI.htm)

#### Tags

- Professional Services Automation
- PSA
- Projects
- Resource Management
- Timecards

#### Properties

- [Documentation](https://help.certinia.com/TechnicalReference/2024.2/ProfessionalServicesAutomation/Apex/GenericAPI.htm)
- [API Reference (PSA Apex 16X)](https://help.certinia.com/psa-api-apex/16X/GenericAPI.htm)

### Certinia Accounting (ERP) API

Certinia Accounting Apex API (namespace prefix `CODAAPI`) for core financials - sales and purchase invoices, credit notes, journals, cash entries, and general-ledger transactions - against the Accounting managed-package objects. Invoked as Apex within a Salesforce org; endpoints modeled from the public developer reference.

- **Human URL:** [Accounting Apex API Developer Reference](https://help.certinia.com/TechnicalReference/2023.2/Accounting/Apex/GenericAPI.htm)

#### Tags

- Accounting
- ERP
- General Ledger
- Finance

#### Properties

- [Documentation](https://help.certinia.com/TechnicalReference/2023.2/Accounting/Apex/GenericAPI.htm)
- [API Reference (Accounting Apex 2022.2)](https://help.certinia.com/accounting-api-apex/2022.2/GenericAPI.htm)

### Certinia Supply Chain Management (SCM) API

Certinia Supply Chain Management Apex API (`FFAAPI`) for inventory, sales and purchase orders, and fulfillment against SCM managed-package objects. Invoked as Apex within a Salesforce org; endpoints modeled from the public developer reference.

- **Human URL:** [SCM Apex API Developer Reference](https://help.certinia.com/scmc-api/2022.3/FFAAPI.htm)

#### Tags

- Supply Chain
- Inventory
- Orders
- Procurement

#### Properties

- [Documentation](https://help.certinia.com/scmc-api/2022.3/FFAAPI.htm)

### Certinia Services CPQ API

Certinia Services CPQ Apex API for configuring, pricing, and quoting services engagements and estimates that feed PSA projects. Invoked as Apex within a Salesforce org against Services CPQ managed-package objects; endpoints modeled from the public developer reference.

- **Human URL:** [Services CPQ Apex API Developer Reference](https://help.certinia.com/ServicesCPQApexAPI/February2023/GenericAPI.htm)

#### Tags

- CPQ
- Quoting
- Services Estimation

#### Properties

- [Documentation](https://help.certinia.com/ServicesCPQApexAPI/February2023/GenericAPI.htm)

## Common Properties

- [Domain Security](security/certinia-domain-security.yml)
- [Authentication](authentication/certinia-authentication.yml)
- [GitHub Organization](https://github.com/certinia)
- [LinkedIn](https://www.linkedin.com/company/certinia)
- [Website](https://www.certinia.com/)
- [Documentation](https://help.certinia.com/)
- [Plans](plans/certinia-plans-pricing.yml)
- [Rate Limits](rate-limits/certinia-rate-limits.yml)
- [Fin Ops](finops/certinia-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
