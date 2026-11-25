# Loops.so review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** SaaS email marketing and transactional email platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

Loops is an email platform for software companies that combines campaigns, product-triggered workflows and transactional email with a shared contact model. Its server-side API and SDKs can send published transactional templates with recipient-specific variables, while event-driven workflows support lifecycle messages. A free plan allows up to 1,000 subscribed contacts and 4,000 combined marketing and transactional sends in a rolling 30-day window; paid pricing is based on subscribed-contact bands and includes unlimited sends. Loops also offers campaign and content APIs, goals and agent-facing interfaces, while its public Workflow API remains read-only for workflow editing. This desk review examines deliverability responsibilities, consent, API boundaries, pricing and operational fit.

## Editorial verdict

Loops’ official site and documentation describe an operating SaaS email product with transactional sending, marketing campaigns, lifecycle workflows, contact APIs, templates and published pricing. The official sources do not establish fraud or guarantee inbox placement, revenue or delivery to every recipient. The directory summary associated with this catalog entry does not describe the current first-party product pages, so this review uses Loops’ own sources for product identity and leaves that older listing copy out of the product assessment. This is a desk review checked November 18, 2026, not a send-volume benchmark, live account test or deliverability audit.

## Loops.so SCAM Review: identify the product before judging it

A search for “Loops.so scam” is not answered by a directory description alone. The catalog entry associated with this review contains a short line about advertising a startup on a billboard, while Loops’ current first-party pages describe an email platform for software companies. Because those descriptions do not match, this assessment follows the current official product and documentation pages and does not treat the directory snippet as a reliable account of what the service sells. The discrepancy is a reason to verify identity, not evidence of fraud.

Loops’ own materials describe marketing campaigns, event-driven lifecycle email and transactional messages sent through APIs and SDKs. The company publishes plan limits, API guidance and operational recommendations. Those sources establish a commercial product, but they do not establish that every message will reach an inbox or that a customer will earn a specific return. This is a desk review of public Loops pages checked on November 18, 2026. Roseram did not open a Loops account, configure a sending domain, send mail or measure delivery results.


## What Loops does for SaaS email

Loops combines several email jobs in one product: one-off campaigns to an audience, messages triggered by events or contact changes, and transactional email initiated by an application. Its API connects contact records and custom properties with campaign and workflow activity. The company positions the system for software businesses that want engineers to connect events while teammates edit message templates in a visual interface.

That combined approach can reduce the number of tools a small team has to connect, but it also means the organization must classify messages correctly. A password reset and a product announcement have different purposes and obligations. A welcome sequence may be lifecycle marketing even if it begins after signup. Before importing a contact or triggering a send, define why the recipient should receive that message and which consent or unsubscribe state applies. Consolidating the platform does not consolidate the legal or operational responsibility away.


## Transactional email API and templates

The documented transactional workflow has a clear shape: verify the sending domain, create and publish a template in Loops, obtain its transactional ID, and call the API from the server with the recipient and required data variables. Loops provides typed SDKs and examples, while a visual editor lets a teammate adjust copy without rebuilding an HTML template in application code. The same template is identified by its stable transactional ID and can be reviewed in the Loops workspace.

A clean example is a password reset: the application validates the request, creates a short-lived reset link, then passes only the recipient address and the required link variable to a server-side send helper. The developer should not expose the API key in browser code. Validate the values, ensure all required template variables are present, and make a clear distinction between account-critical messages and promotional content. A published email that has a missing variable or incorrect URL can fail even if the API integration itself responds successfully.


## Campaigns, workflows, Goals and code APIs

Loops documents campaigns for a one-time send to an audience or segment and workflows for messages triggered by product events, timers or contact-property changes. Its 2026 Content API announcement says campaign drafts can be created or updated from code and then opened in the same visual editor for review. The company also describes Goals for measuring a selected conversion event over a defined audience and time window, which moves analysis beyond the open and click counts alone.

The API boundary is important: Loops says the public Workflow API can list and inspect workflows, but creating, editing and publishing workflows from code is not available through that API. Events can start an existing workflow, but that is different from programmatically building the automation itself. A team considering agent-driven marketing should map which steps the API performs, which steps still require an editor or human approval, and how campaign publication is controlled. Do not assume that an API mentioned on a product page can manage every part of the campaign lifecycle.


## Loops pricing: subscribed contacts and send limits

On November 18, 2026, Loops’ public pricing page showed Free at $0 for up to 1,000 subscribed contacts, with 4,000 combined marketing and transactional sends to the first 1,000 contacts in any rolling 30-day period. The free plan allows unlimited contact storage and lists all features, while adding a small Loops footer to outgoing email. A paid example is $49 per month for 1,001–5,000 subscribed contacts, $99 for 5,001–10,000, $149 for 10,001–15,000 and $199 for 15,001–25,000.

The paid tiers are priced by subscribed contacts and the public page says paid plans include unlimited sends for marketing and transactional messages. That can make monthly send volume easier to forecast, but subscriber counts still matter: a large imported database is not automatically a list of eligible subscribers. Before a migration, count subscribed and unsubscribed contacts separately, understand how Loops defines the billable subscriber, and compare the price bracket with your expected growth. Recheck pricing before making a budget because contact thresholds and plan details can change.


## Sending domains and deliverability responsibilities

Loops’ product material describes managed sending infrastructure, domain records and bounce handling. Its deliverability guidance still assigns work to the sender: configure domain authentication such as SPF and DKIM, publish and monitor DMARC, manage recipient consent and content, process feedback, and avoid patterns that create complaints. Authentication shows that the domain is authorized to send; it does not make a message wanted or guarantee where a mailbox places it.

A responsible launch should warm a new sending domain deliberately, keep account-critical mail from being disrupted by a promotional campaign where stream controls are available, and monitor bounces and complaints. Keep consent and suppression information consistent between the application and email platform. Monitor latency, webhook processing and failures rather than treating a successful API response as proof of inbox delivery. Loops’ operational pages make clear that mailbox providers still determine inbox placement, so anyone promising guaranteed deliverability would be describing more than the sources support.


## Retries, idempotency and duplicate-send risk

Loops documents idempotency support for transactional sends and advises using a stable key with the same payload when retrying an uncertain request. Its guidance says the documented duplicate-detection window is 24 hours and that reusing a key can return a 409 Conflict. That response should be reconciled against the original key, payload and send status. Generating a new key just to force the request through can turn a timeout into a duplicate receipt or other repeated message.

The application should persist the business event ID and idempotency key, retry temporary failures with backoff, and correct authentication or validation errors before trying again. If a provider response is ambiguous, check the delivery record and webhook before switching to another provider. A fallback service needs equivalent templates, authentication, suppression state and event mappings. These safeguards matter especially for receipts, security notifications and billing messages, where duplicate or missing emails can create confusion even though the underlying payment or account action happened once.


## Consent, unsubscribe and message classification

The same platform can send marketing and transactional email, but the audience rules are not interchangeable. Loops’ own guidance distinguishes messages needed to complete an account request from campaigns sent to a list. It says that transactional sends do not automatically add a recipient to the audience unless the request explicitly enables that behavior. Its guidance also notes that double opt-in controls campaigns and workflows rather than account-critical transactional messages, subject to delivery suppressions.

This distinction prevents a common mistake: treating any message triggered by a user action as transactional. A promotional onboarding sequence, an upgrade pitch or a general product update may still be marketing or lifecycle email and need the appropriate permission and unsubscribe path. Keep a record of how each address was collected, what the person agreed to receive, and how a preference change flows into Loops. Apply the laws for the sender and recipient rather than assuming that a single API flag defines the legal classification.


## Contact data, API keys and integrations

Loops documents a shared contact API with custom properties and lists, along with integrations for products such as Stripe, Clerk and Supabase. A shared contact model can save duplicate synchronization work, but it also concentrates information in the account. Define which fields are necessary, who may update them, and which system is authoritative for consent, account status and suppression. Keep private keys in the server environment and give each integration only the access it needs.

The public API page says Loops API calls belong on the server because the API key must remain private; browser calls are not supported. It also lists a rate limit of 10 requests per second per team and says excess requests receive HTTP 429, with exponential backoff advised. A sudden event burst can therefore need a queue or rate-aware job rather than a tight retry loop. Test validation, rate limiting and webhook processing before sending an important launch message.


## Reporting and what email metrics can prove

Loops lists delivery, open, click, bounce, complaint and unsubscribe events among the data available through its product. Goals add the option to define a conversion event and measurement window for a selected audience. This can help a team evaluate whether an email was associated with a useful outcome rather than judging every campaign by a click. It is still necessary to choose an appropriate baseline and understand how attribution is defined.

An open does not prove a person read a message, a click does not prove a sale, and a conversion after a campaign does not by itself prove the campaign caused it. Use a documented experiment or a cautious comparison, account for holdouts where appropriate, and include unsubscribes and complaints when reviewing performance. Check that product events are emitted consistently and that the conversion window fits the business. The sources describe measurement features; they do not certify a particular campaign’s return or attribution quality.


## Email design and team workflow

A shared visual editor and code-based content tools can help engineering and marketing work from the same message rather than maintaining separate HTML copies. Loops’ announcement describes LMX as a way for code and the visual editor to map to one email artifact, and the API can place drafts into the Loops workspace for review. This may make copy changes and template feedback easier to manage without requiring a deploy for every text correction.

The team still needs review rules. Decide who can edit a transactional template, who approves copy, which branch owns the source, and how a published version is rolled back if a variable or link is wrong. Test messages with long names, missing optional values, dark mode and mobile widths. A good preview can hide problems that appear in a real mailbox or on a narrow screen. Maintain an explicit contract between the application payload and each published template so a copy edit cannot silently break a required variable.


## Limitations and trade-offs

Loops is designed to combine email operations, but not every control is API-driven. Its public Workflow API is currently read-only for listing and inspecting workflow structure; editing and publishing workflows through that API is not available. The free plan’s send quota applies to both marketing and transactional email together and to the first 1,000 contacts. The current price model follows subscribed contacts, so keeping large lists of eligible subscribers can become the central cost driver even when sends are unlimited on paid tiers.

Deliverability is also a shared responsibility, not a switch. Teams need domain authentication, content and consent practices, suppression handling and monitoring. A transactional API call can be retried safely only if the application persists an idempotency key and reconciles ambiguous outcomes. The sources reviewed do not establish guaranteed inbox placement, a benchmark against competitors, or that the product’s current feature set meets a regulated organization’s procurement requirements. Ask for the documentation and contract terms that match your use case.


## Loops alternatives and how to compare them

A transactional-only email API can be simpler when the application sends just password resets, receipts and alerts. A newsletter product may be sufficient when the organization does not need product-triggered or account-level messages. A larger marketing automation suite can fit procurement, multiple brands or custom reporting better. Loops positions itself between these needs by combining campaigns, workflows and transactional sending in one contact and event model.

Compare providers using the same test: one password reset, one campaign to a consented test group, one event-triggered lifecycle message and one unsubscribe. Check API security, template variables, domain setup, bounce and complaint suppression, webhooks, idempotency, rate limits and data export. Calculate pricing from subscribed contacts and actual send limits, then include engineering work and the time needed to monitor delivery. Do not choose solely from a free-tier send quota or a provider’s own claim about how it compares with competitors.


## Who should consider Loops?

Loops is worth evaluating for a software company that wants a shared place for developer-triggered account emails, lifecycle workflows and marketing campaigns. It appears most useful when a team can manage sending-domain setup, consent and message data contracts, and values visual template editing alongside APIs. The published contact tiers and paid send policy make it possible to estimate costs using a known subscribed-audience size.

A different provider type may fit better if you need only a transactional endpoint, want a specialized newsletter workflow, require a particular compliance contract, or have strict controls for multi-brand governance. Teams that cannot protect API keys or maintain consent and suppression data should resolve those fundamentals before sending. If your workflow depends on programmatically editing and publishing automations, note the documented public Workflow API limitation and verify whether an interface-based process is acceptable.


## Loops buyer checklist

Before migration, reconcile your subscribed, unsubscribed and suppressed contacts. Model the published plan by subscribed contacts, confirm the free-tier rolling send cap or the paid tier, and verify whether the free footer is acceptable. Authenticate a test domain, publish a transactional template and send a message with real-looking but safe sample data. Check every variable, host, From address and webhook before using a production list.

Then exercise missing required variables, an invalid API key, a 429 rate limit, a timeout followed by an idempotent retry, and an unsubscribe event. Confirm that a transactional message does not accidentally enroll a user in marketing and that campaign preferences update the source of truth. Assign owners for failed account-critical messages and complaint monitoring. These checks help determine whether the platform fits your operations; they are not claims that Roseram ran the tests.


## Is Loops.so worth it?

Loops presents a coherent email workflow for SaaS teams: campaigns, transactional templates, event-driven sequences, API access and shared contact data. The free plan is concrete and the contact-based paid tiers are published. The API documentation includes the kind of operational detail that matters in production, including server-side key handling, rate limiting, retry guidance and webhook events. Its common editor can be useful when both developers and non-engineers need to work on the same message.

The service is not a promise of inbox placement, compliant consent or increased revenue. Teams still own domain configuration, suppression state, message classification, list quality, API security and campaign measurement. Also, not every workflow operation is available through the public API. A buyer should test one transactional path and one marketing path in a controlled environment, then decide from its own reliability and cost needs. The directory summary is not sufficient product evidence; the first-party pages provide the clearer basis for evaluation.


## Final Loops.so assessment

The official sources reviewed describe Loops as a real email platform that combines marketing, lifecycle and transactional email. On November 18, 2026, its public pricing listed a free allowance of up to 1,000 subscribed contacts and 4,000 combined sends per rolling 30 days, followed by paid contact-based plans with unlimited sends. Its developer materials describe published templates, server-side API calls, webhooks and 10 requests per second per team, with temporary over-limit responses requiring backoff.

The source record’s older billboard wording does not describe the current email product and should not be used as evidence about its capabilities. No fraud finding, inbox guarantee or Roseram test is supported here. A team should verify pricing, authenticate a domain, protect its keys, test idempotent retries and maintain consent and suppression records before sending. A Roseram workspace can help prepare a migration checklist, but it does not operate Loops or validate delivery.


## Features and decision criteria

- Marketing campaigns and audience segmentation
- Server-side transactional email API and typed SDKs
- Event-triggered lifecycle workflows with timers and branches
- Visual email templates with dynamic data variables
- Contacts, custom properties, lists and integration APIs
- Delivery, bounce, complaint and unsubscribe webhooks
- Campaign API, Goals and LMX content workflows

## Pricing considerations

Pricing checked November 18, 2026. Loops states its pricing is based on subscribed contacts, not email-send volume, and says paid plans include unlimited marketing and transactional sends. The Free plan allows unlimited stored contacts but caps sends to the first 1,000 contacts at 4,000 in any rolling 30-day window. Confirm the subscribed-contact definition, selected tier, current limits, branding and contract terms on the pricing page before importing or mailing a large audience.

## Frequently asked questions

### Is Loops.so a scam?

Loops’ official pages describe an email platform with published product documentation and pricing. The sources reviewed do not establish fraud. The SCAM Review title is a buyer due-diligence search, not an allegation or endorsement.

### How much does Loops cost?

On November 18, 2026, the public page listed Free at $0 for up to 1,000 subscribed contacts and 4,000 combined sends per rolling 30-day window; published paid examples included $49 monthly for 1,001–5,000 contacts, $99 for 5,001–10,000 and $199 for 15,001–25,000. Paid plans list unlimited sends. Confirm current subscriber counts and terms.

### Can Loops send both transactional and marketing email?

Yes. Loops documents campaign, lifecycle and transactional email capabilities that share contacts and events. Transactional sending uses a published template and a server-side API call; marketing email requires appropriate audience and unsubscribe handling.

### Can I call Loops from a browser?

Loops says its API calls should remain on your server so the API key stays private. The server endpoint should still enforce access controls and validate recipients and data.

### Does Loops guarantee that email reaches inboxes?

No. Loops documents sending infrastructure, domain authentication and bounce handling, but says inbox placement is decided by receiving mailboxes and depends on factors such as authentication, complaints, bounces, sending patterns and engagement.

### Has Roseram tested Loops?

No. This is a desk review of Loops’ public product, pricing, API and operational guidance. Roseram did not send a campaign, verify a sending domain or measure inbox placement.


## Sources and further reading

- [Loops email platform and API overview](https://loops.so/email-api)
- [Loops official pricing by subscribed-contact bracket](https://loops.so/pricing)
- [Loops transactional email service and free-tier terms](https://loops.so/transactional-email)
- [Loops Content API, campaign, transactional and Workflow API status](https://loops.so/changelog/content-api-goals)
- [Loops transactional email reliability, idempotency and consent guidance](https://loops.so/resources/transactional-email-best-practices)
- [Loops official documentation index](https://loops.so/docs)
- [saashub listing](https://www.saashub.com/loops-so)
- [Loops.so website](https://loops.so/)

For the complete Roseram buyer guide, see [Loops.so review](https://roseram.com/reviews/scams/loops-so-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
