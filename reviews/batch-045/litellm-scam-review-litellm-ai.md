# LiteLLM review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Open-source AI gateway and model-routing software  
**Method:** Source-led desk review; no hands-on testing is claimed.

LiteLLM is an AI gateway that presents a common API across model providers and can add routing, virtual keys, budgets, rate limits, and spend tracking. Its current published offer includes a self-hosted open-source version with no license fee and a custom-priced annual Enterprise license for governance, support, and additional controls. Provider inference charges and the cost of operating the deployment remain separate. This review focuses on deployment, logging, cost-map accuracy, security configuration, and the distinction between community and Enterprise features.

## Editorial verdict

LiteLLM’s official site, documentation, and repository describe a usable AI gateway, its open-source license boundary, and paid Enterprise options. The reviewed sources do not support a fraud finding. This is a desk review, not a production deployment, independent security audit, or latency benchmark. Buyers should verify the exact license for the components they install, secure the proxy, validate model-cost mappings, and decide which prompt data is logged or sent to providers and callbacks.

## LiteLLM is a gateway layer, not a model provider

LiteLLM sits between an application and one or more model providers. Its gateway can expose a common API shape while routing requests, applying keys or budgets, and collecting operational information. That can reduce the amount of provider-specific integration code in an application. The gateway does not itself provide all the underlying model capacity, so provider availability, model policies, per-token prices, and rate limits still matter.

A team should draw the request path before deploying it: application, LiteLLM proxy, selected model provider, logging callback, database, and any observability service. Each hop may receive a different subset of data. A common API is an integration convenience, not a guarantee that all providers return identical behavior or that a request can be moved between them without testing. Provider-specific tools, content formats, limits, and safety behavior remain relevant.


## Open-source and Enterprise are distinct offers

LiteLLM’s current pricing page describes the self-hosted open-source gateway as free of license fees and positions Enterprise as an annual license for governance, security, and support. The Enterprise price is custom and based on request capacity, architecture, and support needs. The repository license also contains an Enterprise directory carve-out, so a buyer should not assume every file or feature in the repository has the same license.

Review the license file at the exact version and commit you deploy, and note any Enterprise modules you include. Confirm whether your organization can meet the obligations of the open-source license and whether a commercial agreement is required for the features it needs. ‘Free to self-host’ means no software license fee for the covered open-source components; it does not mean a production gateway costs nothing to operate or that every advanced control is included.


## Gateway pricing and model costs are separate

LiteLLM states that its Enterprise license is not priced per model token, and its open-source gateway has no license fee. The model calls themselves still incur charges from OpenAI, Anthropic, Google, or whichever provider is selected. A self-hosted proxy also needs compute, a database, storage, monitoring, backups, upgrades, and an engineer who can maintain it. Those amounts can exceed the software license cost for a high-traffic or complex installation.

Build a cost estimate from separate lines: provider input and output, cached tokens, images or audio if applicable, gateway infrastructure, database capacity, observability, and operational labor. If model usage is passed through customer accounts, verify how provider credentials are stored and who is responsible for overages. A gateway can track spend only as accurately as its cost map and usage metadata allow; verify that important models are mapped correctly before using the dashboard for billing decisions.


## Model routing and fallbacks need workload tests

A gateway can route requests to configured deployments and provide fallbacks when a provider or model is unavailable. This can help an application avoid hard-coding each provider’s endpoint. However, two models can differ in context window, structured output, tool behavior, latency, and policy. A fallback that accepts the same request shape may still return a result that is not suitable for the original task.

Test a normal request, a provider timeout, a rate-limit response, a malformed answer, and a model that does not support the requested feature. Decide which failures should trigger a fallback and which should fail visibly. Include idempotency and timeout rules for any operation with side effects. Measure quality and cost on the actual application task, not only whether the gateway returned HTTP 200. Routing expands choice but also creates a system that needs explicit acceptance criteria.


## Model cost maps can produce inaccurate budgets

LiteLLM’s cost-map documentation explains that rates are stored by billable unit and that the proxy uses a model cost map to estimate spend. It also notes that an unmapped model can be priced at zero until a verified rate is added. This makes configuration review important: a dashboard can display tidy totals while missing a new model or a provider-specific rate, if the price map is stale or incomplete.

Compare a sample of spend records against the provider invoice for the same requests. Include cached input, long-context pricing, batch rates, image or audio units, and any regional uplift that applies. Add custom prices for models not represented accurately. Treat gateway cost figures as operational estimates until reconciled. If you bill customers using those figures, use safeguards for unknown models and investigate zero-cost requests rather than assuming that the provider charged nothing.


## Prompt logging is a deployment choice

LiteLLM’s UI logging documentation says success and error records are tracked by default, while request and response content is not stored in spend logs unless enabled. Its broader logging documentation supports callbacks to external services, where prompt content may be sent according to configuration. This is a useful privacy control, but it requires operators to understand each destination and verify the settings for the version they run.

Set a minimum logging policy before production. Decide whether content, user identifiers, API keys, headers, model names, or only usage metadata are necessary. Redact sensitive values and restrict who can see logs. Check callback integrations and error logs separately because turning off one storage path does not necessarily stop another from receiving the same request. Test with synthetic markers, then search every configured store to confirm the intended redaction and retention behavior.


## Self-hosting changes who operates the security boundary

LiteLLM’s site says the self-hosted deployment keeps data and keys on the customer’s infrastructure. In practice, that boundary depends on how the customer deploys it. The proxy may send request content to the selected model provider and to configured observability callbacks. Operators manage the network path, credentials, database, images, logging, upgrades, backups, and access controls. ‘Self-hosted’ describes deployment location; it does not automatically make a configuration private or secure.

Follow the official security checklist for ingress, authentication, secrets, outbound requests, release updates, and audit logs. Do not expose an admin interface publicly without access controls. Use a secret manager rather than putting provider keys in source control. Limit who can change routing and models. Review outbound connectivity and telemetry settings. A team should run this review with its own threat model, because a small misconfiguration can reveal credentials or route sensitive prompts to an unintended endpoint.


## Enterprise controls and their boundaries

The Enterprise offer lists SSO, SCIM, audit logs, secret-manager integrations, role-based administration, multi-region control-plane features, support, and service levels. These can matter for teams that need centralized identity, evidence, and help during incidents. The public page describes a custom annual quote rather than a fixed price, so a buyer should request a written scope for the number of requests, deployments, and support expectations.

Ask whether the selected control applies to the exact component and version you operate. For example, a secret-management integration may be limited to the licensed Enterprise edition, while a self-hosted open-source deployment still requires the team to protect secrets through its own mechanism. Confirm how audit records are generated and retained, how support handles sensitive diagnostic data, and what changes if the license ends. A feature list is a procurement starting point, not a substitute for contract details.


## Reliability depends on the whole path

An AI gateway can add a useful layer of routing and observability, but it also becomes a dependency in the request path. If the proxy, its database, or a network route fails, applications may lose access to multiple providers at once. A multi-provider fallback helps only when the fallback is independently reachable and the application can handle differences in output. Decide whether the gateway itself is deployed redundantly and how configuration changes are rolled back.

Test the failure cases that match your architecture: proxy restart, database unavailability, provider timeout, exhausted rate limit, expired credential, and a bad cost-map update. Establish alert thresholds and a way to disable a problematic route. Keep a recovery copy of configuration and verify that a second instance can start from it. These checks are not a measured reliability report on LiteLLM; they are necessary because the buyer operates the surrounding system.


## Privacy and external provider terms

The gateway can control where prompts are routed, but the selected provider still processes the request under its own terms. A callback may also send traces to an observability provider. The customer should identify the model provider, hosting region, retention rules, training policy, and contract for each route. A single OpenAI-compatible endpoint can make the code look uniform while the legal and data-handling conditions differ materially underneath.

Create a provider allowlist for each data class. For sensitive inputs, specify which models are permitted, whether the provider contract allows the processing, and whether content logging is disabled. Avoid routing personal or confidential information through a fallback whose terms have not been reviewed. Include data deletion and user access requests in the design. A gateway makes policy enforcement possible, but it does not decide which policy is appropriate for the organization.


## License and upgrade review

The current repository license states that much of the software outside the Enterprise directory is under MIT terms, while Enterprise directory contents have a separate license file. This is a boundary that deserves attention when building a product from the source. A feature may move between directories or packages over time, so the answer can depend on the version and components included in a specific build.

Record the repository commit, package versions, license notices, and any Enterprise modules in a software bill of materials. Before upgrading, compare the new release’s license structure, security advisories, and migration guidance. Pin production versions and rehearse an upgrade in staging. Open-source access provides transparency and flexibility, but it also means the customer is responsible for tracking changes and maintaining a supported deployment path.


## Alternatives and a fair comparison

Other gateways, provider SDKs, and custom routing code can solve overlapping problems. Compare the same provider set, features, load, observability needs, privacy requirements, and failover behavior. Add the full cost of managed versus self-hosted operations, Enterprise licenses, provider API use, and engineering time. A single unified API is valuable only if it preserves the model features and cost visibility the application needs.

An application with two stable providers may be simpler with direct SDK integrations and a small adapter. A team with many models, centralized budgets, or cross-provider failover may benefit more from a gateway. Use a prototype to see whether routing logic actually reduces maintenance. Avoid deciding based only on a model catalog count or a promise of compatibility; verify streaming, tools, structured outputs, and pricing on the workloads you intend to run.


## Is LiteLLM a scam?

The official pricing page, security documentation, and repository identify LiteLLM as an AI gateway with a self-hosted open-source offer and a paid Enterprise license. The materials reviewed do not support a fraud finding. The title’s SCAM Review wording frames a buyer search, not an allegation. A self-hosted service can still be difficult to maintain or misconfigured, but those possibilities are not evidence of deceptive conduct.

If a buyer encounters an unexpected charge, first separate provider invoices from any Enterprise license, hosting, or support cost. Preserve the quote, license scope, cloud bill, and request-usage logs. Confirm whether the selected features required a license and whether model costs were routed through the provider directly. Ask the appropriate vendor for an itemized explanation. A technically complex bill should be reconciled before conclusions are drawn.


## A practical LiteLLM pilot

Deploy the gateway in an isolated test environment with two low-risk providers. Create one virtual key with a restrictive budget, configure a known model route, and make a small set of normal requests. Verify the selected provider, tokens, cost, and response. Then test an unknown model, an invalid key, a provider timeout, a rate-limit response, and a fallback. Confirm that the proxy does not expose administrative endpoints to the public internet.

Review logs using synthetic secret markers and confirm what is stored in the database and any callback destination. Reconcile one cost entry with the provider’s usage record. Test a configuration rollback and restore from a database backup. This is a buyer test plan, not a claim that Roseram operated or benchmarked LiteLLM. The result should be a written architecture and cost estimate, not just a successful chat response.


## Who should consider LiteLLM

LiteLLM may suit a team that wants a shared API surface across model providers, centralized keys and budgets, or a self-hosted gateway with configurable observability. The open-source license can support experimentation without a gateway license charge, while Enterprise adds governance and support options for eligible buyers. The fit is strongest when the team can operate a proxy and values control over routing and data placement.

A team that does not want to run infrastructure may prefer a managed gateway or direct provider integration. A small prototype with one model may gain little from another service to operate. A regulated organization should inspect the license, security controls, audit scope, and provider terms before routing sensitive traffic. The choice depends on operations and policy as much as on the API format.


## Roseram and LiteLLM serve different roles

A Roseram workspace can assist with software planning and code tasks, while LiteLLM routes application requests to model providers and may apply gateway controls. They can appear in the same development workflow without being interchangeable. A developer still needs to review generated code, validate provider routing, protect gateway credentials, and confirm the cost and data handling of every model that an application can call.

Keep production gateway keys out of prompts and source files. Assign an owner to model configuration and maintain a second-person review for routing changes. Test that a feature using one model behaves acceptably when routed to another. This comparison does not imply an integration, partnership, or included gateway service; it clarifies the separate job each tool performs.


## LiteLLM purchase and deployment checklist

Before deployment, identify which code is open source and which features require Enterprise. Estimate request volume, model-provider charges, compute, database, observability, and staffing. Review the model-cost map for each deployed model. Set a prompt logging policy, restrict the admin interface, manage secrets, review outbound connections, and determine how the team will receive security updates.

For Enterprise, request a quote with capacity, regions, deployment architecture, support response, and audit requirements spelled out. For open source, record the commit and license notices. Test provider failures, zero-cost model mappings, log redaction, and a recovery procedure in staging. These steps give the team evidence about its own configuration and costs; they do not imply that the product itself is fraudulent or unsuitable.


## Final assessment of LiteLLM

LiteLLM offers a flexible gateway with a no-license-fee self-hosted core and an Enterprise option for governance and support. Its strengths are a common provider interface, routing controls, virtual keys, and configurable spend and logging behavior. Its tradeoffs are operational ownership, license boundaries, model-cost map maintenance, and the need to understand data sent to providers and callbacks.

This is a desk review, not a security audit or performance measurement. The official evidence does not justify a fraud claim. Evaluate the gateway with synthetic data, compare cost records to provider invoices, and verify which package features require a commercial license. If the team cannot operate the service securely, a managed alternative may be a better fit despite the open-source software being free to download.


## Features and decision criteria

- OpenAI-compatible gateway for connecting to multiple model providers
- Virtual API keys, teams, budgets, rate limits, and routing controls
- Provider fallbacks and spend tracking through a proxy deployment
- Optional callbacks and observability integrations with logging controls
- Enterprise governance, identity, audit, support, and air-gap capabilities

## Pricing considerations

LiteLLM states that the open-source gateway is free to self-host and that Enterprise pricing is sized by annual gateway request capacity, deployment architecture, and support rather than by model token fees. Provider inference charges remain separate, and self-hosting transfers infrastructure, database, logging, security, and maintenance work to the customer. The public page does not provide a fixed Enterprise price.

## Frequently asked questions

### Is LiteLLM free?

LiteLLM says its open-source gateway can be self-hosted with no license fee. Enterprise governance and support features have custom annual pricing. The customer still pays model providers and for the infrastructure and maintenance needed to run its own proxy.

### Does LiteLLM add a fee to model tokens?

LiteLLM’s official pricing page says its Enterprise license is priced around gateway request capacity and does not add a per-token charge. Model provider charges still apply separately, and the operator may configure margins or other business logic in its deployment.

### Does LiteLLM store prompts by default?

Current proxy documentation says request and response content is not stored in spend logs by default, while success and error metadata can be tracked. Operators can enable content storage or callbacks. Review every logging destination, redaction setting, and backup path in your own deployment.

### Does this review say LiteLLM is a scam?

No. The SCAM Review title introduces a buyer due-diligence query. The official sources reviewed describe an open-source gateway and a paid enterprise offer; they do not establish fraud.

### Has Roseram benchmarked LiteLLM?

No. This is a desk review of first-party documentation and repository information. The deployment and routing checks suggested here are not claimed as measured performance results.


## Sources and further reading

- [LiteLLM official pricing and licensing overview](https://www.litellm.ai/pricing)
- [LiteLLM official gateway and product overview](https://www.litellm.ai/about)
- [LiteLLM repository license](https://github.com/bxnlabs/litellm/blob/main/LICENSE)
- [LiteLLM security guidance](https://docs.litellm.ai/docs/proxy/security/overview)
- [LiteLLM logging and prompt redaction documentation](https://docs.litellm.ai/docs/proxy/logging)
- [LiteLLM spend-log default behavior](https://docs.litellm.ai/docs/proxy/ui_logs)
- [LiteLLM website](https://www.litellm.ai/)

For the complete Roseram buyer guide, see [LiteLLM review](https://roseram.com/reviews/scams/litellm-scam-review-litellm-ai).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
