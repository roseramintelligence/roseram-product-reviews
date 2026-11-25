# CometAPI review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Multi-provider AI model API gateway  
**Method:** Source-led desk review; no hands-on testing is claimed.

CometAPI is a commercial gateway that offers access to third-party language, image, video and audio models through a shared API and account. Its documentation describes an OpenAI SDK-compatible base URL for common requests, while the company advertises centralized model access, billing and usage views. Pricing is presented as usage-based prepaid credits, with model-specific rates and a stated discount against official provider prices. The gateway does not eliminate the need to evaluate each underlying provider or confirm that an endpoint behaves as expected.

## Editorial verdict

CometAPI publishes product, API, pricing, terms, privacy and trust-center materials for an identifiable AI gateway. Those sources do not establish that the service is a scam. They do establish practical diligence questions: verify model identifiers and equivalent unit prices, understand prepaid-credit and discretionary refund terms, and follow prompts through to the selected model provider. The Trust Center says formal security certifications have not yet been initiated and describes the 99.9% figure as a target. This is a source-based desk review, not a firsthand account, audit or performance test.

## CometAPI review: an access layer, not a model developer

CometAPI presents itself as an aggregation layer for third-party model APIs. The company describes a single account and interface for language, image, video and audio services, with a model catalog, usage dashboard and centralized payment balance. For a developer who wants to experiment across providers, this can reduce initial integration work: the documentation shows an OpenAI SDK-style request in which a client uses CometAPI's base URL and account key. The service is still an intermediary. The selected model provider receives the request needed to generate an answer, and that provider's capability and terms remain part of the transaction.

That distinction matters to product design and purchasing. A shared API does not make underlying models identical, guarantee that every model has the same endpoint features, or ensure that a model name will remain unchanged. Tool calls, JSON output, image inputs, safety settings, context limits and streaming can vary. A team should regard CometAPI as a routing and billing choice, then validate each exact model identifier and response behavior for its intended tasks. The catalog is evidence that the company lists a model; it is not by itself a benchmark, guarantee of availability, or proof that a particular output will meet a business requirement.


## CometAPI pricing: compare equivalent units before believing a discount

The live pricing page describes usage-based billing without a monthly subscription and says its official-model prices are set below the respective official pricing. It presents a billing framework where some text offerings are charged by token, while specialty modalities are billed per image, clip, second or another endpoint unit. The same page has a model table, budget estimator and direct-versus-Comet comparison. This is more useful than a single undifferentiated rate, but each model's exact unit and SKU still have to be checked before a budget is approved.

A discount claim can only be compared meaningfully when the two prices refer to the same model release, region, input and output units, quality setting, modality, context or duration, and provider's official rate at the same date. A rate expressed per million tokens is not directly comparable with an image price, and a model alias may hide a different endpoint or variant. Select a representative workload, write down its token or media units, and recreate the estimate from the current SKU table. Treat a calculator as a forecast, not an invoice: retries, longer outputs, larger prompts, taxes, exchange rates and policy changes can alter actual spend.

The service should be evaluated on total cost per accepted result, not only on a percentage badge. A cheaper unit may still cost more in practice if a model takes multiple correction turns, has a lower usable limit, requires a longer prompt, or creates extra engineering work. Conversely, one account, key and bill can save procurement and reconciliation time even where raw per-call savings are modest. Ask the vendor to identify the unit that appears in usage records and verify whether the cost estimate and billing ledger use the same definition. Keep a sample invoice beside request-level measurements before increasing production volume.


## Prepaid credits, auto-reload and the refund boundary

CometAPI's terms describe prepaid credits for usage-based requests, say the credits are not cash or transferable property, and state that purchased credits do not expire while an account remains in good standing. The terms also allow credit revocation or adjustment for fraud, abuse, technical error or a terms violation. Automatic reload is available and authorizes a payment processor to charge the selected method when a balance crosses a configured threshold or other setting. These are material billing details: a gateway balance is a service entitlement, not a bank balance that can be freely withdrawn.

The refund terms distinguish used from unused credit. Consumed requests, compute or outputs are generally non-refundable; unused credits may be eligible only after a written request and CometAPI's review and approval. That makes the amount and threshold of any auto-reload especially important. Begin with a small balance, set a conservative maximum and alert, and disable auto-reload until billing records reconcile with a known request. Confirm how failed or incomplete generations are charged, which units consume credits and how a dispute must be raised. The terms ask customers to report billing errors within 30 days, so preserve request IDs and invoices rather than relying on a dashboard screenshot.

Do not put an unbounded shared key into a public application or a local script that might be checked into Git. Use server-side credentials, environment-specific keys, access controls and usage limits. Separate development from production balances where possible. For a team, decide who can create keys, change reload settings and buy credits. These practices reduce exposure to accidental charges or abuse; they do not replace the provider's account protections or guarantee that a compromised key can be recovered without cost.


## API compatibility and model-specific behavior

The developer documentation shows how to use the OpenAI SDK format with a CometAPI base URL and account key for chat completions. It also describes model lists, cost estimation, polling or webhooks, errors, retries and rate limits. This can make a prototype easier to port from a compatible client. Compatibility should be interpreted narrowly: a request that uses a familiar schema may still have model-specific limitations, response fields, errors or feature support. The documentation directs developers to check model and provider differences rather than assume the endpoint is a substitute for every vendor capability.

Before building around the compatibility claim, test the exact operations the product needs. That may include streaming, tool calls, structured output, image or audio input, maximum context, finish reasons, error payloads and whether a model supports a required system instruction. Keep a compact regression suite with representative requests and known expected properties. A successful short text prompt is not enough to approve a production migration. Capture the model ID, gateway endpoint, request parameters and observed output metadata so that a later SKU change can be detected and reviewed.

The company documents fallback and routing options as part of its broader product. A fallback can improve continuity only if the alternate model is approved for the same data and use case and produces an acceptable result. Design fallback as an explicit policy: define which errors trigger a switch, whether the second request incurs a charge, how duplicate generation is prevented, and how a user is told that another provider handled the task. Avoid silent fallback for regulated or high-impact workflows where model identity and geographic processing affect the decision. Test rate limits and provider outage behavior before making a reliability claim in your own product.


## Catalog coverage, changing inventory and availability

The pricing and model pages advertise a catalog spanning multiple companies and media types. Aggregation is useful for discovery, but a large count is not a stable product contract. The relevant questions for an engineering team are whether its required model is available in the account's region, whether an endpoint is generally available or marked preview, what its current request limits are, and how the service communicates deprecation or replacement. A model in a catalogue can be altered or removed by its underlying provider, by the gateway, or through contractual restrictions.

Pin the exact model identifier in application configuration and maintain an allowlist of endpoints that have passed evaluation. Subscribe to change notices and monitor both the provider's status and CometAPI's status page. If model quality or latency is central to a feature, retain reproducible test prompts and measure results against a baseline before switching. A display name may not preserve a particular release. The gateway can centralize access, but the customer still owns the consequences of model selection, prompt design, data authorization and output review.

The dashboard's request counts, token use, latency and cost breakdown can help with attribution. Validate those figures against your own logs for a controlled set of calls. Look for duplicate submissions, streaming disconnects, partial responses and asynchronous job states that may not be obvious from a high-level monthly total. Establish a reconciliation interval and alert when usage deviates from expected traffic. If an account has several keys or environments, verify that the dashboard can separate them in the way your finance and security teams need. Analytics are useful only when their definitions and collection scope are understood.


## Privacy: prompts pass through to the selected model provider

CometAPI's privacy policy states that the company does not collect or store prompts, inputs, outputs or conversation content. Its terms allow limited technical logs such as IP addresses, timestamps and request frequency for security, compliance and optimization purposes. The company also explains on its about page that requests are routed to the selected model provider, which necessarily receives the content required to produce an answer. That is the central privacy fact: a claim that the gateway does not persist request content is not a claim that the entire processing chain never sees it.

Every selected model provider may have its own retention, training, abuse-monitoring, subprocessor and regional-processing terms. Before sending source code, personal data, customer records or confidential business information, identify the exact underlying provider and model, then read the applicable policy or contract. Confirm whether a chosen zero-retention mode exists for that endpoint and whether the setting covers prompts, outputs, logs and backups. A router cannot extend a provider's privacy commitment to a different provider automatically. If the selected route can change, treat the destination as controlled configuration rather than an invisible implementation detail.

For a data protection review, map the journey from user interface to your application, through CometAPI, to the model provider and any logging or monitoring systems. Decide whether the gateway's terms, DPA, privacy policy and provider agreements satisfy your organization's requirements. Public policy and company descriptions are vendor statements, not an independent audit performed by Roseram. Do not upload special-category, regulated or customer data until the owner approves the full path and relevant contractual safeguards are in place. Redact secrets and use synthetic prompts for initial integration tests.


## Security status, certification evidence and uptime language

CometAPI's Trust Center says formal security certifications have not yet been initiated, and explicitly says the company does not claim certifications it has not received. It lists TLS 1.2 or higher as enforced in transit and describes the 99.9 percent monthly availability figure as a target for the core API gateway. The about page also lists SOC 2 Type II as work on its roadmap. These statements should be read literally: a roadmap item is not an issued audit report, and a target is not necessarily a contractual service-level commitment with a defined measurement window, exclusions and service credits.

For a low-risk prototype, the public documentation may be enough to decide whether to test a limited integration. For production handling sensitive information or a business-critical workflow, request current security questionnaires, architecture and retention details, subprocessor list, incident process, continuity plan and any available independent evidence. Ask which legal entity is contracting, where data is processed, what support response is committed, and what happens after a breach or outage. A Trust Center gives buyers a convenient starting point; it cannot substitute for verifying the exact documents and scope applicable to their agreement.

Availability also has multiple layers. A gateway can respond while a particular provider is unavailable, or a provider can be healthy while an individual model is rate-limited. Monitor request success by model, response latency, quota errors, failed media jobs and your own user-facing completion rate. For important workloads, define an approved fallback, a queue or graceful degradation path, and a budget cap. Check the published status history and measure performance under your own request pattern. Do not promise users a 99.9 percent end-to-end service solely because the gateway page describes a target for its core API.


## Alternatives and a fair procurement comparison

The obvious alternative is direct integration with each model provider. That approach requires separate credentials, bills, provider-specific SDK behavior and operational monitoring, but can give a team a more direct contractual relationship and a clearer view of each provider's terms. Other AI gateways may offer comparable model catalogs, routing, failover or unified billing. A self-hosted open-source model can move some control in-house but brings infrastructure, hardware, quality, patching, security and operations costs. None of these options is universally superior; workload, procurement capacity and data obligations determine the trade-off.

Compare a short list of candidates using the same models and task suite. Include setup effort, accepted-result cost, latency distribution, model coverage, logging scope, data region, rate limits, fallback behavior, support, credits and contract terms. Ask whether rates are pass-through or an advertised discount and whether volume prices apply automatically or only after negotiation. For a gateway, test how easily a team can move from a model alias to a direct provider if needed. Keep the application abstraction small enough that switching does not require a rewrite, but avoid promising portability until schemas and outputs have been tested.

A useful pilot might use non-sensitive prompts for summarization and code generation with a fixed set of expected quality checks. Measure token usage and output length, record exact model IDs, simulate an invalid key and a rate limit, and inspect the bill after each call. Then verify how you would rotate the key, disable auto-reload and export usage records. This is a proposed buyer test, not a test Roseram has performed. A vendor comparison should distinguish measured results from product-page claims so that the final decision remains explainable.


## CometAPI SCAM Review: evidence and buying conclusion

CometAPI has public product pages, developer documentation, a live pricing framework, terms, privacy materials and a Trust Center. Those sources identify a commercial gateway for third-party AI services and describe how requests, prices, credits and security claims are presented. The evidence reviewed here does not establish that CometAPI is a scam. The appropriate conclusion is narrower: buyers should verify current SKU equivalence and billing, understand that model providers receive the necessary request content, and obtain the right security evidence for their intended data and uptime requirements.

This is a source-based desk review. Roseram did not open a paid CometAPI account, send model requests, audit the infrastructure, obtain a vendor questionnaire, or independently confirm the advertised discount. The pricing and model catalog can change; current terms and checkout govern actual obligations. Before funding an account, save the exact price and model pages, review prepaid-credit and refund provisions, start with a capped balance, and test a small workload. For sensitive or business-critical deployments, have procurement, security and legal reviewers confirm provider routing, data-processing terms, certification status and SLA language.

The gateway may be attractive when one API key, a consolidated balance and a broad model menu reduce integration friction. It may be less suitable when an application needs a direct provider contract, a specific privacy commitment, guaranteed access to a fixed model version or independent security certification before launch. A buyer who defines these requirements first can decide whether convenience is worth another dependency. The company name, broad catalog and savings chart are not proof of quality or misconduct; the relevant evidence is the current service behavior, contract, price and data path.


## Features and decision criteria

- One account and API key for a catalog of third-party text, image, video and audio models
- OpenAI SDK-style integration by changing the base URL and key for supported routes
- Prepaid, usage-based billing with a model catalog and a usage dashboard
- Provider and model selection with documented fallback, error and rate-limit guidance

## Pricing considerations

This snapshot was checked on 2026-11-17. The SKU catalog and advertised discounts are dynamic; some rates depend on tokens while other endpoints are priced per image, clip, second or another unit. The official pricing page claims savings for its listed offerings, but buyers should verify the same live model version, quality, region, input/output rates and provider basis at purchase time. Add taxes, exchange-rate effects, failed or incomplete generation rules, and the value of credits that may remain subject to account good-standing terms.

## Sources and further reading

- [CometAPI live pricing and billing framework](https://www.cometapi.com/pricing/)
- [CometAPI API error and rate-limit guides](https://apidoc.cometapi.com/)
- [CometAPI model catalog and live pricing](https://www.cometapi.com/models/)
- [CometAPI Terms of Service and prepaid credit rules](https://www.cometapi.com/terms-of-service/)
- [CometAPI Privacy and Data Protection Policy](https://www.cometapi.com/privacy-policy/)
- [CometAPI Trust Center and stated certification status](https://www.cometapi.com/trust/)
- [CometAPI explanation of model-provider routing and data handling](https://www.cometapi.com/about/)
- [artificial intelligence on Wikipedia](https://en.wikipedia.org/wiki/Artificial_intelligence)
- [CometAPI website](https://www.cometapi.com/)

For the complete Roseram buyer guide, see [CometAPI review](https://roseram.com/reviews/scams/cometapi-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
