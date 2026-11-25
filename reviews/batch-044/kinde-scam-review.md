# Kinde review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Authentication, user management, and SaaS platform services  
**Method:** Source-led desk review; no hands-on testing is claimed.

Kinde provides hosted authentication and user-management services with organization-aware roles, sessions, multi-factor authentication, feature flags, workflows, and an optional SaaS billing module. Its current pricing page lists Free, Pro, Plus, and Scale plans with monthly active user and organization allowances, a base subscription price, feature limits, and separate transaction fees when billing customers through Kinde. This review examines how to model identities and organizations, how plan meters interact, how tokens and sessions should be configured, and what a team should test before making Kinde part of a production sign-in path.

## Editorial verdict

Kinde’s official pages document an authentication and business-management product, tiered usage pricing, token controls, organization-specific roles, and optional billing. Those sources do not establish that Kinde is a scam or that its authentication design automatically meets a buyer’s security requirements. This is a desk review, not an integration test, penetration test, or legal/compliance audit. Buyers should model active users and organizations, distinguish identity fees from transaction charges, and test token revocation, role boundaries, export, and account recovery before migration.

## Kinde SCAM Review: the short answer and scope

A search for “Kinde scam” should lead to specific questions about identity, billing, permissions, and account control. Kinde’s official materials describe a hosted authentication and user-management service, organization-aware roles, token configuration, and an optional billing module. The sources reviewed do not establish fraud. They do show that a buyer must distinguish a base subscription from usage meters and customer-payment fees, then decide whether the hosted identity workflow fits its own architecture.

This is a desk review of Kinde’s public product, pricing, and documentation pages checked on November 18, 2026. Roseram did not connect a production application, purchase a plan, inspect a tenant, or conduct a security test. The useful conclusion is conditional: Kinde may reduce the work of building sign-in and access-management features, but the application owner remains responsible for correct role checks, token handling, recovery design, and cost controls. A documented feature is not proof of a particular integration’s security or suitability.


## What Kinde provides to an application team

Kinde positions itself as an identity and business platform for software applications. Its published feature set includes authentication, user and organization records, roles and permissions, multi-factor authentication, sessions, workflows, feature flags, webhooks, and business billing tools. Those capabilities can be used together, but they are not one indivisible requirement. A team might adopt Kinde for login while keeping subscription payments elsewhere, or use its organization model without adopting every workflow feature.

That modularity makes the first purchase question unusually important: which problem is the team actually trying to solve? Replacing a home-grown login flow is different from migrating a customer database, building business-to-business access, or consolidating billing. Write down the sign-in methods, user volume, organization model, administrative roles, and required recovery behavior. Then confirm each is supported by the selected plan and SDK. A long feature list can reduce integration work only if it maps to the application’s real authorization model.


## Kinde pricing: Free, Pro, Plus, and Scale

On November 18, 2026, Kinde’s pricing page showed four main tiers: Free at $0, Pro at $25, Plus at $75, and Scale at $250 per month. Each plan listed 10,500 monthly active users, with paid plans adding a published rate for usage above that allowance. The page separately listed monthly active organizations, with five included on Free and 50 on paid plans. It also showed plan-specific amounts for custom roles, permissions, API keys, webhooks, feature flags, environments, advanced organizations, and other services.

This is not a flat per-seat price. A forecast should model active users and active organizations separately, then add whichever features the product will use. Kinde’s page says prices are indicative and vary monthly with actual usage. It also states that customers paying more than USD $4 monthly through Kinde Billing are not counted toward MAU under its listed rule. Eligibility and meter definitions matter, so confirm how the account classifies each user and organization. Save the current plan configuration before launch and set a review point after real usage data is available.


## Kinde Billing fees are separate from identity plan prices

Kinde also markets customer billing for subscriptions, usage-based pricing, and invoices. The pricing page lists transaction fees of 0.7% on Free and Pro, 0.6% on Plus, and 0.5% on Scale when collecting payments from customers through Kinde Billing. These fees are separate from the monthly Kinde plan subscription. An authentication-only integration should not be presented as if it automatically incurs those customer-payment fees; the fee is tied to using the billing module to collect payments.

If the business intends to use Kinde Billing, compare its transaction costs with the current payment processor and product architecture. Check how refunds, disputes, taxes, invoices, subscription changes, payment retries, and customer self-service fit together. Confirm who is merchant of record and what external payment account is connected. The pricing page identifies fee rates, but a headline percentage does not resolve every contractual or tax question. Avoid counting the feature as included revenue processing until a test transaction, refund, cancellation, and bookkeeping export have been validated.


## Monthly active users and monthly active organizations

Kinde’s price comparison uses MAU and MAO as separate quantities. That distinction matters in a business-to-business product where one account may belong to a company organization, and a person may interact with more than one organization. The page notes that organizations containing a single active user are not counted toward MAO and explains its customer-paid subscription rule for MAU. Buyers should read the detailed footnotes and verify the account’s own meter rather than multiply a signup count by a per-user number.

Build an estimate from a realistic month: active people, paid customers, test and service accounts, organization membership, and expected growth. Ask how an inactive user, invited user, employee, machine-to-machine credential, or cross-organization member is counted. If the business is near an included limit, make a simple projection for a seasonal peak and confirm the overage rate before onboarding customers. This review does not predict Kinde’s charge for a specific company because that depends on its customer mix and selected features.


## Organizations, roles, and permissions in Kinde

Kinde’s organization model is built for cases where one identity may have different access in different businesses or workspaces. Its documentation says roles and permissions are defined at the business level and applied at an organization level; one person can hold different access in separate organizations. This can match a multi-tenant product, but the application must carry the organization context through every protected request. A UI that hides an action is not authorization; the server must check the relevant permission too.

Test with a user who belongs to two organizations and has different roles in each. Switch the active organization, inspect the token claims, and try both allowed and denied API actions. Then remove a role and verify how the application learns about that change. Kinde’s guidance recommends designing around permissions for greater control as role models grow. The documentation demonstrates the feature surface, not the correctness of custom application code. A wrong organization identifier can expose data even when the identity provider’s own role configuration is accurate.


## Authentication methods and multi-factor options

Kinde’s pricing page lists email and password, passwordless, social identity providers, passkeys, enterprise connections, device flow, and multi-factor methods. The available methods and some limits vary by plan or provider arrangement; for example, SMS authentication may rely on a bring-your-own provider or incur a separate unit price. Verify which sign-in methods are enabled for the chosen application and how account recovery works for each one. A second factor is valuable only when the user can enroll, recover, and remove it in a controlled way.

Plan a test for both successful and failure paths: a first-time sign-in, a wrong password, a lost authenticator, an email change, a social account that already exists, and a disabled user. Confirm which messages are sent, what support can see, and whether a helpdesk action can bypass the intended controls. If an application serves multiple regions or languages, test localized screens and communications. The feature matrix tells a buyer what Kinde lists; the application owner must still make the experience understandable and resistant to account takeover.


## Kinde tokens, sessions, and refresh-token rotation

Kinde’s token documentation describes configurable lifetimes for access, ID, and refresh tokens. It lists default values of 24 hours for access tokens, one hour for ID tokens, and 15 days for refresh tokens, while advising teams to configure settings for each application. The refresh-token guide describes rotation: using one token issues a replacement and invalidates the previous token, with a limited overlap to handle retries. These are meaningful controls, but they require secure storage and correct use by the app.

Kinde explicitly warns that refresh tokens should be stored on a secure backend and not exposed through a client secret in a public frontend. Its documentation also explains that access tokens already issued can remain valid until expiry after a session is revoked, because an API may validate a signed token locally. A product should therefore set a token lifetime aligned to its risk, use appropriate PKCE or backend flows, rotate credentials, and test logout and revocation. A revoke button does not necessarily terminate every previously issued token immediately.


## Session management and account security boundaries

A session can persist across applications or devices, and the acceptable lifetime depends on the product. Kinde’s documentation lets an administrator configure token expiry and SSO inactivity. Its guide warns that ordinary local page navigation does not by itself reset the server-visible inactivity timer. This distinction can surprise teams that assume a user is active because a tab remains open. For a high-value action, the product may need a fresh authorization or additional step rather than relying on a long-running session.

Write down the expected behavior for browser closure, shared devices, an employee departure, password reset, lost device, and organization removal. Then test it against the application’s actual token storage. Kinde documentation says browser SDKs keep tokens in memory by default to reduce certain exposure risks and points to custom domains and secure httpOnly cookies for production persistence. The integration should be reviewed by someone who understands the app’s XSS, CSRF, and session model. Do not treat a hosted login screen as an automatic security certification for the whole product.


## Migration, data export, and leaving Kinde

Kinde’s plan comparison lists self-serve import and export capabilities. That is useful evidence to investigate, not proof that a migration is effortless. A user record may include identifiers, verified addresses, social-provider links, custom properties, organization membership, roles, consent, and authentication state. Some credentials cannot be transferred in a directly reusable form, so the migration may require password resets or reauthentication. Document the identity mapping before exporting anything and protect the file as sensitive personal data.

Ask which fields, audit records, and organization relationships are included in an export, what formats are available, and which plan or role can approve it. Test a small sample in a destination system, validate duplicate handling, and make a rollback plan before moving production accounts. Check the applicable retention and deletion terms for any temporary copy. The public feature table says import and export are available; the buyer still needs to validate the specific dataset and legal basis. A future exit plan is part of the original purchasing decision, not a task to improvise at cancellation time.


## Feature flags, workflows, and webhooks

Kinde groups feature flags, workflows, and webhooks alongside identity services. Feature flags can shape which experiences a user or organization receives, while workflows can react to events and webhooks can notify external services. Those capabilities may consolidate common SaaS tasks, but they create additional dependencies and data flows. Check which plan allows the number of flags and webhooks the product needs, whether a workflow preview is included, and how long runtime logs remain available under that tier.

A buyer should map each automation to its trigger, action, retry behavior, and failure alert. Test a duplicate webhook, an unavailable destination, and a permission update while a user session is still active. A successful event delivery should not be confused with a successfully completed business action; the receiving service must acknowledge and validate its own state. Keep secrets on a server and avoid putting sensitive information into event payloads unless the data path has been approved. The presence of these tools does not mean a company has already implemented a complete lifecycle or feature management system.


## Administration, audit logs, support, and compliance claims

The pricing page differentiates plans by audit-log retention, support options, environments, and compliance materials. Buyers should note the actual period shown for the plan rather than treating “audit logs included” as a timeless record. If an investigation requires months of history, a short retention window may not meet the need. Likewise, a compliance certificate or attestation should be checked directly for its scope, covered entity, current date, and services—not interpreted as proof that the buyer’s own configuration is compliant.

Assign an owner to administer Kinde, invite a second trusted administrator, and define who may export data or change authentication settings. Check the support channel and response commitment for the selected plan. Run a tabletop exercise where the owner account is unavailable and a token needs revocation. This reveals whether the company has workable recovery and escalation paths. The public pricing table is useful for comparing listed entitlements, but the contract and account-specific configuration govern what is actually available.


## Kinde alternatives and fair evaluation criteria

Kinde should be compared with identity providers and application frameworks that solve the same sign-in and access problem. A developer library may provide more control but require the team to operate more pieces. A specialized identity platform may offer different federation, compliance, or administration options. A bundled SaaS platform may link billing and access management while creating additional dependency. The right comparison depends on whether the product needs customer login, workforce SSO, multi-tenant organization roles, customer billing, or all of these.

Use the same test application and identity requirements in each candidate: sign up, sign in, reset credentials, enroll a second factor, join two organizations, change roles, revoke a session, export a user, and process one test billing event if relevant. Record setup effort, user friction, error visibility, support needs, and expected cost at several usage levels. Do not select a provider from a feature checklist alone. The meaningful question is whether it gives the application a safe, maintainable path to identity and access management with an exit plan the organization can execute.


## Who may find Kinde useful—and who should pause

Kinde may suit a SaaS team that wants hosted sign-in, organization-aware permissions, and a path to feature management in one service. Its free allowance and paid tiers give a team a way to estimate growth, and its optional billing tools may appeal to products that want customer plans and entitlements tied to identity. A team that already uses the SDKs or has an established Kinde architecture may benefit from having these administration features in one place.

Pause if the product cannot define authorization rules, if the company needs a particular federation or data-residency commitment that has not been confirmed, or if the team has not modeled users and organizations against the price meters. A business that only needs a simple login may not need the broader platform. A high-risk account system should review token lifetimes, session revocation windows, support, and recovery before choosing a default configuration. These are scoping questions, not evidence of a problem with Kinde itself.


## A Kinde pilot before moving production users

Build a small non-production application with a synthetic user set and at least two organizations. Configure one ordinary member, one elevated role, and one user who has different access in each organization. Exercise sign-in, MFA, sign-out, token refresh, role change, organization switch, and a denied API action. Observe which claims the server receives and whether a recently revoked role remains in a previously issued token. Keep the flow close to the intended application rather than relying only on a dashboard tour.

Then test account export and recovery, estimate MAU and MAO for a typical and peak month, and calculate costs with or without Kinde Billing. If customer payments are included, run a sandbox subscription, invoice, refund, and cancellation. Record the plan, settings, and unanswered questions. This is a suggested buyer protocol, not an integration or test Roseram has completed. Do not upload real customer identities until the data transfer, access, retention, and migration plan has been approved by the organization.


## Is Kinde a scam? The evidence and its limits

Kinde’s official website and documentation describe a working category of service, published plan rates, token controls, and organization-level permission features. The evidence reviewed does not establish that Kinde is fraudulent. A “scam” query should prompt a buyer to confirm who supplies the service, what the selected tier includes, how usage is measured, and which contract applies. It does not justify repeating an allegation based on a search result or using a software directory listing as proof of misconduct.

If an account charge or access behavior later seems wrong, compare the invoice with current usage, user and organization counts, transaction features, and configured environments. Save the dated price and settings. Describe a concern with a specific record or action, and distinguish it from a general opinion. The page does not quote anonymous complaints, invent customer experiences, or claim an authority has made a finding. It also does not certify Kinde as safe. Buyers should use the official sources and their own implementation test to decide whether the product is suitable.


## Final Kinde assessment

Kinde offers a broad set of hosted identity and SaaS administration features. The official plan page separates monthly price from MAU, organization, API, and optional billing units; the documentation gives concrete guidance on organization permissions and rotating refresh tokens. The strongest diligence point is configuration: identity systems are foundational, so a team must test permissions in each organization, manage secrets carefully, and understand how long revoked access tokens can remain valid.

A buyer should pilot the exact sign-in and authorization flow, model its user and organization counts, verify current plan terms, and rehearse export and recovery before moving customer accounts. Teams seeking only a small login feature may prefer a narrower option; teams building multi-tenant SaaS may value Kinde’s connected feature set. A Roseram workspace may help implement a Kinde integration, but it remains separate from Kinde’s identity service and account. The official materials support describing Kinde as an identity and business platform. They do not support a fraud allegation, a blanket security guarantee, or a claim that Roseram tested it hands-on.


## Features and decision criteria

- Hosted authentication for email, passwordless, social, and enterprise sign-in flows
- Multi-factor authentication, configurable sessions, and refresh-token support
- User and organization management with roles and permissions
- Feature flags, workflows, webhooks, and API integrations
- Optional customer subscription and usage-based billing module

## Pricing considerations

The Kinde pricing page was checked November 18, 2026 and says monthly prices are indicative and may vary with actual usage. The page distinguishes MAU from monthly active organizations, lists paid-plan MAU rates and feature limits, and describes transaction fees for use of Kinde Billing. It also states that customers paying more than USD $4 per month are not counted toward billable MAU under the stated rule. Verify the current plan, identity usage, organizations, add-ons, billing fees, and contract terms in the account before forecasting cost.

## Frequently asked questions

### Is Kinde a scam?

The official Kinde pages reviewed describe authentication, user management, organizations, usage pricing, and token behavior. They do not establish a fraud finding. The SCAM Review title is a buyer due-diligence query, not an allegation or endorsement.

### How much does Kinde cost?

On November 18, 2026, the pricing page displayed Free at $0, Pro at $25, Plus at $75, and Scale at $250 per month. Paid tiers include additional MAU and organization usage rates, and optional Kinde Billing applies its own transaction fee. Confirm the active rate card and all meters before adopting it.

### Does Kinde charge transaction fees for authentication?

The listed 0.7%, 0.6%, and 0.5% transaction fees apply to payments collected from the customer through Kinde Billing, according to the pricing page. They are separate from the Kinde plan subscription and should not be assumed to apply to an authentication-only integration.

### Does Kinde support organization-level permissions?

Kinde’s documentation says a user can have different roles and permissions in different organizations. Buyers should test that their application selects the correct organization context and checks permissions for each protected action.

### Has Roseram tested Kinde?

No hands-on integration, penetration test, or compliance audit is claimed. This review is a desk analysis of Kinde’s public materials and a proposed buyer evaluation plan.


## Sources and further reading

- [Kinde official product website](https://www.kinde.com/)
- [Kinde official pricing and usage comparison](https://www.kinde.com/pricing/)
- [Kinde token lifetimes and session security guidance](https://docs.kinde.com/build/tokens/configure-tokens/)
- [Kinde refresh token rotation and storage guidance](https://docs.kinde.com/build/tokens/refresh-tokens/)
- [Kinde organization roles and permissions documentation](https://docs.kinde.com/build/organizations/orgs-for-developers/)
- [Kinde account plan and included usage documentation](https://docs.kinde.com/manage-your-account/profile-and-plan/view-kinde-plan/)
- [Kinde website](https://kinde.com/)
- [publicapi listing](https://publicapi.dev/kinde-api)

For the complete Roseram buyer guide, see [Kinde review](https://roseram.com/reviews/scams/kinde-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
