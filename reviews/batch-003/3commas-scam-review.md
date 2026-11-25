# 3Commas review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Cryptocurrency trading automation  
**Method:** Source-led desk review; no hands-on testing is claimed.

3Commas sells software for automating crypto trades through exchange connections. The most important buyer issue in November 2026 is a platform transition: 3Commas says its v1 service was deactivated on September 11, 2026; exchange orders already placed remain open but are no longer managed, and v1 bots and strategies do not automatically transfer to the v2 successor built with WunderTrading. New buyers should evaluate the current v2 offer rather than rely on legacy tutorials. The official pricing page displays Starter, Pro and Expert plan prices alongside higher reference amounts and a monthly/annual selector; confirm the charged amount, period, exchange-key allowance and active-bot caps in checkout. 3Commas describes itself as non-custodial and recommends trade-only exchange API keys with withdrawals disabled. Those controls reduce particular risks but do not remove exchange, credential or market risk. The official sources reviewed do not substantiate fraud. Roseram did not connect an exchange, place trades, audit security or test returns.

## Editorial verdict

The evidence supports a careful buyer review of a major product transition, not a fraud finding. Existing 3Commas v1 customers faced a real operational cutoff: the publisher says the service stopped on September 11, 2026, already-placed exchange orders remain live without management by the old automation, and strategies require rebuilding in v2. That transition deserves more attention than a feature comparison because unattended exchange orders can continue to affect an account after an automation dashboard is gone. For a new customer, the relevant product is the current v2 platform and its own integrations, plan limits and terms. The pricing page is dynamic and displays discounted and reference prices, so an old article or screenshot is not a quote. Use a demo environment first, connect an API key with withdrawals disabled, verify the permitted exchanges and active-bot limits, and keep an exchange-side recovery plan. The official sources reviewed describe a trading software business; they do not establish fraud. Roseram did not trade, verify profits, inspect customer accounts or independently audit 3Commas security claims.

## The first question is which 3Commas product you mean

A search for 3Commas can lead to years of v1 tutorials, current v2 product pages, exchange setup instructions and third-party commentary. Those sources do not all describe the same live service. This review is dated November 18, 2026 and separates the retired v1 workflow from the v2 platform the publisher now presents as its successor.

That distinction matters more than a familiar name in a browser tab. If you are new, judge the current product, its exchange coverage, limits and contract. If you used v1, start with the exchange account itself: verify what orders remain and whether any positions need attention before you rely on a new dashboard.


## What the official shutdown notice says

The 3Commas Help Center says v1 was deactivated on September 11, 2026. It says the bots and automations stopped, but orders already placed at an exchange can remain live and are no longer managed by 3Commas. The notice advises users to review open positions and orders at the exchange and revoke the old 3Commas API key.

This is an operational fact with a direct buyer lesson: turning off a bot service does not necessarily cancel exchange-side orders. A trader who has not checked the exchange may be relying on an old assumption about what software is still supervising. Use the exchange’s own order and position screens as the source of truth.


## V2 is a successor, not an automatic copy of a v1 account

The publisher describes v2 as a continuation built in partnership with WunderTrading, with familiar trading tools and additional capabilities. That continuity of branding should not be mistaken for automatic continuity of account configuration. The migration article says v1 strategies do not transfer automatically; users need to recreate them in the new product.

Before moving, write down each strategy’s entry conditions, safety rules, pair selection, position size and exit logic. Then compare the result in v2 line by line. If the original strategy was poorly documented, the migration is also a chance to decide whether it should be rebuilt at all.


## Where familiar bot workflows moved

The migration guide maps indicator-based DCA bots to the DCA Bot area in v2. TradingView-triggered and API-triggered DCA workflows are mapped to Signal Bots. Strategy Gallery strategies are presented as DCA Bot Presets. The guide describes a changed location and setup flow, not a promise that every former configuration behaves identically.

This detail is useful when comparing a tutorial with the current screen. A video showing a button in the old DCA menu may simply be out of date. For every recreated bot, compare the trigger type, supported market, order sizing and exit conditions before enabling trading. Do not use a demo result as proof of identical live execution.


## Protect the exchange account during the transition

If you used v1, the vendor specifically recommends reviewing exchange positions and orders and revoking the old API key. Do that at each exchange where a key was installed. Also review key permissions, IP restrictions and the account’s own activity log. A migration checklist is incomplete if it only covers the 3Commas account.

If you plan to use v2, create a fresh key with the narrowest permissions the exchange and required features support. The 3Commas guide says to allow trading and disable withdrawal permission. Where available, restrict the key to the publisher’s listed IP addresses. Keep credentials out of shared documents, screenshots and support chats.


## Non-custodial does not mean risk-free

3Commas describes itself as non-custodial: funds remain with the connected exchange, and its security page says the service cannot withdraw or transfer fiat or cryptocurrency. It describes a Sign Center for API signing and IP allowlisting as available security measures. These are publisher statements about its design; this review did not independently inspect the system or test a key.

Even a key without withdrawal permission can place trades that lose money or create unwanted exposure. Exchange account compromise, a key configured too broadly, an API outage, a bot rule error or a market move can still matter. Review the exact permission summary at the exchange before authorizing access, and start with a small, controlled test.


## Read plan limits as operating constraints

The current pricing page describes Starter as spot-focused and displays one simultaneously active exchange API key, five active DCA bots, two Signal Bots and two Grid Bots. Pro is listed with five active keys and larger bot caps; Expert shows up to 25 active keys and up to 1,000 active bots in each listed category. The page also notes that connected keys and keys that can trade simultaneously are not the same count.

Translate those limits into the portfolio and monitoring work you actually expect. Count the exchanges that must trade at the same time, not merely the number you might connect. Confirm whether the caps apply to active bots, accounts or a particular market, since a plan label alone does not answer every operational question.


## Treat the price card as a starting point, not the final bill

When checked on November 18, 2026, the pricing page displayed Starter at $15 alongside $20, Pro at $38 alongside $50, and Expert at $105 alongside $140 per month. It also presents a monthly/annual selector and savings language. The extracted page does not make every promotion and billing condition unambiguous, so the lower figure should not be copied into a budget without checking the selected term.

Before paying, save the checkout screen and confirm currency, renewal frequency, taxes, discount end date, cancellation route and exchange/bot caps. Compare the full term rather than the most prominent monthly equivalent. Older price tables can become inaccurate quickly when the product is changing plans as well as platforms.


## Use demo mode to learn the interface, not to forecast profit

The pricing page lists a demo account among plan inclusions. That can be useful for learning how to connect a simulated market, create a bot and inspect its orders without committing a live exchange balance. It cannot establish that a strategy will earn money or that live fills, fees and slippage will match a simulation.

Write a small test plan: create a bot with a known trigger, verify its expected action, test a stop or disable path, and confirm what happens if the exchange connection fails. Then check the same state at the exchange, not only in the automation interface. Keep the test small enough that an unexpected action is manageable.


## Automation changes execution, not market uncertainty

Bots can apply rules consistently, but they do not remove uncertainty about price, liquidity or market structure. A backtest, chart, preset or AI-generated strategy is not evidence of a future return. Trading fees, funding, slippage, exchange outages and an incorrectly selected pair can change the result even when a bot follows its instructions exactly.

Decide in advance how much you can lose, which markets are permitted and who can stop the automation. If a strategy requires constant supervision, quantify that attention as part of the cost. Do not fund a bot with money needed for near-term expenses, and do not interpret a feature list as investment advice.


## Check the migration terms separately from the new product pitch

The transition help article describes v1 deactivation and discusses subscription options for eligible legacy users. Those arrangements concern the transition; they are not necessarily the terms offered to a new v2 customer today. A promotion or credit for an existing account should not be assumed to apply to a fresh signup.

Ask support to put any migration credit, expiry date, refund, account eligibility or exchange compatibility answer in writing. Keep the original subscription receipt and the relevant terms. If you are buying new, read the new product’s current plan, renewal and cancellation language rather than applying an old v1 FAQ to v2.


## What this review can and cannot establish

The sources reviewed are official 3Commas product, pricing, security and help materials. They support the product descriptions and transition details attributed above. They do not independently establish uptime, security effectiveness, actual customer returns or the experience of every account. No exchange was connected and no live order was placed for this review.

The words SCAM Review in the page title are a search label for a buyer check; they are not evidence of criminal conduct. The material reviewed does not substantiate fraud. Readers with a specific billing or account issue should preserve their own records and contact the exchange and the provider through authenticated channels.


## Alternatives depend on how much automation you need

Compare 3Commas with the exchange’s own native tools, a manual workflow or another automation provider based on the same exchange, bot type and market. Ask how each handles exchange authorization, failed signals, order cancellation, position monitoring and data export. For a v1 migration, compare the exact v2 mapping with any alternative before rebuilding a large strategy library.

An alternative is not automatically safer or more profitable. Make a small feature matrix, verify supported exchanges in current documentation and read the pricing at checkout. If your plan can be expressed with a simple exchange-native order, a third-party automation layer may add complexity without enough value.


## Who may find 3Commas worth evaluating

A technically comfortable trader who already understands exchange orders, API scopes and the risks of automated execution may find the current v2 platform worth evaluating. The strongest evidence-based fit is someone who wants to build or monitor multiple rule-driven workflows and is prepared to validate each bot against the exchange itself.

A legacy v1 user may value the published migration map, but should treat strategy recreation as a fresh setup. Start with the smallest strategy that can test a required feature. Keep screenshots or written settings, and confirm that the current product supports the exchange and market your plan needs.


## Who should pause before connecting an account

A first-time crypto buyer who cannot explain the difference between a trade key and a withdrawal-enabled key should pause. So should anyone expecting a bot to guarantee returns, leave open orders safely managed during a service outage or replicate an old v1 strategy without review. Those expectations are not supported by the product materials.

If you need a regulated financial adviser, custody service, tax calculation or guaranteed order handling, confirm whether 3Commas supplies that specific service; do not infer it from trading automation. Use exchange-native support for open positions and keep control of the exchange account independent of any bot dashboard.


## A buyer checklist before starting a paid plan

Check the exact v2 exchange list, account connection method and active-key cap. Confirm plan price and renewal period in the checkout. Rebuild one strategy in demo mode, verify its trigger and exit, and inspect how to pause it. Create a trade-only API key, disable withdrawals and use an IP allowlist if supported.

For v1 accounts, inspect exchange-side orders and positions, then revoke old keys the publisher says are no longer needed. Save the current plan terms and migration answers. If a provider cannot clarify a price, permission or failure behavior that is material to your decision, treat it as unresolved and do not scale up yet.


## The practical conclusion

3Commas is a trading automation product whose buyer story in late 2026 is shaped by a completed v1 shutdown and a v2 successor. The concrete facts are more useful than a generic rating: v1 automations stopped, exchange orders may remain open, old strategies do not automatically transfer, and the current pricing page has plan-dependent limits that should be checked in checkout.

For a new user, judge v2 on a demo setup and the permissions your exchange will grant. For a former v1 customer, first inspect the exchange. The reviewed sources do not establish fraud, profitability or independent security assurance. Make the purchase decision on current terms, operational controls and the risk you can afford.


## Features and decision criteria

- Connect exchange accounts through API keys and configure supported trading automations
- Current pricing lists DCA, Signal and Grid bots, with plan-dependent active-bot and exchange-key limits
- The v2 transition guide maps several legacy bot workflows to new locations and presets
- 3Commas describes a non-custodial model and publishes API key security guidance; these are publisher statements, not an independent audit
- A demo account is listed among the plan inclusions on the pricing page

## Pricing considerations

Official pricing page checked November 18, 2026. Its text presents both lower displayed amounts and higher reference amounts, with a monthly/annual selector and savings language. The rendered page may show a promotion or a different billing selection by region or account. Treat the live checkout as controlling; save the amount, renewal period, cancellation path, tax, exchange-key allowance, and active bot limits before paying. Pricing can change.

## Frequently asked questions

### Is 3Commas a scam?

The official materials reviewed describe a trading automation service and a transition from v1 to v2. They do not substantiate fraud. The SCAM Review label is a buyer-diligence format, not a legal finding or allegation. This review did not connect an exchange or audit the service.

### Is 3Commas v1 still operating?

3Commas says v1 was deactivated on September 11, 2026. Its help article says automations stopped and exchange orders already placed may remain open without being managed by 3Commas. Check positions and open orders directly at the exchange and review the old API key.

### Do 3Commas strategies transfer to v2?

The publisher says v1 strategies do not transfer automatically. Its migration guide maps older workflows to current v2 areas—for example, TradingView and API-triggered DCA workflows move to Signal Bots, while Strategy Gallery items become DCA Bot Presets. Rebuild and verify each strategy rather than assuming settings carried over.

### How much does 3Commas cost?

The official pricing page checked November 18, 2026 displayed Starter at $15 alongside $20, Pro at $38 alongside $50, and Expert at $105 alongside $140 per month, with a monthly/annual selector. Confirm the selected billing period, actual charge, tax and limits in your own checkout.

### Can 3Commas withdraw my crypto?

3Commas says its software cannot withdraw or transfer funds, and its API guide tells users to grant trading access only and disable withdrawals. Those are publisher descriptions and setup guidance. Review the exact permissions at your exchange, use any supported IP allowlist, and never paste a withdrawal-enabled key into a third-party service.

### Does using 3Commas guarantee profitable trades?

No. Automation can follow configured rules; it cannot guarantee market direction or profit. A demo account can help you understand setup, but simulated results do not prove live performance. Decide your maximum loss and test exchange-side stop and recovery procedures before authorizing live trading.


## Sources and further reading

- [3Commas Help Center: v1 deactivation, open orders and v2 transition](https://help.3commas.io/en/articles/16245835-3commas-v2-everything-you-need-to-know)
- [3Commas Help Center: v1-to-v2 feature and bot migration guide](https://help.3commas.io/en/articles/16300161-moving-from-3commas-v1-to-3commas-v2-feature-bot-migration-guide)
- [3Commas current pricing and plan limits](https://3commas.io/pricing)
- [3Commas security overview and publisher-described custody/API controls](https://3commas.io/security)
- [3Commas Help Center: create and connect exchange API keys](https://help.3commas.io/en/articles/16281186-create-and-connect-api-keys)
- [3Commas developer documentation: API errors and permissions](https://developers.3commas.io/quick-start/errors/)
- [3Commas website](https://3commas.io/)
- [saashub listing](https://www.saashub.com/3commas)

For the complete Roseram buyer guide, see [3Commas review](https://roseram.com/reviews/scams/3commas-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
