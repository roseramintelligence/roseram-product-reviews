# Langfuse review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Open-source LLM observability and AI engineering platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

Langfuse is an open-source AI engineering and observability platform for tracing model and agent activity, managing prompts, evaluating outputs and running experiments. It can be used as a hosted Cloud service or self-hosted, so the buyer must compare the managed plan’s ingestion pricing and data-access window with the infrastructure and operational responsibility of running it independently.

## Editorial verdict

Langfuse publishes product documentation, open-source and self-hosting information, plan prices, unit definitions and data-retention documentation. The cited materials support a legitimate AI observability product, not a fraud finding. The important distinction is between historical data access and actual deletion: a shorter plan window can hide older traces without deleting them, while permanent retention deletion is a separate opt-in feature with plan and self-hosted requirements.

## Langfuse review: observe and improve an AI application

Langfuse is an AI engineering platform that brings observability, prompt management, evaluation and experiments together. A trace can represent an application interaction, while observations describe work inside that interaction: a model generation, tool call, retrieval operation or other step. Teams can attach scores, compare variants and examine the path that led to a response. That makes Langfuse more than a conventional infrastructure dashboard, but it is still a measurement and development layer. Its documentation explicitly distinguishes it from a managed agent runtime: it records and evaluates agent behavior but does not execute a stateful agent on a customer’s behalf.

The platform is relevant when developers need to answer questions beyond whether a request returned HTTP 200. Which prompt version was active? Which model and tool were called? How much did a conversation cost? Did the retrieval step return useful context? Did a reviewer mark the final answer as correct? A trace can help explain those events, provided the application instruments the right fields and the organization has decided which user content is safe to record. Instrumentation is a design choice, not an automatic audit of every model decision.


## Tracing, sessions, and the shape of billable units

Langfuse’s pricing FAQ defines a billable unit as a trace, an observation within a trace, or a score. A single user request can therefore generate several metered units as it calls a planner model, a retrieval service, a tool, and a final model. A simple event count based only on user messages can understate Cloud usage. Before choosing a plan, instrument a representative test session and calculate the number of traces, spans, events, generations and scores it creates. The estimate should reflect real application behavior rather than a vendor-neutral guess that one prompt equals one unit.

A detailed trace can be valuable for debugging an agent workflow, but collecting every field also increases cost and can expose information that does not belong in analytics. Decide whether to capture prompts, outputs, retrieved document fragments, tool arguments, end-user identifiers and feedback. Sample routine events if full-fidelity traces are not necessary, while preserving enough context to investigate errors. Use consistent trace and session IDs so one workflow is understandable without duplicating unnecessary personal data across every span.

Check the unit count after instrumentation, not just before it. A framework update may start emitting new spans or generations, and an evaluator may add scores to previously unscored observations. If every internal retry creates a separate trace and generation, the monthly total can grow more quickly than the number of user conversations. Compare a small sample of traces with the billable-unit calculator and set an alert below the point that would require immediate budget approval.


## Langfuse pricing: Hobby, Core, Pro and Enterprise

The Cloud pricing page checked on 2026-11-17 listed Hobby at no cost with 50,000 units per month, 30 days of data access and two users. Core was listed at $29 per month with 100,000 units, 90-day access and unlimited users. Pro was $199 per month with 100,000 units, three-year access and a data-retention feature. Enterprise was listed at $2,499 per month and adds enterprise features such as custom rate limits, audit logs and service-level terms. These numbers are a dated snapshot of the provider’s public page, not a quote for a specific region, tax treatment or contract.

The page lists additional usage at $8 per 100,000 units for the first paid tier above included usage, with graduated rates decreasing at larger volume bands. Estimate costs from measured events and consider how sampling and scoring change the unit count. A high-volume application can spend more on captured traces than expected, while a low-volume prototype may fit on Hobby. Check the detailed plan matrix before buying: user count, retention management, ingestion throughput, support and security features differ. Do not choose Pro solely because an older record should remain viewable; first determine whether the plan’s data-access window meets the need.


## Data access is not the same as data deletion

Langfuse’s retention documentation distinguishes the historical data-access window from the deletion policy. Cloud plan access windows are listed as 30 days for Hobby, 90 days for Core and three years for Pro and Enterprise. The pricing FAQ says older data can remain stored and can become accessible again after an upgrade. Actual automatic deletion is a separate opt-in feature available on Pro and Enterprise; it applies at a project level and deletes traces, observations, scores and media older than the configured period. This is a consequential difference for both a storage budget and a privacy schedule.

A self-hosted Langfuse installation does not automatically delete event data by default according to the documentation. The retention feature has self-hosted prerequisites, including S3 delete permissions, and versioned object storage may require lifecycle rules to remove non-current versions. Dataset items and audit logs are excluded from some retention deletion behavior. Create a data map that accounts for traces, saved dataset examples, associated media, audit records, backups and storage versions. Test deletion on a development project and verify the downstream object-store lifecycle rather than assuming one control removes every copy.

A retention schedule should name a data owner and a verification step. For example, an administrator can create a test trace, wait for the configured retention cycle, then confirm that the trace, its observations and its media have disappeared from the expected storage. Separately check saved dataset examples that were deliberately copied from traces, because preserving an evaluation case can be appropriate but changes the deletion obligation. Keep a record of the project policy, backup lifecycle and exceptions so a later account administrator does not mistake a viewing window for a deletion guarantee.


## Prompts, experiments and evaluation workflow

Langfuse prompt management lets teams version prompts, use labels, compose prompt pieces and fetch deployed versions from an SDK or API. The company’s documentation describes client-side caching so fetching a prompt after the first request does not necessarily add a network round trip each time. The playground can compare prompt variants with their own model settings and variables, and experiments can use datasets to evaluate the effect of a change. These tools help separate prompt iteration from application code releases, but the team still owns its production rollout and its acceptance criteria.

Treat a prompt change as a release artifact. Keep a baseline, record the model and tool configuration, define examples for expected behavior, then compare candidate versions against that evaluation set. If an evaluator is model-based, inspect its false positives and false negatives before using a score to block production traffic. A high average score can conceal a failure on a vulnerable user group or rare but important request. Human annotation queues and user feedback can add context, though they require a process for reviewer consistency and for handling sensitive user content.

Prompt caching creates a deployment tradeoff: it can reduce network work and provide a local fallback when the management service is temporarily unavailable, yet a stale cached version can delay the moment a new prompt takes effect. Langfuse documents configurable cache lifetimes and a fallback prompt. Decide whether a safety or legal correction must take effect immediately; if so, design an explicit invalidation or refresh path and test it. If a brief delay is acceptable, record the maximum cache window in the release checklist so reviewers know what behavior to expect.


## Integrations, data volume, and visibility limits

Langfuse documents SDKs, OpenTelemetry integrations and hooks into AI frameworks, so an application can emit traces through multiple instrumentation paths. The interface depends on those integrations sending consistent identifiers, model names, token usage and cost metadata. If one framework integration records a model call while a custom tool step does not, the resulting trace can look complete while omitting a consequential operation. Establish an instrumentation standard and sample the stored traces after every material framework or model change.

Ingestion throughput and access history differ by plan; the current pricing matrix lists distinct throughput ceilings. The exact need depends on peak event volume and the number of observations created per application request. Test what happens when ingestion is throttled and decide whether the application must continue if observability is temporarily unavailable. Typically, production work should not block merely because a trace event failed to post, but the loss should be visible to operators. Monitor both the customer-facing model path and the telemetry pipeline.


## Privacy and self-hosting considerations

Self-hosting can give a team control over where Langfuse and its backing data stores run, but it does not remove the need to configure access control, encryption, backups, updates and retention. Langfuse’s self-hosted telemetry page says its open-source deployment sends aggregated usage metrics to the company and does not send raw traces, prompts, observations, scores or dataset contents. Its data-masking documentation describes client-side masking before transmission, and an enterprise-only server-side masking option. Those distinctions should be included in the threat model before sensitive data is instrumented.

Client-side masking is the safer choice when certain fields must never leave the application boundary. Build an allowlist of fields for each event and test that credentials, payment information, health information and customer text are removed before the event is serialized. If the Cloud deployment is used, review the DPA, region, retention configuration and provider terms for the workspace. Self-hosted does not mean risk-free; a compromised telemetry instance can expose a valuable map of user behavior and internal prompts even if the upstream model call itself is properly secured.

Use separate projects or environments for development, staging and production, with distinct keys and access rights. Confirm that a test project cannot query production traces and that support access is assigned only to staff who need it. Review the telemetry instance’s administrator accounts, backups and network exposure as carefully as the main application. Observability systems are attractive targets because they may contain a chronological picture of internal workflows even when credentials were properly removed.


## Alternatives and a practical Langfuse buyer test

Compare Langfuse with provider-native observability, OpenTelemetry-based tracing stacks, managed AI evaluation products and a custom logging pipeline. A native vendor console may be simpler for a single-provider application but less useful when multiple models and tools are involved. An open-source telemetry stack can avoid a per-unit hosted fee while requiring more work to build prompt management, evaluation and user-feedback workflows. Langfuse’s differentiator is the combination of those capabilities and the option to self-host; its fit depends on how much of that workflow the team will actually use.

Instrument one representative workflow containing a model call, retrieval step and tool action. Confirm that the trace records the correct sequence, usage and model name, and that unwanted content is masked before storage. Create a small evaluation set, compare one prompt change and export a dataset. Estimate monthly units at normal and peak traffic, then verify a retention deletion on a test project. This is a proposed buyer test, not a claim that Roseram installed Langfuse or benchmarked its Cloud service.


## Langfuse SCAM Review: evidence and buying conclusion

Langfuse publishes documentation for its open-source platform, Cloud pricing, billable units, data-access windows and deletion controls. The evidence describes a commercial hosted option alongside self-hosted software and does not support a scam allegation. Roseram did not inspect a private deployment, run the software or verify a customer’s billing records. This review is a desk analysis of public materials and explains what a buyer should confirm before sending production traces.

Before selecting a plan, count billable units from real traces, identify who may see prompts and outputs, and decide how long each data class must be retained. Confirm whether the organization needs Cloud, self-hosted or an enterprise contract, and test event deletion across object storage and dataset copies. Compare the annual operational cost of self-hosting against the Cloud plan and included usage. The product can suit teams that need a shared view of model behavior and prompt quality; it is less compelling if the application has little instrumentation or if the team will not staff the retention and observability workflow.

Ask a dashboard user to locate a failed interaction from its session identifier, reproduce the model and prompt version, and find the action taken to correct it. If that takes too long, adjust trace fields and saved dashboards before expanding ingestion. Good observability is not a large volume of telemetry; it is the ability to answer a specific operational question without unnecessary data collection. A short pilot can reveal whether integrated prompts and evaluations add enough value to justify the recurring Cloud or self-hosting work.


## Features and decision criteria

- Traces and agent graphs with sessions, users, token and cost measurements
- Prompt versioning, release labels, playgrounds and experiments
- Online and offline evaluations, scores, datasets and human annotation workflows
- Hosted Langfuse Cloud or self-hosted open-source deployment

## Pricing considerations

Prices and included units were observed on Langfuse’s live pricing page on 2026-11-17 and may change. One billable unit is a trace, an observation such as a span/event/generation, or a score; it is not simply one end-user prompt. Core and higher plans bill for usage above included units. Data access describes how far back a plan can view events and is distinct from deletion. The self-hosted software can be used without a usage-based fee, but the total operating cost is not zero.

## Sources and further reading

- [Langfuse Cloud pricing and plan comparison](https://langfuse.com/pricing)
- [Langfuse billable-unit definition and usage calculator](https://langfuse.com/pricing?calculatorOpen=true)
- [Langfuse data-retention controls and exceptions](https://langfuse.com/docs/administration/data-retention)
- [Langfuse self-hosted telemetry policy](https://langfuse.com/self-hosting/security/telemetry)
- [Langfuse self-hosted data masking documentation](https://langfuse.com/self-hosting/security/data-masking)
- [Langfuse prompt management setup documentation](https://langfuse.com/docs/prompt-management/get-started)
- [Langfuse open-source scope and platform overview](https://langfuse.com/resources/engineering/clarifications)
- [observability on Wikipedia](https://en.wikipedia.org/wiki/Observability)
- [Langfuse website](https://langfuse.com/)
- [devhunt listing](https://devhunt.org/tool/langfuse)
- [saashub listing](https://www.saashub.com/langfuse)

For the complete Roseram buyer guide, see [Langfuse review](https://roseram.com/reviews/scams/langfuse-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
