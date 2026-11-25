# Rork review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** AI-assisted mobile and web app development platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

Rork is an AI-assisted app-building platform whose current documentation distinguishes design-only work on its free plan from building and publishing working applications on paid plans. Its Rork Max product describes native SwiftUI apps for Apple platforms, Kotlin and Jetpack Compose for Android, and React-based web apps; older projects may use React Native and Expo. Credits measure AI work and can also be consumed by build or simulator use. Store accounts, review decisions, ongoing app maintenance and end-user privacy obligations remain separate responsibilities.

## Editorial verdict

Rork publishes current plan documentation, a detailed FAQ, terms, privacy disclosures and platform guidance. The sources reviewed do not establish that Rork is a scam. The most consequential purchasing checks are the credit budget and failure charges, which account sees which plan, whether a project uses the new or legacy stack, what code export requires, and what information is retained or sent to connected services. A generated app still needs engineering review, testing and store approval. This is an editorial desk review, not a firsthand app build or an independent security audit.

## Rork review: turn a prompt into an app project, then take responsibility for the product

Rork is an AI-assisted development service for people who want to describe an app and work through screens and code with an agent. Its current product documentation separates Design mode, which explores a concept and its screens, from Build mode, which creates an application that can be previewed, tested, edited and prepared for distribution. That distinction explains the practical boundary in the plan table: the free tier can help shape a concept, while a paid plan is needed to build and publish a working project. A visual preview can help a founder make the idea tangible, but it does not by itself validate the app's data model, security, performance or suitability for a store.

The product can be useful as an accelerator for prototypes and early implementations. Rork's FAQ describes apps with multiple screens, API integrations, on-device storage and AI features, alongside connections to services such as Supabase, Firebase and RevenueCat. The important buyer question is whether the generated result is a starting point your team can inspect and own operationally. Before committing to a large app, identify which backend, authentication, payment, notification and analytics choices the project will use, and test a small end-to-end slice. A polished onboarding screen is only one component of a reliable application.


## Rork pricing: design credits are not the same as a finished mobile app

The official subscription guide, updated November 11, 2026, says the free plan offers Design mode and no build mode. It describes five design credits per day, with a monthly total that varies by region: up to 35 in major markets and five in other regions. The guide says Rork Max starts at $20 per month for 100 credits, and lists larger monthly options from $200 through $1,800 for 1,000 to 10,000 credits. It also identifies an India-specific Start plan and says some older accounts may still see Rork Pro. This is a meaningful account-cohort distinction, so public marketing prices should not be treated as the exact quote for every user.

A credit represents AI compute, roughly one request, but the guide notes that a substantial request can cost more than one credit. Build activity can add to the cost of a message, and running a cloud simulator spends credits by the minute. The FAQ explains that credit use can continue while the agent works through steps, and that an unsuccessful result may still consume AI or build work. That makes credit planning different from paying a flat fee for a guaranteed app. Estimate the work from a small sample project: count screens, iterations, build runs, simulator time and fixes, then compare the expected monthly use with the tier's allowance.

The price page is a snapshot, not a promise that each account sees the same plan. Before paying, check the billing screen for the account's plan name, renewal date, credits, top-up options and cancellation route. The FAQ says paid-plan credits reset on the monthly anniversary and describes top-ups and auto top-up for paid users. Confirm the current price and renewal basis at checkout, especially when a subscription was purchased through a mobile store or created under an older plan. Keep an internal alert before the renewal date and set a spending owner so the project does not quietly grow into an unexpected monthly commitment.


## Native iPhone and Android output, plus a legacy-project distinction

Rork's current FAQ says Rork Max builds native iOS apps with SwiftUI and native Android apps with Kotlin and Jetpack Compose, while web apps use React and Vite. The company says it can run Xcode builds in cloud Macs and stream a simulator preview to a browser. The FAQ also makes a crucial migration distinction: projects created before its move to native code can remain React Native and Expo projects. A buyer should inspect the actual project type rather than infer the implementation from the current product name or a feature page. Platform support and output format can affect which developer tools, libraries and expertise are needed after generation.

Native output may be a good fit when a project needs platform-specific interface behavior, store distribution or direct use of Apple or Android APIs. It also means testing multiple device sizes and platform versions remains necessary. A simulator is a useful development aid, but an app should be exercised on real devices where possible, with accessibility, permissions, offline behavior, network failure, battery use and data deletion included in the review. A successful compile is not the same as a secure production release, and an AI-generated implementation does not eliminate the need to understand its dependencies or review code that touches accounts and payments.

Rork's FAQ says projects can target iPhone, Android and web, and that Max adds capabilities across iPad, Apple Watch and Vision Pro, including widgets and other platform-specific experiences. Treat those as available product capabilities to investigate rather than a guarantee that every generated feature will be complete on the first attempt. Define a narrow acceptance checklist for each platform: what must work, what permission appears, how an error is shown, and how a user can recover. For a cross-platform product, keep shared business rules separate from platform-specific views so that a generated change in one app does not silently break another.


## Preview, publishing and the app-store approval boundary

Rork's FAQ describes an App Preview flow for testing before publication. Its publishing instructions say the service can compile iOS apps and upload them to App Store Connect, after which the customer confirms whether to submit the build for Apple review. The FAQ identifies a paid Apple Developer Program membership, listed there as $99 annually with possible country variation, as a separate requirement. For Google Play, the FAQ says Rork generates an Android App Bundle that the developer uploads manually in Play Console; APK downloads are useful for testing. These steps mean the software can prepare an artifact and streamline parts of release work, while the developer account and store review still govern actual availability.

No builder can guarantee that Apple or Google will accept an app. The app owner remains responsible for accurate store metadata, privacy disclosures, content rules, intellectual-property permissions, billing design, account access and any requested corrections. Before buying a plan on the assumption that an app will be published immediately, inspect current store requirements and confirm that the intended account can sign and submit the generated build. If publication is a critical date, reserve time for a rejected build, a policy clarification, metadata correction or a rebuild rather than treating the app-builder button as an approval decision.

A safe release checklist includes a build artifact with the correct bundle identifiers, signing configuration, version, screenshots and privacy details; a test account with appropriate permissions; and a device-level pass through the main user journey. Confirm that personal data is collected only when needed, that the app includes a working deletion or support path where required, and that the store listing accurately describes functionality. Use a staged test release when practical. Rork's publishing features can reduce manual steps, but the release owner still needs access to the Apple or Google account and should keep credentials and signing assets under organizational control.


## Code export and project portability

Rork's FAQ says that users own generated code on paid plans and can use a GitHub integration to export and continue development in Cursor, VS Code or another IDE. It describes a two-way synchronization workflow and different project types for SwiftUI, Kotlin, React/Vite and older React Native/Expo apps. This is an important practical benefit: a team can move work into a familiar review, version-control and deployment process instead of treating the app builder as the only place where the product can be maintained. Confirm the paid-plan prerequisite and test an export early, while the project is small enough to understand.

Portability should be checked with an actual repository rather than inferred from a marketing statement. Verify that source files, assets, environment configuration, build instructions, package dependencies and the relevant project history are present. Ask another developer to clone the repository into a clean environment, build it and run a preview without relying on local caches or undocumented secrets. Confirm what happens to server functions, generated API credentials and hosted backends when code is exported. A portable client project is not automatically a portable backend, database, deployment pipeline or third-party account.

The Terms of Service say Rork retains rights in the service itself while excluding the customer's content and applications; they also limit the license to use Rork's platform. The FAQ separately states that generated code is owned by users on paid plans. A buyer should read these together and check the exact plan and terms that apply to their account. Keep a scheduled export and a backup of source and assets, and record which services the project calls. That reduces the chance that a plan change, account issue or product change leaves the app without a usable development path.


## Integrations, backend choices and recurring operational costs

The official FAQ describes integrations with Supabase and Firebase, a Rork Backend for serverless functions, third-party APIs, hosted AI capabilities and RevenueCat for in-app purchases or subscriptions. It also says paid plans can host AI features without requiring a user to paste provider keys into each app. These integrations can help move a prototype toward a fuller product, but every connection adds a service boundary. The person building the app must understand where authentication lives, where user records are stored, which system can read a secret, how a payment event changes entitlement, and what happens if one provider is unavailable.

Price the whole system rather than only the app-builder subscription. Potential costs include cloud functions, database storage, model calls, media, app-store memberships, payment processing, analytics, domains and customer support. Decide which service owns each record and who can export or delete it. Keep payment and model secrets on a trusted backend; the FAQ presents server-side API calls as a Rork Backend capability, which is a safer pattern than embedding long-lived keys in a mobile bundle. Check whether the integration's current plan and region support the feature, and test access controls before using real customer data.

A useful first milestone is a deliberately small vertical slice: sign in, create one record, call one permitted API, display the result, and then delete the account or record through the intended process. Test unauthenticated access, revoked credentials, network interruption, slow response and duplicate submission. Document which provider handles each step and which user consent is required. This is proposed buyer diligence, not a claim that Roseram implemented or tested an app with Rork. An AI builder can generate integration code quickly, but the product owner is still accountable for the authorization rules and lifecycle behavior.


## Privacy, project data and user-facing obligations

Rork's privacy policy describes collection of account details, project prompts and source code, assets and generated output, technical usage information, transactions, connected-service data and support communications. It says project content is retained for the life of the account and routine backups, may persist after closure, and can be subject to a deletion request. The policy also says connected-service providers may retain request records for up to a year, separate from their technical logs. Those disclosures help buyers identify questions before uploading code or customer records; they do not mean all data has the same retention period or is processed only by Rork.

The policy describes advertising measurement and sharing of certain identifiers or activity when marketing tracking is permitted by the user's choice and applicable regional rules. For projects that collect end-user information, Rork's terms say the app publisher, rather than Rork, acts as the controller or responsible party for that collection. The publisher must provide legally sufficient notices, obtain required consent, use information lawfully, protect it and honor applicable access, correction or deletion rights. An app builder's privacy policy does not become the privacy notice for every app made with it.

Before sharing proprietary source or real customer data with an AI coding service, review internal policy, the privacy disclosures, the connected providers and the contractual terms. For mobile apps that request Apple Developer credentials or submit builds, the current Rork policy describes encrypted storage of sessions and generated App Store Connect keys until account deletion or disconnection. That makes credential handling a specific procurement topic: understand who can disconnect, how a key is deactivated, how the app owner monitors access, and what cleanup is needed after a project ends. Use synthetic data during evaluation, rotate credentials when appropriate, and test the application's own deletion flow before release.


## Terms, plan enforcement and practical buyer safeguards

Rork's Terms of Service identify Rork, Inc., describe a limited license to use its platform, and state that the customer retains rights to content, applications and data created or processed using the service. They also provide that fees may change with notice, paid access may be suspended for non-payment, and the service can be modified or discontinued. The agreement includes warranty disclaimers, liability limitations and an indemnification provision tied to the customer's content, app and use. These are significant clauses to review as a business buyer, particularly if the generated app will serve paying customers or handle sensitive information.

A customer should keep an independent copy of the generated source, assets and documentation; identify the support channel and response expectations; and decide how the project would continue if a feature or plan changes. Before production, check that licenses for generated content and third-party packages permit the intended use, and obtain permission for any brand, dataset or interface the app reproduces. Build regular backups and retain access to app-store accounts, domains and backend credentials. A contract review is especially worthwhile where an app has meaningful revenue, regulated data or obligations to end users.

The company's own documentation distinguishes current plans by credits and account history. Do not assume an allowance, feature or code-export right from a blog post or another user's screenshot. Save the plan details, renewal terms and current support guidance shown to the purchasing account. If usage is credit-metered, set a budget and a person responsible for monitoring it; if a task appears stuck, the FAQ advises stopping and contacting support rather than assuming the status is idle. Written cost controls and an export backup are simple safeguards for a product that evolves through many AI-assisted iterations.


## Rork alternatives and an honest evaluation exercise

Alternatives include conventional native development in Xcode or Android Studio, cross-platform stacks such as React Native, managed no-code tools and other prompt-led app builders. A conventional codebase can provide more direct control but requires developer time. A low-code platform can speed up standard workflows but may have different export and hosting boundaries. A generative builder can compress early design and implementation loops, yet it also introduces model-credit costs and a need to review generated architecture. Compare these choices against the actual target: a clickable concept, a private internal utility, a web app, or a store-distributed consumer product.

Run a controlled evaluation using the same short specification in each candidate. Ask for a login screen, one data-backed list, an edit form and a deletion flow. Record time to first working preview, number of corrective prompts, credit use, errors, accessibility issues and whether another developer can maintain the result. Export the code, build it from a clean checkout, inspect dependency and secret handling, and test on a real device. These are suggested checks, not performance measurements made by Roseram. They reveal whether the tool saves effort for your team rather than merely producing an impressive first screen.

Choose based on which environment leaves you with the best maintainable product at a known cost. For an experiment that may be discarded, rapid iteration could matter most. For a long-lived service, stable source export, reliable backend ownership, privacy commitments and store-update procedures may outweigh generation speed. Do not let an early prototype become a production system without a deliberate review of architecture, security, accessibility, error handling and ownership. A build tool's ability to generate code is useful; it is not the same as accepting operational responsibility for the app.


## Rork SCAM Review: evidence and buying conclusion

Rork publishes official subscription documentation, a product FAQ, technical and publishing guidance, terms and privacy disclosures. The materials describe a real app-building workflow with plan-dependent design and build modes, credit-based usage, platform-specific project outputs and code-export options. The sources reviewed do not establish that Rork is a scam. The decision instead turns on whether its current plan, stack, data handling and export path fit the buyer's project and whether the customer is prepared to test and maintain the generated app.

This is a source-based desk review, not a firsthand Rork subscription, generated project, store submission, security audit or measured benchmark. Prices and feature entitlements were checked in public documentation on November 17, 2026; account, region and legacy-plan differences can change the actual offer. Before purchase, verify the account-specific credit balance and renewal, test a small project, export it under the applicable plan, and review how failed work is billed. Before production, validate the native build on real devices, confirm signing and store ownership, inspect external-service data flows and provide the user notices and deletion paths required for the app.

Rork may be a practical accelerator for a founder or team that wants to explore an app and can retain engineering oversight. It is less compelling if the buyer expects a finished, policy-approved release from a prompt, unlimited build work at a fixed low price, or a backend that requires no separate operational and privacy decisions. Treat a generated project as the beginning of software ownership. The most useful purchase test is whether your team can move from idea to a functioning, documented and maintainable application within a credit budget it understands.


## Features and decision criteria

- Prompt-led design and build workflows for iOS, Android and web projects
- Native SwiftUI output for supported Apple projects and Kotlin with Jetpack Compose for Android; legacy projects may differ
- Project preview, integrations, publishing guidance, and code export or GitHub sync on paid plans
- Credit-metered AI work, build activity, and simulator or emulator usage

## Pricing considerations

The public subscription documentation was checked on 2026-11-17 and says it was updated November 11, 2026. It describes accounts created on or after August 4, 2026 as seeing Rork Max, while earlier accounts may retain Rork Pro; the FAQ says plans and prices can vary by account and region. A message can cost more than one credit, builds can add cost, and a cloud simulator consumes credits by minute. The FAQ says some unsuccessful AI work may still consume credits, while certain failed or cancelled preview actions are free. Check your own billing screen and the current credit rules before selecting a tier.

## Sources and further reading

- [Rork pricing, plans and credit rules (official documentation)](https://docs.rork.com/introduction/subscriptions)
- [Rork official FAQ: native platforms, integrations, publishing and billing](https://rork.com/faq)
- [Rork Terms of Service, updated November 11, 2026](https://rork.com/terms)
- [Rork Privacy Policy, updated November 14, 2026](https://rork.com/privacy)
- [Rork Android App Bundle generation guide](https://docs.rork.com/submitting-to-play-store/creating-the-aab-file)
- [Rork product and web app information](https://rork.com/web)
- [Rork documentation home and supported development guides](https://docs.rork.com/)
- [mobile app development on Wikipedia](https://en.wikipedia.org/wiki/Mobile_app_development)
- [Rork website](https://rork.com/)

For the complete Roseram buyer guide, see [Rork review](https://roseram.com/reviews/scams/rork-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
