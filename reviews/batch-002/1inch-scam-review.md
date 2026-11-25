# 1inch review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Decentralized finance and Web3 APIs  
**Method:** Source-led desk review; no hands-on testing is claimed.

1inch Business offers a suite of Web3 APIs and developer services, including swap, token, balances, portfolio, transaction and chain-data endpoints. It is infrastructure for building crypto products, not a promise that a trade will be profitable or risk-free.

## Editorial verdict

The official developer portal publishes product documentation, plan limits and commercial terms. The key buyer checks are whether commercial use is covered by the selected plan, how network and infrastructure fees affect a request, how a wallet authorizes transactions, and what happens when an endpoint or chain is unavailable. The public evidence reviewed does not support calling the service a scam.

## 1inch review: what the product does for crypto developers

The 1inch name covers consumer-facing decentralized-finance products as well as a developer business portal. This **1inch review** focuses on the latter because the catalog entry links to 1inch Business: APIs and services that developers can integrate into wallets, trading interfaces and other Web3 software. The published catalog includes swap routing, orderbook, balance, spot-price, token, transaction, portfolio, gas-price, NFT, tracing, history, Web3 RPC, domain, token-detail and chart products.

That breadth can reduce the work of stitching together blockchain data and execution paths, but the API is only one layer of a financial product. A quote does not remove token volatility, smart-contract risk, liquidity constraints, bridge or chain risk, wallet compromise or user error. The review evaluates the public technical and commercial materials; it does not recommend a token or claim that using 1inch makes a trade safe or profitable.


## 1inch API features and developer workflow

The Business portal presents APIs for common DeFi building blocks, with account-based access and API keys for subscription plans. A developer can select the products needed, authenticate requests, inspect API documentation and monitor usage. For a swap interface, the relevant evaluation is not simply whether an endpoint returns a route: it is whether the response exposes the amounts, route details, chain, token addresses, fees, expiry and failure conditions the application needs to show clearly before a user signs anything.

Before adopting an endpoint, create a small integration that uses the exact chains and tokens intended for production. Compare quotes at the same time against another source, include gas and any applicable infrastructure charge, simulate the user journey from approval through confirmation, and define how stale quotes and failed transactions are presented. No request, wallet signature, swap or integration test was performed for this review, so those steps remain buyer checks rather than claimed results.


## 1inch pricing, free plan and rate limits

The official pricing page lists a Developer tier with 100,000 API calls per month and a limit of 60 requests per minute. Its paid tiers list 1 million calls at 10 requests per second for Startup, 3 million at 20 requests per second for Professional, and 7 million at 40 requests per second for Business. The displayed paid price pairs are $149/$199, $299/$399 and $599/$799 respectively; the page offers billing-interval selection, so confirm which price corresponds to the interval and the exact invoice before purchase.

The page says prices exclude infrastructure fees. It also explains that standard plans do not turn short spikes into automatic overage bills: requests above the configured throughput are blocked with HTTP 429, and teams should upgrade, configure a custom plan or negotiate enterprise terms. That is more predictable than an unbounded bill, but a rate-limited integration still needs backoff, alerting and graceful handling. Multiple keys share account limits under standard plans, so creating extra keys is not a substitute for capacity planning.


## 1inch public API versus commercial use

The terms draw a meaningful line between the public API and business use. The public API is restricted to limited, non-commercial personal evaluation or access to functionality otherwise available through the 1inch frontend. The terms say profit-generating activity, trading activity and use in the course of a business require the appropriate commercial API subscription or agreement. A developer building an application for customers should not assume that an endpoint being reachable for free grants a commercial license.

The Developer plan appears as a free tier on the Business pricing page, but that should be evaluated within the account’s current commercial terms and endpoint permissions. Record which API family is enabled, what the chosen plan permits, what rate limits apply and whether any separate product-specific agreement is required. The commercial terms also say availability and compatibility can change, putting responsibility on the integrator to keep documentation and code current.


## 1inch USDC billing and transaction risk

The provider describes prepaid subscriptions paid in USDC on Ethereum and an optional x402 pay-per-call model on Base starting at $0.00018 per request, with a $2 minimum deposit. That can suit developers who want usage-based API billing, but it is crypto billing: network fees, wallet custody, chain settlement and payment authorization become part of the operating process. The amount shown for an individual call may be updated, so the protocol response or current dashboard should be checked at the point of authorization.

Under the commercial terms, x402 payments are authorized by the user’s cryptographic signature and, once authorized, are generally final, irreversible and non-refundable except for the specific contractual exceptions. The terms also place blockchain-network availability, delays and related transaction behavior outside 1inch’s control. Keep private keys out of application logs, do not trigger signed payments without clear user intent, and test billing separately from trade execution. This review did not move funds or authorize a payment.


## 1inch reliability, security and operational caveats

The commercial terms characterize the service as technology access and put responsibility for implementation and outcomes on the customer. They reserve the ability to update, suspend or discontinue APIs and do not guarantee that later versions remain backwards compatible. This does not by itself show poor service; it is a reason to pin and monitor integrations, read release notices, keep a fallback path where warranted and avoid making a single quote endpoint a hidden dependency for every customer action.

A product review cannot certify the security of a specific smart contract, wallet, token, RPC provider or third-party component. Before production, review the current technical documentation, obtain appropriate security assessment for your own integration, verify contract addresses from trusted sources and build explicit user confirmation around token approvals and on-chain transactions. Treat promotional “enterprise-grade” language as positioning, not a substitute for a service-level agreement, audit scope or deployment test.


## Who should consider 1inch and how to compare alternatives

1inch Business is a plausible candidate for teams that need several Web3 data and swap functions under one developer portal and can work within its plans, chains and legal conditions. A small prototype may start with the free Developer allowance; sustained production traffic needs a measured estimate of requests, rate bursts, historical retention and fee-bearing routes. Teams with a narrow requirement may prefer a direct chain provider, a single-purpose API or another routing service if it offers clearer coverage, contract terms or cost for their exact use case.

Compare alternatives with the same wallet, network, token pair, timestamp and transaction size. Include quote response time, route quality, gas, approval steps, reliability under load, support response, data handling and total cost—not just a headline API price. In a rapidly changing crypto environment, preserve the quote and terms shown at decision time, and never describe an API listing as independent validation of a token or investment.


## Is 1inch a scam? Evidence-based conclusion

The official Business portal identifies the service, documents multiple APIs, publishes subscription limits and provides terms for public, commercial and pay-per-call use. Those materials support treating 1inch as an identifiable Web3 infrastructure provider. They are not proof of a particular trade outcome, a guarantee that every connected third-party component is secure, or an endorsement of every token that can be queried or swapped.

No wallet was connected, no funds were moved and no transaction, smart-contract audit or live uptime test was performed. Confirm that the domain and account are authentic, select terms that cover your intended business use, verify each transaction in your wallet and understand the non-refundable payment conditions before signing. The material reviewed supports careful technical and financial due diligence; it does not substantiate a scam allegation.


## Features and decision criteria

- Swap, orderbook, balance, spot-price and token APIs
- Portfolio, transaction, gas, NFT, history and Web3 RPC APIs
- Quota-based subscriptions and x402 USDC pay-per-call
- Developer documentation, API keys and usage monitoring

## Sources and further reading

- [1inch Business API pricing and plan limits](https://business.1inch.com/pricing)
- [1inch Business documentation](https://business.1inch.com/portal/documentation)
- [1inch Swap API](https://business.1inch.com/products/swap)
- [1inch Business Terms of Service](https://business.1inch.com/portal/terms-of-service)
- [1inch Commercial API Terms of Use](https://business.1inch.com/portal/commercial-terms-of-service)
- [1inch Business subscription setup](https://business.1inch.com/portal/documentation/payment-methods/subscriptions/getting-started.md)
- [1inch Network on Wikipedia](https://en.wikipedia.org/wiki/1inch_Network)
- [1inch website](https://business.1inch.com/)
- [publicapi listing](https://publicapi.dev/1inch-api)

For the complete Roseram buyer guide, see [1inch review](https://roseram.com/reviews/scams/1inch-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
