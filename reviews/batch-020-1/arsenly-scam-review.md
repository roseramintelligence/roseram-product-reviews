# Arsenly review: features, pricing and buyer considerations

**Last editorial review:** 2026-10-27  
**Category:** Web & API Security Reconnaissance Toolkit  
**Method:** Source-led desk review; no hands-on testing is claimed.

Arsenly, published by XowiaLabs, provides online reconnaissance, asset discovery, and utility tools for bug bounty hunters, penetration testers, and application security teams. The platform divides functionality between client-side utilities, limited free server lookups, and paid subscriptions that add REST API access and continuous monitoring. Operating on a periodic token model that refreshes across six-hour intervals, it offers passive domain discovery, DNS auditing, and payload generation while deliberately excluding active server-side port scans. This review evaluates its documented architecture, published token budgets, operational boundaries, and practical fit for security teams.

## Editorial verdict

This desk review does not establish that Arsenly is a scam or certify the business as safe. The cited publisher material describes an offer that can be evaluated against your requirements. Before paying, verify the seller, the current terms, any cancellation rules and the capabilities that matter to your use case. The discussion below separates publisher claims from suggested buyer checks; it does not report hands-on testing or an independent security audit.

## What to know before choosing Arsenly

Prospective buyers frequently enter phrases like Arsenly scam review when researching newly launched security dashboards. In offensive security and application testing, practitioners exercise natural caution before registering accounts, typing target scopes, or entering payment cards on unfamiliar portals. Searching for potential scams is a standard operational risk management practice rather than proof of commercial wrongdoing. Analysts want to confirm whether a cloud service delivers reliable intelligence, safeguards project targets, respects stated terms, and processes billing transactions properly without hidden surprises.

Arsenly is presented by XowiaLabs as a unified dashboard for web and application programming interface reconnaissance, targeting penetration testers, bug bounty hunters, and internal security teams. Because modern reconnaissance suites often process sensitive target scopes, assessing publisher authenticity is critical before incorporating an online tool into daily audit workflows. Buyers must distinguish between marketing claims and actual operational constraints.

Evaluating Arsenly requires examining its published documentation, listed utility sets, token allocations, and explicit scanning limitations. Evidence in this desk analysis is drawn strictly from first-party publisher pages reviewed in late 2026. This review does not conduct live laboratory scanning or verify business safety. Instead, it breaks down what the tool promises, highlights areas requiring independent verification, and outlines a practical test framework.


## Platform Scope and Core Functional Architecture

Arsenly structures its security tooling across seven defined categories, including reconnaissance and discovery, web security auditing, exploitation and out-of-band testing, payloads and wordlists, cryptography, encoders, and reporting. The primary interface organizes findings across designated project scopes, surfacing potential concerns like SQL injection, cross-site scripting, server-side request forgery, open redirects, and exposed access keys in JavaScript files. It aims to consolidate disparate asset discovery steps into a single web dashboard.

A central design choice in Arsenly is the division between client-side utilities and server-backed intelligence engines. Client-side tools execute directly inside the user's web browser. These nineteen standalone utilities handle common operational tasks, including HTTP request formatting between formats like Raw HTTP, curl, and fetch, JSON minification and validation, hash identification, and token generation. Because these utilities execute in the browser session, they do not consume platform server resources or deplete account token balances.

In contrast, server-side tools execute queries from Arsenly's central infrastructure. These tools handle external intelligence tasks such as passive subdomain enumeration, WHOIS queries, Domain Name System posture reviews, and vulnerability checks by querying remote feeds. Understanding this distinction allows prospective users to budget their operational usage, saving metered server allowances for broad discovery while using client tools freely.


## Reconnaissance Engines and Data Sourcing

External asset discovery forms the backbone of attack surface mapping. Arsenly's documentation indicates that its subdomain engine queries multiple public records and passive databases, including certificate transparency logs via crt.sh, open threat feeds, Shodan indexes, and historical web archives like the Wayback Machine. This passive multi-source approach identifies staging environments, legacy portals, and historical paths without sending noisy, aggressive traffic directly to the target host.

The dashboard also sorts discovered web paths into classified URL groups, separating application programming interface endpoints, authentication flows, sensitive administrative folders, and JavaScript assets. Additionally, the platform highlights sensitive secrets detected in public files, such as internal tokens or development configuration maps. This automated categorization seeks to accelerate the early reconnaissance phase by structuring raw target data into distinct analytical buckets.

However, passive discovery relies on the accuracy and freshness of third-party public repositories. Public certificate logs and web archive snapshots frequently contain decommissioned servers, stale hostnames, or outdated route mappings. Prospective buyers should not assume that all discovered endpoints are live. An essential buyer test involves pointing the tool at a known staging target to evaluate how cleanly the engine separates active hosts from historical noise.


## Token Mechanics and Operational Scarcity

Arsenly regulates server computing capacity through a structured token budget rather than simple flat query caps. The platform employs a six-hour replenishment cycle across its tiers. Free accounts receive 30 tokens every six hours, which equates to roughly 120 tokens across a full twenty-four-hour day. The Pro plan provides 150 tokens per six-hour window, yielding around 600 daily operations, while the Max plan removes the token budget entirely to offer unmetered scanning.

Server-side operations consume between two and six tokens per run depending on the computational intensity and external sources involved in the query. A straightforward domain record lookup requires fewer tokens than an intensive subdomain discovery job or vulnerability check. Once an account drains its active token pool to zero, server-side tools pause until the next six-hour reset window opens, unless the user elects to upgrade their subscription plan.

This quota system demands careful operational planning, particularly for bug bounty hunters assessing wide corporate scopes. While browser-based client tools remain available at all times without token deductions, automated batch lookups can rapidly consume allowances on entry-level tiers. Organizations evaluating the platform should track their typical daily query volume during onboarding to ensure the six-hour refresh schedule aligns with their testing routines.


## Documented Technical and Boundary Limits

A critical step in software due diligence is reviewing what a platform deliberately refuses to do. Arsenly explicitly documents that it does not run network port scans or launch active connecting probes from its central servers. The publisher notes that this boundary is strictly enforced to comply with acceptable-use policies established by its shared hosting infrastructure, which prohibit network scanning activities that third-party hosts could flag as abusive or hostile.

Rather than running direct host exploration from its central servers, Arsenly generates command-line instructions that analysts copy and execute locally from their personal workstations. Furthermore, to avoid search engine indexing issues and potential tool abuse, Arsenly excludes aggressive offensive utilities, such as unauthenticated reverse shell generators. These explicit boundaries indicate that Arsenly functions as a passive reconnaissance and web analysis hub rather than a fully automated offensive exploitation suite.

Buyers searching for a turnkey cloud platform that conducts raw TCP port scanning, network-level vulnerability checks, or direct penetration probing will find that Arsenly does not perform those server-side functions. Acknowledging these boundaries early prevents teams from confusing deliberate design choices with platform failures or misrepresentation.


## Subscription Plans and Commercial Terms

Arsenly outlines a tiered pricing structure intended to scale from casual evaluation to heavier professional consulting. The Free tier includes permanent access to all nineteen client-side utilities and eight free server tools, accompanied by 30 tokens per six-hour window, single-project tracking, and seven days of scan history retention. This free tier enables analysts to assess dashboard responsiveness and data organization without entering payment details.

For sustained professional work, Arsenly publishes Pro and Max tiers with monthly and annual billing options. Pro introduces scoped REST API access, continuous target monitoring alerts, three scoped projects, ninety-day history retention, and full access to sixteen professional server tools. The Max tier removes project limits and token quotas, offering unmetered scans, higher rate limits, and priority assistance. Billing transactions are processed via Stripe for international users and Razorpay for domestic payments within India, keeping credit card details isolated on third-party payment rails.

The publisher advertises a seven-day full refund policy on subscriptions, alongside self-service cancellations that stop renewals at the close of the current billing cycle. Yearly subscriptions are eligible for pro-rated refunds upon request. While clear refund policies and established payment gateways reduce purchasing friction, prospective buyers must still verify that billing cancellation and refund workflows operate as advertised during their initial week.


## Workflow Organization and Scope Controls

Security assessments require strict operational boundaries to ensure researchers do not inadvertently scan out-of-scope digital assets. Arsenly incorporates project scope controls into its dashboard, enabling users to bind target root domains, hostnames, and specific URL paths to dedicated workspaces. This layout helps analysts avoid querying client domains that fall outside formal testing authorizations or bug bounty rules of engagement.

Scan data retention varies depending on the subscription level. Free accounts store scan history for seven calendar days, Pro accounts retain logs for ninety days, and Max accounts provide unlimited retention. Regardless of tier, Arsenly supports scan data exports in common structured formats, including JSON, CSV, and Markdown. These standard formats allow analysts to extract discovered hostnames, vulnerability observations, and endpoint trees without friction.

Structured export options prevent lock-in and simplify operational reporting. Security professionals can ingest raw JSON output into custom analysis scripts or import Markdown tables directly into client-facing vulnerability deliverables. During early evaluations, technical teams should inspect the consistency of exported fields to confirm they match downstream reporting and storage schemas.


## Developer Interfaces and API Automation

Application security workflows increasingly depend on programmatic automation to track shifting web assets. Arsenly provides a documented REST API on its Pro and Max subscriptions, allowing security engineers to trigger scan profiles, query asset indices, and extract findings directly from terminal scripts or build tools. Access is controlled through scoped API keys, enabling teams to limit permissions based on specific operational needs.

Programmatic connectivity enables teams to incorporate Arsenly's passive reconnaissance into continuous deployment pipelines or scheduled cron jobs. For example, an application security team can establish nightly queries against corporate primary domains to identify newly exposed staging portals or forgotten subdomains before external parties locate them. The API returns standardized data structures that reflect the visual web interface.

When evaluating the platform's API, engineers should review published endpoint rate limits and test response payload consistency. Because rate limits vary between tiers—enforcing specific tool caps on Pro while raising thresholds on Max—developers building custom automations must account for these constraints by implementing structured retry logic and error-handling routines.


## Comparative Analysis: Market Alternatives and Tool Stacks

Security practitioners operate across an established ecosystem of commercial security platforms and community-maintained open-source utilities. Traditional local intercepting proxies like Burp Suite Professional and OWASP ZAP dominate deep manual application testing, session manipulation, and proxy-based fuzzing. Arsenly does not replace these local interception proxies; instead, it serves as an early-stage discovery hub for gathering subdomains, auditing DNS posture, and converting request payloads before active testing begins.

Compared to broad external attack surface management platforms, Arsenly positions itself as a streamlined, self-directed alternative for independent practitioners and boutique consultancies. Large enterprise discovery platforms often demand expensive annual contracts, mandatory sales calls, and complex onboarding, whereas Arsenly provides self-service onboarding, transparent monthly plans, and a collection of free client utilities requiring no registration.

Conversely, teams that maintain customized open-source command-line toolchains—combining utilities like Sublist3r, Amass, httpx, and shell scripts—already possess capable reconnaissance pipelines. Arsenly appeals primarily to specialists who prefer a centralized visual dashboard, multi-source data consolidation, and ready-to-use web utilities over the administrative burden of maintaining independent script collections on private virtual servers.


## Coordinating Specialist Tooling with Project Workspaces

Conducting vulnerability research and external surface audits requires maintaining clear distinctions between specialized reconnaissance tooling and broader software coordination. While utilities like Arsenly gather subdomain records, evaluate DNS records, and format payload strings, engineering teams still require structured environments to plan code refactoring, draft implementation updates, and organize remediation work across their applications.

Engineering teams managing application codebases often use a dedicated project workspace to plan, draft, and revise their software architectures as security findings emerge. Within a Roseram workspace, developers can coordinate project roadmaps, organize technical specifications, and manage application revisions alongside raw assessment data. The publisher of this review maintains a commercial interest in Roseram, which operates as a general software planning and development workspace rather than a dedicated security scanning utility.

Preserving clear operational boundaries between security reconnaissance utilities and software project platforms helps teams remain organized. By pairing purpose-built discovery tools for external asset analysis with centralized project workspaces for application planning and software construction, development organizations maintain an orderly progression from early discovery through patch completion.


## Structured Buyer Evaluation Plan

To evaluate Arsenly methodically without unnecessary financial commitment, technical buyers should execute a staged, four-step verification plan. The initial step focuses entirely on the nineteen client-side utilities, accessible without creating an account or entering credentials. Testers should run sample inputs through the HTTP request converter, JSON workbench, and hash identifier to evaluate execution speed, interface clarity, and data accuracy across basic day-to-day conversion tasks.

The second step evaluates the platform's passive reconnaissance capabilities on a known, authorized corporate domain using the Free tier's token allowance. Testers should compare discovered hostnames, historical URL paths, and DNS posture records against their organization's internal inventory. This comparison illustrates how effectively Arsenly filters inactive records, how cleanly it aggregates feeds like crt.sh and Shodan, and whether the thirty-token replenishment window supports their initial reconnaissance workflow.

The third step requires assessing data export fidelity by downloading findings in JSON, CSV, and Markdown formats to ensure output structures parse cleanly into internal documentation tools. Finally, teams considering a paid tier should take advantage of the advertised seven-day refund window to evaluate REST API endpoints, key management workflows, and notification alerts under realistic testing volumes before committing to long-term subscription renewals.


## Desk Due Diligence Synthesis

This desk review indicates that Arsenly operates as an accessible web security and passive reconnaissance toolkit rather than an unverified scam. Developed by XowiaLabs, the platform provides clear public documentation regarding its token budgets, payment routing via Stripe and Razorpay, and explicit operational limitations. It offers immediate utility by making nineteen browser-based client tools available without registration, while reserving server-side enumeration for tiered token allowances.

The platform is functionally targeted toward independent bug bounty hunters, solo penetration testers, and small security teams looking for a consolidated reconnaissance dashboard. However, buyers requiring active network port scanning, automated TCP probing from cloud servers, or unrestricted scanning on entry-level tiers should heed the platform's documented constraints. Arsenly explicitly delegates active network exploration to locally executed command lines to adhere to shared hosting policies.

Prospective users should base their procurement decisions on verified operational alignment. By testing the free browser tools, monitoring token consumption across the six-hour refresh window, and validating passive asset accuracy on known staging environments, security professionals can objectively confirm whether Arsenly meets their technical requirements.


## Features and decision criteria

- Collection of nineteen browser-based client utilities including HTTP request converters, encoders, decoders, and text comparers.
- Passive domain and subdomain discovery aggregating public records from sources such as crt.sh, Shodan, and historical web archives.
- Token-metered server operations refreshing across six-hour windows across tiered account levels.
- Scoped REST API access supporting programmatic queries and scan automation on paid subscriptions.
- Reconnaissance data export options supporting JSON, CSV, and Markdown file formats across all tiers.

## Frequently asked questions

### Does Arsenly perform direct port scans against target servers?

No. Arsenly explicitly documents that it does not run port scans or active connecting network probes from its central servers to comply with shared hosting acceptable-use policies. When active target probing is required, the platform outputs command-line syntax for analysts to execute locally on their own machines.

### How does the token consumption model work on Arsenly?

Server-side queries consume between two and six tokens per run depending on the computational complexity of the tool. Free accounts receive 30 tokens every six hours (roughly 120 per day), Pro accounts receive 150 tokens every six hours (around 600 per day), and Max accounts receive unmetered access.

### What export formats are available for scan findings?

According to the publisher's plan comparison table, scan data and findings can be exported across all account tiers using JSON, CSV, and Markdown file formats.

### What refund policy applies to paid subscriptions?

Arsenly advertises a seven-day full refund policy from the initial transaction date for any subscription. Cancellations halt billing at the conclusion of the active period, with pro-rated refunds available upon request for annual commitments.


## Sources and further reading

- [Arsenly website](https://arsenly.com/)
- [Arsenly official publisher reference](https://arsenly.com/pricing)
- [saashub listing](https://www.saashub.com/arsenly)

For the complete Roseram buyer guide, see [Arsenly review](https://roseram.com/reviews/scams/arsenly-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
