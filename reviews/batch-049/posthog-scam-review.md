# PostHog review: features, pricing and buyer considerations

**Last editorial review:** 2026-10-21  
**Category:** Product analytics & experimentation  
**Method:** Source-led desk review; no hands-on testing is claimed.

PostHog provides product analytics and related tools for understanding product usage. Its documentation describes event-based trends, funnels, retention and paths, with links to session replay, feature flags and experiments.

## Editorial verdict

The cited publisher pages document a product, pricing units and privacy controls. They do not establish the correctness of your tracking setup or the lawfulness of your data collection. This review makes no fraud finding and does not claim to have installed or benchmarked PostHog.

## A useful dashboard starts with a trustworthy event

PostHog explains that analytics depends on the events and identity information your product sends. Our view: the first buying decision is whether your team can define the activity it wants to measure. A signup button click, a completed account and a paid subscription are different events. A beautiful funnel can mislead when those distinctions are lost.

Try a proposed instrumentation audit before adding more dashboards. Give one test account a known journey, record the expected sequence and compare it with the stored events. Check repeat visits and duplicate submissions. Keep a short event dictionary that another person can read. This is a suggested verification exercise; Roseram has not run it against PostHog for this article.


## Free allowances need a workload, not a guess

The pricing page lists monthly free quantities across several products. Our analysis: work backwards from what you plan to collect. A high-traffic landing page can generate many low-value events while a small paid product generates fewer, more meaningful actions. Define which decisions each event will support before treating a generous allowance as a reason to capture everything.

Build a sample month with expected visits, events per visit and the share of sessions you intend to record. Keep each billed product on a separate line. Then test a traffic spike scenario. Ask the publisher which settings can limit spend and what happens at the boundary. The numbers in the pricing table are dated observations, rather than a promise that your account will remain free.


## Privacy configuration is part of the implementation

PostHog states that customers decide what they collect and communicate to users, while the product supplies controls. That division matters. Purchasing analytics does not decide which information your business needs or which permissions apply. Keep those decisions with the responsible owner and document the collection you actually enable.

For a practical review, inspect a sample of events and recordings using non-sensitive test data. Look for fields that reveal more than the intended business question needs. Check access to the project, retention choices and removal procedures. Treat the privacy documents as implementation references, not a blanket certification for your own deployment. A simpler tracking plan can be easier to verify and maintain.


## Features and decision criteria

- Event-based product insights
- Funnels, retention and user paths
- Connections with replay and experiments
- Collection, processing and storage controls

## Pricing considerations

PostHog lists separate allowances and pricing units for different products. An event, recording and feature-flag request are different units. Check current rates, retention and project requirements before enabling paid usage.

## Sources and further reading

- [PostHog current product pricing](https://posthog.com/pricing)
- [PostHog product analytics documentation](https://posthog.com/docs/product-analytics)
- [PostHog privacy controls and customer responsibilities](https://posthog.com/docs/privacy)
- [PostHog website](https://posthog.com/)
- [saashub listing](https://www.saashub.com/posthog)

For the complete Roseram buyer guide, see [PostHog review](https://roseram.com/reviews/scams/posthog-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
