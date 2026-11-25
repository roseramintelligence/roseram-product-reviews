# Prometheus review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-16  
**Category:** Time-series monitoring and alerting  
**Method:** Source-led desk review; no hands-on testing is claimed.

Prometheus collects and stores metrics as time series, with labels identifying dimensions and queries used for analysis and rules.

## Editorial verdict

The open-source project documents its monitoring model. Evaluate the data retention and support promises of a hosted provider separately.

## Prometheus scrape monitoring for an on-call operator

Begin with the step a customer will notice when it breaks. Instrument a sample endpoint and stop it in a trial environment. Ask the operator to find which target failed and what the customer experienced. Watch how missing data appears alongside normal activity.

Write a **Prometheus alert rule** around one action the operator can take. Exercise a real fault and a short nuisance spike separately. Decide how long the signal must persist and who gets paged.


## Prometheus label cardinality and operating cost

Review which label values can grow without bound. Identify a request identifier or customer-specific label that would create many distinct series. Use aggregate dimensions where they tell the operator enough to act. Track the change to query usefulness as well as resource usage.

Agree on *retention and recovery expectations* before moving important monitoring to the new setup. Budget for the service, the alert destination and the people who must keep the rules intelligible after the original author moves on.


## Features and decision criteria

- Metric collection and time series
- Label-based queries
- Recording and alerting rules

## Sources and further reading

- [Prometheus project overview and documentation links](https://prometheus.io/docs/introduction/overview/)
- [Prometheus monitoring software on Wikipedia](https://en.wikipedia.org/wiki/Prometheus_(software))
- [Prometheus website](https://prometheus.io/)
- [saashub listing](https://www.saashub.com/prometheus)

For the complete Roseram buyer guide, see [Prometheus review](https://roseram.com/reviews/scams/prometheus-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
