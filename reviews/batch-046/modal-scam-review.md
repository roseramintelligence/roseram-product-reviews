# Modal review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Serverless cloud compute and AI infrastructure  
**Method:** Source-led desk review; no hands-on testing is claimed.

Modal is a serverless platform for running containerized Python functions, web services, scheduled jobs, GPU workloads, and isolated sandboxes. Its pricing is usage-based for compute, while the Team plan adds a monthly subscription and larger included compute credit. The product documentation distinguishes functions, sandboxes, servers, and model APIs because their cost and data retention differ. Buyers should size resources, set budgets, understand startup and idle behavior, and choose the right product surface for their workload before production use.

## Editorial verdict

Modal’s official pricing, billing, security, and terms pages identify a commercial cloud compute service and explain how it charges and handles different workload types. Those materials provide no basis for calling Modal a scam. This is a source-led desk review, not a load test, security audit, or guarantee of availability. A practical evaluation should model the actual runtime, confirm what remains after the job finishes, use spend controls, and distinguish compute billed by the second from model APIs billed by tokens.

## What Modal sells: execution infrastructure

Modal is best understood as a way to package Python workloads and run them on managed cloud resources. The documented building blocks include functions, web functions, scheduled functions, servers, endpoints, queues, and sandboxes. A team writes or adapts the application, specifies resource requirements, and deploys it through Modal’s tools. This is an infrastructure product; it does not automatically provide a finished customer application, data model, authentication policy, or operations team.

That distinction matters when judging the value of a demo. A notebook that runs one time is not the same as a deployed service that handles traffic, reports errors, controls spend, and recovers from failure. For a fair review, list what your team must still build: request validation, authentication, business logic, monitoring, data storage, secrets management, and user support. The platform may reduce infrastructure work, but the application owner remains responsible for the job the service performs.


## The product surface changes the answer to key questions

Modal’s documentation treats Functions, Sandboxes, Servers, Shared Endpoints, and Dedicated Endpoints as separate products. Their startup patterns, scaling behavior, pricing units, and retention rules are not interchangeable. A scheduled task that runs briefly may fit a function, while a continuously available API may fit a server or endpoint. A sandbox is designed for a different isolation and execution model than a normal web service.

Before selecting a pattern, draw the request path from the user to the workload and back. Mark where input is stored, where code executes, how results are returned, and which logs or files survive the run. This small diagram can prevent a costly mismatch. It also makes the platform review specific: you are evaluating a known service shape, rather than assuming one short description applies to every feature bearing the Modal name.


## Containerized Python is flexible but requires ownership

Modal positions its platform for containerized Python applications, including machine-learning inference, training, data pipelines, and compute-heavy jobs. Teams can specify the software environment and resources in code, which can make deployments easier to reproduce than a manually configured machine. The portability benefit depends on the team keeping image definitions, dependencies, and deployment configuration under version control.

A maintained runtime is still a software project. Pin dependencies, rebuild images on a planned schedule, scan packages, and test that a previous image can still be redeployed. Keep the deployment definition separate from secrets and customer data. Assign an owner for dependency upgrades and runtime incidents. If a workload depends on a specific GPU library or kernel behavior, verify it in the actual deployment region rather than assuming every model or package is available in every configuration.


## Cold starts and resource requests belong in the trial

Serverless convenience can come with startup time when a container has to launch or scale from zero. Modal’s documentation covers container lifecycle and scaling, but the practical delay depends on the image, model download, region, resource type, concurrency, and request pattern. A small local demonstration cannot reveal what a large model or a burst of traffic will feel like to a customer.

Run a representative pilot with both quiet periods and a traffic burst. Measure first-request delay separately from warm request latency. Include image build and model download time where they affect the user experience. Set a target for acceptable response time and decide what the interface should show during startup. If the cost of keeping a service warm is justified by a response-time requirement, include it in the forecast instead of describing scale-to-zero as a free performance improvement.


## GPU choice should follow the workload, not the headline rate

The pricing page lists per-second rates for individual GPUs, including an H100 at US$0.001097 per second and an L4 at US$0.000222 per second at the time checked. Those numbers are not a complete task price. A running container also uses CPU and memory, and the time to load a model or process an input affects the billed duration. Selecting a cheaper accelerator can also change throughput or require a different concurrency plan.

Benchmark the smallest configuration that meets your acceptance criteria, then compare one step above and below it. Record output quality, time to first response, throughput under realistic load, memory headroom, and total cost per successful task. A GPU’s theoretical speed is not a substitute for an end-to-end measurement. Keep the model version, batch size, sequence length, and region fixed while comparing; otherwise, the numbers do not describe the same workload.


## Starter credits make a pilot easier but do not cap every charge

The current Modal pricing page lists a Starter plan at no monthly subscription charge with US$30 in monthly compute credits. It shows Team at US$250 per month with US$100 of monthly compute credits, and Enterprise as custom. The precise seat, concurrency, and included usage rules should be confirmed on the live account page before a purchase. Included compute is not the same as a general token allowance for every AI model exposed by the platform.

The same pricing documentation separates model APIs from compute. Model API tokens are billed per token from the first request and do not use the Starter compute credit. A workload that combines a GPU function and a model API may therefore create two cost lines. Write those lines separately in the budget. If a subscription includes a credit, treat it as a deduction against eligible usage, not a promise that your particular workload will stay below it.


## Build a cost estimate from active seconds and stored data

Modal publishes rates for CPU, memory, GPUs, volumes, and network egress. Its FAQ explains that compute credits apply to functions and sandboxes billed by the second, while model APIs use token pricing. A volume can continue to incur charges while data remains stored, and network traffic beyond an included allowance can add another line. A task estimate based only on the GPU rate leaves out the rest of the resource bill.

Use a workload spreadsheet with expected invocations, average active duration, CPU cores, memory, GPU type, storage size, and network transfer. Include retries and initialization. Then compare the estimate with a capped real run. The platform’s spend budget can help constrain risk, but monitoring should still alert the owner before a busy period exceeds the planned amount. Confirm whether environment-level or workspace-level limits cover the specific service and whether an action is stopped or merely reported when the threshold is reached.


## Choose the product based on what data it retains

Modal documents different retention by product. Inputs and outputs from Functions may be kept for up to seven days. Request and response payloads for Servers, Dedicated Endpoints, and Shared Endpoints are described as not stored and proxied directly to the serving container. Logs can remain for one day on Starter, 30 days on Team, or a configurable period on Enterprise. Files placed in Volumes persist until the customer removes them.

A zero-retention statement for one endpoint should not be generalized to logs, files, snapshots, or all Modal workloads. The application can also write prompt content to stdout or stderr, which then becomes a log under the plan’s retention period. Inspect the code for sensitive logging, decide how long stored results should remain, and test deletion. A data map with product names, content types, retention periods, and owners is a practical control for privacy reviews.


## Security depends on the shared responsibility boundary

Modal describes TLS 1.3 in transit and encryption at rest, plus platform controls such as access management, API tokens, role-based access control, and secret storage. Its security guide also makes the customer responsible for identities, token rotation, application code, images, dependencies, and endpoint authentication. Those controls form a shared responsibility arrangement; the presence of a cloud security feature does not configure it for a particular organization.

Use least privilege for deployment identities, rotate credentials, and keep secrets out of images and logs. Decide which endpoints are public, authenticate requests, and restrict network egress for workloads that execute untrusted code. Add timeouts and resource limits. Modal documents Restricted Functions and Sandboxes as isolation primitives for untrusted workloads, but the customer must select and configure them appropriately. Review the current Trust Center and contractual terms if a specific compliance control is required.


## Reliability needs monitoring and a recovery path

A serverless platform can scale compute without requiring a team to operate each machine, yet the deployed application can still fail because of bad inputs, exhausted quotas, a dependency change, unavailable model capacity, or a downstream outage. The terms do not promise that every service runs without interruption. A buyer should define what happens to a user request when a function times out or a partial result is produced.

For a pilot, add structured status reporting, a correlation ID, and an alert for errors and spend. Make retries idempotent so a repeated request does not create duplicate work or charges where that is avoidable. Save enough metadata to investigate the failure while avoiding sensitive payloads in logs. Decide whether requests go to a queue, fail visibly, or use a tested fallback. Recovery behavior is part of product fit, not a detail to add only after the first incident.


## Budget controls should be paired with measurement

Modal’s billing guide describes monthly billing, incremental automatic charges after usage thresholds, and workspace- or environment-level spend budgets. Those features give a team levers for managing a pay-as-you-go platform, but they do not remove the need to understand the workload. The user who sets a limit should know what happens when it is reached and whether that behavior is compatible with the application’s availability needs.

Use separate environments for development and production, assign an accountable owner, and review usage before a release increases traffic. Tag each deployment or task class so costs can be attributed to the application that caused them. Set a budget based on a measured pilot plus a deliberate buffer, not an arbitrary round number. Keep the invoice and the usage dashboard in the purchasing record so finance can reconcile actual resource consumption with the initial estimate.


## A buyer test for a real workload

Start with one representative job and a clear definition of done. Include a routine input, a large input, a malformed input, and a case that needs a timeout. Deploy the same code and container you expect to use later, then measure first-run latency, warm latency, resource consumption, output quality, and the behavior after a failure. Save the deployment configuration and exact image revision so the result can be repeated.

Repeat the run at the expected concurrency and a modest peak above it. Confirm how many simultaneous containers the plan allows, whether the chosen region has the needed resource, and whether the service remains within the budget. Check the logs and deletion behavior after the task completes. The sources cited here establish product documentation and public prices; they do not provide a Roseram benchmark or guarantee that your own program will achieve a particular response time.


## Alternatives and when Modal may fit

Compare Modal with the cloud provider you already use, a specialized inference service, and a self-managed container platform. Match the workload, region, security requirements, and traffic profile. Include engineering time, GPU capacity, idle behavior, deployment rollback, observability, support, and data retention. A lower resource rate may not make the full operation less expensive if your team must build more surrounding infrastructure.

Modal may suit a Python team that wants to deploy bursty or compute-heavy jobs and pay for active resources, provided it is comfortable owning application code and configuration. It may be a weaker fit if your organization requires a control that is available only under a custom contract or another cloud environment. A software-building workspace is a separate tool, not a cloud hosting substitute. Decide based on the job and validate it with a bounded, budgeted pilot.


## Scheduled work and retries need business-level safeguards

Scheduled functions can move recurring work out of a manually operated machine, but the schedule is only one part of a dependable job. State which time zone defines the run, what happens when two executions overlap, and how missed or delayed work is recovered. Add an idempotency key for tasks that may be retried. A job that charges a card or sends a customer email should not repeat the side effect simply because a worker was restarted.

During a pilot, deliberately make a task fail halfway through and then inspect its state. Confirm how logs, outputs, retries, and alerts appear to the operator. Decide how a human can pause future work and how to resume it without duplicating completed steps. The scheduled function may run as documented, but the application owner still decides what the business process means when a task is late, incomplete, or repeated.


## Isolation is a design choice, not a default assumption

A cloud container can execute arbitrary code, and AI-assisted applications may run user-submitted scripts or packages. Modal documents Sandboxes and Restricted Functions for isolating untrusted workloads. A team should choose the primitive that matches its threat model and then configure timeouts, CPU and memory bounds, filesystem access, network egress, and credential separation. The product’s existence does not mean a regular function is automatically safe for every user-provided program.

Test the boundaries with harmless probes before accepting outside input. Verify that a job cannot read another user’s files, access deployment secrets, or make unexpected network calls. Keep dependencies pinned and review the base image. Make logs useful for incident response without collecting private task content. If the workload must meet a formal security requirement, review the current security materials and contract with the person responsible for compliance rather than treating an isolated demo as approval.


## Workspace ownership and migration deserve a plan

A production deployment should have an organization owner, at least one backup administrator, and a written process for rotating credentials. Keep source code, deployment configuration, container definitions, and operational notes in a repository that the company controls. Confirm how access is removed when an engineer leaves and how a new operator can reproduce a release. This continuity work matters even for a compact serverless application.

Ask which parts of the system can move to another container host and which use Modal-specific APIs or storage. Export a sample volume, configuration, and result as part of the pilot. Estimate the engineering effort to recreate secrets, scheduled work, queues, and monitoring elsewhere. A portable workload may be valuable even if you never migrate. Roseram workspace can help draft and revise software, but it does not own the Modal account, deploy the production service, or guarantee that a migration will succeed.


## Features and decision criteria

- Python-based serverless functions and web applications
- On-demand CPU, memory, GPU, and container resources
- Scheduled functions, job queues, and containerized deployment workflows
- Sandboxes for isolated code execution with separate pricing and controls
- Workspace and environment budgets for managing compute spend

## Pricing considerations

The official pricing page was checked on 2026-11-18. It lists Starter at $0 plus compute with $30 monthly compute credits and Team at $250 plus compute with $100 in credits; confirm current seat, concurrency, and included-usage terms before ordering. GPU, CPU, memory, volume, network egress, sandbox multipliers, and model API tokens can affect total cost. Model APIs are billed per token from the first request and are not covered by compute credits. Workspace and environment budgets can help limit out-of-pocket spend.

## Frequently asked questions

### Is Modal a scam?

The official company pages reviewed here identify a cloud compute service and document its pricing, billing, security, and contractual terms. They do not establish fraud. This review makes no fraud allegation and does not claim to have load-tested or audited Modal. The SCAM Review label is a due-diligence query for prospective buyers.

### Does Modal Starter mean all usage is free?

No. The current pricing page lists $30 in monthly compute credits for Starter, but compute beyond the included amount can be billed, and model API tokens are billed separately from the first request. Resources such as GPUs, CPU, memory, storage, egress, and sandboxes can also affect the bill.

### Does Modal have zero data retention?

The answer depends on the product. Modal documents zero retention for request and response payloads served through Servers, Dedicated Endpoints, and Shared Endpoints. Inputs and outputs from Functions may be kept up to seven days, logs have plan-specific retention, and files stored in Volumes persist until the customer deletes them.

### Can Modal safely run untrusted AI-generated code?

Modal documents Restricted Functions and Sandboxes as isolation primitives and advises customers to apply egress restrictions, resource limits, timeouts, and secret separation. A team still needs to configure these controls correctly and review its own code, images, dependencies, and data flows.

### Has Roseram benchmarked Modal?

No benchmark, deployment trial, or measured reliability claim is made. This is a desk review of official product and policy pages. The proposed buyer checks are not presented as test results.


## Sources and further reading

- [Modal official pricing](https://modal.com/pricing)
- [Modal billing guide](https://modal.com/docs/guide/billing)
- [Modal security and privacy documentation](https://modal.com/docs/guide/security)
- [Modal terms of service](https://modal.com/legal/terms)
- [Modal GPU documentation](https://modal.com/docs/guide/gpu)
- [Modal website](https://modal.com/)
- [saashub listing](https://www.saashub.com/modal)

For the complete Roseram buyer guide, see [Modal review](https://roseram.com/reviews/scams/modal-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
