# EspoCRM review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-24  
**Category:** Open-source CRM and sales software  
**Method:** Source-led desk review; no hands-on testing is claimed.

EspoCRM is a customizable customer relationship management system available for self-hosting and through the vendor’s cloud service. The self-hosted software is licensed under AGPLv3, while the cloud plans have user minimums, storage and record limits; extensions and alternative commercial licensing can add separate costs.

## Editorial verdict

EspoCRM can suit teams that want control over a customizable CRM and can decide between operating it themselves or paying for a hosted instance. Its cloud offering lists a free one-month trial, then per-user pricing with minimum seats and defined storage/record limits. Review the AGPL license, extension costs, data boundaries and backup responsibilities before building a business-critical workflow around it.

## Compare self-hosting with the cloud seat minimum

EspoCRM provides two different operating paths. Self-hosting gives an organization control over infrastructure but requires technical administration. The cloud registration page lists per-user prices and minimum seat counts, which can make the hosted option more expensive than a single-user headline suggests.

Estimate the actual cloud minimum at the required plan and compare it with hosting, updates, backups and staff time for self-hosting. For the cloud trial, verify whether the listed storage, record limits and extensions match the production plan you expect to use after the trial ends.


## Read AGPLv3 and commercial licensing before customization

The vendor states that the self-hosted product is licensed under AGPLv3 and offers a commercial license for organizations seeking an alternative to that copyleft model. Teams that modify or expose the software as a service should have counsel or a qualified licensing professional review the obligations for their specific architecture.

Keep a record of the exact software release, license text, patches and extensions in use. Do not assume cloud subscription terms and self-hosted source terms are identical. Ask the vendor about the commercial license if proprietary modifications or distribution requirements are important to the business.


## Test limits, backup and recovery expectations

EspoCRM Cloud lists different storage and record limits across its plan levels, along with an external API and integration features. A business should estimate customer, activity, attachment and audit data growth over the expected retention period, not only count contacts at migration.

For self-hosting, test database and file backups together and rehearse a restore into a clean environment. Review role permissions, application secrets and available recovery documentation. For cloud service, ask about export format, backup schedule, retention, incident handling and termination data access before moving sensitive customer information.


## Build workflows only after permission and extension checks

EspoCRM documentation covers roles, security, authentication, jobs, emails, campaigns and customization. Those capabilities can support a tailored sales process, but each extension or custom formula changes the maintenance surface. Begin with the native functions required for a clear business workflow and add extras only after checking compatibility and support.

Use a staging instance with synthetic data to evaluate integrations and API permissions. Confirm which functions are core, which require a paid extension and which are included in the cloud tier. This article is based on official documentation, not a penetration test or implementation report.


## Features and decision criteria

- Contacts, deals, service cases, campaigns and API access
- Self-hosting under AGPLv3 with customizable fields and workflows
- Cloud plans include listed storage and record limits with seat minimums
- Extensions and commercial licensing options have separate terms

## Pricing considerations

Cloud pricing and limits are from the vendor’s registration page and can change. The source lists SSL, external API and integrations as plan features; verify exact support hours, billing period, trial terms and extension entitlements before purchase.

## Frequently asked questions

### Can EspoCRM be self-hosted?

Yes. The vendor offers a self-hosted download licensed under AGPLv3 and documents server, Docker and database setup.

### Does EspoCRM Cloud have user minimums?

The cloud registration page lists minimums of 3 users for Basic, 5 for Enterprise and 10 for Ultimate.

### Are extensions automatically included with self-hosting?

No. Extensions can have separate terms or prices; confirm each extension’s license and support requirements.


## Sources and further reading

- [EspoCRM official download and open-source license](https://www.espocrm.com/download/)
- [EspoCRM official cloud plans](https://www.espocrm.com/cloud-registration/?plan=demo)
- [EspoCRM official documentation](https://docs.espocrm.com/)
- [EspoCRM official commercial license](https://www.espocrm.com/espocrm-commercial-license/)
- [EspoCRM website](https://www.espocrm.com/)
- [saashub listing](https://www.saashub.com/espocrm)

For the complete Roseram buyer guide, see [EspoCRM review](https://roseram.com/reviews/scams/espocrm-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
