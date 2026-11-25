# CloudFlare review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Internet infrastructure and website security services  
**Method:** Source-led desk review; no hands-on testing is claimed.

Cloudflare sells a broad set of internet services. This review focuses on its Network and CDN website plans, authoritative DNS and the DNS proxy setting that routes eligible HTTP traffic through Cloudflare. Zero Trust, Workers, storage, email routing, registrar services, and add-ons have separate product pages, prices and limits.

## Editorial verdict

Cloudflare publicly lists Free, Pro, Business and contract plans for Network and CDN, explains how DNS proxy status changes the traffic path, and says DNS queries are not capped; Free, Pro and Business plans do not charge for those queries. This documents a commercial infrastructure provider, not evidence of a scam. The operational risk lies in choosing the wrong service scope, exposing an origin, or changing DNS, TLS, caching or security rules without a tested rollback.

## Cloudflare review: identify which Cloudflare product is being purchased

Cloudflare is a company and product family, not one single service with one price. A common website setup uses Cloudflare as an authoritative DNS provider and optionally routes web requests through its network. The company also sells Zero Trust, developer compute, storage, image and media services, and other products. Those services have their own pricing and limits. This review concentrates on the Network and CDN plan selector, authoritative DNS and proxy status; it should not be read as an evaluation of every Cloudflare product.

Write down the actual intended service before opening a plan comparison. Is the team changing nameservers, proxying a website, using the web application firewall, deploying code to Workers, storing files in R2, or providing employee access through Zero Trust? Each action changes a different part of the architecture and may add a different bill. A company may use Cloudflare DNS without changing its web host, but a proxied record changes how HTTP traffic reaches the origin. Treat product selection and traffic architecture as one design task.


## Cloudflare plans and pricing: Free, Pro, Business and Contract

Cloudflare’s Network and CDN pricing selector listed Free at $0 per month, Pro at $20 per month billed annually or $25 month-to-month, Business at $200 annually billed per month or $250 month-to-month, and Contract at a custom annual price when checked on 2026-11-17. The page positions Free for personal or hobby projects that are not business-critical, Pro for professional sites that are not business-critical, Business for small businesses operating online, and Contract for mission-critical applications. The distinction matters because the price is not just a fee for a bigger traffic allowance.

The feature matrix shows plan-specific controls, support and service commitments. For example, it lists lossless image optimization starting with Pro, PCI DSS 4.0 compliance starting with Business, and a 100% uptime SLA for Business and Contract, subject to the applicable service terms. Do not convert an SLA into a promise that a site can never fail: read its scope, exclusions, claim process and credit remedy. Select the plan using the actual features, support path and business criticality required. Taxes, add-ons and separate products can change the checkout total.


## Cloudflare authoritative DNS and what the no-query-limit claim means

Cloudflare’s DNS FAQ says authoritative DNS is available on all plans, DNS queries are not capped, and Cloudflare does not charge per DNS query for Free, Pro or Business plans. It also notes that DNS query count can be an input to an Enterprise quote. This is a precise statement about authoritative DNS billing, not a claim that every Cloudflare service is free or unmetered. DNS Firewall, analytics, logs, Workers and other products have their own terms and price dimensions.

DNS hosting does not require moving a domain registrar or a website host. In a full setup, the nameserver delegation is changed at the registrar, after records are checked and imported. Before making that change, inventory web records, mail exchangers, SPF, DKIM, DMARC, verification tokens, subdomains and records used by vendors. A missing mail or verification record can break an unrelated workflow even when the homepage still loads. Export a copy of the zone and keep the original values until the new authoritative setup has been checked from outside the account.


## Cloudflare proxy status: DNS-only and proxied are different paths

For eligible A, AAAA and CNAME records, Cloudflare’s proxy switch determines whether HTTP or HTTPS requests pass through its network. With proxying enabled, DNS answers use Cloudflare anycast addresses and requests can be optimized, cached, protected and evaluated by configured rules before reaching the origin. With DNS-only, the DNS answer reveals the origin address and HTTP traffic does not pass through Cloudflare. MX and TXT records are not proxied. Cloudflare recommends proxying web-serving address records while keeping verification and other non-web records DNS-only.

This affects configuration, troubleshooting and origin exposure. Once traffic is proxied, the origin must accept the relevant connections and be configured to trust client-IP headers only from the expected path. If the origin remains publicly reachable from any address, proxying alone does not prevent a direct-origin request. Conversely, an overly broad firewall or incorrect TLS mode can block legitimate requests. Record the existing DNS state and origin settings, test one hostname, and confirm both browser behavior and server logs before applying the setting to all records.


## Caching, SSL and security controls need a deliberate rollout

A CDN can serve cached copies of eligible responses, but a cached response is not the same as a live application result. Test pages with personalization, authentication, checkout, account data and rapidly changing content separately. Verify cache headers, cache rules, purge behavior and whether cookies or query parameters change the response. For a static marketing page, caching may help reduce origin work. For a logged-in workspace, an overly broad rule can serve the wrong content or make an update appear not to have taken effect.

Review certificate coverage and encryption between the visitor, Cloudflare and the origin. A browser lock does not by itself prove that every hop uses the intended certificate and protocol. Enable security protections in a staged way, observe false positives, and create a tested exception process for legitimate traffic. Save a rollback for changes to DNS, redirects, WAF rules, SSL mode and cache behavior. Infrastructure controls can reduce attack exposure, but they need an owner, monitoring and incident procedure; a plan name does not configure them safely by itself.


## Cloudflare limits, support and separate product charges

The Network and CDN page displays a plan matrix for DNS, CDN, SSL, DDoS protection, WAF, image optimization, support and service commitments. Read the selected tier rather than assuming that the same feature has identical depth on every plan. Cloudflare’s broader product selector contains SASE and Zero Trust, Compute and Storage, and other categories; those are not automatically included in the website subscription. Usage charges for compute, storage, logs, media or add-ons may be separate from the zone plan and should be checked in the relevant product’s price table.

For a site with multiple administrators, decide who can alter nameservers, billing, proxy state, security rules and API tokens. Keep API credentials scoped and rotate them after a change in ownership. Identify which support channel is included and what evidence support will need during an incident. If uptime or compliance language is driving the purchase, read the exact service-level agreement and verify that the intended configuration and account meet its eligibility conditions. A support label in a feature matrix is not an assurance that every incident receives the same response.


## Cloudflare alternatives and migration planning

Compare the Network and CDN service with the DNS, CDN and application security features already offered by a host, registrar, cloud platform or specialist provider. Alternatives can include AWS CloudFront and Route 53, Fastly, Akamai and other managed networks. The useful comparison follows one real domain through authoritative DNS, TLS, caching, origin access, logs and support. Consider where the origin is hosted, what rules must be migrated, how certificates are renewed, and whether the team can operate a second control plane.

Plan an exit before the service becomes critical. Export DNS records, retain a written copy of rules and redirects, document origin IPs, and note where API tokens or certificates are used. Test whether another operator can restore a DNS zone from that runbook. Keep nameserver transfer steps and a fallback host in the organization’s records. This is not a claim that a migration is effortless; proxy features and rules may require translation or replacement. A continuity plan makes a provider change a controlled project rather than a late-night reconstruction.


## Cloudflare buyer test: one hostname, one reversible change

Use a non-critical hostname with a representative origin to test the configuration. First establish a baseline: DNS resolution, certificate chain, redirect behavior, cache headers, origin logs, email delivery for the zone and application response. Add or import the record, verify nameservers, then toggle proxy status only for the intended web record. Test from another network and an ordinary browser, confirm the origin still responds correctly, and check that mail and domain-verification records remain untouched.

Next, test the rollback. Restore the prior DNS values or proxy state, allow for resolver caching, and verify the site again. Capture the time required for each step and the information an on-call teammate needs. This is a proposed evaluation protocol, not a Roseram security test or performance benchmark. If the business cannot tolerate a test-induced outage, use a staging domain and a reviewed change window. The evidence should be a successful repeatable configuration and a working recovery path, not a green dashboard icon.


## Cloudflare SCAM Review: what the evidence supports

Cloudflare publishes a detailed Network and CDN price matrix, authoritative DNS documentation and a technical explanation of proxy behavior. Its documentation says DNS queries are not capped and that Free, Pro and Business do not charge for those DNS queries, while its contract tier can price query volume into a quote. The materials support the service and billing distinctions described above. They do not establish that Cloudflare is a scam, guarantee performance for a particular website, or certify a customer’s security posture. Roseram did not audit a Cloudflare account or run a traffic benchmark for this review.

Before paying, verify that the quoted plan is specifically the Network and CDN plan, and list every separately enabled service, add-on, usage meter and contract term. Confirm whether annual billing is required for the displayed monthly equivalent, what support channel is available, and how any SLA claim is made. Keep an export of the DNS zone and configuration under company control. A provider can be an appropriate component of a web architecture while still requiring careful configuration and operational discipline. That is the evidence-based conclusion here, not a verdict of fraud.


## Features and decision criteria

- Authoritative DNS with no DNS-query cap and no query charge on Free, Pro and Business
- Optional reverse-proxy routing for supported A, AAAA and CNAME web records
- Network and CDN plan tiers with DDoS, SSL, caching and security features
- Separate Cloudflare products such as Zero Trust and Workers with their own billing

## Pricing considerations

These are the US prices shown on Cloudflare’s Network & CDN selector on 2026-11-17. This is not the full price list for Workers, R2, Zero Trust, Stream, Images, add-ons or enterprise services. Cloudflare says DNS queries are uncapped and free on Free, Pro and Business; Enterprise pricing can use query volume as an input. Confirm the selected product, billing cadence, features, SLA eligibility and checkout quote.

## Sources and further reading

- [Cloudflare Network & CDN plans and feature matrix](https://www.cloudflare.com/plans/)
- [Cloudflare authoritative DNS FAQ and DNS-query billing](https://developers.cloudflare.com/dns/faq/)
- [Cloudflare DNS proxy status and traffic behavior](https://developers.cloudflare.com/dns/proxy-status/)
- [Cloudflare DNS record management](https://developers.cloudflare.com/dns/manage-dns-records/)
- [Cloudflare terms of service](https://www.cloudflare.com/terms/)
- [Cloudflare internet infrastructure company on Wikipedia](https://en.wikipedia.org/wiki/Cloudflare)
- [CloudFlare website](https://www.cloudflare.com/)
- [saashub listing](https://www.saashub.com/cloudflare)

For the complete Roseram buyer guide, see [CloudFlare review](https://roseram.com/reviews/scams/cloudflare-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
