# Sanity.io review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Headless CMS and content data platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

Sanity is a hosted content platform with a real-time Content Lake, an open-source React-based Studio, structured content modeling, APIs, visual previews, and collaboration features. Its current plans distinguish Free, per-seat Growth, and custom Enterprise pricing, with limits on users, datasets, documents, API requests, assets, and bandwidth. Private dataset availability, backups, custom access control, and additional datasets also differ by tier or add-on. This review focuses on the true cost of a Sanity project, public-versus-private content exposure, role design, backup activation, and what teams should validate before making it a system of record.

## Editorial verdict

Sanity’s official product, pricing, security, roles, and backup pages document a real headless content platform and concrete plan boundaries. The sources reviewed do not establish that Sanity is a scam or that a default configuration is safe for every dataset. This is a source-led desk review, not an implementation, benchmark, or security audit. Buyers should understand public dataset and asset visibility, role combination behavior, Growth seat pricing and usage caps, and the fact that backup availability depends on plan and explicit activation.

## Sanity.io SCAM Review: the short answer

Searching “Sanity.io scam” is a reasonable prompt to investigate a purchase, but it is not evidence of wrongdoing. Sanity’s official pages document a headless CMS, hosted Content Lake, project roles, dataset visibility, current pricing, and backup behavior. The reviewed materials do not establish fraud. They do reveal several details that should be part of a buyer’s decision: Growth is priced per seat, usage limits are separate, a public dataset can be queried without authentication, and backups are not enabled automatically.

This review uses Sanity’s product and documentation pages checked on November 18, 2026. Roseram did not open a project, publish content, test a migration, or conduct a security assessment. The product may suit teams that want structured content and a customizable Studio, but a team must choose dataset visibility, permissions, usage levels, and backup arrangements intentionally. The evidence supports describing the product and its listed limits; it does not support a blanket safety guarantee or an accusation that Sanity is a scam.


## What Sanity is: Studio, Content Lake, and delivery APIs

Sanity combines an editor-facing Studio with a hosted content data service called Content Lake. Teams define structured content and build editorial interfaces, while a website or application queries that content through Sanity’s APIs. The Studio is built with React and can be customized; the platform lists GROQ and GraphQL support, live previews, visual editing, real-time access, and collaboration capabilities. This architecture makes Sanity more than a page builder, but also means the customer’s frontend and content model remain part of the implementation work.

A structured source can help when product details, articles, or media must appear across a web site, mobile app, and other channels. A buyer should test whether editors understand the schema and whether developers can evolve it without disrupting published pages. The platform’s flexibility is valuable when the team has a real content architecture to manage. If the requirement is simply a few fixed pages, a simpler site builder may require less configuration. Product breadth should be judged against the content workflow, not against the number of boxes in a feature table.


## Sanity pricing: Free, Growth per seat, and Enterprise

On November 18, 2026, Sanity’s pricing page listed Free at $0, Growth at $15 per seat per month, and Enterprise at custom pricing. Free included up to 20 seats and two public datasets. Growth included up to 50 seats and two public or private datasets. The plan comparison also listed document counts, project requests, CDN requests, assets, bandwidth, live connections, roles, and history retention. Growth usage above included limits is pay-as-you-go, so the per-seat amount should not be treated as the whole bill.

The current add-on table is an important part of the decision. It lists a Growth increased-quota add-on at $299 per month and additional datasets at $999 per dataset per month, up to two. Dedicated support appears at $799 per month. Those are large enough to change a project’s economics. Confirm whether the selected account needs them, whether quotas are shared per project or per dataset, and which overage meter applies before planning a rollout. Enterprise terms are custom; do not invent a quote from the published self-serve amounts.


## Sanity datasets: public and private have different exposure

Sanity documents two dataset visibility modes. A public dataset can be queried without authorization; a private dataset requires authenticated access or an authorization token. The pricing page lists Free datasets as public only and Growth datasets as public or private. That distinction should be made when creating each dataset, especially if a project contains drafts, internal material, customer data, or non-public assets. A Studio account role does not turn a public API dataset into a private store.

The role guide calls out a related point: if a dataset is public, project members can read its published content even when their role is set to no access. Sanity’s safety page also says assets stored in a dataset are publicly retrievable by anyone who has the asset URL, even if the dataset itself is private. Sensitive files need the documented Media Library visibility controls or another protected storage design. Treat dataset visibility and media visibility as separate questions, and test both through unauthenticated requests before placing confidential content in the system.


## Roles, permissions, and additive access in Sanity

Sanity describes built-in project roles including Administrator, Viewer, Editor, Developer, and Contributor, with availability depending on plan. Enterprise plans list custom roles and more granular access. The roles documentation explains that privileges can be configured at dataset and content-resource levels, and that permissions are additive. If one role grants broad access and another role adds a narrow rule, the narrow rule does not subtract the access already granted. A person holding the standard Editor role can still edit all documents even when an additional custom role is restricted to one content type.

This is a subtle but important administrative rule. Start with least privilege and test the total permissions a member has across every assigned role. For a customer-facing application, check which tokens are exposed and what data they can read. Sanity warns against putting write tokens in browser code and recommends a server-side proxy for submissions. Create test accounts with real combinations of roles, inspect access to settings and datasets, and try an action that must be denied. A correctly configured access model cannot be inferred just from the role names visible in a dashboard.


## Sanity backup pricing, activation, and restore behavior

Backups should be checked before a dataset becomes important. Sanity’s documentation says backup service is off by default and has to be enabled for each dataset. The chosen plan must support it; otherwise the command to enable backups fails. The public pricing table lists backups as unavailable on Free and Growth and custom on Enterprise. This means that neither a hosted database nor a plan label should be treated as proof that a recoverable backup is running for a project.

A buyer should confirm the selected contract, enable backups where available, list the backups, and practice downloading and importing one into a test dataset. Sanity explains that importing a backup with replacement updates matching document IDs but does not automatically delete documents created afterward; restoring an exact earlier state may require additional steps. That distinction matters during recovery. Also check the role needed to list and download backups: the docs require Administrator, even though a Developer can enable or disable the service. Write down the procedure and test it with an authorized administrator before relying on it.


## Documents, API requests, bandwidth, and usage overages

Sanity’s price table separates project quotas for documents, API requests, API CDN requests, assets, and bandwidth. On the page checked, Free showed 10,000 documents, 250,000 API requests, one million API CDN requests, 100 GB of assets, and 100 GB of bandwidth. Growth showed 25,000 documents and the same listed request, asset, and bandwidth figures before add-ons or pay-as-you-go usage. Additional Growth charges were shown for requests, asset storage, and bandwidth. These meters represent different kinds of activity, so a usage estimate should not collapse them into a single traffic number.

Estimate the typical page or app flow: how many queries run, whether CDN caching applies, how often editors preview, how many documents the team retains, and how quickly media grows. Measure a representative week and project a seasonal peak. Ask how usage is metered across environments, datasets, and applications. If a team expects to exceed a limit, compare the add-on with the per-unit price and verify whether the product continues operating when an allowance is reached. This review has not run a Sanity workload and makes no claim about a specific project’s likely invoice.


## Sanity Studio, collaboration, and editorial workflow

Sanity lists real-time editing, multiplayer presence, live preview, visual editing, and a presentation tool across its plans. Growth adds comments, tasks, and scheduled drafts compared with Free. Those capabilities can improve a multi-person editorial process, but their value depends on how a team publishes. Model a real article or product update and follow it through draft creation, review, preview, approval, publication, and correction. Check whether the editorial team can understand the interface without asking developers to repair every routine content change.

The pricing comparison also lists different review-history retention: three days on Free and 90 days on Growth for draft changes, with longer or custom history on Enterprise. The exact retention matters if a team needs to investigate a content change several months later. An activity feed is not automatically a complete audit trail; Sanity lists full audit history as an Enterprise capability. Buyers should match the history they need to the appropriate feature and not rely on screenshots or an assumed version history.


## Content modeling and the developer experience

Sanity’s structured approach lets developers shape content around the organization’s domain instead of forcing every page into the same fixed template. That flexibility brings a design obligation: define reusable fields, references, validation, localization, and editorial states that remain understandable as the catalog grows. A poor schema can turn a capable CMS into a confusing form. A useful pilot starts with the most common content type, then includes one exception that often breaks a simple model.

The Studio is open-source and built with React, so teams can extend the editing experience. They still need to own that code, manage versions, and test compatibility when dependencies change. Sanity supplies hosting and APIs, but the website frontend, caching strategy, deployment, and public data filtering remain part of the overall system. Keep write credentials on the server, make mutations explicit, and ensure the frontend requests only the fields intended for public display. A headless CMS is a foundation; it does not remove the need to engineer the surrounding application.


## Security, API tokens, and media exposure

Sanity’s safety guidance warns that anyone with a write-enabled token may be able to alter or delete content. If a token becomes public, the documentation says to treat it as lost and revoke it. It also advises against putting access tokens in browser JavaScript because visitors can inspect shipped code. A public frontend should use a server-side proxy or query only intentionally public data, rather than embedding a private token and assuming it remains secret.

Media requires its own treatment. The docs say assets in a dataset are exposed through the asset CDN even when the dataset is private; anyone with a known URL can fetch the file. Private per-asset visibility and signed URLs are available through the Media Library, or the buyer can host restricted files elsewhere. Before uploading sensitive documents, confirm the actual storage path and URL access rules. This review does not claim a vulnerability in Sanity. It explains the publisher’s documented data model so a customer can avoid placing confidential assets in a publicly accessible location by mistake.


## Sanity alternatives and a fair comparison

Compare Sanity with other headless CMS products, a hosted content service, or a simpler website builder according to the same requirements. A developer-oriented Content Lake may be attractive when structured data, custom Studio behavior, and live preview matter. Another platform may bundle more built-in editorial workflow, provide different access controls, or price users and content differently. A website builder may be easier when the content model is small and stable. There is no universal winner for every publishing team.

Use one real publishing brief in each candidate. Model the same content types, add a user with restricted access, produce a preview, publish a change, export content, and recover a dataset. Compare the complete cost for one year, including seats, add-ons, usage overages, media handling, and support. A vendor’s marketing claim or customer logo cannot replace that comparison. Roseram may help plan a site or evaluate a CMS integration, but it does not host Sanity’s Content Lake or make the vendor’s dataset private.


## Who Sanity may suit—and who should pause

Sanity may suit a product team that wants a structured source of content, a customizable editor, and the ability to deliver data to more than one frontend. Developers who can own a React Studio and content schema may value the platform’s flexibility. Growth can be relevant when a team needs private datasets and richer collaboration without a custom Enterprise arrangement, provided its seat and usage projections fit the per-seat and pay-as-you-go model.

Pause if the project needs private data on the Free plan, expects backup service without enabling it, or has not assigned an owner for access tokens and media visibility. A small organization should compare the per-seat bill with its actual editor count and understand that paid viewers are treated differently if assigned extra roles. If procurement requires custom SSO, a full audit trail, an SLA, or specified backup terms, confirm which Enterprise agreement provides them. These are fit and configuration considerations, not evidence of misconduct.


## A Sanity evaluation before committing content

Create a test project with synthetic information. Use two datasets, one public and one private if the selected plan supports both. Publish a harmless entry, query it without a token, and check the expected response. Upload a test file and try the asset URL separately. Give two users overlapping roles, then inspect what each can read, edit, publish, and change in project settings. Confirm that a write token never reaches the browser bundle and that a failed request does not reveal private content.

Next, verify limits and recovery. Measure the request volume for one user flow, estimate asset growth, check the plan’s seat and dataset quotas, and run a backup export/import if the chosen plan includes backups. Confirm whether the restore procedure deletes or preserves newer records. Record the project settings and current rate card. This is a suggested evaluation method, not a claim that Roseram ran these tests. Do not put customer records or confidential media into a trial project until the data transfer and access controls have been reviewed by the organization.


## Is Sanity.io a scam? What the evidence supports

Sanity’s official site describes the CMS and its commercial plans, and its documentation explains dataset visibility, role behavior, tokens, and backups. The evidence reviewed does not establish a fraud finding. The “SCAM Review” title frames a due-diligence question; it is not a statement that the company committed misconduct. A buyer should use the dated pricing table and current account terms to determine which features and limits apply to the specific project.

If a charge or access outcome differs from what a buyer expected, compare the invoice with seat counts, request usage, assets, bandwidth, dataset add-ons, and the contract. Preserve screenshots or exports of the relevant settings. For a security incident, revoke exposed credentials and follow the documented support route; do not assume that deleting a token from a local code file removes a copy already published. No customer complaints, testimonials, or legal outcomes are fabricated in this review. Any specific allegation should be tied to a dated, attributable source.


## Final Sanity.io assessment

Sanity offers a flexible headless CMS with a customizable Studio, hosted content data, and APIs. Its current pricing is shaped by per-seat Growth billing and project quotas, with sizable add-ons for additional datasets and higher usage. The most important technical details are concrete: Free datasets are public-only, dataset assets remain publicly fetchable when their URLs are known, role permissions add together, and dataset backups must be available on the plan and deliberately enabled.

A buyer should pilot the exact content model, account for users and usage, test dataset and asset visibility, combine roles deliberately, and rehearse a backup export before using the service for essential content. A Roseram workspace may help plan a website or prototype a CMS integration, but it does not host Sanity’s content database. Teams without developers may prefer a simpler CMS; teams needing deeply customized content workflows may value Sanity’s approach. The official materials support a clear description of the service and its limits. They do not support a fraud allegation, an automatic security assurance, or a claim that Roseram has installed and tested Sanity.


## Features and decision criteria

- Structured content in a hosted real-time Content Lake
- Open-source React-based Sanity Studio with live preview and visual editing
- GROQ and GraphQL content querying with APIs and webhooks
- Project roles and dataset visibility controls, with tier-specific custom access options
- CLI-based dataset export and plan-dependent backup features

## Pricing considerations

These are the USD monthly values and quotas displayed on Sanity’s pricing page on November 18, 2026. Growth is billed per seat, and usage above included quotas is pay-as-you-go. Enterprise is custom priced. The page lists separate add-ons for support, higher quotas, and additional datasets; additional datasets are shown at $999 each per month. Verify project-specific limits, tax, billing interval, current add-on availability, and which features require Enterprise before checkout.

## Frequently asked questions

### Is Sanity.io a scam?

Sanity’s official pages describe its content platform, public pricing, access controls, and backups. The reviewed materials do not establish a fraud finding. The SCAM Review title is a buyer due-diligence query, not an allegation or endorsement.

### How much does Sanity cost?

On November 18, 2026, Sanity listed Free at $0, Growth at $15 per seat per month, and Enterprise at custom pricing. Plans also have document, request, asset, bandwidth, seat, and dataset limits; Growth usage above its included quotas is pay-as-you-go. Check all project meters and add-ons before estimating total cost.

### Are Sanity datasets private by default?

Sanity documents public and private dataset modes. The Free plan lists public-only datasets; Growth lists private or public datasets. A public dataset can be queried without authorization, so choose visibility deliberately and never treat published content as private merely because a Studio role is restrictive.

### Are Sanity backups automatically enabled?

No. Sanity’s documentation says backups are off by default and must be enabled per dataset. The plan must include the backup feature; verify its availability and test an export or restore before depending on it.

### Has Roseram tested Sanity?

No installation, migration, performance test, or security audit is claimed. This is an editorial desk review of Sanity’s public materials and a proposed buyer evaluation plan.


## Sources and further reading

- [Sanity.io website](https://www.sanity.io/)
- [Sanity official pricing and usage limits](https://www.sanity.io/pricing)
- [Sanity dataset visibility, asset access, and token security guidance](https://www.sanity.io/docs/content-lake/keeping-your-data-safe)
- [Sanity project roles and additive permission behavior](https://www.sanity.io/docs/user-guides/roles)
- [Sanity dataset backup setup and restore documentation](https://www.sanity.io/docs/content-lake/backups)
- [Sanity role and permission model documentation](https://www.sanity.io/docs/content-lake/roles-concepts)
- [saashub listing](https://www.saashub.com/sanity-io)

For the complete Roseram buyer guide, see [Sanity.io review](https://roseram.com/reviews/scams/sanity-io-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
