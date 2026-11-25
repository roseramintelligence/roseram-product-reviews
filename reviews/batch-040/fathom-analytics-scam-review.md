# Fathom Analytics review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Privacy-focused website analytics  
**Method:** Source-led desk review; no hands-on testing is claimed.

Fathom Analytics is a website analytics service that prices plans by monthly page views across sites and describes cookieless, site-specific visitor signatures. It offers a seven-day trial that requires a payment card, then bills automatically unless canceled; customers should test metric definitions, legal suitability, event counting and export or deletion behavior.

## Editorial verdict

Fathom publishes pricing, trial, cancellation, terms and privacy documentation. The sources reviewed do not substantiate a scam allegation or establish that one analytics setup meets every jurisdiction’s privacy rules. Compare its metrics with first-party logs, understand the trial’s automatic billing, export before cancellation and treat privacy-compliance claims as inputs for a legal review.

## Fathom Analytics SCAM review: distinguish privacy claims from the bill

Fathom Analytics is a hosted website analytics product from Conva Ventures Inc. Its pricing page charges according to monthly page views across a customer’s sites, and the vendor promotes a privacy-oriented approach that does not rely on analytics cookies or cross-site visitor profiles. The product documentation defines its visitor and view measures, while its terms and support pages explain trials, recurring subscriptions, cancellation and data deletion.

“SCAM Review” is the directory label, not a determination of fraud. The sources reviewed do not substantiate that accusation. The main buyer questions are measurable: whether Fathom counts the traffic the team expects, how custom events affect usage, what the trial will charge if not canceled, and what happens to data when billing stops. Its privacy positioning is relevant but does not automatically decide legal compliance for every site or jurisdiction.


## What Fathom Analytics counts as a page view and visitor

Fathom’s dashboard guide distinguishes views, page visitors and site visitors. A page view is a page load; a site visitor is a unique individual for a 24-hour period under the company’s daily reset method. The vendor’s FAQ says custom events count toward the monthly pageview allowance, including events sent through its API. These definitions matter because the subscription price is not based only on the number of pages or websites in an account.

Before installing the script, decide which analytics events the business plans to send and compare Fathom’s counts with existing logs or analytics for a representative week. Include page loads, repeated sessions, API events and any single-page application route changes. Do not treat the visitor count as a lifetime person-level identity; Fathom says its visitor signature resets daily. Use the definition that the dashboard documents when explaining the metric to clients or finance.


## Fathom pricing is based on monthly page views across sites

The pricing page reviewed lists monthly tiers beginning at US$15 for up to 100,000 page views, then higher tiers at 200,000, 500,000, one million and more, with custom pricing above 25 million. It says every plan includes at least 50 sites and that customers can add site packs. Pricing is based on the combined pageview use across the account, not a separate allowance for each listed website.

Forecast all production sites together, including low-traffic campaign pages and internal tools if they use the same account. Count custom events and API submissions, not just document loads. Save the live quote and compare its currency and billing term with the business’s analytics budget. A site portfolio can grow unevenly, so check whether a marketing launch or measurement change will push the account into another tier.


## The seven-day Fathom free trial requires a payment card

Fathom’s trial guide says the trial lasts seven days, starts immediately at signup and requires a payment card. It says the card is not charged until the trial ends and that the provider sends an email reminder before charging on day seven. The pricing page likewise says the selected plan begins billing automatically when the trial ends unless the account is canceled. The vendor explains the card requirement as a measure against misuse of unrestricted trial access.

Set a calendar reminder on the day of signup and another before the end of the trial. Confirm that the reminder email reaches the account owner and that the billing page shows the correct selected plan. If the evaluation is not complete, cancel in the dashboard before the trial ends and keep the confirmation. A card-required trial is not inherently deceptive, but the automatic conversion is a real cost decision that should be made deliberately.


## There is no permanent free tier to use as a long-term archive

The pricing FAQ says Fathom does not offer a free plan and explains that subscriptions fund operation and development of the service. It describes a free trial for evaluation rather than permanent no-cost access. A company evaluating analytics therefore needs to budget for a paid tier if it wants to continue collecting data after the trial. The absence of a free tier also makes data export and migration planning relevant before the trial begins.

Run Fathom alongside an existing analytics system during the trial, as the pricing FAQ suggests, and compare the metrics while both tools collect the same traffic. Verify that consent settings and scripts do not count one visit differently due to duplicate implementation. Export a sample report and test the destination format. Decide in advance what the company will do if the plan is too costly, so the trial does not become an accidental subscription simply because the team has not made a decision.


## Overages, pageview limits and plan changes

Fathom’s pricing page says occasional traffic spikes do not automatically stop analytics. For substantial or sustained overages, the provider says it will email the customer to request an upgrade, and the customer approves plan changes. It says unresolved overages can restrict dashboard and API access while collection continues. The FAQ also says pageview limits include custom events and API events, so instrumentation choices can affect the allowance.

Review usage during launches, paid campaigns and seasonal peaks. Set an internal threshold below the plan limit, and assign an owner to investigate a sudden increase. Check what happens to collected data while dashboard access is restricted and what exact action restores service. Do not assume that a normal site spike automatically changes the bill, but do not ignore an overage notice. Confirm upgrade pricing before approving a change.


## Cookieless visitor signatures are the vendor’s described method

Fathom’s product explanation says it briefly processes an IP address and user agent, hashes them with a site identity and a daily salt, and uses the resulting site-specific signature for visitor measurement. It says the salt rotates at midnight UTC and that the approach avoids analytics cookies and cross-site advertising profiles. This is the vendor’s account of how its system works and can be read alongside its current privacy policy and data-processing terms.

“Cookieless” does not mean that no information is ever processed or that no privacy obligations apply. The provider says it briefly processes request metadata; the site owner should understand the full data flow, what events are configured, which integrations receive results and what the law requires for the site’s audience. Review the actual implementation and consent setup with a qualified privacy adviser. Avoid converting a product claim into an unverified blanket statement that a cookie banner is never needed.


## Analytics metrics are not the same as first-party server or sales records

Fathom’s dashboard provides aggregated views, page visitors, referrers, entry and exit pages and custom events. Each metric has a definition and a collection method. A missing referrer can mean a direct visit, an email or app link, or an unavailable referrer, as the dashboard guide explains. Analytics data can be helpful for trends but may not exactly match server logs, advertising platforms or a payment processor.

When reporting campaign results, define the source for each number and avoid combining unlike counts. Use server-side order records for completed purchases, analytics for traffic patterns and advertising reports for the platform’s attributed activity. Compare time zones, bot filtering, consent choices, browser restrictions and event de-duplication. If a client requests “unique users,” explain Fathom’s daily visitor definition rather than treating it as a permanent identity record.


## Custom events and API tracking require implementation discipline

Fathom documents custom events and API submissions as part of its analytics workflow, and says they count toward the pageview allowance. This creates flexibility to measure signups or actions that do not correspond to ordinary page loads. It also creates a risk of duplicate or accidental events when a browser script and server integration both record the same action, or when a single-page application fires a route event more than once.

Name events consistently, define when each fires and test a single conversion end to end. Avoid sending email addresses, full names or other personal data in event names or custom properties; the Terms say the service must not be used to track personal data. Keep API credentials server-side and revoke them when an integration is removed. Review the billing dashboard after launch so an implementation bug does not quietly inflate usage.


## Personal data restrictions and privacy review

Fathom’s Terms say the service must not be used to track personal data such as full name, email address or mailing address, and reserve the right to terminate an account for intentional personal-data tracking. The current Privacy Policy describes how Fathom handles customer account information and website visitor data as a processor. Privacy laws and consent obligations vary by region, site function and the other technologies installed alongside analytics.

Do not place identifiers in URLs, event names or custom properties if they can reveal a person. Check every plugin and tag that runs on the page, not just Fathom, and document what each one collects. Review the DPA, subprocessors, cross-border processing and retention for the actual account. If the site operates in multiple jurisdictions or handles sensitive audiences, get tailored advice rather than relying on a general marketing statement.


## Cancellation and account deletion have different outcomes

Fathom’s support page says a subscription canceled from Settings and Billing remains active through the current billing period, with no further charge, and that a customer can export data before then. After the paid period ends, the provider queues sites and analytics data for deletion, which can take up to 60 days; resubscribing during that window can restore them. The same page says account deletion is immediate and permanent, with no recovery period.

The Terms use the phrase that cancellation of auto-renewal occurs immediately, while the more detailed support instructions explain that subscription access continues until the paid period ends. Read the dashboard confirmation for the account’s exact effective date. Export and download the data before canceling, and do not confuse turning off renewal with deleting the account. If deletion is intended, first confirm that the business has every report and record it needs.


## Backups, export and migration from another analytics platform

Fathom’s cancellation guide explicitly recommends exporting data before account deletion and says deletion removes access to dashboards and exports. That makes an export test more valuable than merely assuming that a report can be downloaded later. A migration also needs careful comparison because other analytics products may define users, sessions, page views, events and attribution differently.

Download a date-bounded sample from the trial and store it in the organization’s reporting archive. Verify that the export includes the fields and granularity needed by finance or product teams. Keep an independent conversion ledger for purchases or signups. If a business needs long-term retention, write a schedule that assigns an owner to export data before the final service date and check a restore or import in the destination system.


## Fathom terms and the age of a legal document

The Fathom Terms page retrieved for this review shows a last-updated date of December 21, 2021, while the current pricing and privacy pages contain newer information. The older terms discuss recurring monthly or annual charges, payment failure, suspension and user obligations. The date is worth noticing because customers should not assume that an older legal text captures every current plan detail or feature introduced later.

Before subscribing, review the terms presented during checkout and any current data-processing agreement, rather than relying on a search snippet or archived copy. Check the applicable entity, governing law, renewal rules, data handling and limitations for the specific account. Save a copy of the terms that apply at purchase. If language in the contract conflicts with a help-center explanation, ask the provider for written clarification before relying on the more favorable interpretation.


## Fathom Analytics alternatives and a fair measurement comparison

Alternatives include first-party server analytics, privacy-focused hosted dashboards, open-source tools and broader product-analytics systems. They differ in cookie behavior, event depth, identity handling, data ownership, retention, integrations and pricing. A hosted plan can reduce infrastructure work, while self-hosting shifts patching and backup responsibility to the site owner. A larger analytics suite may support more detailed funnels but carry different collection and consent obligations.

Run candidates alongside the current tool on the same pages for a representative period. Compare pageviews, visitor definitions, event counts, referrers, exports and performance impact. Test a conversion and check for duplicate events. Calculate the monthly tier across all sites and custom events. The goal is not to pick a vendor whose marketing says “privacy-first”; it is to choose a measurement design that answers business questions with an acceptable data footprint and a documented legal basis.


## Fathom Analytics SCAM review verdict: simple pricing, card trial and deliberate data exit

The official materials reviewed describe Fathom as a paid analytics service priced by page views across sites, with a seven-day trial requiring a payment card. The company publishes definitions for views and visitors, describes its site-specific cookieless signature, and explains how custom events count, how to export data and how cancellation differs from permanent account deletion. These disclosures help a buyer plan a controlled evaluation.

The sources reviewed do not substantiate a scam allegation or prove that Fathom automatically satisfies every site’s privacy obligations. Verify visitor and event counts against first-party records, set a trial-cancellation reminder, review current terms and privacy documentation, avoid personal identifiers and export data before cancellation or deletion. This is a public-source desk review, not a live installation or legal audit. Official pricing, trial, help and privacy pages were reviewed November 18, 2026; check the account’s current plan and contract before purchase.


## Features and decision criteria

- Website traffic and content analytics
- Custom events and API reporting
- Cookieless visitor-signature approach described by the provider
- Pageview-based plans and data export

## Sources and further reading

- [Fathom Analytics current pricing, pageview tiers, trial and plan FAQ](https://usefathom.com/pricing)
- [Fathom explanation of its seven-day card-required free trial](https://usefathom.com/docs/start/trials)
- [Fathom documentation for canceling, exporting and deleting account data](https://usefathom.com/docs/account/close)
- [Fathom Terms and Conditions, subscription and personal-data rules](https://usefathom.com/legal/terms)
- [Fathom Privacy Policy](https://usefathom.com/legal/privacy)
- [Fathom documentation describing its cookieless visitor-signature approach](https://usefathom.com/why-fathom-analytics/cookieless-analytics)
- [Fathom dashboard guide defining visitors, views and pageview-based billing](https://usefathom.com/docs/start/dashboard)
- [Fathom Analytics website](https://usefathom.com/)
- [saashub listing](https://www.saashub.com/fathom-analytics)

For the complete Roseram buyer guide, see [Fathom Analytics review](https://roseram.com/reviews/scams/fathom-analytics-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
