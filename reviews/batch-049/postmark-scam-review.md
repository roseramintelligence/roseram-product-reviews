# Postmark review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-24  
**Category:** Transactional email delivery  
**Method:** Source-led desk review; no hands-on testing is claimed.

Postmark delivers transactional and broadcast email through APIs and SMTP, with message streams to separate different mail types. Its plans are usage-based by monthly email volume and include delivery analytics, templates, suppression management and retention features that vary by tier.

## Editorial verdict

Postmark is worth considering when dependable application messages and clear separation from marketing email are priorities. The 100-message recurring free tier supports integration evaluation, and paid plans show transparent monthly pricing at lower volumes. Confirm stream limits, retention, overage pricing and the account’s sending policy before routing production or promotional mail through the service.

## Separate user-triggered email from promotions

Postmark centers its product on transactional messages and provides separate Broadcast Message Streams for one-to-many mail. The vendor’s policy describes transactional mail as unique messages recipients expect after an action, such as a receipt or password reset. Product announcements and promotional campaigns are not transactional simply because a business sends them from its application.

Create separate streams and sending rules for different message purposes. Keep subscription marketing on the broadcast path with the required consent and unsubscribe handling, and use the transactional path for messages triggered by the recipient’s own activity. This distinction can protect operational notifications from campaign traffic and makes reporting easier to interpret.


## Estimate cost from volume and overages

Postmark lists a recurring free developer tier of 100 emails per month, followed by paid plans with monthly volume choices and extra-message rates. It also offers add-ons for dedicated IP addresses, longer activity retention and DMARC monitoring. A low displayed starting price is only meaningful when the included volume matches actual application traffic.

Estimate password resets, receipts, account notices, inbound processing and retry volume separately. Add headroom for peak periods and confirm whether inbound messages count toward the same allowance. Monitor the dashboard after launch and set an internal alert before expected volume reaches the tier limit.


## Review retention and access controls

Email content and delivery logs can contain personal details, account identifiers and reset links. Postmark’s plan page shows default retention and additional retention options; it also lists roles and API permission controls by tier. Decide how long an operator actually needs message content for troubleshooting and limit who can view it.

Use scoped server credentials and separate environments. Store API tokens in a secret manager, rotate them when staff or services change, and avoid copying sensitive mail content into issue reports. Confirm the current retention behavior for content, metadata and analytics rather than assuming all logs expire together.


## Test real message paths before production

Use the free tier to validate template rendering, event webhooks, bounce handling and inbound parsing with test addresses. Check that suppressions are honored and that a failed send produces a useful event for the application. A successful API call does not prove inbox placement or correct sender authentication.

Set up SPF, DKIM and DMARC for the sending domain and test messages across common inbox providers. Postmark publishes delivery data and status information, but no provider can guarantee that every message reaches the inbox. This review is based on public vendor materials, not an independent deliverability benchmark.


## Features and decision criteria

- REST API and SMTP for transactional email
- Separate transactional and broadcast message streams
- Templates, event webhooks, suppression controls and delivery analytics
- Inbound email parsing and message retention vary by plan

## Pricing considerations

The comparison uses the plan’s default volume selector and displays separate rates, retention and stream limits. Dedicated IPs, custom retention and DMARC monitoring are extra. Verify current volume, overage and add-on pricing on the vendor page.

## Frequently asked questions

### Is the free tier suitable for production at scale?

The pricing page describes 100 emails per month as an evaluation and side-project allowance with no overages; it is not a high-volume plan.

### Can marketing campaigns share the transactional stream?

Postmark says transactional and bulk traffic should be separated; broadcast messages belong in a separate Broadcast stream.

### Do unused messages roll forward?

The official pricing FAQ says unused email quota does not roll over to the next billing period.


## Sources and further reading

- [Postmark official pricing and plan comparison](https://postmarkapp.com/pricing/)
- [Postmark official message stream guide](https://postmarkapp.com/support/article/how-to-create-and-send-through-message-streams)
- [Postmark official transactional email policy](https://postmarkapp.com/support/article/804-what-are-transactional-emails)
- [Postmark website](https://postmarkapp.com/)
- [saashub listing](https://www.saashub.com/postmark)

For the complete Roseram buyer guide, see [Postmark review](https://roseram.com/reviews/scams/postmark-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
