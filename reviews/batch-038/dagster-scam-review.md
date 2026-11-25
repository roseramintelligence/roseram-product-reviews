# Dagster review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Data orchestration and pipeline platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

Dagster is a data orchestration platform organized around assets, jobs, schedules, sensors, and pipeline operations. Its commercial Dagster+ service currently lists Solo at $10 per month plus usage and Starter at $100 per month plus usage, with credit and serverless-compute meters; Pro is sales-priced. Dagster Labs announced that Prefect acquired Dagster in July 2026, so buyers should confirm the current contracting entity and product roadmap. This review distinguishes open-source tooling from hosted plans and examines cost, deployment, and ownership considerations.

## Editorial verdict

Dagster’s current pricing and product pages describe an orchestration platform with distinct open-source and Dagster+ offerings. Dagster Labs has also publicly announced its acquisition by Prefect in July 2026, a material ownership change buyers should consider. The sources reviewed do not support a fraud finding. This is a desk review, not a benchmark, production pipeline test, or legal analysis of the acquisition. Confirm current terms, hosting, data controls, and product support with the provider before adopting it for critical data workflows.

## Dagster organizes data work around assets

Dagster is a data orchestration tool for defining, scheduling, and monitoring work that produces or updates data assets. Its model can connect a table, model, file, or other output to the jobs that create it and the downstream work that depends on it. Teams can also use schedules, sensors, partitions, and backfills to manage time-based or event-based pipeline behavior.

This asset-oriented approach is useful when a data team needs to understand what is produced, how it changes, and which computations depend on it. It may be more structure than a short script needs. Before evaluating the interface, map one representative pipeline: inputs, transformations, outputs, dependencies, owner, and acceptable freshness. Then see whether the asset model makes the workflow easier to maintain than the current scheduler and documentation.


## Open source and Dagster+ are different deployment choices

Dagster has open-source software that teams can operate themselves and a hosted Dagster+ service with plan-level features. Self-hosting can give a team more control over infrastructure and data handling, but it also means maintaining the deployment, database, upgrades, monitoring, and incident response. Dagster+ can reduce some of that work while introducing a subscription and usage meters.

Decide which controls are mandatory before comparing monthly prices. A self-hosted installation still needs secure access, backups, upgrade testing, and operational ownership. A hosted plan may offer catalog, metrics, collaboration, or support features that the team would otherwise build. The software license cost alone is not the total cost of self-hosting; include compute, storage, backups, staff time, and the effort of supporting production runs.


## Dagster+ plan fees and usage credits

The current Dagster+ pricing page lists Solo at $10 per month plus usage, Starter at $100 per month plus usage, and Pro as a sales-led plan. Solo and Starter have different per-credit rates, and the page separately lists Serverless compute at $0.010 per minute. Hybrid deployments are described without that compute charge. The plan fee is therefore a base amount, not a complete estimate for a pipeline that runs frequently or processes many assets.

Dagster defines one credit as an asset materialization or an executed op. A job with many steps may therefore consume credits according to its execution model, not just the number of scheduled runs. Count representative asset materializations and ops, estimate serverless minutes if applicable, and include data warehouse or cloud compute charges that are billed elsewhere. Use the current product calculator and a measured pilot to refine the forecast.


## Usage depends on pipeline structure

The credit model makes pipeline design financially relevant. A run that materializes several assets or executes many ops can consume more credits than a simple job, even if both are triggered once. Retries, partitions, backfills, and development runs may also contribute to the total depending on which assets and ops execute. Buyers should model the actual workload and read the current metering definitions carefully.

For a pilot, record each run, number of materializations, ops, retries, and compute minutes. Compare a normal week with a backfill or incident scenario. Determine whether a failed step is billed and how a retry changes credit use. Do not make a monthly estimate from a single successful run if the production workflow includes many partitions or frequent updates. Usage analytics should be part of the rollout review, not an afterthought.


## Development, deployment, and code locations

Dagster documentation describes local development and deployment workflows that connect project code to a running orchestrator. Hosted plans list limits for users, code locations, and deployments that can affect how a team organizes environments and projects. Those limits are operational details that should be checked against the current plan; a feature matrix may change as the product evolves.

Test how code reaches development and production. Confirm where dependencies are installed, how secrets are passed, how a code change is reviewed, and how an old deployment is restored. A data pipeline may work on a laptop and fail in the hosted environment because of package versions, network permissions, or credentials. Keep the pipeline definition in source control and make a release reproducible so a later maintainer can explain which code produced a particular dataset.


## Schedules, sensors, retries, and data quality

Schedules and sensors help start work on a cadence or in response to an event. Backfills and partitions help process historical or segmented data. Those capabilities can improve visibility, but they do not guarantee that upstream data is correct or that a retry will be harmless. A pipeline needs explicit handling for late inputs, duplicate events, partial writes, and dependencies that are temporarily unavailable.

Define data-quality checks before the pipeline is considered successful. Test a missing source, an empty dataset, a delayed event, a duplicate row, and a job that fails after writing part of an output. Decide whether outputs are atomic or how an incomplete partition is repaired. Orchestration records execution state; the business still needs to define what makes the resulting data valid and safe to use.


## Observability and operational ownership

Dagster+ pricing describes metrics, asset health, alerts, and data catalog features that vary by plan. Those tools can help a data team trace a failed or stale asset. Confirm the historical lookback, alert destinations, role controls, and log access available to the selected plan. If a key alert is restricted to a higher plan, include that in the budget before designing an operational process around it.

Name an owner for each production pipeline and set a clear escalation path. Monitor freshness, run failures, duration, credit use, and downstream impact. Keep a runbook for pausing schedules, rerunning a partition, and notifying users of stale data. Alerts that are not assigned to a person are easy to ignore. A polished dashboard is useful when it connects to an operational response, not as a substitute for one.


## Dagster and the Prefect acquisition

Dagster Labs publicly announced in July 2026 that Prefect acquired Dagster, including the product, codebase, customer relationships, and many team members. This is material current information for a buyer considering a multi-year data platform. It does not mean the product has disappeared: Dagster’s pricing and documentation pages remain available, and the announcement describes the transaction. It does mean older company and contracting details may no longer fully describe the current operating relationship.

Before procurement, confirm which legal entity signs the order, who provides support, how existing contracts and data are handled, and what the product roadmap is. Ask whether there are changes to hosting, subprocessors, service-level terms, or account ownership. Treat these as normal diligence questions after an acquisition rather than evidence of wrongdoing. The customer should know which party is responsible if an incident, billing dispute, or migration question arises.


## Privacy, data, and deployment mode

A hosted orchestration service can process metadata about pipelines, assets, run status, and sometimes credentials or configuration. Dagster’s privacy policy and terms describe how its service handles information, while the deployment mode determines what remains in the customer’s own infrastructure. A buyer should distinguish pipeline code, data records in an external warehouse, orchestration metadata, execution logs, and support artifacts.

Make a simple data map and check how credentials are stored, who can view logs, and how long run history and metadata remain available. If the service connects to production databases, use least-privilege credentials and a read-only role where possible. Test exports and deletion procedures with a non-sensitive project. If data residency or regulated processing matters, confirm the exact plan and deployment option in a current contract, especially in light of the Prefect acquisition.


## Reliability and failure recovery

A data orchestrator is part of a chain that includes code repositories, compute, databases, warehouses, and upstream sources. Any of those can fail. A hosted control plane may show run history while the customer’s code or external compute executes elsewhere, depending on deployment architecture. Understand which component is responsible for retries, which state is durable, and what happens if the orchestrator is temporarily unavailable.

Run a recovery drill with a disposable pipeline. Stop a worker, expire a test credential, interrupt an operation, and restore from a backup. Confirm whether the system retries automatically, how duplicate writes are prevented, and how the team sees a partial result. This is a suggested buyer test, not a measured availability result for Dagster. A clear recovery plan matters more than an uptime label for pipelines that influence financial or customer-facing decisions.


## Alternatives and when to compare them

Airflow, Prefect, managed ETL tools, cloud-native schedulers, and custom orchestration code may solve overlapping needs. Their models, deployment work, observability, and billing units differ. Compare one real pipeline and include retries, backfills, deployment environments, data checks, team permissions, and operational effort. A familiar tool may be attractive if the team already knows it; another may offer a more useful model for asset lineage or collaboration.

Dagster’s acquisition by Prefect makes a direct comparison especially relevant for organizations weighing the two product ecosystems. Confirm how each product is supported and contracted today rather than relying on old comparisons written before the transaction. Keep the benchmark focused on requirements: a small scheduled transform differs from a large data platform with many teams. Evaluate the time to diagnose a failure, the cost of usage, and the ease of moving definitions and data if your choice changes.


## Is Dagster a scam?

The official documentation describes data orchestration software and a hosted Dagster+ service. Dagster Labs and Prefect also publicly announced an acquisition in July 2026. The sources reviewed do not support a fraud finding. The SCAM Review wording is a buyer query, not an allegation. A recent change in ownership is relevant to continuity and contracts, but by itself does not indicate misconduct.

If a customer is uncertain about an invoice or roadmap commitment, compare the order form and service terms with the current provider’s announcement and contact information. Preserve emails and account records. Ask which entity is responsible for the service and how existing customer terms are handled. An acquisition can raise reasonable questions about support and product direction; answer them with current contractual information rather than assumptions based on the company name alone.


## A practical Dagster pilot

Choose one noncritical pipeline with a real source, one transform, and a downstream asset. Define what a valid output looks like, who owns it, how often it should refresh, and what a failure should do. Run the pipeline locally and in the intended hosted or self-managed mode. Record setup steps, code deployment, configuration, logs, and the number of assets and ops executed.

Then test a retry, a backfill, a missing input, a credential failure, and a duplicate event. Check credit totals against execution counts and serverless minutes against run duration. This is an evaluation plan, not a performance result claimed by Roseram. The goal is to discover whether Dagster’s asset model improves the team’s ability to understand and recover its data workflows at a cost the organization accepts.


## Who may find Dagster useful

Dagster may suit data engineering teams that need an explicit asset graph, scheduled or event-driven orchestration, partitions, backfills, and visibility into pipeline health. Dagster+ offers hosted plans for teams that prefer a managed service and have a usage model they can forecast. The open-source option may suit organizations comfortable operating the platform themselves.

A simple one-off script may not justify an orchestrator. A team with strict regional requirements, an existing Prefect contract, or a large pipeline estate should verify the current post-acquisition service terms and migration path. The product should be selected because its workflow model improves a real data system, not because a feature matrix contains the largest number of checkmarks.


## Roseram and Dagster serve separate parts of a workflow

A Roseram workspace can help with application planning and code tasks, while Dagster organizes data pipeline execution and asset dependencies. These capabilities may appear in a broader software project, but they are not substitutes. A team still needs to test pipeline definitions, manage credentials, validate data, and decide which orchestrator runs in production.

Keep production data and secrets out of prompts unless the organization has approved that use. Review generated code before it changes a schedule or writes to a warehouse. Confirm the current Dagster+ terms with the provider, including the contracting entity after the acquisition. This comparison clarifies roles without implying a partnership or that a Roseram plan includes Dagster hosting.


## Dagster purchase checklist

Before choosing, decide between self-hosted Dagster and Dagster+. Estimate asset materializations, executed ops, serverless minutes, users, code locations, and deployments. Check which monitoring, catalog, access, and support features appear in the plan. Confirm data locations, retention, credentials, backups, and any contractual terms. Given the 2026 acquisition, verify the legal entity and current support path directly.

In a pilot, measure cost and failure recovery for one representative pipeline. Test a backfill, retry, partial write, and credential rotation. Export a pipeline definition and confirm it can be operated from source control. Assign a billing owner and operational owner. These checks help determine whether the current offering meets your needs; they are not a claim that the acquisition or product is problematic.


## Final assessment of Dagster

Dagster offers a distinct asset-oriented way to orchestrate data workflows, alongside a hosted Dagster+ service with a subscription and usage-credit model. Its strongest case is a data team that benefits from explicit asset dependencies, quality checks, backfills, and operational visibility. The tradeoffs include learning and operating the model, understanding per-credit and compute charges, and confirming current support and contract terms after Prefect’s acquisition of Dagster Labs.

This desk review does not claim a production test or a legal conclusion about the acquisition. The reviewed sources do not support calling Dagster a scam. Verify plan rates and the current provider entity, then run a controlled pipeline test that includes a failure and cost reconciliation. The result will be a more reliable purchase decision than relying on a static product description or an outdated comparison.


## Features and decision criteria

- Asset-oriented orchestration for data pipelines and dependent computations
- Jobs, schedules, sensors, partitions, and backfills for recurring workloads
- Local development tools and integrations with data platforms
- Hosted Dagster+ plans with credit, serverless, catalog, and monitoring options
- Open-source components for teams that want to operate their own deployment

## Pricing considerations

Dagster defines a credit as an asset materialization or an executed op. Solo and Starter use a subscription plus per-credit pricing; Serverless compute is billed at $0.010 per minute, while the page says Hybrid has no compute charge. Infrastructure and external data-provider charges may remain separate. Prefect announced its acquisition of Dagster Labs in July 2026; confirm the live contracting entity and terms before relying on older agreements or pricing snapshots.

## Frequently asked questions

### Is Dagster free?

Dagster’s open-source software can be self-operated without a Dagster+ subscription, but the team pays for infrastructure and maintenance. Hosted Dagster+ currently lists Solo at $10 per month plus usage and Starter at $100 per month plus usage.

### How does Dagster+ usage credit billing work?

Dagster’s pricing FAQ says each asset materialization and each executed op counts as one credit. Solo and Starter list different per-credit rates; Serverless compute is separately metered per minute. Estimate from pipeline execution counts and deployment mode, not simply the number of assets in a catalog.

### Who owns Dagster now?

Dagster Labs announced in July 2026 that Prefect acquired Dagster, including the product, codebase, customer relationships, and many team members. Buyers should confirm the current contracting entity, terms, and product support directly with the provider.

### Does this review claim Dagster is a scam?

No. The SCAM Review phrase is a due-diligence query, not a fraud allegation. The reviewed official sources describe the product and a publicly announced acquisition; they do not establish fraud.

### Has Roseram tested Dagster pipelines?

No. This is a desk review of first-party documentation and pricing. The proposed pipeline trial is a buyer checklist, not a performance test or production deployment report.


## Sources and further reading

- [Dagster official pricing and usage-credit definitions](https://dagster.io/pricing)
- [Dagster acquisition announcement from Prefect and Dagster](https://dagster.io/prefect)
- [Dagster+ terms of service](https://dagster.io/terms)
- [Dagster privacy policy](https://dagster.io/privacy)
- [Dagster official documentation](https://docs.dagster.io/)
- [Dagster+ plan and deployment documentation](https://docs.dagster.io/deployment/dagster-plus)
- [Dagster website](https://dagster.io/)
- [saashub listing](https://www.saashub.com/dagster)

For the complete Roseram buyer guide, see [Dagster review](https://roseram.com/reviews/scams/dagster-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
