# BunkerWeb review: features, pricing and buyer considerations

**Last editorial review:** 2026-10-27  
**Category:** Web Application Firewall  
**Method:** Source-led desk review; no hands-on testing is claimed.

BunkerWeb is an open-source web application firewall and reverse proxy distributed under the AGPLv3 license. It places security controls in front of websites, applications, and APIs, running on Linux, Docker, or Kubernetes. Alongside its free core and external plugins, the project offers commercial self-hosted tiers and managed cloud options. A systematic buyer evaluation must verify whether its dual-license architecture, rule inspection overhead, and plugin ecosystem fit existing infrastructure, while testing actual false-positive rates and operational support commitments against business requirements.

## Editorial verdict

This desk review does not establish that BunkerWeb is a scam or certify the business as safe. The cited publisher material describes an offer that can be evaluated against your requirements. Before paying, verify the seller, the current terms, any cancellation rules and the capabilities that matter to your use case. The discussion below separates publisher claims from suggested buyer checks; it does not report hands-on testing or an independent security audit.

## What to know before choosing BunkerWeb

BunkerWeb’s cited material describes a web application firewall and related deployment options. Evaluating that offer means comparing the documented rules, management workflow, support terms and commercial feature boundaries with the services you operate. The test plan should examine both blocked attacks and ordinary requests that must continue to work. Technical teams need to verify whether a security solution truly delivers on its advertised capabilities or whether critical operational features are withheld behind aggressive paywalls. They need to know if the product creates severe operational instability, introduces unmanageable false positives, or fails to deliver prompt support when production services experience sudden outages.

Evaluating a web application firewall demands extra caution because placing a broken or poorly implemented proxy in front of production services can cause immediate downtime. Buyers want to determine if the vendor's performance metrics are realistic, whether the open-source AGPLv3 code can be operated safely in production without mandatory enterprise contracts, and whether the company's subscription fees match the actual level of maintenance provided. This editorial review dissects the publicly documented product details, technical architectures, plugin distinctions, and commercial terms provided by the publisher. It frames the product through balanced due diligence, presenting concrete steps buyers should execute to verify the software themselves rather than accepting publisher promises at face value.

It is important to emphasize the evidentiary boundaries of this assessment up front. The findings in this guide are derived strictly from publisher pages and documented technical releases examined as of October 2026. Publisher statements, marketing claims, and partner testimonials cannot substantiate third-party audit verification, independent stability proofs, or absolute protection against cyber threats. Buyers must treat all published specifications as claims requiring internal testing. Throughout this document, technical features are evaluated based on how they operate within a standard web stack, providing engineering teams with an objective framework to test performance, license compatibility, and false-positive handling inside their own isolated staging environments.


## Architectural Foundation and Core Reverse Proxy Mechanics

BunkerWeb is built to act as a security-focused reverse proxy that sits directly between external clients and internal backend web services. According to its architectural documentation, the software terminates incoming HTTP and HTTPS connections, examines request headers and payloads, and applies configured security policies before routing legitimate traffic to backend services. The tool can be deployed on standalone Linux distributions, managed via container runtimes using Docker or Docker Swarm, and orchestrated at scale within Kubernetes clusters. By acting as the sole entry point, it attempts to centralize security policy management, SSL certificate handling, and inbound traffic inspection in a single operational layer.

The software incorporates multiple open-source web application firewall engines within its modular structure. The core distribution provides a ModSecurity integration pre-configured with the OWASP Core Rule Set, while an external plugin integration offers the alternative Coraza WAF engine. Requests hitting the proxy undergo inspections that look for recognizable exploit patterns, including SQL injection, cross-site scripting, and generic path traversal attempts. Because it operates at the proxy layer, BunkerWeb can enforce additional network-level controls such as IP blacklisting, DNS-based blackhole list lookups, country-based geo-blocking, reverse DNS validation, and rate limiting to blunt basic volumetric denial-of-service attempts.

In addition to filtering payload anomalies, BunkerWeb handles fundamental proxy responsibilities that would otherwise require independent web servers. Its core plugins include automatic issuance and renewal of TLS certificates through Let's Encrypt, alongside support for static custom certificates and mutual TLS authentication. It can inject custom security headers, serve caching instructions to downstream clients, compress traffic using Brotli or Gzip, and manage reverse proxy routing to upstream targets or local PHP-FPM sockets. This consolidated proxy approach reduces the number of disparate network hops, though it places tremendous operational dependency on BunkerWeb's stability, since any crash or misconfiguration immediately halts all incoming application traffic.


## Open Source AGPLv3 Governance and Proprietary PRO Features

A critical area of evaluation for prospective enterprise adopters is BunkerWeb's licensing model. The core software is distributed under the GNU Affero General Public License version 3. The AGPLv3 is designed to preserve software freedom by mandating that any modifications made to the source code must be made publicly available if the modified software is accessed over a network. For organizations building internal developer tooling or hosting private backends, the AGPLv3 may align with corporate policies. However, for organizations that embed proxy tools into proprietary commercial software distributions or commercial software-as-a-service offerings, AGPLv3 terms can raise compliance concerns that corporate legal departments must carefully review.

Beyond open-source licensing concerns, buyers must pay close attention to the functional boundaries between the community version and the commercial PRO tiers. The publisher divides BunkerWeb into core free plugins, external free plugins requiring manual configuration, and proprietary paid PRO plugins. Core plugins cover essential capabilities like ModSecurity, Let's Encrypt, HTTP basic authentication, and local data backups. External integrations extend this to include external scanners like ClamAV, VirusTotal APIs, CrowdSec bouncers, and notification webhooks for Discord, Slack, and Matrix. These free capabilities provide basic protection, but buyers must recognize that critical enterprise administrative tooling is reserved exclusively for commercial tiers.

The vendor's commercial PRO tier introduces features that many enterprise environments consider non-negotiable. Upstream load balancing with health checks, advanced anti-DDoS traffic filtering, S3-compatible remote backup plugins, and reverse proxy caching are restricted to paid tiers. Crucially, enterprise access control and identity federation, including OpenID Connect, LDAP single sign-on, and user role management for the web interface, require a PRO subscription. Even the automated Easy Resolve tool, which streamlines false-positive remediation, is a commercial feature. Prospective buyers must carefully audit their technical requirements to avoid assuming that advanced governance, SSO, and cluster management are provided in the free open-source base.


## Commercial Pricing Tiers and Contractual Value Dynamics

BunkerWeb structures its commercial offerings across three self-hosted tiers and a dedicated SaaS cloud option. For teams needing commercial features on their own infrastructure, the vendor publishes the Standard Shield plan at 49 euros per month. This tier provides self-hosted PRO features and relies on active community support, making it aimed primarily at small-to-medium businesses or early-stage development teams. The next tier, Enterprise Fortress, is priced at 149 euros per month and targets multi-site organizations and sensitive industries. It includes priority technical support directly from core maintainers and claims readiness for critical production environments. Both self-hosted plans include an advertised 30-day free trial.

For complex enterprise architectures, the vendor lists a Custom Sentinel package. This tier moves beyond standardized subscriptions into bespoke proposals that include custom development, specialized cyber security consulting, customized integration services, and defined support service-level agreements. Pricing for Sentinel is quote-based and requires direct engagement with the publisher's sales representatives. When analyzing these self-hosted tiers, buyers should note that published pricing covers software licensing and support access, but does not include the underlying compute, storage, bandwidth, and administrative labor required to host and maintain the proxy cluster on internal infrastructure.

Organizations that prefer to avoid managing infrastructure can consider BunkerWeb CLOUD, the vendor's fully managed SaaS offering. Published figures indicate that the Essential cloud package starts from 639 euros per month. This managed tier provides the WAF as a turnkey service operated by the vendor's engineering staff, granting full access to PRO features and a centralized monitoring platform. Custom cloud deployments with bespoke resource allocations, specialized providers, and dedicated SLAs are also available via direct quotation. Buyers must balance the significant cost step from self-hosted tiers to cloud tiers against their internal staff capacity to patch, tune, and monitor self-hosted reverse proxies.


## Plugin Architecture and Security Automation Mechanisms

The primary functional strength highlighted in BunkerWeb's design is its plugin architecture. Rather than forcing administrators to hand-craft monolithic web server configurations, the platform relies on discrete modules to handle specific security tasks. For instance, the Antibot plugin challenges suspicious visitors using automated JavaScript execution tests or CAPTCHA prompts to filter non-human traffic before it reaches backend application handlers. Similarly, the Bad Behavior plugin monitors incoming traffic patterns and automatically blocks IP addresses that generate an excessive volume of HTTP error codes over a designated time threshold.

Threat intelligence sharing is implemented through plugins like BunkerNet, which connects individual BunkerWeb instances to a collaborative threat-sharing network. System administrators can also activate the CrowdSec bouncer plugin to consume community-driven blocklists and block malicious actors identified across the wider CrowdSec ecosystem. To restrict attack surfaces further, the platform provides country-based geo-blocking, reverse DNS validation, ASN filtering, and integration with remote DNS blacklists. File upload protections can be introduced by pairing external plugins with ClamAV engines or querying third-party intelligence services like VirusTotal via API keys.

This modular design also encompasses daily operational tooling. The Backup plugin automates scheduled local archives of configuration states, while the Database plugin coordinates how BunkerWeb stores settings across distributed instances. Cluster coordination is managed using Redis to synchronize dynamic client bans, active sessions, and shared cache records across multiple proxy nodes. While this modularity allows teams to assemble an adaptable defense pipeline, it introduces complex dependency chains. A misconfigured Redis backend or a failing external DNSBL server can introduce latency spikes or unintended proxy fail-overs, reinforcing the need for exhaustive integration testing during deployment.


## Operational Suitability Across Developer and Production Profiles

BunkerWeb presents distinct trade-offs depending on an organization's size, operational maturity, and compliance posture. For solo developers, hobbyists, and non-profit projects operating on modest budgets, the free AGPLv3 version is a practical candidate for evaluation. Deploying a single Docker container running BunkerWeb in front of a handful of web applications gives independent administrators automated Let's Encrypt certificates, baseline ModSecurity inspection, and integrated rate limiting without licensing fees. For these users, managing occasional false positives through configuration files and relying on community Discord channels is often an acceptable trade-off.

Small to medium businesses operating commercial software stacks face a different calculation. The Standard Shield plan at 49 euros per month provides access to the web UI's advanced features, but it explicitly relies on community support rather than guaranteed vendor response times. Teams without dedicated internal devops personnel may struggle if an undetected rule update blocks paying customers. Conversely, organizations with experienced infrastructure engineers can use the 30-day trial to assess whether the PRO features deliver measurable efficiency gains over standard NGINX or Traefik configurations paired with independent ModSecurity modules.

In enterprise, multi-site, and regulated industries like healthcare or financial technology, suitability depends heavily on support agreements and governance controls. The Enterprise Fortress plan at 149 euros per month provides priority technical support from core maintainers, which is essential when proxy incidents threaten strict uptime obligations. However, enterprises must evaluate whether the vendor's support team provides around-the-clock incident response or operates within restricted business hours. Furthermore, enterprise legal teams must verify that using open-source components with commercial plugin overlays complies with internal vendor risk guidelines and third-party software licensing policies.


## Critical Limitations, False Positives, and Failure Modes

Like any security system built on top of deep packet inspection, BunkerWeb possesses inherent limitations that buyers must prepare to mitigate. The most frequent operational challenge stems from WAF false positives. ModSecurity paired with the OWASP Core Rule Set is notoriously strict; legitimate REST API requests, complex JSON payloads, or administrative form submissions containing code snippets can easily trigger false alarms and block genuine users. While BunkerWeb offers an Easy Resolve feature in its PRO tier to remediate false positives from the management view, teams using the open-source base must manually identify matching rule IDs and write configuration exclusions.

Another operational limitation involves resource consumption under high-volume throughput. Terminating TLS, parsing HTTP headers, running regex-heavy rule sets, executing bot challenges, and calculating rate limits introduce CPU and memory overhead. In high-traffic environments, poorly tuned proxy nodes can experience latency degradation or memory pressure. While published testimonials describe instances handling large request volumes on moderate hardware, buyer performance will vary wildly depending on payload sizes, rule complexity, and whether CPU-intensive modules like ClamAV scanning or deep payload inspections are active.

Finally, architectural single-point-of-failure risks must be planned for carefully. If an automated configuration reload fails or a corrupted database state prevents BunkerWeb from initializing, the reverse proxy halts all inbound traffic to downstream applications. The software documentation highlights clustering using Redis and integration with load balancers like HAProxy, but establishing a highly available, multi-region proxy cluster requires substantial engineering effort. Organizations lack out-of-the-box multi-cloud failover unless they invest in bespoke Sentinel contracts or subscribe to the managed cloud service, meaning baseline fault tolerance remains entirely the customer's operational responsibility.


## System Integrations and Configuration Export Workflows

Evaluating BunkerWeb requires inspecting how well it integrates into modern automation pipelines and existing monitoring infrastructure. In containerized environments, BunkerWeb integrates with Docker and Kubernetes environments, enabling automated discovery and configuration via container labels or environment variables. This enables platform teams to declare security rules alongside application deployment manifests. Outside container platforms, the proxy integrates with standard Linux environments, where it can be provisioned through automated shell scripts, configuration management tools, or custom orchestration platforms.

Monitoring and observability integrations represent another clear dividing line between tiers. The core open-source distribution exposes baseline traffic and security metrics via its Metrics plugin. However, dedicated Prometheus metrics endpoints and official pre-configured Grafana dashboards require the PRO Prometheus Exporter plugin. Alerting is comparatively flexible in the free tier, with external plugins supporting event notifications sent to Discord channels, Slack channels, Matrix rooms, or arbitrary HTTP webhooks. File inspection integrations rely on network communication with local ClamAV daemons or authenticated API calls directed to VirusTotal endpoints.

When it comes to configuration migration and exports, BunkerWeb provides specific utilities. The PRO tier includes a Migration plugin that allows operators to transfer configuration states between different BunkerWeb instances directly through the graphical user interface. Users on the open-source version must rely on the core Backup plugin, which saves configuration files and data directories locally. These local backup archives can be incorporated into external backup automation, but restoring configurations across disassociated clusters requires manual file system placement and database restoration, highlighting the extra manual labor expected of open-source administrators.


## Comparative Analysis: BunkerWeb versus Market Alternatives

To make an informed purchasing decision, buyers must contextualize BunkerWeb against broader industry alternatives. In the self-hosted open-source proxy space, BunkerWeb competes directly with tools like NGINX paired with ModSecurity or Coraza, Traefik, HAProxy, and Caddy. Conventional reverse proxies like Traefik excel at dynamic service discovery and lightweight routing, but they generally lack an integrated out-of-the-box WAF security posture. Operating a secure WAF on Traefik or standard NGINX usually requires administrators to manually compile, tune, and maintain third-party modules, whereas BunkerWeb packages these security capabilities, Let's Encrypt automation, and a dedicated web UI into a cohesive distribution.

When compared to commercial cloud-native WAF providers like Cloudflare, AWS WAF, Fastly, or Akamai, the architectural trade-offs become stark. Cloud WAFs operate globally distributed edge networks that absorb massive multi-gigabit DDoS attacks before traffic reaches the customer's origin network. BunkerWeb CLOUD attempts to bridge this gap, but self-hosted BunkerWeb deployments are fundamentally bounded by the bandwidth, compute limits, and network transit capacity of the host infrastructure. A self-hosted WAF cannot mitigate a volumetric network saturation attack that fills the host datacenter's physical pipe, meaning self-hosted BunkerWeb is optimized for application-layer inspection rather than massive network-layer absorption.

BunkerWeb occupies a distinct middle ground between bare web servers and proprietary cloud firewalls. It provides full transparency, source code auditability, and data sovereignty under its AGPLv3 core, which cloud-native firewalls do not offer. However, compared to enterprise-grade solutions like Cloudflare Enterprise or F5 BIG-IP, self-hosted BunkerWeb demands significantly higher internal maintenance, ongoing rule optimization, and continuous infrastructure monitoring. Buyers must weigh the benefits of self-hosted data ownership and open-source transparency against the operational burden of managing their own proxy cluster.


## Project Lifecycle Planning and Workspace Coordination

Deploying and managing a reverse proxy WAF like BunkerWeb represents just one specialized component of a modern engineering delivery lifecycle. Before an organization can place a WAF in front of its production services, teams must systematically design backend application architectures, define API contracts, formulate strict security policies, and orchestrate automated continuous integration pipelines. A standalone network firewall cannot resolve design flaws, flawed authorization logic, or missing database constraints within the application itself. Infrastructure hardening must always be coordinated alongside proactive software design, clear team documentation, and disciplined prototyping.

Teams frequently utilize dedicated environments to structure technical roadmaps, outline infrastructure migrations, and draft configuration manifests before applying them to live proxy clusters. Using a unified planning environment like a Roseram workspace allows engineers to prototype application service definitions, document routing boundaries, and align security requirements across development and operations teams. Having an integrated workspace to model software components helps verify that application code adheres to standard security principles before it ever reaches the proxy layer, ensuring that the operational firewalls deployed downstream serve as a defense-in-depth shield rather than a rushed patch for unvetted code.

It is crucial to clarify the exact roles of these disparate tools. While an AI project workspace provides cross-functional structure for planning, building, and revising software projects, it does not replace a specialized network proxy like BunkerWeb, which performs real-time HTTP packet inspection and network-level packet dropping. Similarly, BunkerWeb cannot assist in project scoping, code iteration, or collaborative sprint planning. Engineering organizations achieve the greatest resilience when specialized network tools are deployed alongside comprehensive planning platforms, ensuring that both software design and perimeter defense operate with clarity and accountability.


## A Pragmatic Step-by-Step Buyer Evaluation Plan

Before entering into a paid commercial agreement or replacing established reverse proxies in production, prospective buyers should execute a structured evaluation plan. The first step involves standing up the open-source version of BunkerWeb in an isolated staging environment that mirrors production network topologies. Administrators should route non-sensitive staging traffic through the proxy and enable the core ModSecurity plugin alongside the OWASP Core Rule Set. This staging baseline reveals how the proxy handles standard application payloads, identifies routing idiosyncrasies, and exposes immediate rule conflicts without endangering customer operations.

The second phase of the evaluation plan focuses on systematic false-positive benchmarking. Engineering teams should execute automated end-to-end integration test suites against staging services while monitoring BunkerWeb's inspection logs. Special attention must be paid to complex multi-part file uploads, administrative forms containing rich markup, and API endpoints accepting nested JSON structures. Operators should measure how long it takes to diagnose a blocked request, identify the triggered rule ID, and deploy a stable exclusion rule. If the team finds manual rule tuning excessively time-consuming, evaluating the commercial Easy Resolve plugin during the 30-day free trial becomes an objective operational test.

The final evaluation step requires rigorous load testing and failover verification. Teams should deploy benchmarking tools like k6 or Locust to subject the staging BunkerWeb instance to realistic concurrent request volumes, measuring latency degradation, CPU saturation, and memory stability under sustained load. Furthermore, teams must simulate failure modes: terminate the Redis backend to test session handling, disrupt DNS access to observe DNSBL timeouts, and test container restarts to verify Let's Encrypt renewal continuity. Documenting support turnaround times by engaging the vendor with technical questions during the trial phase ensures that commercial commitments are verified before production signing.


## Operational Governance, Compliance, and Due Diligence Checklist

The final stage of evaluating BunkerWeb requires assessing organizational governance, regulatory compliance, and ongoing operational maintenance. Software distributed under the AGPLv3 mandates careful legal review if an organization plans to modify the core proxy or integrate it directly into proprietary distributed platforms. Engineering leads must work with corporate legal counsel to ensure that deploying BunkerWeb across company infrastructure adheres to internal open-source license policies, confirming that proprietary backend application code remains strictly separated from the AGPLv3 proxy layer.

Operational maintenance demands clear governance frameworks. System administrators must establish documented procedures for keeping BunkerWeb updated against newly disclosed vulnerabilities, as running an outdated web application firewall creates a false sense of security. Teams must decide whether to rely on community Discord forums for troubleshooting or to purchase the Enterprise Fortress plan to guarantee direct access to core maintainers. If choosing the commercial tier, procurement teams must request formal documentation outlining incident response times, guaranteed bug-fix turnarounds, and support escalation paths.

To assist engineering leads and procurement specialists, this operational checklist synthesizes the essential verification tasks. Teams should verify license compatibility with legal counsel, audit the functional split between free core plugins and paid PRO features, benchmark false-positive rates using automated test suites, evaluate proxy latency and memory overhead under simulated load, verify SSL renewal automation, and test backup restoration routines. Completing these pragmatic validation steps ensures that any deployment decision is rooted in verifiable internal engineering data rather than promotional promises or ungrounded online skepticism.


## Features and decision criteria

- Reverse proxy architecture functioning as an entry point for HTTP and HTTPS traffic inspection
- Dual WAF engine integration supporting ModSecurity with OWASP Core Rule Set and Coraza
- AGPLv3-licensed open-source foundation with self-hosted Linux, Docker, and Kubernetes deployment options
- Modular plugin system separating free core capabilities from paid commercial PRO features
- Automated Let's Encrypt certificate issuance, custom TLS handling, and mTLS support
- Managed SaaS cloud hosting alternative alongside self-hosted enterprise packages

## Frequently asked questions

### What deployment modes does BunkerWeb support?

BunkerWeb functions as a reverse proxy deployed directly on Linux hosts or within container environments using Docker, Docker Swarm, and Kubernetes. The vendor also provides a fully managed SaaS option called BunkerWeb CLOUD.

### What is the primary licensing model for BunkerWeb?

The core software is distributed under the AGPLv3 open-source license. Certain enterprise capabilities, advanced management utilities, and dedicated support services require commercial subscriptions under paid PRO plans.

### Which security engines does BunkerWeb integrate for traffic inspection?

BunkerWeb includes plugins for the ModSecurity engine paired with the OWASP Core Rule Set, alongside an external plugin option to inspect incoming requests using the Coraza WAF engine.

### What commercial plans are offered by the vendor?

The vendor lists self-hosted paid tiers, including Standard Shield at 49 euros per month and Enterprise Fortress at 149 euros per month, custom enterprise plans, and fully managed cloud services starting from 639 euros monthly.


## Sources and further reading

- [BunkerWeb website](https://www.bunkerweb.io/)
- [BunkerWeb official publisher reference](https://www.bunkerweb.io/pricing-plan/)
- [devhunt listing](https://devhunt.org/tool/bunkerweb)

For the complete Roseram buyer guide, see [BunkerWeb review](https://roseram.com/reviews/scams/bunkerweb-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
