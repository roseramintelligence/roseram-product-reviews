# BaseTen review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** AI model inference infrastructure  
**Method:** Source-led desk review; no hands-on testing is claimed.

Baseten provides model APIs and infrastructure for teams serving AI workloads. Its product choices include token-priced Model APIs, dedicated GPU inference, training and isolated agent sandboxes, with pay-as-you-go use and custom production capacity options. Prices, model support and retention depend on the selected service and deployment configuration.

## Editorial verdict

Baseten publishes a live product and pricing page, security practices, legal terms and a data-processing agreement. The sources do not support calling the service a scam. Buyers should separate token-billed Model APIs from uptime-billed dedicated compute and from training or sandbox products, then verify product-specific Zero Data Retention and what is kept for deployment, asynchronous work, logs, checkpoints and customer-controlled configuration.

## Baseten review: model APIs and serving infrastructure are different buys

Baseten is an AI inference platform whose product menu includes hosted Model APIs, Dedicated Inference, training and Sandboxes. The distinction matters to both cost and engineering ownership. A Model API customer calls a listed model and pays according to token usage. A Dedicated Inference customer deploys a model on configured compute and pays for that compute over time. Training jobs, saved checkpoints and isolated sandbox environments introduce different work and retention behavior. A product comparison that collapses all of these into the phrase “AI hosting” misses the decisions that drive the bill.

Begin with whether the team needs an existing model endpoint or must run a model it selects and configures. If the main goal is to compare model quality or add one API call, start by evaluating a Model API. If the team needs a custom model, stable control over deployment, a dedicated GPU or self-hosted infrastructure, then investigate Dedicated Inference and deployment options. Write down latency, concurrency, region, data-residency and expected uptime requirements before choosing a tier. Those requirements determine whether a simple shared API is sufficient or an engineering deployment project is justified.


## Baseten pricing: token meters versus GPU uptime

Baseten’s pricing page separates Model APIs, Dedicated Inference, Training and Sandboxes. For Model APIs, the page lists input, cached-input and output token rates per million tokens. When checked on 2026-11-17, its table showed GLM-5.3-Flash at $0.15 per million input tokens, $0.03 per million cached input tokens and $0.50 per million output tokens. These figures describe one model at one point in time; another model can be materially more expensive, and the table can change as model availability and rates change.

Dedicated Inference uses a compute meter. The live page listed a T4 at $0.01052 per minute, or about $0.6312 per hour; an A100 at $0.06667 per minute, or about $4.00 per hour; and an H100 at $0.10833 per minute, or about $6.50 per hour. Multiplying an hourly figure by active hours gives only a first estimate. Replicas, whether a deployment remains warm, scale-up and scale-down behavior, storage and training add operational cost. A model that receives occasional traffic may be cheaper on a token meter, whereas a dedicated deployment may be justified when a team needs control, predictable capacity or a particular runtime.

Model the expected idle periods as well as the busy hours. A warm replica can reduce startup latency but may keep a GPU bill running while few or no requests arrive. A scale-to-zero configuration may reduce quiet-period cost while making the first request slower. Write both scenarios into the estimate and ask how the configured deployment reports active minutes, failed revisions, autoscaling and storage. The arithmetic should use the exact GPU and replica configuration that the team intends to deploy, not just the cheapest hardware row on a broad pricing page.


## Pay-as-you-go entry and production-scale agreements

The pricing page presents a pay-as-you-go path with usage-based prices and no need to contract for capacity in advance, and a separate production-scale path for capacity planning, volume discounts, reserved or priority compute, custom regions and support. The latter is a commercial discussion rather than a visible universal subscription price. Buyers should request a written estimate for the actual model, GPU class, replica count, region, traffic shape and support needs. A headline that says pay for use does not tell you whether the service will meet a particular latency target at a particular workload.

Ask for the expected monthly amount at low, normal and peak traffic, and separately identify costs that continue when the model is idle. Confirm whether the quotation assumes a minimum number of replicas, continuous operation, a specific deployment mode or a committed term. Ask what happens if traffic exceeds the reserved capacity and whether a route to serverless or a different region exists. The written service order, rather than a marketing comparison, governs any custom commitment. Save the version of the price page and quote you used in the business case.


## Deployment choices: managed cloud, self-hosted and hybrid

Baseten’s security practices describe three deployment configurations: a managed Baseten Cloud using multi-cloud infrastructure and autoscaling, self-hosting the inference stack inside a customer’s cloud, and a hybrid arrangement where the customer sets how workloads run and may use Baseten Cloud for elastic spillover. This gives teams different balances of infrastructure control and provider operation. Self-hosting can keep customer content within a controlled environment according to the stated option, but it also makes the customer responsible for the surrounding cloud account, network, identity and operating practices.

The right choice depends on who will operate the deployment. A small team may value a managed control plane and autoscaling because it avoids a new GPU-on-call burden. A team with strict network or region requirements may need a self-hosted or hybrid architecture and the staff to maintain it. Confirm the exact region behavior, cloud provider path, outbound connections, model artifact storage and support boundary for your configuration. Test a deploy, scale event and rollback with non-sensitive data before placing a critical service behind it.


## Autoscaling, cold starts and reliable inference

Autoscaling and dedicated hardware do not make the service operationally automatic. The model and runtime must initialize, compatible GPU memory must be available, dependencies need to load, and request traffic must be routed to ready replicas. The buyer should find out how the selected configuration handles scale-to-zero or warm capacity, how long a cold start may take, and whether a deployment can queue requests or return an error while scaling. A GPU price cannot be evaluated without knowing the service’s lifecycle behavior.

Instrument the request path from the client through queueing, model startup and the response. Track first-token latency, full response time, timeout count, replica count, GPU utilization, errors and cost per accepted task. Build bounded retries and an idempotency strategy for requests that time out after the model has started. Test how the application behaves when a deployment is unavailable and how it rolls back after a broken model or dependency update. Ask Baseten for the SLA and support arrangement applicable to your paid service; do not infer an uptime guarantee from infrastructure descriptions.

Include a representative input that approaches the model’s memory and latency limits, not just a short successful prompt. A change in input length or concurrent users can affect batching and GPU utilization, so the capacity result may differ from a single-request demo. Capture a baseline before changing runtime settings, then change one parameter at a time. If the model is loaded from a customer-controlled source, test credential rotation and an inaccessible artifact. A reliable rollback needs the previous model revision, weights and runtime dependencies to remain identifiable.


## Baseten security and Zero Data Retention scope

Baseten’s security practices describe a multi-tenant platform with logical separation and list single-tenant dedicated clusters and self-hosted options for additional isolation. The document says it has a Zero Data Retention posture for Model APIs inputs and outputs and for Dedicated Inference inputs and outputs, subject to product detail and customer-controlled configuration. The same page distinguishes asynchronous inference, where inputs can be queued temporarily for up to 72 hours, and records such as custom model weights, training checkpoints or sandbox files that persist according to their own lifecycle.

That product boundary should be part of procurement. The terms say model and third-party product licenses remain relevant, customer configurations can affect retention, and customers remain responsible for their own data when it is in their control. Review the current Security Practices, DPA, terms, subprocessor list and Trust Center materials. If handling personal or health data, determine whether the selected configuration is eligible and whether a BAA or other contract is actually in place. Do not treat a company-level security badge or ZDR phrase as proof that every feature, dependency and customer setting follows the same path.


## Training, model weights, and ending a deployment

Training is asynchronous: the security materials say requests and data may be held temporarily while training or sampling runs, and resulting checkpoints and Customer Models remain until the customer deletes them. Dedicated inference model weights may be loaded dynamically, while some configurations such as a delivery network can store or cache weights to deploy and serve the model. Sandboxes retain customer files, code and other content until the customer deletes them. These are not equivalent to transient real-time inference, and the customer should decide how long each asset must exist.

Before building a durable workflow, record where the source dataset, model checkpoint, image or runtime dependency is stored and who can retrieve it. Test the export and deletion process, then confirm what remains in provider backups under the published lifecycle. For a subscription ending, Baseten describes a thirty-day retrieval period for relevant content before deletion; confirm the specific service and contract. Keep the training dataset, model license, evaluation set and deployment configuration under your own version control so you can reproduce or replace a model without relying on a single console.

Treat the first production deployment as a change-management event. Record the model artifact hash, code image, GPU type, environment variables, launch settings and traffic allocation. Give only the release owner permission to promote a new version, and preserve a known-good revision that can be restored quickly. For teams using customer models, write down whether a weight artifact is copied into provider infrastructure or pulled at startup from customer storage. That detail affects both data governance and the time needed to recover a deployment.


## Model APIs, third-party models and production responsibility

A model exposed by a platform may have been developed by a separate lab. Baseten’s terms distinguish its own infrastructure services from third-party products, and say the third-party model’s license and usage policies apply. A shared API can simplify authentication and billing, but it does not make each model interchangeable. Context length, tool use, output style, supported parameters, safety behavior and change notices can vary by model and version. An application that relies on a specific behavior should pin and test the model identifier where possible and monitor for changes.

For each model, review the license, usage restrictions, provider dependencies and data terms. Keep credentials server-side and restrict team access to deployment, API keys and customer data. Add model-output validation for the task, particularly when generated results could be shown to customers or trigger automated actions. Include a human review step for high-impact decisions. A provider can supply infrastructure and controls; it cannot determine whether your application’s model use is accurate, legally authorized or safe for its audience.


## Baseten alternatives and a workload-based evaluation

Compare Baseten with direct model APIs, shared inference platforms, other GPU deployment providers and a self-managed Kubernetes or cloud-GPU stack. The alternatives differ in available model families, token or GPU meters, warm capacity, supported regions, release tools, security boundaries and on-call responsibilities. A direct API can make a one-model integration straightforward. A serving platform can help teams deploy a custom model or tune infrastructure. Self-hosting can provide more control while requiring staff to maintain the full production path. Compare the system you intend to buy, not a generic vendor label.

Use a representative test with permitted data: one normal request, a burst, an invalid input, a cold deployment, a scale-up and a rollback. Record output quality, end-to-end latency, time to first token, errors, token usage or GPU hours, and any operator work. Compare a month of expected shared API traffic with a dedicated deployment at realistic active hours and replica count. This is a proposed evaluation and not a Roseram benchmark. Keep the acceptance criteria fixed while testing vendors so the result reflects the workload rather than an attractive demo.


## Baseten SCAM Review: evidence and buying conclusion

Baseten publishes product pricing, a model catalog, legal terms, security practices, DPA and Trust Center materials. These sources describe a commercial inference and deployment platform with distinct pricing and retention paths. They do not establish that Baseten is a scam. Roseram did not deploy a model, test production latency, inspect a private Trust Center report or independently verify certifications for this article; it is a desk review of public publisher documentation and a structured buyer checklist.

Before signing up or accepting a quote, confirm whether the purchase is Model APIs, Dedicated Inference, training or Sandboxes, then record the model or GPU, token or uptime meter, scale settings, region, retained artifacts, terms and support level. Test failure handling and model replacement before moving customer traffic. Verify the contract’s price, retrieval period and deletion conditions. The platform can be a fit for teams that need managed model serving or custom deployments, but the right decision depends on measured workload economics and engineering capacity, not solely on model availability or a token-rate comparison.


## Features and decision criteria

- Model APIs with token-based billing for listed language models
- Dedicated inference deployments billed by configured compute and active usage
- Training, model optimization and isolated agent sandbox products
- Managed cloud, self-hosted and hybrid deployment choices described in security materials

## Pricing considerations

These prices were visible on Baseten’s dynamic US pricing page when checked on 2026-11-17. The page separately lists Model APIs, Dedicated Inference, Training and Sandboxes; costs from one product should not be generalized to another. Dedicated compute prices are usage rates, not a complete monthly estimate, and a continuously running GPU accumulates hours. Include replicas, scale behavior, storage, training, sandbox runtime, data transfer, support and any custom terms in a workload estimate.

## Sources and further reading

- [Baseten live model API and GPU pricing](https://www.baseten.co/pricing/)
- [Baseten inference and deployment documentation](https://docs.baseten.co/)
- [Baseten Model API catalog](https://www.baseten.co/models/)
- [Baseten Security Practices and product-specific retention](https://www.baseten.co/security-practices/)
- [Baseten Terms and Conditions](https://www.baseten.co/terms-and-conditions/)
- [Baseten Data Processing Agreement](https://www.baseten.co/dpa/)
- [Baseten Trust Center](https://trust.baseten.co/)
- [machine learning model serving on Wikipedia](https://en.wikipedia.org/wiki/Model_serving)
- [BaseTen website](https://www.baseten.co/)
- [saashub listing](https://www.saashub.com/baseten)

For the complete Roseram buyer guide, see [BaseTen review](https://roseram.com/reviews/scams/baseten-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
