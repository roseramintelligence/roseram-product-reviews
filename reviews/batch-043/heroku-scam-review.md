# Heroku review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Cloud application hosting and platform-as-a-service  
**Method:** Source-led desk review; no hands-on testing is claimed.

Heroku is a platform-as-a-service for deploying applications as dynos, connecting data services and add-ons, and managing releases. Its current published Common Runtime dyno prices include Eco at $5 per month for a shared pool of 1,000 dyno hours, Basic at $7 per dyno per month, and Standard-1X at $25 per dyno per month. Dynos use ephemeral filesystems, and Eco dynos sleep after inactivity. This review covers the application platform and current public pricing, not every Salesforce product or private contract.

## Editorial verdict

Heroku’s official product and developer documentation describes an identifiable application platform with published dyno plans, usage rules, restart behavior, and security options. The sources reviewed do not support a fraud finding. This is a desk review, not a live deployment, performance test, or customer survey. Buyers should distinguish shared Eco hours from always-on dynos, price data services separately, and design for restarts and ephemeral filesystems before relying on the platform.

## What Heroku sells

Heroku is a platform-as-a-service where application processes run in dynos and are managed through releases, configuration, scaling, logs, and related services. A developer can use supported buildpacks or containers, declare process types, and connect data services or add-ons. This gives a team a managed deployment layer without administering every part of a conventional virtual machine. It does not mean the provider designs, tests, or operates the customer’s application for them.

This review focuses on the Heroku application platform and public dyno pricing. Heroku’s broader product and Salesforce relationships should not be collapsed into one plan comparison. Private Spaces, data products, enterprise contracts, and marketplace add-ons can have separate features and costs. Buyers should identify whether they need a common-runtime web app, background worker, private network, managed database, or a different platform component before using a headline per-dyno price to estimate the project.


## Heroku dynos and the process model

A dyno runs a process from a built application artifact. A web process handles inbound requests, a worker process can consume jobs, and one-off dynos can run administrative tasks. Heroku’s documentation describes a dyno manager that starts, stops, and replaces processes. This process-oriented model can make deployment and scaling straightforward when the application is already designed to be stateless and to restart cleanly.

It also asks the developer to learn the platform’s lifecycle. A process may restart during releases, configuration changes, daily cycling, or a fault. Local file writes do not become shared application storage. A scheduled task is not automatically exactly-once. When evaluating Heroku, model the whole process formation and the external services it depends on, rather than picturing one always-present server with a durable disk.


## Eco plan: a small pool with sleep behavior

Heroku lists Eco at $5 a month for 1,000 dyno hours shared across Eco dynos. The platform’s docs say Eco dynos sleep after 30 minutes of inactivity and wake when traffic returns. The plan can suit intermittent applications or development environments if the pool and startup delay are acceptable. It is not a free, always-on web tier, and the hour pool may be shared across applications and pipeline activity.

Track all consumers of the pool. Review apps, CI jobs, and other Eco dynos can use hours too. The official documentation says Eco hours are shared at account level, and unused balances or exhaustion have specific behavior. Check the current billing screen and the exact reset rules. If a public app must respond immediately, test the first request after idle time and decide whether the latency is acceptable before using Eco in production.


## Basic and Standard pricing

The public pricing page currently lists Basic at $7 per dyno per month and Standard-1X at $25. Standard-2X is listed at $50, with larger Performance options at substantially higher amounts. The usage documentation explains that common dyno charges accrue according to wall-clock time while a dyno is scaled above zero and are prorated to the second; the displayed monthly figure represents continuous use for a billing cycle. The Eco subscription follows a different monthly-pool model.

A real application usually needs more than one process. Add web dynos, workers, review apps, data plans, add-ons, and support requirements. If a worker runs continuously, its monthly amount is separate from a web dyno. If an app has a database, check that product’s own pricing, backup policy, and connection limits. Use the current Heroku calculator or account estimate rather than multiplying one dyno price and treating it as the whole bill.


## Filesystem behavior requires external persistence

Heroku’s official documentation is explicit that dyno filesystems are ephemeral. A dyno receives a fresh copy of the deployed artifact, and writes made while it runs are discarded when it stops or restarts. Dynos do not share their local files with each other. This design supports replaceable processes, but it means that a local upload folder, cache, or SQLite database cannot be treated as durable shared storage.

Put important records in a managed database or object store and test the application against the possibility of a restart at any time. Check how uploads are retried, how jobs behave after a worker is replaced, and whether a database transaction can be resumed safely. This is not an unusual flaw in one product; it is a core architectural property of the platform. An app designed for durable local disks may need changes before it can run correctly on Heroku.


## Restarts, releases, and reliability

Heroku says dynos can restart after a release, configuration or add-on change, process exit, scheduled cycling, or infrastructure fault. The developer documentation describes restart and crash policies, including backoff behavior for some runtimes. These rules are important when assessing reliability: the platform may replace a process, but the application must be able to start reliably and recover connections, jobs, and cached state.

Run a restart drill in a test app. Deploy a change, update a configuration variable, and intentionally terminate a process. Confirm how long a replacement takes, whether health checks keep bad code from receiving traffic, and which logs reveal the cause. For critical services, define a rollback procedure and a database migration plan. Do not interpret ‘managed platform’ as a promise that a particular application never experiences interruption.


## One-off dynos and scheduled work

One-off dynos are useful for migrations, maintenance commands, and scripts. Heroku’s documentation cautions that these executions are not guaranteed to happen exactly once in every rare case. A scheduler may start a one-off dyno with a time-to-live linked to its interval. This matters for any command that charges a card, sends an email, or changes an external record: a repeated execution must not duplicate the effect.

Design scheduled operations to be idempotent. Use a unique job key, record completion in a durable database, and make retries safe. Test timeout behavior and what happens if a command finishes its side effect but loses its response. Keep logs for troubleshooting and ensure the job has enough time for its intended workload. Heroku provides a way to run a command; the business-level guarantees need to be built into the application.


## Logs, metrics, and observability

Heroku streams and collates application and platform log events through its logging system, and its dashboard offers metrics and events for troubleshooting. A unified stream can help teams see messages from web processes, workers, and routing components in one place. Log availability and retention depend on the relevant plan or add-on, so buyers should verify how far back a record remains accessible and whether long-term archival is needed.

Avoid logging passwords, access tokens, private user content, or payment details. Check what application code emits and who can read the resulting logs. For incidents, capture request identifiers and timestamps without exposing unnecessary data. If the team relies on long-term audit history, send required events to an approved external system and test that delivery. Platform logs are operational evidence; they are not a replacement for application analytics or an audit system configured for your requirements.


## Security controls and plan boundaries

Heroku publishes security and compliance materials describing authentication and access controls, logging, encryption, backups, and differences among runtimes and plans. Some higher-tier capabilities, such as single sign-on, private networking, and specialized compliance options, may require a specific plan or product. A buyer should retrieve the actual reports and agreements relevant to the account instead of assuming every Heroku app has all enterprise controls enabled.

Protect account access with strong authentication and role-based invitations. Separate production credentials, restrict add-on permissions, and rotate exposed secrets. Review which runtime handles the data and how access to logs, backups, and support works. Heroku’s platform isolation and provider controls do not secure application code automatically. The application still needs secure authentication, validation, dependency management, and a responsible process for fixing vulnerabilities.


## Data, add-ons, and third-party responsibility

Heroku’s security policy explains that applications can use third-party add-ons and services. Those integrations expand what the system can do but also add providers, contracts, data flows, and support paths. A database plan, email add-on, object store, and payment integration may each have distinct retention and security terms. The fact that a service is discoverable from a Heroku catalog does not mean Heroku controls every aspect of its operation.

Maintain an inventory of connected providers and the information each receives. Confirm where production data is stored, how it is backed up, who can authorize an add-on, and what happens when a subscription ends. Check whether the vendor’s contract permits your intended data and use. A simple architecture diagram with account owner, provider, data type, and deletion method makes a procurement review much clearer than an undifferentiated list of integrations.


## Alternatives and migration considerations

Render, Railway, Fly.io, cloud provider application services, and self-managed containers may overlap with Heroku on application hosting. Each has a different process model, billing meter, persistent storage strategy, and operational burden. Compare the same app components and traffic level. Include migration labor, database exports, logging, private networking, build pipelines, scheduled jobs, and the service levels required by the organization.

An existing Heroku app may use platform-specific buildpacks, config vars, add-ons, or review-app behavior. Before switching, identify those dependencies and export the records that must move. Test the replacement in parallel, route a small amount of traffic, and keep rollback possible. A lower monthly server figure can be outweighed by conversion work or increased operational responsibility. The correct alternative is the one that meets the business requirement at a manageable full cost.


## Is Heroku a scam?

The official product pages describe Heroku’s dyno plans, usage billing, restarts, filesystem behavior, and security controls. The evidence reviewed does not support calling Heroku a scam. The title uses a buyer’s search phrase to introduce due diligence, not to state that Salesforce or Heroku committed fraud. A product can be legitimate while still being too expensive, unsuitable, or confusing for an individual customer’s needs.

If a charge seems wrong, retain the invoice, app formation, usage dashboard, plan description, and any support correspondence. Compare the number of dynos and hours to the billing rules for that period. Ask the provider to explain the bill using the account’s records. A sleeping Eco dyno, a continuously scaled Basic process, and a database add-on can create different line items. A clear reconciliation is more useful than inferring wrongdoing from a total that needs investigation.


## A buyer test for Heroku

Create a small application with one web process and one worker, then deploy it to a disposable test account. Confirm how code reaches a release, where configuration lives, how logs are viewed, and how to roll back. Let an Eco dyno sit idle and observe its wake behavior if you plan to use that tier. Restart a process and verify that the app does not depend on local files for important information.

Run a scheduled command with a harmless, repeatable action and simulate a retry. Check that duplicate execution does not create a duplicate business event. Estimate costs using the number of processes and expected hours, then compare them with the account’s usage records. This is a test plan, not a report of measured results from Roseram. It helps a buyer evaluate the workflow before attaching production records or customer traffic.


## Who should consider Heroku

Heroku may suit a team that wants a managed application runtime, a clear process model, integrated logs, add-ons, and a familiar deployment workflow. Eco may be useful for intermittent development work, while Basic or Standard dynos may be considered for services that need to remain available. Higher tiers provide more compute or organizational controls, at a correspondingly higher cost.

Teams with strict data-location, private-network, compliance, or availability requirements should verify the exact runtime and contract before committing. Applications that depend on persistent local storage need redesign. Teams that want very granular cloud infrastructure control may prefer a lower-level provider. Fit is not a referendum on the platform; it is a match between the documented offer and the application’s verified requirements.


## Roseram and Heroku are different tools

A Roseram workspace can assist with planning and creating software projects, while Heroku runs deployed application processes. These products can occupy different stages of a developer’s workflow, and neither automatically replaces the other. A team that uses an AI workspace should still review code, run tests, manage source control, and select a host. Heroku charges for its own dynos, data services, add-ons, and account features under its current terms.

Keep production ownership with the organization: source repository, domains, cloud account, credentials, and database exports. Avoid pasting private secrets into a prompt or a support request. Compare Heroku to the other hosts based on the same workload and recovery needs. This distinction is especially helpful when a marketing phrase suggests that one subscription includes both AI assistance and application hosting; verify each product’s actual scope separately.


## Heroku purchase checklist

Before buying, decide whether Eco’s shared hours and sleep behavior are acceptable, or whether an always-on dyno is necessary. Count every web, worker, scheduler, and review-app process. Price databases and add-ons separately. Check whether the organization needs Private Spaces, SSO, compliance documentation, custom support, or longer log retention, and confirm the required plan and contract.

Test restarts, deploy rollback, filesystem loss, a job retry, and database recovery before production. Set an account owner, billing reviewer, and incident contact. Document data exports and add-on dependencies. Save the current pricing and usage terms that apply to the account. These checks provide a practical basis for a decision without assuming the vendor will meet needs that are not included in the selected configuration.


## Final assessment of Heroku

Heroku remains a documented application platform with a useful process model, managed deployment, and a range of dyno types. Its current public pricing makes the distinction between a $5 Eco pool and per-dyno always-on plans clear, but the full bill includes the app’s process formation and associated data services. Ephemeral filesystems and restarts are core operational conditions; applications need durable external storage and retry-safe jobs.

This is a desk review, not a benchmark or a claim of hands-on experience. The official sources do not support a fraud finding. Confirm the current plan, calculate the entire application bill, and test the deployment lifecycle with data that can be discarded. A small, reproducible pilot is the strongest next step for a buyer deciding whether Heroku is a good fit for a specific service.


## Features and decision criteria

- Deploy applications to managed dynos using supported runtimes and containers
- Git and Docker-based workflows, releases, and configuration variables
- Unified application logs and a process model for web and worker dynos
- Add-ons and data services that extend application capabilities
- Higher tiers with scalability, dedicated compute, and organization controls

## Pricing considerations

Public pricing is for the listed dyno types and does not represent the full application bill. Data services, add-ons, team plans, private spaces, and other services may be additional. Heroku’s usage documentation says common dyno usage is based on wall-clock time while scaled above zero and prorated to the second; Eco is a monthly plan. Check the current calculator, included hour pool, app formation, and data-service terms before purchase.

## Frequently asked questions

### Is Heroku still free?

Heroku’s current public plans include paid Eco and dyno options rather than the historical free dyno tier many older articles describe. Eco is listed at $5 per month for a shared pool of 1,000 dyno hours. Other free trial or credit offers should be verified in the current account and pricing terms.

### What does the Heroku Eco plan include?

The official pricing and usage pages describe Eco at $5 per month with 1,000 dyno hours shared across Eco dynos, and Eco dynos sleep after 30 minutes of inactivity. Review apps and pipeline use can count toward the pool.

### Can files be stored on a Heroku dyno?

A dyno has an ephemeral filesystem. Heroku’s documentation says changes are discarded when a dyno stops or restarts. Store durable uploads and records in an appropriate external data service, and test the storage and recovery path.

### Does this review claim Heroku is fraudulent?

No. The SCAM Review title is a buyer due-diligence query. The official sources reviewed describe Heroku and its billing and platform rules; they do not establish fraud.

### Has Roseram benchmarked Heroku?

No. This is a desk review of public product, pricing, and developer documentation. The evaluation steps are suggested buyer checks, not performance measurements.


## Sources and further reading

- [Heroku official product pricing](https://www.heroku.com/pricing/)
- [Heroku usage and billing documentation](https://devcenter.heroku.com/articles/usage-and-billing)
- [Heroku dyno tiers](https://devcenter.heroku.com/articles/dyno-tiers)
- [Heroku dyno restart behavior](https://devcenter.heroku.com/articles/dyno-restarts)
- [Heroku security policy](https://www.heroku.com/policy/security/)
- [Heroku security and compliance features](https://devcenter.heroku.com/articles/security-and-compliance-resources-and-features)
- [Heroku website](https://www.heroku.com/)
- [saashub listing](https://www.saashub.com/heroku)

For the complete Roseram buyer guide, see [Heroku review](https://roseram.com/reviews/scams/heroku-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
