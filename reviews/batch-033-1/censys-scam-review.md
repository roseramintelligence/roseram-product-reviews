# Censys review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Internet asset discovery and security research  
**Method:** Source-led desk review; no hands-on testing is claimed.

Censys is an internet intelligence platform used to search information about hosts, certificates and web properties, with separate free, Starter and enterprise tiers. Its credit model deserves a close read: a Free account receives 100 monthly credits that expire at month end, while searches, asset lookups, result pages, filters and reports can each consume credits. Free and Starter users also receive five no-credit actions each day. The current Starter options are $79/month for 500 credits and $599/month for 4,000 credits, with a one-month rollover; enterprise Search and Core plans require a sales quote. Plan tier affects data visibility, history, result limits and API access, so a low price is not a substitute for checking whether the fields you need are searchable. Censys’s AI Query Assistant sends the user’s prompt and generated query to OpenAI, while the vendor says it has opted those inputs out of model improvement and offers privacy settings. The sources reviewed do not substantiate fraud. Roseram did not run queries, audit data coverage or test an account.

## Editorial verdict

The evidence supports reviewing Censys as a specialized internet-asset intelligence service, not treating it as a fraud finding. The platform can help security teams investigate exposed services and certificates, but the cost is tied to the actions a user performs and the visibility their tier unlocks. On Free and Starter, even opening more result pages and adding filters can consume credits; enterprise plans separate the largely unlimited UI from API credit use. A buyer should estimate a representative investigation, including lookups, result pagination and reports, then compare that total against the Free allowance or paid allotment. Current Starter plans are $79 for 500 credits and $599 for 4,000, with one-month rollover; Free credits expire monthly. Enterprise pricing is sales-led. Before using the AI query helper, decide whether sending prompts to OpenAI is acceptable for your workflow and review the account privacy settings. Censys’s tier documentation also shows meaningful differences in host history, protocols, CVE data and result depth. Roseram did not verify scan completeness, run tests or assess a specific security program. The reviewed sources do not establish fraud.

## Censys is for searching internet-facing assets

Censys describes its Platform as a searchable view of internet hosts, certificates, web properties and related security data. Teams use that material to investigate exposed services, triage alerts and understand what infrastructure appears reachable from outside. This is a specialized security-research product, not a general web analytics service or a replacement for an organization’s internal asset inventory.

The practical question is whether the records and fields it exposes answer a defined investigation. Write down a task such as checking a known public IP, identifying certificates associated with a domain, or researching an internet-visible service. Then confirm that the correct asset type, protocol and history are available at the tier you plan to use.


## The Free plan is useful for orientation, with firm limits

Censys documentation says Free accounts receive 100 credits per month, basic protocol and certificate visibility, and limited web-property data. A Free search is limited to one page of 100 results. The monthly credits expire at the end of the month; five additional Platform actions per day are described separately as free actions for Free and Starter users.

That makes Free suitable for learning the search interface and checking whether a data source is relevant to a small task. It is not the right basis for assuming that an investigation can enumerate a large result set or access every protocol. Review the tier matrix before you build a workflow around a field that might be locked.


## Understand the credit meter before you explore deeply

For Free and Starter accounts, the documentation says common Platform actions cost one credit: running a search, opening an asset, loading another results page, adding a filter, or running a report. The five no-credit daily actions help, but they do not replace the monthly balance for repeated work. Credit depletion restricts credit-consuming actions until the next allocation or a plan change.

A seemingly small investigation can therefore involve several billable actions. One search, several pages of results, a detail lookup and a report are separate steps in the meter described by Censys. Before a team adopts the product, reproduce a normal investigation and record the action count. That usage sample is more informative than counting only the initial query.


## Starter plans differ by credit volume and entitlements

The current Starter documentation lists Starter at $79 per month with 500 credits and Starter Pro at $599 with 4,000. Both receive five free Platform actions each day. The page says the Pro tier includes more tags and collections. A Starter plan also unlocks broader API endpoints than Free, while the data-access table still imposes protocol, result and historical-data limits.

The credit allotment is only one part of the purchase. Starter subscriptions have a one-month rollover: credits are effectively valid for two months after they are added, then unused credits expire. Confirm the billing-cycle allocation date and rollover in the account rather than treating a static plan comparison as a live balance.


## A result cap can matter as much as the monthly credit total

Censys says Starter searches are limited to 500 results per query, with 100 results shown per page. Free is limited to one 100-result page. Enterprise Search and Core tiers allow unlimited paginated results according to the tier documentation. If your task depends on broad enumeration, a large credit balance does not necessarily remove the result ceiling attached to the plan.

For a buyer, the distinction is simple: credits count actions, while result caps limit how much a query can return. Estimate both. Check whether your work requires CSV export, additional pages, longer host history or access to advanced protocols. The feature matrix identifies several of these as tier differences, so validate them before you rely on an export or automation.


## Free, Starter, Search and Core are not just price bands

The tier table shows distinct data entitlements. Free has basic protocols and one result page. Starter adds features such as regex search and seven days of host history, while the Search and Core enterprise offerings provide broader protocol data and at least 31 days of host history. Other fields—such as CVE data, threat data, deep-application scans, reputation information and web screenshots—vary by tier or add-on.

The words “Search” and “Core” refer to Censys enterprise offerings, not ordinary labels for a search bar. The vendor’s documentation says Censys Search does not include vulnerability data and threat-data search, while Core includes some additional capabilities and may require Adversary Investigation or Critical Infrastructure modules for more. Compare the precise entitlement table with your use case rather than assuming the more expensive plan includes every dataset.


## Enterprise pricing is a sales conversation

Censys’s public pricing page directs organizations to contact sales for Core, Adversary Investigation and Security Operations packages. It lists plan highlights such as user counts, API calls, data history, collections and security features, but it does not publish a comparable enterprise price. The quote and contract therefore become part of the diligence process.

Ask for the included monthly credits, overage or additional-credit terms, historical-data window, user count, module availability, API access role, support level and renewal conditions. Also ask which parts of the proposal are optional add-ons. A demo helps explain the interface; it does not replace a written quote with the exact entitlements your organization will buy.


## The API is tiered and credentials need protection

Censys’s API documentation says endpoint access varies by plan. Free has lookup endpoints; Starter adds Global Data and Collections endpoints other than Live Rescan; Search and Core have broader endpoints, with some additional modules required. Organization users on paid tiers need the API Access role. Calls consume credits, and concurrency limits differ between Free/Starter and enterprise tiers.

The API guide warns that Personal Access Tokens grant significant access and should never be exposed in public repositories or client-side code. Store tokens in a server-side secret manager, use separate service credentials where the plan supports them, and revoke keys that are no longer needed. If you expect automated use, model the credit cost and concurrency before deployment.


## The AI Query Assistant has a specific data path

Censys says its Query Assistant turns natural-language requests into editable CenQL queries. Generating a proposed query does not consume credits; clicking Search does. The documentation also says prompt input and the generated query are shared with OpenAI, and that Censys has opted this data out of being used to improve OpenAI models. Users can adjust personal or organization privacy settings.

That disclosure should be part of the security review. Do not put credentials, private incident notes or customer information into the assistant unless your organization permits that processing. Test it with a generic query first, inspect the generated syntax, and run it only after confirming that the target fields are available in your tier. The assistant’s natural-language output is a draft query, not an independent security conclusion.


## Censys data should complement internal asset ownership

An outside-in platform can surface infrastructure and certificates that are useful leads for an investigation. A public record does not by itself prove that a host belongs to your organization, is vulnerable, or is currently exploitable. Ownership, business purpose and remediation priority still require internal context and, where appropriate, validation by the asset owner.

Create a process that records the search date, query, relevant asset identifiers and internal owner. Validate important findings through an authorized channel before taking action. Keep scanning and testing within the scope your organization is allowed to assess. This avoids turning an internet observation into an unsupported vulnerability claim or an unauthorized test.


## Use the same investigation to compare alternatives

Compare Censys with your existing cloud inventory, an external attack-surface management product, a threat-intelligence subscription or a manual certificate and DNS workflow. Use the same domain or public IP set and write down what each can discover, how often it refreshes, which fields are searchable, what export is available and what an analyst must verify manually.

The right comparison is not simply which dashboard looks richer. Include the recurring analyst time, credit usage, API limitations, extra modules and time needed to confirm asset ownership. If an existing security platform already provides the required data with appropriate history and integration, a separate subscription may add little. If a specific Censys dataset closes a documented gap, value it against that gap.


## A small trial can reveal whether the credit model fits

Use the Free tier to test one representative query, then count every search, page, filter, lookup and report. Record which data fields appear locked and whether the result cap is sufficient. If the workflow needs several hundred assets, determine how many lookups or pages that entails before choosing Starter or Starter Pro.

For an API use case, run a small sample with a server-side token, confirm the organization ID and access role, observe credit consumption, and simulate a revoked token or rate limit. For the AI assistant, use non-sensitive prompt text and verify the generated CenQL. Keep this test separate from any live remediation action until the asset owner confirms scope.


## Check what happens when a Starter plan ends

Censys says a Starter subscription can be canceled at any time in the Platform billing page. The help material says features and credits remain until the next billing cycle starts; collections are archived, and tags remain visible but become non-editable. Users can continue with a Free account or subscribe again later.

Before canceling, decide whether collections are part of an ongoing monitoring process and export or document any work your team must retain. Check the current account screen for the exact renewal date and any current changes to this behavior. The downgrade from Starter Pro is described as canceling Pro and resubscribing at Starter after the paid term ends.


## Who may find Censys useful

A security analyst, threat researcher or infrastructure team that needs a searchable outside-in view of hosts, certificates and services may find Censys useful. The Free plan can help evaluate basic records; Starter adds deeper access and API search; enterprise tiers target teams with requirements for broader history, data, collaborators or monitoring.

The fit is strongest when the buyer can name an investigation workflow, a data field and an action that follows the result. A plan purchased merely because a vendor advertises comprehensive visibility is harder to evaluate. Define the first two or three questions your analysts need answered, then check whether the corresponding data is available and affordable.


## Who should pause before upgrading

A casual user who only needs occasional checks may be served by the Free allowance, especially if one page of 100 results is enough. A team expecting unlimited searches from a $79 Starter subscription should pause: that plan has 500 monthly credits, and many UI and API actions consume them. A buyer who needs CSV export, long result pagination or particular threat and vulnerability data must check enterprise entitlements.

Organizations with strict rules about sending prompts to third-party AI services should review the Query Assistant privacy settings before enabling it. Teams that cannot protect API credentials or confirm who owns a public asset should postpone automation until their access-control process is ready. The platform is a research tool; it does not substitute for incident response, asset-owner confirmation or a tested remediation procedure.


## The purchase checklist

Confirm the data tier, exact field availability, result cap, page depth and host-history window. Estimate credits using a real investigation, including filters and asset detail lookups. Compare the 100 Free credits, $79 Starter allotment and $599 Starter Pro allotment, including their different expiration rules. For enterprise, obtain a written list of modules, credits, users, API use and renewal terms.

Review API roles and token storage, the Query Assistant’s OpenAI processing, data retention and collection behavior after cancellation. Use a non-sensitive test and verify one finding with the asset owner. If those checks produce a useful result at an acceptable cost, move forward with a documented use case rather than treating a plan tier as a guarantee of coverage.


## The evidence-based conclusion

Censys offers a technically specific product with tiered internet data, API access, credit billing and self-service Starter plans. Its documentation is unusually clear about how common actions consume credits, how Free differs from Starter and how a subscription cancellation changes collections and tags. The main buyer risk is purchasing a tier without understanding the data and action limits that govern the real workflow.

The official sources reviewed do not substantiate fraud. This SCAM Review is a buyer-check format, not an accusation or legal finding. Roseram did not create an account, run a query, validate scan coverage or audit data handling. Evaluate the current documentation and quote against a small, authorized test before depending on Censys for a security decision.


## Features and decision criteria

- Search internet-facing host, certificate and web-property records, with data access depending on tier
- Use CenQL and a natural-language Query Assistant to build editable searches
- Save and monitor query results in collections; Starter and enterprise tiers offer different limits
- Use plan-dependent Platform API endpoints and credit balances for programmatic lookup and search
- Choose Free, self-service Starter or sales-quoted enterprise Search/Core plans

## Pricing considerations

Official documentation and release notes checked November 18, 2026. The Starter subscription page lists $79/month for 500 credits and $599/month for 4,000. It describes a one-month rollover; unused Starter credits expire at the end of that rollover period. Free users receive 100 credits monthly, which expire at month end. Five free Platform actions per day are separate from that monthly credit allotment. Enterprise Search/Core pricing is quote-based. Verify current prices, data entitlements, renewal and cancellation details in the Platform billing screen before purchase.

## Frequently asked questions

### Is Censys a scam?

The official sources reviewed describe an internet asset intelligence platform, tiered subscriptions, credit accounting and API documentation. They do not substantiate fraud. SCAM Review is a buyer-diligence label, not a legal finding. Roseram did not test the platform or independently audit its data.

### How much does Censys cost?

The current Starter documentation lists $79/month for 500 credits and $599/month for 4,000 credits. The Free tier includes 100 monthly credits, and enterprise Search/Core pricing requires contacting sales. Verify the billing screen and tier-specific features before subscribing.

### What uses Censys credits?

For Free and Starter users, searches, asset lookups, opening additional result pages, adding filters and running reports can each use credits. The docs list one credit for common actions. Five free UI/API actions per day are separate from the monthly credit balance.

### Do Censys credits roll over?

Free-tier monthly credits expire at the end of the month. Starter subscription credits have a one-month rollover, meaning they can remain valid for two months after allocation; any unused amount then expires. Check the current billing page for your allocation date and balance.

### Does Censys send AI search prompts to OpenAI?

Censys’s Query Assistant documentation says prompt input and the generated query are shared with OpenAI, and that Censys has opted this data out of model improvement. It also describes personal and organization privacy controls. Avoid entering sensitive information unless your policy permits it.

### Can I use Censys for all internet-security investigations on the free plan?

No. The Free tier has basic data visibility, limited API endpoints and one page of 100 results. Starter and enterprise plans unlock additional data, history, results and API features. Check the exact fields, protocol data and maximum result depth your investigation requires.


## Sources and further reading

- [Censys Starter subscription prices, credits, rollover and cancellation](https://docs.censys.com/docs/platform-starter-subscriptions)
- [Censys credit costs and monthly allocation for Free and Starter](https://docs.censys.com/docs/platform-credits-free-starter)
- [Censys feature and data access tiers](https://docs.censys.com/docs/data-access-tiers-entitlements)
- [Censys Platform release notes: credit model and Starter plans](https://docs.censys.com/changelog)
- [Censys API access, authentication and endpoint entitlements](https://docs.censys.com/reference/get-started)
- [Censys Query Assistant: prompt processing and privacy controls](https://docs.censys.com/docs/platform-query-assistant)
- [Censys enterprise pricing and plan overview](https://censys.com/resources/pricing/)
- [Censys website](https://censys.com/)
- [saashub listing](https://www.saashub.com/censys)

For the complete Roseram buyer guide, see [Censys review](https://roseram.com/reviews/scams/censys-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
