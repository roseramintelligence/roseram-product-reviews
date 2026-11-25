# Resend review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Transactional email API and marketing broadcasts  
**Method:** Source-led desk review; no hands-on testing is claimed.

Resend is an email service for developers, with an API and SDKs for transactional messages, plus contacts and broadcasts for permission-based marketing. Its published Free tier lists 3,000 emails per month but caps sending at 100 per day; Pro starts at $20 per month and Scale at $90, with optional usage overages. Email and log retention is 30 days on Free, Pro and Scale. Buyers should model event volume, recipients, inboxes and automation runs separately, and verify domain authentication and data-retention needs before moving a critical workflow.

## Editorial verdict

The reviewed first-party materials do not substantiate a scam allegation. Resend publishes plan quotas, overage mechanics, retention and security details. The main risks to assess are engineering fit, deliverability operations, usage billing, limited log history and the distinction between transactional sends and broadcasts. A sandbox integration and a realistic cost forecast are more useful than judging the service by a successful hello-world email.

## Resend SCAM review: what the label means and what this review checks

“SCAM Review” is the directory’s page label, not a finding that Resend is fraudulent. This is a public-source buyer review of the service’s documented product, pricing, usage rules, data practices and operational trade-offs. No Resend account was purchased, no email was sent, and no deliverability or support test was performed for this article. The conclusion therefore stays within what the vendor’s public materials establish.

Resend presents an API-first email service aimed at software teams. It offers transactional delivery tools alongside contacts and broadcasts, rather than only a form-based newsletter product. A buyer should assess whether it fits the application’s message types, audience permissions, operational ownership and privacy requirements. “Email API” describes an interface; it does not by itself guarantee inbox placement, regulatory compliance for a sender, or a particular response rate.


## What Resend does for an application team

The product combines an HTTP API, SMTP relay, official SDKs, batch sending, scheduled messages, templates, event webhooks and dashboard tooling. The central job is to let an application trigger messages such as account verification, password resets, receipts and alerts without building mail transport infrastructure from scratch. The dashboard also includes inboxes and audience or broadcast features, so the team can manage some operational and marketing work in the same account.

That breadth can shorten the path from a user action to a delivered message, but it still leaves application decisions in the developer’s hands: which event may send, how retries are handled, which address is authoritative, how duplicate sends are prevented, and where unsubscribe preferences are enforced. Build a small proof of concept that covers a real message path, not only the provider’s sample request.


## Resend pricing: plan quotas are only one part of the bill

The pricing page observed for this review lists Free at $0 with 3,000 emails per month and a separate 100-email daily cap. Pro is listed at $20 per month for 50,000 monthly emails; Scale is $90 for 100,000. Both paid plans show an additional transactional-email price of $0.90 per 1,000 messages. These amounts are the published USD prices, not a checkout quote for a particular country, tax treatment or future billing cycle.

The Free tier is useful for a small proof of concept, but the daily cap can bind before the monthly allowance during a launch, incident or bulk notification. Paid plans remove the listed daily cap, but do not remove monthly quotas unless a paid account enables the applicable overage option. The page lists automations at $0.0015 per run beyond 10,000 free runs and additional inboxes at $1 per inbox per month. Add those lines to the forecast when they are used.


## Transactional emails and broadcasts are different meters

Resend defines transactional messages as sends through the `/emails` API and marketing messages through `/broadcasts` or the dashboard. Its pricing FAQ says broadcast sending is measured against existing contacts rather than the transactional email quota, while every inbound email counts toward transactional usage. A newsletter sent through `/emails` still consumes transactional quota. The company says broadcasts can only go to existing contacts.

This distinction matters because copying the same newsletter workflow into the wrong endpoint can change both consent handling and the bill. For `/emails` newsletters, the pricing guidance says the sender must provide an unsubscribe link plus the List-Unsubscribe and List-Unsubscribe-Post headers. Broadcasts can handle their unsubscribe link when the documented placeholder is included. Keep marketing permission records and suppression lists attached to the recipient workflow, not only to an API key.


## Overages, daily caps and failure behavior

The vendor says paid users can enable pay-as-you-go for transactional email over quota. Additional use is billed in 1,000-email buckets at the plan’s overage rate. If the setting is off and an account exceeds its limit, Resend says the customer will be notified and offered a plan upgrade. The same pricing page describes automation overage and extra inbox pricing separately. These settings are billing controls, not an assurance that a message will be accepted or delivered.

Before launch, set usage alerts and a conservative forecast around ordinary volume, peak demand and retry storms. Decide whether a payment failure, quota ceiling or provider error should queue, retry, fall back or stop a non-critical notification. Never let a retry loop multiply a billing incident. Send a few controlled tests and inspect webhook events, bounce behavior and logs before relying on the service for account recovery or time-sensitive messages.


## Deliverability is an ongoing operating responsibility

Resend lists domain authentication, suppression handling, bounce details, open and link tracking, deliverability insights and webhook events among its capabilities. Its pricing page says open and click tracking can be enabled per domain on every tier. Tracking support is not evidence that a campaign will reach the inbox: recipient consent, domain reputation, list quality, message content, bounce rates and recipient-provider filtering still affect outcomes.

Authenticate the sending domain with the records shown in the account, then verify SPF, DKIM and DMARC alignment from an external diagnostic before production. Start with a permission-based audience, monitor hard bounces and complaints, and avoid importing scraped or stale addresses. Separate transactional traffic from promotional campaigns if their volume and reputation risks differ. A dedicated IP is a paid add-on listed for qualifying high-volume Scale users; it also brings warm-up and reputation work rather than removing it.


## APIs, webhooks and integration fit

Resend’s documented developer approach can fit applications that already have an event model and deployment process. The batch endpoint can send up to 100 messages in one request, and the pricing FAQ says the batch request counts as one request toward the team’s API request-per-second limit. The same FAQ says plan upgrades do not increase that rate limit. Teams with higher request rates should verify requirements with support instead of assuming a larger plan changes the API ceiling.

Treat webhooks as untrusted input until signatures are verified, and make handlers idempotent. Keep API keys server-side, use the narrowest permission scope available, rotate exposed credentials, and test a key revocation path. Map provider event IDs to your own message records so retries or duplicated webhook events cannot double-trigger an action. If you need advanced routing, suppression synchronization or compliance retention, include that integration work in the total cost.


## Data retention, location and security questions

Resend’s GDPR page states that email and log data is retained for 30 days on Free, Pro and Scale plans; Enterprise plans have flexible retention. It says remaining customer data is deleted within 90 days after termination, dashboard account deletion occurs after seven days, and backup copies expire seven days later. The page also says stored data is in the United States even when a sending region is selected, and describes Standard Contractual Clauses and the EU-U.S. Data Privacy Framework for transfers.

The same security material lists AES-256 encryption at rest, TLS 1.3 or higher in transit, annual third-party penetration tests and SOC 2 Type II. It explicitly says Resend is not HIPAA compliant and cannot sign a Business Associate Agreement. These are vendor statements, not an independent audit by this review. A regulated organization should assess the signed DPA, subprocessors, data region, retention window and its own legal requirements before sending sensitive information.


## Pricing alternatives and how to compare them fairly

A useful comparison is not “cheapest email provider” in isolation. Estimate monthly transactional sends, peak daily bursts, inbound mail, marketing contacts, automation runs, number of sending domains, inboxes, retention needs and support expectations. Then compare the same scenario across providers. Some alternatives price by message volume, some by active contacts, and some separate deliverability, dedicated IPs or marketing features. Their plan names and headline quotas are not directly interchangeable.

Resend may be attractive where a developer-friendly API and a visible usage model matter. An organization with a large newsletter audience should examine contact-based billing and campaign tools; a team with strict data-retention or residency rules should put those requirements ahead of an easy integration. Ask each vendor to clarify what counts as a billable send, whether inbound messages consume quota, and what happens at the limit.


## Who Resend may suit, and who should test alternatives

A product team that can own message templates, event instrumentation, authentication and bounce handling may find the API-first workflow straightforward. The free tier can support limited development and testing, and the published Pro and Scale tiers give buyers a starting point for estimating a production workload. The availability of both transactional and broadcast tools may also reduce the number of systems a small team has to coordinate.

It is less suitable to choose solely because a demo email sends in seconds. Teams that need a long searchable history, regulated health-data processing, a guaranteed delivery outcome, or a turnkey marketing operation should verify those needs directly and compare alternatives. A provider cannot decide whether your recipient list has valid permission or whether your retry policy is safe.


## Resend buyer checklist before moving production email

Write down each message class, its trigger, recipient, consent basis, business criticality and monthly volume. Check the 100-per-day Free cap, paid quotas, overage enablement, automation charges, extra inbox costs, API rate limit and webhook count for the plan that would actually be used. Confirm the target plan’s 30-day data retention is sufficient for support and incident investigation.

Authenticate a sending domain, implement suppression and unsubscribe behavior, verify webhook signatures, store event IDs, and test duplicate events and provider failures. Make a backup of templates, DNS values and configuration. Keep a fallback or queue plan for critical account messages. Review the current pricing, terms, privacy policy and DPA at checkout, because these public pages and prices can change.


## Resend SCAM review verdict: a transparent API service with limits to plan around

Resend publishes a clear entry-level price, separate monthly and daily limits, paid overage conditions, add-on charges and retention details. The reviewed public sources do not establish that Resend is a scam. They do establish that “3,000 free emails” is not the whole story: the Free tier also has a 100-per-day cap, the data and logs are retained for 30 days, and additional billing can apply to paid usage, automation runs, domains or inboxes.

The practical decision is whether the documented API and operational model fit the sender’s workload. Test the precise message path, calculate peak and monthly use, verify domain authentication, and review the data terms before switching. This is a dated public-source desk review, not a live account inspection, deliverability test, security audit or legal opinion. Pricing, features and terms were checked November 18, 2026; verify current first-party materials before subscribing.


## Features and decision criteria

- Transactional email API, SMTP relay, batch sending and SDKs
- Contacts, broadcasts, inboxes, templates, automations and webhooks
- Domain authentication, tracking and deliverability tools
- Plan-specific quotas, retention windows and paid overages

## Pricing considerations

Published US-dollar prices and limits observed on Resend’s official pricing page November 18, 2026. The page describes optional paid-plan overages, billed in 1,000-email buckets; automation overage at $0.0015 per run; additional inboxes at $1 per month; and add-ons including domains, dedicated IP and SSO. Taxes, contract terms, actual usage and current checkout should be confirmed before purchase.

## Sources and further reading

- [Resend official pricing, plan limits, add-ons and email categories](https://resend.com/pricing)
- [Resend GDPR and data-retention details](https://resend.com/security/gdpr)
- [Resend security overview](https://resend.com/security)
- [Resend Privacy Policy](https://resend.com/legal/privacy-policy)
- [Resend Terms of Service](https://resend.com/legal/terms-of-service)
- [Resend email API on Wikipedia](https://en.wikipedia.org/wiki/Resend)
- [Resend website](https://resend.com/)
- [saashub listing](https://www.saashub.com/resend)

For the complete Roseram buyer guide, see [Resend review](https://roseram.com/reviews/scams/resend-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
