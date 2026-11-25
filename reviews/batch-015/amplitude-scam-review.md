# Amplitude review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Digital product analytics, experimentation and user engagement  
**Method:** Source-led desk review; no hands-on testing is claimed.

Amplitude is a digital-product analytics platform with event analytics, session replay, experimentation, feature flags, guides, surveys and AI-assisted analysis. Its current pricing page describes a no-cost Free plan with up to 2 million events per month, unlimited seats and no credit card requirement; documentation says the Free tier retains data for one year. Plus is self-serve and usage-based, while Growth and Enterprise are sales-led, and paid tiers differ in event or monthly-tracked-user volumes, retention and governance controls. Amplitude’s documentation says paid usage can incur overage charges at the account’s per-unit rate. Free users who exceed the monthly limit three times can be blocked from charts and dashboards, and continued over-limit use can lead to account deletion six months after the initial block. This makes instrumentation design and quota alerts important even when the initial price is zero. Amplitude publishes privacy, security and data-processing materials and says customers control event data they submit, but the customer must avoid unnecessary personal data and configure deletion, retention and consent appropriately. The evidence reviewed supports a real analytics platform and does not substantiate a scam allegation.

## Editorial verdict

Amplitude publishes a broad product, pricing and billing documentation set that explains event volumes, retention, overages and Free-plan consequences. The free tier is substantial for a small product, but 2 million events are not an unlimited allowance; noisy instrumentation can exceed the threshold. Paid Plus uses usage-based charges, so teams should review the estimate, per-unit rate, event-per-MTU guardrail and renewal terms. Nothing reviewed substantiates calling the service a scam. The review is based on public materials, not an instrumented product test, billing simulation or independent security audit.

## Amplitude SCAM review: evaluate the data plan behind the dashboard

Amplitude is a hosted product-analytics platform used to understand what people do inside a digital product. Its current product pages combine event analytics with features such as session replay, experimentation, feature flags, guides, surveys and AI-assisted analysis. The platform is more than a charting interface: it depends on decisions about what counts as an event, how identities are stitched, which properties are collected and how long data is retained.

This article uses “SCAM Review” as the directory’s label, not as a finding that Amplitude has committed fraud. Amplitude publishes plan details, usage documentation, legal terms and privacy materials. Those primary sources support identifying it as a real analytics service. They do not verify that an individual company has implemented its tracking correctly, that a particular chart is causal evidence, or that the tool is appropriate for every data-regulated use case. The key buyer risks are instrumentation quality, quota growth, event-level privacy and the difference between the marketing page and the limits in the billing documents.


## What Amplitude analytics measures

Amplitude describes an event as an action in a product, such as a page view, signup, purchase or button click. A team can send those records and analyze adoption, journeys, funnels and behavior across user cohorts. The same organization may also use session replay or experiments to understand how a flow performs and test a change. These capabilities are useful when product, design and engineering teams agree on what an event means and when it fires.

Before implementing an SDK, define a short tracking plan: event name, trigger, required properties, identity rules, owner and intended question. Avoid sending every click just because the SDK makes it easy. Duplicate events, inconsistent naming and changing property types make analysis less trustworthy and can consume volume unnecessarily. A tracking plan is a product-data contract between engineering and the people who will use reports.


## Free plan: substantial allowance with a real monthly ceiling

Amplitude’s current pricing page describes a Free plan with up to 2 million events per month, no time limit and no credit card required. The billing documentation also lists core analytics features and one-year data retention on Free. This makes it possible for a small team to begin measuring a product without choosing a paid analytics contract immediately.

The event limit is still a quota. A single user can produce many events, and a product with verbose instrumentation, automated traffic or duplicated client/server tracking can consume the allowance faster than expected. Measure real event flow before deciding that 2 million is enough. Keep a way to access raw source events or another reporting layer if dashboards become unavailable due to a limit. The public docs say repeated Free-plan overruns can block access to charts and dashboards; that operational outcome should be part of launch planning.


## Free-plan overages can affect access and eventually data

Amplitude’s billing documentation says a Free organization that exceeds its monthly limit three times can be blocked from charts and dashboards. Administrative functions such as the User API remain available so customers can address compliance needs. If the organization continues to exceed the limit without upgrading, the docs say Amplitude deletes the account six months after the initial block. These are specific plan consequences that a team should understand before sending production data.

Set owner alerts, monitor the in-product quota dashboard, and establish an escalation path before the limit is reached. Include the cost of a paid tier in the architecture budget rather than treating a free plan as a permanent zero-cost infrastructure dependency. If the product has a traffic spike, bot event storm or instrumentation bug, know how to pause or filter ingestion. Preserve a separate data backup where appropriate and verify retention needs against the current plan documents.


## Paid usage is metered and may create additional charges

Amplitude’s help pages describe Plus as a self-serve plan that scales with event or monthly tracked user volume. The billing docs say that paid usage beyond included volumes can be charged at the same per-unit rate as the plan. The Plus Plan Addendum describes fees for additional event or MTU volume, and reserves the ability to suspend or terminate access if usage exceeds a defined multiple of the purchased amount. The exact billing basis depends on the plan and contract.

Before upgrading, find out whether the organization is billed by events, monthly tracked users or another contract metric; what event-per-MTU allowance applies; how excess is calculated; when charges are collected; and what controls prevent unexpected ingestion. Use a representative event sample to estimate volume and run a test project before shipping a new SDK. A usage estimate is useful only when the instrumented event definition and traffic assumptions match production.


## Retention changes by tier

Amplitude’s documentation lists one year of retention for Free, two years for Plus and seven years for Growth and Enterprise, while the product plan and agreement govern the account’s actual terms. Longer retention can support long-range cohort or lifecycle analysis, but it also means more historical data remains in the system and may require different governance decisions.

Decide how much history the business needs before paying for a tier. Keep separate records of account retention and application-level deletion duties; a longer platform retention setting should not override a user’s deletion request or your own retention schedule. Ask how deletion propagates to derived tables, session replay and backups. If a project changes plans, verify whether older data remains accessible and how data is treated when the plan is downgraded.


## Instrumentation quality matters more than the number of charts

An analytics tool cannot rescue ambiguous event design. If “activation” is counted differently in mobile and web, or if a purchase event fires before payment settles, a dashboard can make a flawed process look precise. Establish shared definitions for key actions, test them in staging and production, and monitor event volume by release and source. Revisit the schema when product behavior changes.

A sound implementation distinguishes user, account and anonymous identities, handles consent choices, validates required properties and prevents duplicate client/server events. Document how tests and employees are excluded from business reporting. Keep a change log for event definitions, SDK versions and filters. These tasks take engineering and product time; include them when comparing Amplitude with lighter analytics tools.


## Interpret charts as evidence about behavior, not automatic causation

A funnel can show where people leave a workflow, and a cohort chart can show a difference between groups. Neither alone explains why that difference occurred. Product changes, marketing campaigns, seasonality, device mix and instrumentation releases can all alter the numbers. Write down the question before building a chart and check whether its event definitions actually represent the user action you intend to measure.

For decisions with a large business impact, combine behavioral data with user research or a controlled experiment where practical. Check sample size, exposure rules, missing events and whether the same person appears more than once. Keep a note of caveats beside the report instead of presenting a single percentage without context. This approach helps a team use Amplitude as an analytical instrument rather than treating a dashboard as an oracle.


## Privacy and customer data responsibility

Amplitude’s privacy and security pages say customers control the data they choose to send and provide data-processing documentation and deletion/access tools. Its public security materials describe certifications and security controls; those are company disclosures and should be verified through the trust documentation relevant to a buyer’s plan. The Privacy Notice covers information Amplitude processes as a controller, while customer event data also sits within contractual processor terms and the DPA.

A customer remains responsible for deciding whether an event property should be collected, explaining the tracking to users and honoring relevant rights. Avoid direct identifiers or sensitive fields unless the product and contract specifically support the use and your legal team has approved it. Mask inputs in session replay, configure IP handling and evaluate consent requirements for analytics cookies or SDKs in each region. A vendor’s DPA does not automatically make an organization’s collection lawful.


## Session replay and experimentation need product guardrails

Session replay can help teams see where a user encounters a confusing flow, and experimentation can compare alternatives. Those features also create additional data flows and can expose on-screen text if masking is not configured correctly. The product page lists these features, while plan pages and security documentation describe availability and controls that vary by account.

Before enabling replay, inspect what is captured on login, payment, health, support and account pages. Test masking with realistic fields and confirm that excluded content is not visible to unauthorized staff. For experiments, define the primary metric and guardrail metrics, avoid changing multiple factors without a design, and decide who may launch or stop a test. A chart showing a difference is not automatically proof that the variant caused it; consider sample, seasonality and selection effects.


## AI analytics: useful assistance, still a question of input and verification

Amplitude’s pricing page includes AI-related features and agents. Its documentation says AI capabilities may use customer data that the customer has submitted, depending on the feature, and explains vendor controls and data-retention claims. These capabilities can make it easier to ask questions about product data, but the result depends on event quality, metric definitions and the model’s interpretation of the dataset.

Provide only data that the feature needs, review the applicable AI terms, and validate generated answers against the underlying chart or query. Do not make customer eligibility or employment decisions from an unreviewed analytics summary. Keep human review for changes to production instrumentation or customer-facing experiments. AI can shorten analysis setup; it does not turn observational product data into causal proof.


## Implementation cost and team fit

Amplitude may be a fit for product organizations that have an engineering owner for event collection and analysts or product managers who will use funnels, cohorts and experiments regularly. Teams with multiple surfaces can benefit from a shared event model. A small site that needs only page views and basic referral attribution may not need the full product-analytics workflow.

Budget for instrumentation, governance, training and event maintenance as well as the subscription. If no one owns data definitions, reports often diverge and stakeholders stop trusting them. Assign an administrator, a data dictionary owner and an escalation route for schema changes. Start with a focused workspace and expand only after the first analyses produce decisions that the organization can explain.


## Alternatives and a fair product-analytics comparison

Alternatives include open-source analytics, lightweight web analytics, a warehouse-first event pipeline, CRM reporting or another hosted product-analytics service. These options differ in data ownership, required engineering, event volume, retention, replay, experimentation and support. A warehouse-first approach can provide flexibility but requires more implementation and maintenance; a lightweight analytics tool can be easier to run but may lack behavioral cohorts or experimentation.

Compare the same sample flows, event volume, retention need, export options, access control, privacy configuration and likely annual cost. Test how each tool handles identity, deletion and quota exhaustion. Ask product users to answer the same questions in each pilot: where do users abandon onboarding, which cohort returns, and what changed after a release? Choose the system whose results are understandable and governed, not simply the one with the most chart types.


## Amplitude SCAM review verdict: strong analytics capability, watch usage thresholds

Amplitude publishes an analytics platform, a Free allowance of 2 million events a month, paid plans, retention differences, usage limits and detailed overage documentation. Its privacy and security pages describe customer control of submitted event data and associated processor materials. This is enough to identify a real product and to set out concrete buyer checks, but it does not verify each customer’s implementation or a specific security certification report.

The evidence reviewed does not substantiate calling Amplitude a scam. Buyers should model event volume, understand the Free-plan blocking and deletion behavior, confirm paid overage terms, design a disciplined schema and configure privacy before collecting production events. This is a source-based desk review, not an account trial, instrumented benchmark, billing test, legal opinion or security audit. Official materials were reviewed November 18, 2026; confirm the live plan and contract before implementation.


## Features and decision criteria

- Event-based product analytics, funnels and behavioral journeys
- Free tier with 2 million events per month and no credit card requirement
- Session replay, experimentation, feature flags and customer engagement tools
- Usage-based paid plans with data retention and feature differences by tier

## Sources and further reading

- [Amplitude official pricing: Free and Plus plan overview and current feature claims](https://amplitude.com/pricing)
- [Amplitude billing and plans documentation: plan differences, event caps and overage outcomes](https://www.amplitude.com/docs/faq/billing-and-plans)
- [Amplitude limits and quotas: event counting and paid-account alerts](https://www.amplitude.com/docs/data/limits-and-quotas)
- [Amplitude Plus Plan Addendum: overage fees, nonrefundable fees and account thresholds](https://amplitude.com/plus-plan-terms)
- [Amplitude Terms of Service, effective July 21, 2026](https://www.amplitude.com/terms)
- [Amplitude Privacy Notice, updated November 3, 2026](https://www.amplitude.com/privacy)
- [Amplitude Security and Privacy: customer controls and privacy tools](https://www.amplitude.com/security-and-privacy)
- [Amplitude security and privacy documentation, including the Data Processing Addendum](https://amplitude.com/docs/admin/security-and-privacy)
- [Amplitude website](https://amplitude.com/)
- [saashub listing](https://www.saashub.com/amplitude)

For the complete Roseram buyer guide, see [Amplitude review](https://roseram.com/reviews/scams/amplitude-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
