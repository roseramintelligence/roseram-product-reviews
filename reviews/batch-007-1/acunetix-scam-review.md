# Acunetix review: features, pricing and buyer considerations

**Last editorial review:** 2026-10-28  
**Category:** Dynamic Application Security Testing (DAST)  
**Method:** Source-led desk review; no hands-on testing is claimed.

Acunetix, transitioned by its publisher into the Invicti Web + API family, is an automated dynamic application security testing platform. It crawls running web applications, single-page frameworks, and APIs to uncover vulnerabilities like SQL injection, cross-site scripting, and OWASP Top 10 risks. The vendor highlights runtime validation, proprietary risk scoring, and optional agent-based code tracing. Buyers evaluate Acunetix to automate runtime scans within development pipelines, though procurement requires navigating custom enterprise packaging, domain target limits, scan duration overhead, and vendor documentation changes across product generations.

## Editorial verdict

This desk review does not establish that Acunetix is a scam or certify the business as safe. The cited publisher material describes an offer that can be evaluated against your requirements. Before paying, verify the seller, the current terms, any cancellation rules and the capabilities that matter to your use case. The discussion below separates publisher claims from suggested buyer checks; it does not report hands-on testing or an independent security audit.

## What to know before choosing Acunetix

When security analysts and development managers enter searches such as an Acunetix scam review, their intent is rarely to investigate petty consumer deception. Instead, software buyers use extreme terminology to cut through enterprise marketing polish during expensive procurement processes. Evaluating commercial testing tools demands rigorous verification of technical claims, service reliability, pricing fairness, and software performance. In the web application security space, purchasers often struggle with high false positive rates, excessive licensing costs, and intrusive sales calls. They require independent analysis to see if an automated crawler delivers actionable vulnerability data or creates an administrative burden.

A critical factor in evaluating Acunetix today is understanding its significant corporate and brand repositioning. First-party documentation confirms that Acunetix is operating as Invicti Web + API following consolidation under the Invicti application security umbrella. While traditional technical manuals still detail standalone Acunetix on-premises setups and cloud architectures, marketing channels funnel users into unified platform packages. This corporate transition introduces natural friction for technical evaluators. Teams researching legacy Acunetix feature sets often encounter inconsistent product terminology, changing license boundaries, and shared code engines. Prospective customers must recognize that reviewing Acunetix requires reviewing Invicti Web + API mechanics and documentation.

This editorial review relies strictly on verified first-party vendor sources, technical manuals, and explicit support policies documented by the publisher. It avoids unsubstantiated sales assertions and unverified performance superlatives. In dynamic security scanning, absolute assertions of complete safety or total automation are inherently unprovable. By examining published architectural features, licensing parameters, integration capabilities, and technical constraints, buyers can clarify what the system provides. This baseline allows security leaders to structure targeted technical evaluations before committing organizational budgets to the platform.


## Core Dynamic Application Security Testing Mechanics

At its operational foundation, Acunetix executes Dynamic Application Security Testing, commonly known as DAST. Unlike static code analyzers that review dormant source code repositories, a DAST tool evaluates applications from the outside in while they are active. Acunetix operates by crawling the accessible endpoints, forms, input parameters, and stateful flows of a web property. Once it maps the attack surface, the scanning engine delivers controlled, simulated attack payloads. It monitors application responses to detect vulnerabilities, such as structured query language injection, cross-site scripting, and server configuration oversights.

Modern web development frameworks introduce complex scanning challenges that traditional HTML crawlers cannot navigate. The publisher documents scanning support for single-page applications, heavy JavaScript frontends, and stateful application programming interfaces, including RESTful endpoints, GraphQL structures, and SOAP interfaces. The crawler executes client-side scripts, analyzes dynamic Document Object Model mutations, and tracks sessions through custom authentication routines. To scan behind authenticated barriers, the software provides login sequence recording, custom header definitions, client certificates, and multi-step form authentication profiles.

The primary workflow advantage of dynamic scanning is its technology-agnostic perspective. Because tests operate across HTTP and network interfaces, the scanner does not require direct access to backend application frameworks or bespoke language runtimes. It probes applications precisely as an external attacker would probe them. However, dynamic crawling remains constrained by application logic, strict session state behaviors, and complex input validation. If a crawler cannot interpret a custom user interface control or solve a navigation sequence, underlying application routes remain uninspected. Teams must understand these functional mechanics before deploying automated crawlers across complex internal software.


## Vendor Claims Around Proof-Based Scanning and AI

A prominent commercial claim made by the publisher involves its proprietary proof-based scanning capability. Vendor materials state that the dynamic engine achieves a 99.98% confirmation accuracy rate for exploitable vulnerabilities, effectively eliminating false positive results. The underlying concept involves generating safe exploit verifications, such as extracting controlled data samples or executing harmless arbitrary read commands, to prove exploitability. The platform displays highlighted HTTP requests and responses directly within vulnerability alerts to demonstrate the issue. While this proof-oriented reporting saves triage time, users should understand that this verification mechanism applies primarily to specific flaw classes, such as direct database injection or file inclusion, rather than subtle business logic defects.

Alongside proof-based reporting, current vendor pages heavily promote artificial intelligence capabilities, marketing terms like agentic penetration testing, and predictive risk scoring algorithms. The vendor asserts that proprietary machine learning models analyze over 200 outward-facing asset features to predict relative risk levels before active scanning starts. Furthermore, marketing documentation cites an 8x scanning speed advantage over competitors, 40% higher flaw discovery volumes, and a 70% acceptance rate on AI-generated remediation guidance. These metrics reflect vendor-administered performance comparisons and promotional figures that external teams cannot universally verify across diverse environments.

In enterprise software evaluation, such sweeping performance statistics should be treated as directional vendor marketing rather than guaranteed operational performance. Scanning speed and vulnerability discovery rates fluctuate heavily based on web server latency, network bandwidth, application path depth, and dynamic database queries. An automated platform cannot replace comprehensive manual testing for intricate business logic flaws or complex authorization bypasses. Evaluators must treat automated AI claims as specific capabilities to inspect during a controlled trial rather than established operational certainties.


## AcuSensor and Hybrid Runtime Visibility

To narrow the functional gap between exterior dynamic scanning and internal source code visibility, Acunetix provides an optional technology named AcuSensor. Documented as an interactive application security testing or hybrid scanning agent, AcuSensor is deployed directly within backend application runtimes. First-party manuals detail specific AcuSensor installation packages for various server environments, including PHP, Microsoft .NET, Java application servers, and Node.js instances, supporting traditional operating system hosts as well as containerized Docker deployments.

When installed, AcuSensor operates cooperatively with the external dynamic scanning crawler. As the crawler delivers simulated attack payloads to target interfaces, the internal sensor inspects code execution pathways within the server process. This internal vantage point allows the scanner to correlate external vulnerabilities directly with specific backend source lines, file names, and database query executions. The vendor documents that this hybrid visibility enhances scan accuracy, uncovers hidden configuration flaws, and provides granular remediation guidance directly to engineering teams.

Deploying internal sensor agents introduces operational considerations that buyers must assess during planning. Unlike non-intrusive external DAST scanning, deploying AcuSensor requires modifications to runtime environments, container configuration adjustments, and coordination with development or systems engineering teams. Organizations with strict production change management policies may restrict running third-party binary agents inside live workloads. Consequently, teams must evaluate whether they can deploy AcuSensor in pre-production staging tiers, or if they must rely exclusively on standard external dynamic scanning profiles.


## Licensing Structure and Target Definitions

Procuring enterprise dynamic testing software requires an understanding of how vendors calculate licensing usage and price boundaries. Historical dynamic scanners often utilized concurrent scan engine licensing or flat organization licenses. Under current published policies, Invicti Web + API packages scanning capacity around defined targets and service packages. The vendor highlights flexible packages with transparent terms, contrasting its approach with legacy models that charge based on rigid deployment environments or artificial scan worker limits.

The critical technical variable in this pricing model is the vendor definition of a target. First-party documentation clarifies that a target is defined as a single Fully Qualified Domain Name (FQDN). Under this published rule, standard domain variations like secure protocol wrappers, base hostnames, and subordinate URL directories are grouped together as one target. For instance, example.com, secure variations of that address, and standard subdirectory paths count as a solitary target. However, the documentation notes that separate subdomains, unique hostnames, and alternative network port assignments represent distinct targets. Scanning test.example.com or an alternate port on the same server consumes additional target allocations.

This target definition has significant financial implications for modern engineering organizations that operate microservice backends, separate localized hostnames, or complex testing environments. A company managing dozens of distinct staging environments, service endpoints, and developer portals across unique host subdomains can rapidly exhaust entry-level target quotas. Prospective buyers should map their complete infrastructure inventory before commercial discussions to prevent unexpected mid-contract licensing true-ups or unmonitored digital assets.


## SDLC Integrations and Workflow Automation

Dynamic vulnerability scanning provides little organizational value if findings remain isolated inside disconnected administrative security dashboards. Technical documentation for Acunetix outlines extensive integration options designed to bridge security operations with standard software delivery workflows. The platform provides connectors for primary issue management systems, including Atlassian Jira, GitHub Issues, GitLab, Azure Boards, Bugzilla, Redmine, and ServiceNow Incident Management. When the scanner confirms an exploitable issue, it automatically formats and transmits bug tickets to assigned development teams.

For teams practicing continuous integration and continuous deployment (CI/CD), Acunetix provides pipeline automation hooks. Vendor manuals outline configuration processes for integrating scans directly into CI/CD systems, such as Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI, Bamboo, and TeamCity. These pipeline integrations allow automated scanning tasks to trigger following software builds or test deployments. Based on configurable vulnerability severity thresholds, teams can configure pipelines to pass, issue build warnings, or halt deployments if high-severity flaws appear.

In addition to developer-focused issue trackers and pipelines, the platform supports enterprise administrative integrations. First-party manuals detail single sign-on connections using SAML protocols with providers like Okta, Azure Active Directory, and PingIdentity, alongside identity provisioning through SCIM. The system also documents integrations with Web Application Firewalls, such as AWS WAF, F5 BIG-IP ASM, and Fortinet FortiWeb. These allow teams to export temporary virtual patching rules while developers work on permanent code fixes. These integrations are extensive, but establishing and maintaining them across active pipelines requires disciplined administrative oversight.


## Vendor Support Tiers and Implementation Services

Vendor support agreements are an essential component of due diligence for any security tool deployed across mission-critical workflows. Invicti documents three distinct customer support tiers: Standard Support, Premium Support, and Premium Support + Guided Success. Standard Support provides general technical assistance during standard business hours covering twenty-four hours across five working days. This baseline tier includes core product manuals, user documentation, and routine technical troubleshooting through ticket submission channels.

For enterprises requiring accelerated access and round-the-clock availability, the vendor provides upgraded support packages. The Premium Support tier extends operational coverage to twenty-four hours a day across seven days a week, accompanied by priority-based first-reply guarantees. Published response times range from a one-hour target for urgent issues to six hours for low-severity inquiries. The Premium Support + Guided Success package adds assigned application security managers who conduct recurring technical check-ins, provide implementation guidance, assist with custom pipeline integrations, and host quarterly business reviews.

Prospective buyers must balance their internal technical maturity against these tiered support models. Organizations with seasoned security engineers, dedicated automation architects, and established pipeline workflows may find baseline documentation and standard ticketing support sufficient. Conversely, teams building their first formal application security program often struggle to configure authentication macros, tune scanning profiles, or integrate complex enterprise web firewalls without expert guidance. Buyers should assess the total cost of ownership, including paid onboarding or support upgrades, when calculating return on investment.


## Practical Evaluation and Proof-of-Concept Strategy

Because automated dynamic scanners can generate operational friction or encounter edge-case failures, organizations should never purchase enterprise licensing without a structured proof-of-concept (PoC) evaluation. First-party documentation confirms that the vendor provides proof-of-concept licenses, allowing prospects to test the platform in their actual computing environments. Buyers must use this trial window to run rigorous, empirical tests rather than passive vendor-guided feature demonstrations. A well-designed evaluation exposes real-world limits before contracts are finalized.

An effective testing plan begins with target authentication and crawl verification. Evaluators should challenge the scanner against a staging application that utilizes their most demanding front-end framework, dynamic single-page controls, and multi-factor or OAuth authentication flows. The testing team must verify whether the engine reliably maintains session persistence across deep paths, or whether it drops authentication and generates misleading empty scan logs. Additionally, operators should test the crawler against undocumented or complex API collections using imported OpenAPI definitions to verify endpoint coverage.

The second phase of the evaluation must measure operational overhead and report accuracy. Security personnel should deliberately run scans against applications containing known, pre-identified vulnerabilities alongside safe complex forms. This measures whether the scanner reliably flags actual vulnerabilities, successfully attaches exploit evidence, and minimizes false positives. Crucially, the engineering team must record total scan completion times and observe server resource utilization. Dynamic scans that overwhelm backend databases or take dozens of hours to complete can disrupt delivery schedules, making them impractical for fast-moving production pipelines.


## Navigating Planning Workspaces and Security Tools

Building reliable web applications requires a clear operational distinction between dynamic scanning tools and project delivery environments. A specialized DAST scanner functions as an automated inspector, evaluating completed interfaces and flagging broken implementations after runtime deployment. However, it cannot author technical specifications, align project scopes, or structure engineering tasks. Software leaders often use a dedicated workspace to coordinate system designs, map testing schedules, and track iterative development before code ever meets an automated security pipeline. The commercial entity behind this publication develops software in the team productivity domain, maintaining a direct business interest in workspace technologies.

Within an end-to-end engineering lifecycle, technical teams can utilize the Roseram workspace to plan application architectures, draft implementation milestones, and coordinate remediation backlogs alongside external scanner evaluations. While an automated scanner uncovers runtime flaws and generates exploit proofs, a unified planning space allows engineers to organize development sprints, document testing parameters, and track technical debt across functional teams. Dedicated workspaces do not replace security testing utilities, nor do security analyzers organize collaborative project plans. Maintaining this functional balance allows organizations to design software methodically while using specialized testing tools to validate code in dynamic staging environments.

When security findings emerge from automated test runs, cross-functional collaboration determines how rapidly teams resolve underlying code defects. Security alerts require translation into actionable refactoring assignments, database parameterization tasks, or identity handling updates. Documenting these architectural decisions within a central development workspace ensures engineering priorities remain aligned with security findings. Organizations that integrate proactive architectural planning with automated dynamic scanning build a more sustainable defense against emerging web application vulnerabilities.


## Limitations, Operational Overhead, and Scanner Constraints

Despite automated capabilities, dynamic application security testing has fundamental limitations that buyers must understand. First, dynamic scanning is inherently resource-intensive and time-consuming compared to static code inspection. Probing thousands of dynamic parameters with simulated payloads requires issuing continuous streams of HTTP requests. Depending on application complexity, network latency, and server processing capacity, full scans can run for hours or even days. If scan speeds are improperly configured, aggressive testing can flood databases with test records, trigger rate limiters, or degrade service performance across live staging environments.

Another operational constraint involves business logic vulnerabilities. Automated scanners excel at identifying technical injection patterns, missing security headers, outdated software components, and cross-site scripting vulnerabilities. However, dynamic engines cannot reliably understand business context. A scanner cannot independently determine whether a user accessing another user's invoice records represents an authorized accounting workflow or an insecure direct object reference. Uncovering subtle privilege escalation flaws, multi-step transaction tampering, and bespoke workflow circumventions still requires skilled human penetration testing.

Finally, automated dynamic testing incurs continuous maintenance overhead. As engineering teams update frontend libraries, revise API endpoints, and modernize authentication gateways, security administrators must actively maintain scan configurations. Login macros can break when UI layouts change, excluded scan paths may need regular updating, and API schemas require ongoing synchronization. Treating Acunetix as a completely hands-off utility often leads to incomplete crawls, uninspected routes, and a false sense of security coverage.


## Competitive Alternatives and Market Landscape

Organizations assessing Acunetix operate within a competitive application security marketplace offering diverse architectural approaches. In the enterprise commercial DAST sector, solutions like Rapid7 InsightAppSec, Veracode Dynamic Analysis, and Qualys Web Application Scanning provide automated crawl engines designed for large corporate asset inventories. These platforms vary in their pricing models, asset grouping configurations, cloud hosting architectures, and integrated software composition analysis capabilities. Buyers must evaluate how each vendor handles target definitions and reporting requirements.

For teams seeking developer-centric security testing, alternative tools emphasize lightweight pipeline scanning and proxy-driven workflows. Solutions such as PortSwigger Burp Suite Enterprise provide automated dynamic scanning powered by the widely recognized Burp testing engine, appealing directly to security analysts accustomed to manual penetration testing toolsets. Concurrently, open-source scanners, such as OWASP ZAP (Zed Attack Proxy), offer cost-effective scanning capabilities for technical teams capable of building custom pipeline automation without vendor support agreements.

Selecting the right tool depends heavily on organizational structure, technical skills, and testing volume. Companies with dedicated application security teams may favor flexible proxies and scriptable scanning toolkits, whereas organizations seeking centralized compliance reporting, turnkey CI/CD issue generation, and automated verification often prefer packaged commercial scanners like Acunetix. Weighing platform capabilities against internal management bandwidth ensures teams select an approach aligned with their technical needs.


## Buyer Due Diligence Checklist and Final Verdict

Completing thorough buyer due diligence on Acunetix requires cutting through marketing branding to confirm concrete operational realities. Reviewing the available evidence demonstrates that Acunetix, operating as Invicti Web + API, provides an established dynamic security scanning platform with deep crawler mechanics, proof-based exploit reporting, and extensive pipeline integrations. However, prospective buyers should not interpret these technical capabilities as an effortless substitute for manual testing or a guarantee of flawless protection. Successful dynamic scanning demands ongoing maintenance, skilled profile configuration, and realistic scanning schedules.

Before executing a binding software agreement, procurement teams should complete a structured verification checklist. First, audit your organizational domain inventory to determine the exact number of Fully Qualified Domain Names, subdomains, and ports requiring inspection. Next, secure an active proof-of-concept license to measure scan execution times, crawl completeness, and session handling against your primary single-page applications and API endpoints. Finally, review support package agreements to ensure response time guarantees and onboarding assistance align with your internal security bandwidth.

In conclusion, Acunetix represents a mature, highly configurable dynamic scanning platform capable of automating critical application security workflows when properly configured. It is neither a hands-off silver bullet nor a deceptive platform. By approaching procurement with realistic expectations regarding maintenance overhead, target licensing limits, and scan duration, organizations can make an informed, value-driven investment in their application security infrastructure.


## Features and decision criteria

- Dynamic security scanning for modern web applications, single-page apps, and REST or GraphQL APIs.
- Proof-based vulnerability validation designed to show exploitability evidence within generated findings.
- AcuSensor server-side agent deployment for runtime application security tracing in supported environments.
- Native issue tracking and continuous integration connectors for platforms like Jira, GitHub, and Jenkins.
- Built-in compliance and technical reporting templates mapped to OWASP, PCI DSS, and ISO 27001 standards.

## Frequently asked questions

### What is the relationship between Acunetix and Invicti Web + API?

Publisher announcements across official web pages indicate that Acunetix has been repositioned as Invicti Web + API under the broader Invicti corporate umbrella. While legacy documentation still references Acunetix and Acunetix 360 configurations, current product marketing directs prospective buyers toward Invicti packages, unified dynamic scanning engines, and multi-agent penetration testing features.

### How does Acunetix define and count licensing targets?

Vendor licensing models define a scan target by its Fully Qualified Domain Name (FQDN). Under this published definition, standard domain variants sharing an identical host structure count as one target, whereas distinct subdomains, alternative hostnames, or unique network ports are categorized and metered as separate scanning targets.

### What is the AcuSensor component and how does it work?

AcuSensor is an optional server-side agent that operators install inside specific runtime technology stacks, such as Java, .NET, PHP, or Node.js. By operating inside the application environment, it provides code-level traceability that correlates exterior dynamic scanning requests with interior backend code execution points.

### Can buyers test Acunetix prior to purchasing an enterprise license?

The vendor states that prospective organizations can request a proof-of-concept license to evaluate the dynamic scanning platform within their own infrastructure. However, exact terms, functional limits, and technical scopes for these evaluations are determined through sales interactions rather than open self-service access.


## Sources and further reading

- [Acunetix website](https://www.acunetix.com/)
- [Acunetix official publisher reference](https://www.acunetix.com/pricing/)
- [Acunetix official publisher reference](https://www.acunetix.com/support-plans/)
- [Acunetix official publisher reference](https://www.acunetix.com/support/)
- [Acunetix official publisher reference](https://www.acunetix.com/product/)
- [saashub listing](https://www.saashub.com/acunetix)

For the complete Roseram buyer guide, see [Acunetix review](https://roseram.com/reviews/scams/acunetix-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
