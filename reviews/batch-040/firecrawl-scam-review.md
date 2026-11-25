# Firecrawl review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Web scraping, crawling and search API for AI applications  
**Method:** Source-led desk review; no hands-on testing is claimed.

Firecrawl is an API that crawls websites and returns structured or LLM-ready page data through endpoints for scrape, crawl, map, search, interact, monitor, and agent workflows. Its credit system charges by endpoint and feature: basic scrape and crawl are priced per page, search per result batch, and browser interaction by time; some structured formats add credits. The current pricing page lists 1,000 free monthly credits and paid plans from Hobby through Scale, with optional pay-as-you-go top-ups that can be capped. Unused base credits generally do not roll over except on Scale and Enterprise. Enterprise plans can enable zero data retention. The linked privacy policy is dated December 2024, so teams should obtain current data-handling terms before sending sensitive inputs.

## Editorial verdict

The official sources reviewed identify Firecrawl as a web-data API and publish plan prices, credit accounting, terms, and a zero-data-retention option for Enterprise. They provide no source-based reason to call it a scam. This is a desk review, not a benchmark of crawl coverage or extraction accuracy. The central buyer risks are controlling usage, understanding which page responses consume credits, checking permissions for the target websites, and reconciling product documentation with the older linked privacy policy. A 403 or 404 response can still incur a credit, and Enterprise zero retention is an option that must be enabled, not a default promise for every account.

## Firecrawl turns web pages into data for search and AI workflows

Firecrawl describes itself as an API that converts websites into LLM-ready data. Its endpoint set includes scrape for a page, crawl for a site or page collection, map for URL discovery, search for finding pages, and browser interaction for actions that need a rendered session. Monitor checks pages on a schedule, while Agent combines more autonomous research behavior. These operations solve different jobs. A developer should draw the pipeline first and then choose the smallest endpoint that returns the data the application actually needs.

The introduction and product material frame the output as data to feed into applications, not as a complete answer-quality guarantee. A crawl may retrieve a page, but the downstream system still needs to decide what is current, relevant, permitted to use, and safe to show. Pages can change, block requests, or require JavaScript and authentication. Keep source URLs, retrieval time, status, and parsing rules alongside extracted text so a later answer can be traced back to its source.


## Credits are shared across endpoints, and advanced formats add cost

Firecrawl's pricing page lists 1 credit per basic scraped or crawled page and 1 credit per Map request. Search costs 2 credits for each group of 10 results; Interact costs 2 credits per browser minute. JSON, Question, and Highlight output formats add 4 credits per page, while the deterministic Monitor extraction is priced at 7 credits per page per check. The credit balance is shared, so a crawler, search layer, and monitoring schedule draw from the same monthly pool.

This structure rewards estimating calls before setting a plan. A workflow that searches, fetches results, extracts structured fields, and monitors those pages can consume several times the base scrape cost. A retry is not necessarily free: the price page says a scrape with no result is not charged, but a page returning an HTTP status such as 403 or 404 still incurs one credit. Count error responses and repeated checks in the budget. Add a hard monthly cap before enabling a scheduled job or production agent.


## Published plans combine monthly credits, concurrency and optional top-ups

The pricing page checked on November 18, 2026 lists a free plan with 1,000 credits each month and no payment card requirement. Hobby provides 5,000 credits, Standard 100,000, Growth 500,000, and Scale 1,000,000. The paid monthly rates were $19, $99, $399, and $749 respectively; annual billing showed monthly equivalents of $16, $83, $333, and $599. Each tier also changes concurrent requests and support. The annual equivalent is not the same thing as a month-to-month charge.

Paid plans may add credits in $5 increments when usage reaches zero, and the account owner can set a monthly limit or turn top-ups off. The page says included credits do not roll over for Hobby, Standard, and Growth; Scale carries one month and Enterprise has a custom rollover amount. Purchased credits remain until used but expire if the subscription is cancelled. Confirm these rules in the live billing screen before enabling automation, especially if a process can issue many requests without human review.


## The target website's access rules still matter

A scraping API makes requests easier to integrate, but it does not grant permission to collect every page or reuse every result. Firecrawl's terms require use in compliance with applicable law and incorporate provider-specific terms for data obtained from third parties. The customer should check the target site's terms, access controls, privacy notices, copyright rights, rate limitations, and any separate provider terms that apply. A public URL is not automatically a license for commercial reuse, personal-data enrichment, or redistribution.

Design a crawler to limit scope to the domains and paths needed for the job. Respect authentication boundaries and do not use the service to bypass restrictions. Store provenance and retrieval dates, avoid collecting unrelated personal information, and provide a way to delete a result when the underlying need ends. These are buyer safeguards rather than allegations about Firecrawl. The platform delivers requests; the organization using it remains responsible for selecting targets and deciding what happens to collected content.


## Zero data retention is available only with a configured Enterprise option

Firecrawl's October 2026 explanation says Enterprise customers can enable zero data retention for endpoints that handle page content, including scrape, crawl, parse, search, interact, and agent. With that setting, the service says it does not persist page content, extracted data, or search queries beyond the request lifetime. One exception is an Agent result, which remains available for 24 hours and is then deleted. The page distinguishes search modes because an upstream provider may cache an anonymized query unless the end-to-end option is selected.

This is an opt-in plan feature, not a general property of all Firecrawl accounts. The linked privacy policy currently displays a last-revised date of December 26, 2024, while the product and terms pages have newer material. That age is a reason for a business handling sensitive information to request the current privacy, security, and data-processing documents and confirm they match its Enterprise configuration. Do not treat a ZDR announcement as a substitute for checking which routes and upstream providers are covered in the signed agreement.


## Terms and billing conditions deserve attention before scaling

Firecrawl's terms of service page states that the agreement was revised in October 2026. It discusses payments through a third-party processor, plan and order-form terms, and says the company does not generally provide refunds, with an exception described for a case where it can no longer offer the service. It also says users may cancel and stop further charges after the current billing period. The terms further prohibit commercial use except where Firecrawl expressly authorizes it; a business buyer should confirm that its plan or order form authorizes the intended workflow. These are material terms for a service whose paid usage can automatically add credits in $5 increments unless an account cap or setting prevents it.

The terms also incorporate the privacy policy and may incorporate third-party data terms for provider data surfaced through the service. Those documents can change over time. Keep a copy of the terms that applied when you subscribed, disable uncapped pay-as-you-go if it is not intended, and assign an owner to review renewal, credit expiry, and provider-specific conditions. A pricing display does not answer how a specific contract or third-party data provider's rules apply to a customer's use.


## A fair Firecrawl pilot tests output quality and total credit consumption

Choose a small set of pages the organization is allowed to process. Run a basic scrape, a multi-page crawl, a Map request, and one structured extraction feature that the real application needs. Compare output against the source page and note missing tables, repeated navigation, stale content, blocked status codes, and fields that require cleanup. Save the endpoint, options, page count, credits debited, response status, and capture time. This is a proposed test; Roseram has not measured Firecrawl's coverage or parsing accuracy.

Then simulate the planned schedule and top-up behavior with a spend limit in place. Verify what happens when a page returns 403, when a page is empty, and when a crawl is retried. Check that the application handles a job that exceeds concurrency or becomes queued. If a production workflow uses Enterprise zero retention, test the exact configured endpoint and confirm the contractual setting. The successful result is a reproducible cost and data-retention profile, not simply a good-looking Markdown sample.


## Who should consider Firecrawl, and what should they compare?

Firecrawl may fit an engineering team that needs to collect web pages for a search index, research assistant, monitoring pipeline, or content-processing application. The shared credit system can simplify usage accounting across endpoints, while paid plans offer greater concurrency and optional top-ups. It may not suit a project that needs contractual zero retention but cannot buy Enterprise, cannot verify permission for the target data, or cannot control the cost of automated crawls.

Compare Firecrawl with direct site APIs, a browser automation stack, a search provider, and a self-hosted crawler. Use the same URLs, extraction fields, schedule, and error handling, then include engineering and cleanup time with API charges. Compare each provider's data retention, upstream dependencies, supported formats, rate limits, and source-attribution options. The right choice is the method that collects only permitted data, produces a verifiable result, and remains within a budget that a named owner can control.


## Features and decision criteria

- Scrape, crawl and map endpoints for extracting website pages and discovering URLs.
- Search, browser interaction, monitor and agent workflows with separate credit rules.
- Structured outputs such as JSON, questions and highlights with additional usage charges.
- Shared monthly credit balance across endpoints, plus paid-plan top-ups and spend caps.
- SDKs, API access and integrations intended for AI and data pipelines.
- Optional Enterprise zero-data-retention settings for supported endpoints.

## Pricing considerations

The public pricing page checked November 18, 2026 lists amounts in USD. A basic scrape or crawl costs 1 credit per page, Map 1 credit per call, Search 2 credits per 10 results, and Interact 2 credits per browser minute. JSON, Question, and Highlight formats add 4 credits per page; Monitor's deterministic extraction is 7 credits per page per check. Failed scrapes with no result are not charged, but an HTTP error page such as 403 or 404 still costs 1 credit. Paid plans can add credits in $5 increments and set a monthly spend cap. Hobby, Standard, and Growth monthly allowances do not roll over; Scale carries one month, Enterprise is custom. Purchased credits expire if the subscription is cancelled. Confirm live rates and the required plan before use.

## Frequently asked questions

### Is Firecrawl a scam?

The official company site and documentation describe a web-data API and publish current credit pricing, terms, and enterprise retention options. This review found no source-based reason to call Firecrawl a scam; it does not verify crawl coverage, extraction accuracy, or an individual billing record.

### How much does Firecrawl cost?

The pricing page checked November 18, 2026 lists 1,000 free monthly credits, then Hobby at $19 monthly or $16 billed annually, Standard at $99 or $83, Growth at $399 or $333, and Scale at $749 or $599. Endpoint features consume credits at different rates, and paid plans can add pay-as-you-go credits.

### Does Firecrawl charge for failed requests?

Its pricing page says a scrape that returns no result is not charged. A page that responds with an error status such as 403 or 404 is still returned and costs one credit. Check the returned result and billing record for the exact case.

### Do Firecrawl credits roll over?

The current pricing page says included credits roll over only on Scale, for one month, and Enterprise, under a custom amount. Hobby, Standard, and Growth monthly credits do not roll over. Purchased top-up credits expire if the subscription is cancelled.

### Does Firecrawl offer zero data retention?

Firecrawl says Enterprise can enable zero data retention for supported endpoints. Its October 2026 documentation says page content and extracted data are discarded after a request, except Agent results remain retrievable for 24 hours. Confirm the setting and endpoint in your agreement; it is not the standard default for every plan.


## Sources and further reading

- [Firecrawl official pricing and credit table](https://www.firecrawl.dev/pricing)
- [Firecrawl API introduction and endpoint overview](https://docs.firecrawl.dev/introduction)
- [Firecrawl terms of service, revised October 2026](https://www.firecrawl.dev/terms-of-service)
- [Firecrawl privacy policy, revision date shown on publisher page](https://www.firecrawl.dev/privacy-policy)
- [Firecrawl zero data retention announcement and endpoint scope](https://www.firecrawl.dev/blog/zero-data-retention)
- [Firecrawl Trust Center](https://trust.firecrawl.dev/)
- [Firecrawl third-party data terms](https://www.firecrawl.dev/terms/third-party-data)
- [Firecrawl website](https://www.firecrawl.dev/)
- [saashub listing](https://www.saashub.com/firecrawl)

For the complete Roseram buyer guide, see [Firecrawl review](https://roseram.com/reviews/scams/firecrawl-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
