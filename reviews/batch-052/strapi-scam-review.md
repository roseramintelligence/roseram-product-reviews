# Strapi review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Headless content management system  
**Method:** Source-led desk review; no hands-on testing is claimed.

Strapi is an open-source, JavaScript and TypeScript headless CMS for modeling, editing, and delivering content through APIs. Buyers can self-host the Community edition or use Strapi Cloud. The current Cloud page lists Starter, Pro, and Business hosting with different request, asset, environment, backup, and observability allowances; paid CMS capabilities such as content history, review workflows, and SSO may require a separate CMS license. This review examines that product split, current public prices, permissions, delivery limits, hosting responsibilities, and a practical evaluation path.

## Editorial verdict

Strapi’s publisher pages document a real headless CMS, self-hosted and hosted options, a public Cloud rate card, and granular administration features. Those materials do not establish that Strapi is a scam or prove that it will fit a particular project. This is a source-led desk review, not a hands-on installation, security audit, or performance benchmark. The key buyer task is to compare the CMS license, hosting plan, runtime needs, and operational responsibilities as separate parts of one deployment.

## Strapi SCAM Review: the short answer and review scope

A search for “Strapi scam” deserves a careful answer, not a dramatic verdict. Strapi’s official pages identify a headless content-management system, a Community edition, Cloud hosting plans, and documentation for administrator roles and end-user permissions. The materials reviewed here do not establish fraud. They do reveal a buying detail easy to miss when comparing headline prices: the CMS application and the hosting service are related but separate parts of the offer.

This is a desk review built from Strapi’s product, pricing, support, and documentation pages checked on November 18, 2026. Roseram did not install the software, create a Cloud account, make a purchase, test a deployment, or audit its security. The practical conclusion is neither blanket praise nor suspicion. Strapi may fit a team that wants structured content and API delivery, provided it budgets for the full operating arrangement and verifies the exact license and hosting terms before publishing important data.


## What Strapi does as a headless CMS

Strapi is a content management system designed to keep content administration apart from the website or application that displays the content. A team defines content types and fields in the CMS, editors manage entries through an administrative interface, and a separate frontend retrieves that material through APIs. This approach can support a marketing site, a mobile application, a partner portal, or multiple channels using the same structured source. It also means the CMS is one component in a larger software system, not a finished public website by itself.

That separation is useful when the publishing team wants one content source to serve several experiences, or when developers need control over how data is rendered. It introduces choices too: someone must design the content model, build the frontend, configure access, and keep both application layers in working order. A buyer should therefore compare Strapi with the actual project architecture in mind. Counting available API features will not answer whether the organization has the people and time to maintain the whole system.


## Strapi Community edition, paid CMS features, and hosting are different costs

The most consequential pricing distinction is between the CMS license and the place where it runs. Strapi’s pricing materials list a Community edition and separate paid CMS capabilities, while Strapi Cloud has its own Starter, Pro, and Business hosting plans. The support article on Cloud billing says Cloud charges cover hosting and do not automatically grant paid CMS features such as Content History, Review Workflows, and SSO; those may need a Growth or Enterprise CMS license. A buyer who combines both pages into one assumed subscription can underestimate the bill.

Self-hosting shifts the calculation in a different direction. A no-cost Community license would not make servers, database operations, monitoring, backups, email delivery, media storage, incident response, or staff time disappear. A hosted plan can reduce infrastructure tasks while adding request, storage, bandwidth, runtime, and contract limits. Before choosing a route, draw a small responsibility map: who updates the CMS, who owns the database, where media lives, who restores a failed deployment, and which features require a separate license. Price that complete arrangement rather than the word “free” or the lowest Cloud card.


## Strapi Cloud pricing: Starter, Pro, and Business

On November 18, 2026, the Strapi Cloud page displayed monthly Starter at $35 per project, Pro at $90, and Business at $450. Starter included 100,000 API requests per month and 50 GB each for asset storage and bandwidth. Pro listed one million requests, 250 GB of storage, 500 GB of bandwidth, weekly and manual backups, and an always-on runtime. Business listed ten million requests, 1,000 GB of storage and bandwidth, daily backups, two included environments, and a 99.9% uptime SLA. These are dated publisher figures, not quotes for every account.

The page also offers yearly billing, excludes applicable local taxes, and says checkout determines the final amount. Its comparison lists additional API requests at $1.50 per 25,000 and additional asset storage at $0.60 per GB; bandwidth has a separate allowance and extra-use price on the current rate card. Do not simply multiply a request estimate and assume the result is the complete bill. Check which environment is metered, whether assets are served through the included bandwidth, what counts as an API request, and whether an add-on or CMS license is required for the deployment you intend to run.


## Request, storage, bandwidth, and environment limits

A content-heavy project can meet a storage or bandwidth ceiling before it reaches its API request allowance. Images, downloadable files, and repeated asset delivery should be estimated separately from editorial entries. Strapi’s page distinguishes asset storage from asset bandwidth and states that storage is per environment in the comparison table. A staging environment that duplicates media may therefore affect the cost in a way a simple page-view estimate misses. Ask how overages are calculated and whether the system pauses, continues at an extra charge, or requires an upgrade when an allowance is exhausted.

Request counts also need context. A single user action may trigger several frontend calls, and caching can change the number that reaches the CMS. Use a small representative prototype to measure requests for a typical page, an editor preview, a search, and a mobile screen. Multiply those observations by realistic traffic and add a reserve for growth. This is a buyer method, not a claim about Strapi’s measured performance. If a project is near a published tier boundary, verify the counting rules with the provider instead of assuming a request is equivalent to a visitor or page view.


## Content modeling, APIs, and frontend responsibilities

Strapi’s content types, components, and API delivery can give a product team a deliberate schema instead of a collection of loosely formatted pages. The benefit depends on modeling the information editors actually need. A useful schema distinguishes reusable facts from page-specific presentation, allows required fields to be validated, and names relationships clearly. If the model is designed around one launch page and not the next season of content, the team may later face awkward migrations or a growing number of exceptions.

REST and GraphQL are delivery options, not a replacement for a frontend design or API governance. Developers still decide how to render content, manage caching, handle missing fields, control public exposure, and coordinate schema changes with a deployed application. Buyers should check which API capabilities are included in the chosen edition and whether plugins or extensions alter the support boundary. A good evaluation builds one representative content type, sends it to the intended frontend, changes a field, and observes whether both editors and users can handle the change without an unexpected release problem.


## Editorial work, draft publishing, and collaboration

The CMS should be judged by the people who will use it each day. Editors need to understand where a draft lives, how a change becomes public, and whether a colleague can review it before release. Strapi’s current feature matrix separates some advanced capabilities from the base hosting offer, so confirm whether the workflow your organization needs is available under its CMS license. A Cloud subscription alone should not be treated as evidence that every editorial feature shown in an enterprise comparison is enabled.

Map a real publishing task from brief to update: create an entry, attach media, preview it on the target frontend, request a correction, approve it, publish it, and later revise or withdraw it. Record which steps happen inside Strapi and which require another application or custom code. This exposes whether the interface fits the editorial process instead of merely looking capable in a feature list. If content requires multiple languages or legal approval, add those cases to the test. The public documentation is a starting point; it cannot tell a buyer whether the team’s own responsibilities and release calendar are a good fit.


## Strapi roles and administrator access control

Strapi’s administrator RBAC documentation describes roles and permissions for actions across content types, settings, plugins, uploads, and other administrative areas. Its examples include create, read, update, delete, and publish permissions for content. Granular control is valuable because an editor, developer, and administrator rarely need identical authority. It also requires careful configuration: a permission matrix is only protective when the organization assigns roles deliberately, reviews exceptions, and removes access when responsibilities change.

A practical buyer check is to create non-production accounts representing an author, an editor, and an administrator. Try opening, editing, publishing, deleting, and exporting sample content under each role. Confirm that the visible screens and API actions match the intended boundary, then document who may change the permissions themselves. Strapi’s documentation demonstrates that these controls exist; it does not establish that a particular installation has been configured correctly. Treat access setup as part of implementation and review, not as a box checked by the presence of a roles page.


## End-user sign-in and API permissions

Strapi separates administrators who manage the CMS from end users who sign in to a front-facing application. The Users & Permissions documentation describes account registration, JWT-based authentication, and an access-control strategy for protecting API routes. It lists public and authenticated roles and explains that administrators configure which actions an end-user role may perform. This may help when a product needs a member area or a protected API, but it should not be confused with a complete identity-management service for every enterprise requirement.

Before making the API public, test both sides of the boundary. An anonymous request should return only information the application intends to expose. An authenticated user should see only the records and actions allowed by that role. Check sign-up settings, email confirmation, token handling, password resets, provider configuration, and how secrets are stored. The docs describe options, including a refresh-token mode for short-lived access sessions; implementation choices remain the buyer’s responsibility. Do not move customer accounts into a new system until migration, recovery, consent, and support paths have been reviewed.


## Deployment, backups, and day-to-day operations

Strapi Cloud’s published tiers differ in runtime behavior, environments, backup frequency, observability, and log retention. Starter is listed as sleeping when idle, while Pro and Business are always on. Pro includes weekly and manual backups in the pricing table; Business lists daily backups. These are useful distinctions, but a backup is not a recovery plan until someone has restored it into a working project and verified the result. A project’s recovery time depends on its database, media, configuration, secrets, frontend, and external services—not only the CMS database copy.

Ask where application and uploaded media backups are stored, how long they are retained, and which plan supports the required restore workflow. Exercise a restore before relying on it. For self-hosting, assign an owner to operating-system and dependency updates, database health, network rules, backups, and monitoring. For Cloud, identify which operational responsibilities remain with the project team and which are included in the selected tier. The published uptime SLA is tied to Business on the page reviewed, so lower plans should not be described as carrying the same promise.


## Security and data handling questions for a Strapi buyer

Access controls and authentication features are building blocks, not a complete security conclusion. A buyer should establish the intended data classification, admin access rules, API exposure, deployment location, backup handling, and incident contact before importing confidential or personal information. Check the current plan and contract for any security or compliance commitments the organization requires. A logo or a generic phrase such as “enterprise-ready” cannot answer where data is processed, how long it is retained, or who can access it under the applicable service terms.

Run a bounded review in a test environment: rotate a credential, remove a user, inspect API permissions, try a backup restore, and confirm that public routes return only approved fields. For a self-managed setup, verify secrets are not committed to source control and that updates have an owner. For a hosted setup, read the current provider documentation and contract rather than inferring a control from a plan name. This review does not claim a vulnerability, a breach, or an independent security assessment of Strapi. It identifies the evidence a cautious deployment decision should collect.


## Strapi alternatives and fair comparisons

The most useful alternative is the one that matches the same job. Compare Strapi with another headless CMS, a hosted content platform, or a custom application only after writing down the content types, number of editors, delivery channels, API traffic, localization needs, and publishing approvals. A more managed service can reduce operational work but may narrow customization or add recurring charges. A self-hosted option can increase control while requiring more engineering attention. A conventional website builder may be simpler if the project only needs a small number of pages.

Use the same small content model and publishing task in each candidate. Measure setup time, the number of steps an editor must learn, API behavior after a schema change, access configuration, export options, and the full one-year cost. Include both license and hosting charges, plus the work needed for backup and support. Strapi should not be declared cheaper or more flexible for every buyer from a rate card alone. The result depends on what the team already operates and which capabilities it needs to own.


## Who Strapi may suit—and who should pause

Strapi may be a reasonable candidate for a development team that wants structured content, API delivery, and control over the frontend while accepting responsibility for a multi-part application. A team with editors who publish to several channels may value a shared content model. A group with an existing JavaScript or TypeScript capability may find the developer-oriented approach easier to evaluate than an organization without technical staff. The Cloud plans provide a clearer hosted path, though they still require choosing suitable allowances and checking whether paid CMS functions need another license.

Pause before adopting it if the project needs a turnkey public site but has no one to build or maintain the frontend, if a vendor must own all recovery work, or if the procurement team has not reconciled the CMS license with hosting. A high-traffic service should model API and asset usage before selecting a plan. A regulated project should independently confirm the exact data, contract, region, and compliance requirements. These are fit questions, not judgments against Strapi; they help prevent a technically capable CMS from being bought for a job the team is not prepared to operate.


## A practical Strapi evaluation before paying or migrating

Start with a disposable project and a content model close to the real one. Create a draft, attach an image, render the entry in the intended frontend, change a field, and publish the revision. Use separate administrator accounts to test role boundaries. If the application has end users, test registration and API permissions with synthetic accounts. Record which steps require code, a plugin, a different CMS license, or an outside service; that list is more useful than a general impression after a product tour.

Then measure the operational and financial pieces. Estimate API calls for the expected user journey, count the media that needs to be stored, and calculate bandwidth for representative traffic. Ask how overages work and compare those numbers to Starter, Pro, and Business. Confirm the billing interval and CMS license in checkout. Restore a backup in a test instance and export content you may need to migrate. Write down the date and plan used for each observation. This is a proposed buyer test, not a report that Roseram has completed one or measured Strapi’s performance.


## Is Strapi a scam? Buyer due diligence, not a fraud allegation

The official Strapi pages reviewed identify a product, documentation, public Cloud pricing, and a support explanation of how hosting and CMS licensing are billed. They do not establish a fraud finding, and this page does not call Strapi a scam. A search phrase is a request to investigate; it is not evidence. The review’s value is to show the details a buyer can verify before committing: product identity, the selected CMS edition, hosting tier, API and asset allowances, extra feature licenses, and terms at checkout.

If a billing or access issue arises later, compare the invoice with the account’s plan, billing interval, usage, and license. Save the product page and purchase terms that applied at the time. Ask support about a specific discrepancy and keep the response with the relevant records. A pricing change, technical outage, or misunderstanding of included features may be frustrating, but none alone proves intentional deception. Describe any concern with dates and evidence, and distinguish personal experience from an independently verified finding. No complaint or customer testimonial is invented in this review.


## Final Strapi assessment

Strapi is best understood as a headless CMS with a choice between self-managed infrastructure and hosted Strapi Cloud. The publisher’s current monthly Cloud page separates Starter, Pro, and Business by API requests, assets, runtime, backup, and operational features. The support guidance separately identifies paid CMS capabilities that are not included merely by paying for hosting. This split does not make the offering inherently difficult or deceptive, but it does make a one-line plan comparison incomplete.

A buyer should choose Strapi only after matching the CMS license and hosting to a real content workflow, testing editorial and access controls, estimating requests and media, and practicing an export or restore. Teams that already maintain JavaScript applications may value the control; teams seeking a finished website with minimal technical ownership should compare a more managed alternative. A Roseram workspace may help draft a content model or review a CMS integration, but it is not a CMS and does not include Strapi hosting. The reviewed official evidence supports describing Strapi as a documented CMS product. It does not support a fraud allegation, a blanket security endorsement, or a claim that Roseram has tested the service hands-on.


## Features and decision criteria

- Open-source headless CMS with configurable content types and components
- REST and GraphQL APIs for delivering structured content
- Admin roles with granular permissions for content and settings
- End-user authentication and role-based API permissions through Users & Permissions
- Self-hosted Community and managed Strapi Cloud paths

## Pricing considerations

These were the monthly values displayed on Strapi’s Cloud pricing page on November 18, 2026. The page also offers yearly billing and says the final amount is calculated at checkout; applicable local taxes are excluded. Cloud hosting is separate from paid CMS features: Strapi’s billing guidance says Content History, Review Workflows, and SSO require a separate Growth or Enterprise CMS license. Verify the selected billing interval, overage schedule, license, and limits on the account’s checkout page.

## Frequently asked questions

### Is Strapi a scam?

The official pages reviewed document Strapi CMS, its Cloud hosting plans, billing, roles, and user permissions. They do not establish a fraud finding. The SCAM Review title is a buyer due-diligence query, not an allegation or endorsement. Confirm the exact license, hosting account, and terms that apply to your purchase.

### How much does Strapi Cloud cost?

On November 18, 2026, Strapi’s Cloud page displayed monthly Starter at $35, Pro at $90, and Business at $450 per project, with different request, storage, bandwidth, backup, and environment allowances. Yearly billing is also offered, taxes are extra, and paid CMS features can require a separate Growth or Enterprise license. Confirm checkout for the current total.

### Is Strapi free to use?

Strapi lists a Community CMS edition separately from its paid Cloud hosting. A self-hosted deployment can still involve infrastructure, maintenance, backups, email, storage, and engineering costs. The Cloud page lists paid hosting tiers; the CMS license and hosting bill should be evaluated separately.

### What is the difference between Strapi CMS and Strapi Cloud?

Strapi CMS is the content-management application and its feature licensing. Strapi Cloud is a hosting service with request, asset, runtime, and operational limits. Strapi’s billing guidance says hosting does not by itself include paid CMS capabilities such as Content History, Review Workflows, and SSO.

### Has Roseram tested Strapi?

No hands-on installation, security audit, or performance benchmark is claimed. This page is an editorial review of the linked publisher materials and a proposed evaluation checklist buyers can run in their own environment.


## Sources and further reading

- [Strapi website](https://strapi.io/)
- [Strapi Cloud monthly pricing and plan limits](https://strapi.io/pricing-cloud)
- [Strapi CMS edition comparison and feature matrix](https://strapi.io/pricing)
- [Strapi Cloud usage, billing, and separate CMS licensing guidance](https://support.strapi.io/articles/3581379360-understanding-strapi-cloud-usage-and-billing)
- [Strapi administration role-based access control documentation](https://docs.strapi.io/cms/features/rbac)
- [Strapi end-user authentication and permission documentation](https://docs.strapi.io/cms/features/users-permissions)
- [saashub listing](https://www.saashub.com/strapi)

For the complete Roseram buyer guide, see [Strapi review](https://roseram.com/reviews/scams/strapi-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
