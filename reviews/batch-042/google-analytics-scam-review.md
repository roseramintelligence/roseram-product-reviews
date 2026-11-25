# Google Analytics review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Web and app analytics service  
**Method:** Source-led desk review; no hands-on testing is claimed.

Google Analytics is a web and app measurement platform that collects event data through site tags and mobile SDKs. GA4 offers reports, explorations, audiences, advertising integrations, and BigQuery export. The standard service is available without a subscription fee under Google’s published terms, while Google Analytics 360 is a contracted enterprise product with higher limits and service commitments.

## Editorial verdict

Google’s official terms and documentation describe a real measurement product with published standard and enterprise limits. The sources do not support a fraud allegation. The key diligence work is protecting visitor privacy, respecting consent and data-use rules, measuring meaningful events, and understanding the differences between aggregated reports, retention windows and raw BigQuery exports.

## Google Analytics review: measurement depends on event design

Google Analytics helps a site or app record interactions and present them as reports, explorations, audiences, and advertising measurements. The quality of the output begins before the first chart: teams must decide what an event means, how it is named, which parameters matter, and whether a visitor has consented to the collection that triggers it. A default installation can show activity, but it cannot define the business outcome that the team ought to optimize.

A clear implementation starts with a measurement plan. Define a small event vocabulary for important actions such as a signup, a purchase, or completion of a key workflow. Specify the event source, required parameters, and the person responsible for validation. Avoid creating a new event for every page element or copying personal details into URLs. Test with a staging property and a small set of controlled journeys before using reports to make budget or product decisions.


## Google Analytics pricing: free standard properties and paid 360

Google’s terms state that GA4 properties are provided without charge, while the enterprise Analytics 360 offering is positioned separately with higher limits and contracted capabilities. Standard includes useful analytics at no subscription fee, but it has per-property configuration and export limits. Analytics 360 increases collection, reporting, BigQuery export, retention, and support capabilities, and its commercial terms are handled through Google rather than a public self-serve price table.

Include costs that live outside the Analytics line item. A BigQuery dataset can incur storage and query charges, and Google’s documentation notes an additional charge for streaming export. Tag management, server-side collection, consent management, data modeling, implementation work, and analytics support may also require time or paid services. Make the service and cloud costs visible as separate budget lines. A no-subscription price does not remove the cost of collecting data responsibly and keeping the measurement system maintained.


## GA4 limits: audiences, events, reports and BigQuery exports

The standard and 360 products have different limits for configured items and data handling. Google’s help pages list standard limits for audiences, key events, explorations, API tokens, data retention, and daily BigQuery exports. Standard properties can export up to one million events per day through the daily export; if that volume is exceeded persistently, the export can be paused, and earlier missed daily exports are not reprocessed. Filtering streams or events can help keep the export within the documented allowance.

The streaming export has no event-count limit in Google’s current help page, but it is described as best-effort and may omit data; it also has separate BigQuery cost implications. Some user-attribution fields for new users are unavailable in the near-real-time stream or take time to populate. For stable, complete daily analysis, understand the batch export's timing and schema. Do not use an intraday table as though it were a finalized daily record, and compare the raw BigQuery event data with the processed interface before reconciling totals.


## Data retention, privacy and consent are part of setup

Google’s current retention documentation lets standard properties set user-level and event-level retention to two or fourteen months, with shorter rules for certain demographic and interest data. These controls affect user-level and event-level data used in explorations and funnel reports; they do not erase standard aggregated reports in the same way. Google says larger properties can be limited to two months, and that changing a retention period can affect already-collected data. Review settings before a reporting requirement depends on a long historical window.

Google prohibits sending personally identifiable information to Analytics, and its data-safeguards material says website and app operators need to inform visitors about data collection and provide a chance to grant or deny consent where required. Cookies and app instance identifiers are measurement mechanisms, not a replacement for a legal basis or a clear privacy notice. Audit URLs, form fields, campaign parameters and custom event properties for email addresses, names, health information, or other sensitive values. Use data deletion controls when needed, and restrict property access to people with a business reason.


## Reports, sampling and the BigQuery source of truth question

Google Analytics reports and BigQuery exports serve related but different purposes. Reports present processed and modeled views with the dimensions and metrics available in the product, while the BigQuery export contains raw collected events and user-level data under the selected export configuration. Google notes that the export can differ from the interface because the interface applies additional value additions. A difference is not automatically evidence of a broken tag; it can arise from processing, attribution, modeling, sampling, filters, time zones, and export timing.

Before using Analytics as the source for revenue or attribution decisions, define which system is authoritative for transactions and consent. Reconcile a small sample of events against the application or payment system, including time zone and currency. Confirm whether a report is sampled, filtered, or modeled. Keep implementation version history and annotate material tag changes. If financial reporting requires exact order-level records, do not substitute aggregate web analytics for the underlying transaction ledger.


## Google Analytics setup, integrations and account governance

Analytics can connect to Google Ads, Search Console, Tag Manager, BigQuery, and other Google products. Those integrations can shorten the path from an observed visit to a campaign or search report, but each link creates a permission and data-flow decision. Google documents property roles and BigQuery project ownership requirements for exports. Keep ownership with the organization, not one departing employee, and use named administrators with minimal roles instead of sharing a login.

Document which sites, mobile apps, regions, and environments send to each property. Separate test activity from production, use internal-traffic filters carefully, and monitor for duplicate tags that inflate event counts. Review who can alter retention, link advertising accounts, export data, or create audiences. A two-person review for high-impact configuration changes reduces the chance that a mistaken tag or permission change silently damages months of reporting.


## Google Analytics alternatives and the buyer test

Compare GA4 with privacy-oriented analytics products such as Matomo or Plausible, product analytics platforms, and a self-hosted event pipeline. Use the same question set: what user-level detail is needed, how will consent be recorded, where will data live, who can access it, how long will it be retained, and what exports are available? The cheapest tool is not necessarily the right fit if its data model or regulatory approach conflicts with your needs. A simpler measurement plan can also reduce the need for an enterprise tier.

Test one important journey from a consent decision to an event, a report, and any BigQuery export. Confirm that denied consent behaves as intended, the event contains no prohibited personal information, and a purchase reconciles against the transaction source. Then change the retention setting in a test property and confirm its reporting effect. This is a proposed evaluation, not a claim that Roseram audited a Google Analytics property or measured campaign results.


## Google Analytics SCAM Review: what the evidence says

Google publishes product features, free standard service terms, configuration limits, retention controls, privacy rules, and BigQuery export behavior. That public material describes an identifiable service, not evidence of a scam. This page is a desk review of the linked documentation. Roseram did not install tags, inspect a customer account, test consent behavior, or certify compliance.

Before relying on Analytics, confirm your data collection notices, consent path, event schema, property owner, access roles, retention policy, and downstream BigQuery billing. Review limits for the exact property size and export type you plan to use. Ask a privacy professional about applicable law and deployment choices if your organization handles sensitive information. The responsible decision is based on a validated implementation and a clear data purpose, not on a search snippet or an assumption that a free service has no operating costs.


## Features and decision criteria

- Web and app event measurement with reports and explorations
- Audience, campaign and conversion analysis
- Google Ads, Search Console, Tag Manager and BigQuery integrations
- Data retention, user deletion and property-level administration controls

## Pricing considerations

A free Analytics account does not mean the implementation or every linked service is free. Standard GA4 daily BigQuery export is limited to 1 million events. Streaming export has no event-count cap in the documentation but is best-effort and may incur BigQuery charges. Review current property, export and Cloud billing terms.

## Sources and further reading

- [Google Analytics terms and standard service fee](https://marketingplatform.google.com/about/analytics/terms/us/)
- [Google Analytics features and integrations](https://marketingplatform.google.com/about/analytics/features/)
- [GA4 configuration limits and 360 comparison](https://support.google.com/analytics/answer/12229528?hl=en-EN)
- [Google Analytics data retention controls](https://support.google.com/analytics/answer/7667196?hl=en-au)
- [GA4 BigQuery export limits, timing and billing](https://support.google.com/analytics/answer/9358801?hl=en)
- [Google Analytics data safeguards and PII rules](https://support.google.com/analytics/answer/6004245?hl=en)
- [Google Analytics on Wikipedia](https://en.wikipedia.org/wiki/Google_Analytics)
- [Google Analytics website](https://analytics.google.com/analytics/web/)
- [saashub listing](https://www.saashub.com/google-analytics)

For the complete Roseram buyer guide, see [Google Analytics review](https://roseram.com/reviews/scams/google-analytics-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
