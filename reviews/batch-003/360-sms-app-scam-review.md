# 360 SMS App review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Salesforce-native messaging and SMS software  
**Method:** Source-led desk review; no hands-on testing is claimed.

360 SMS App is a Salesforce-installed messaging product for SMS, MMS and other customer communication workflows. It describes one-to-one and batch messaging, scheduled or triggered sends, templates, inbound processing and consent controls. Its terms make the cost model more complex than a seat license alone: user licenses, phone numbers, carrier and registration charges, a 10% administrative fee on specified carrier-related amounts, segment-based billing and charges for messages submitted even if they are not delivered all require careful review.

## Editorial verdict

The vendor publishes a detailed service agreement, Salesforce setup guides, messaging documentation and opt-in/opt-out material. The evidence reviewed does not substantiate a scam accusation. The main buyer risks are configuration and spend control: SMS consent must be valid, STOP handling must be tested across every campaign path, Unicode can multiply billable segments, and submitted messages may remain chargeable when filtered or rejected. Confirm all rates and fees in the order form and test suppression in a Salesforce sandbox before launch.

## What 360 SMS App adds to Salesforce

360 SMS App is a managed Salesforce package for communicating with customers from CRM records and workflows. Its documentation describes individual and batch SMS or MMS, scheduled messages, templates, inbound keyword handling, alerts, automation and conversation views. The vendor also markets WhatsApp, telephony and other messaging channels. Because it is installed in a Salesforce organization, setup involves Salesforce permissions, licenses, sender numbers and channel configuration rather than a standalone texting login.

A CRM-centered approach can keep message history and consent fields near customer records, which may help staff understand prior communications. The vendor says the product is Salesforce-native, but its current terms qualify this: data processing is largely inside Salesforce with exceptions for message transmission and limited system metadata or security logs. Ask for a current data-flow diagram and confirm which fields, content and metadata leave the Salesforce environment.


## Messaging features and the Salesforce setup burden

The user guide describes installation from Salesforce AppExchange, permission sets and user licenses for outbound sending. It says trials may allow unlimited users during evaluation, while production users who send messages need licenses. The vendor’s batch guide lists sending from list views, reports and campaigns, with opted-out records skipped even if the report itself did not filter them. These are useful controls, but they still depend on correct configuration and testing.

Before rollout, test on a Salesforce sandbox with a small set of consenting internal numbers. Verify that an inbound STOP or equivalent opt-out updates the correct record, blocks manual sends, suppresses scheduled campaigns and stops flows or integrations. Check duplicate contacts, shared numbers, consent timestamps, campaign membership, sandbox-to-production differences and error logging. A checkbox on one contact record does not guarantee suppression across every object or data-import path.


## Consent, opt-out and compliance responsibility

The vendor describes opt-in and opt-out fields, channel or geography preferences and automatic handling for recognized keywords. Its compliance pages explain the importance of recording consent and honoring opt-outs. These tools can support a compliance program, but they do not decide whether a particular organization has lawful consent to send a particular message in a particular jurisdiction. The sender remains responsible for the audience, message purpose, timing and legal basis.

Write down how consent is collected and retained, which disclosure the recipient sees, who can change consent fields and how withdrawal is propagated. Test all known opt-out keywords and natural-language requests under the organization’s current settings. Make sure messages identify the sender and offer any required help or opt-out instructions. Review applicable laws, carrier rules and industry-specific requirements with qualified counsel; the vendor’s marketing guide is not a substitute for that review.


## Fees, segments and delivery billing

The current terms describe several separate costs: user licenses, phone-number fees, carrier charges, registration and recurring A2P/10DLC fees, per-segment surcharges and a 10% administrative fee on specified carrier-related charges. Message length affects segment count. The terms say GSM-7 messages use one segment up to 160 characters and 153-character segments thereafter; Unicode characters such as emoji or curly punctuation can change encoding to a 70-character initial segment and 67-character subsequent segments.

The terms also say messages are charged when submitted to the carrier network even if a carrier filters or rejects them. That makes cost controls essential. Ask for the exact country-specific rates, registration fees, number rental, international pricing, MMS charges, minimum commitments and treatment of failed sends. Set alerts and hard limits, estimate typical message length in real templates, and verify whether the dashboard shows segments, carrier outcomes and administrative fees clearly enough to reconcile invoices.


## Data handling and security boundaries

360 SMS describes the product as Salesforce-native and the service terms state that most data operations occur inside the customer’s Salesforce instance, with defined exceptions for transmission, metadata and security logging. The terms also put responsibility for securing the Salesforce environment on the customer and disclaim responsibility for breaches in that environment. This boundary is important: installing a managed package does not automatically configure least-privilege access, retention, identity controls or monitoring for the organization.

Request the full current security overview, subprocessors, transmission flow, retention periods, breach notification terms and support-access controls. Verify which staff and vendor personnel can view message content, how logs are protected, and whether support exports contain personal data. Review Salesforce permission sets, connected apps, API access and audit logs before production. The product’s messaging data model should be included in the organization’s retention and deletion rules.


## Pricing, evaluation and alternatives

The public materials reviewed do not provide a single complete price for a deployment. The product uses Salesforce licensing and communication charges, with carrier and registration costs that vary by country, channel and volume. A written quote should break out seats, phone numbers, message rates, registration, carrier surcharges, the administrative fee, onboarding, support, AI features and any third-party carrier account requirements.

Compare the package with Salesforce’s built-in messaging options, a direct carrier or CPaaS integration, and other Salesforce-native apps. Use a representative month of contact volume, real template lengths and campaign types to model total cost. Evaluate deliverability, inbound conversation handling, permission administration, opt-out propagation, reporting and data retention. No 360 SMS installation, carrier account, message campaign or production suppression flow was tested for this review.


## Is 360 SMS App a scam? Review conclusion

360 SMS publishes product documentation, Salesforce installation guides, messaging workflows and detailed terms covering charges, data handling and responsibility. Nothing in the material reviewed substantiates calling it a scam. The product appears to have a defined CRM messaging use case, but the true cost and compliance behavior depend heavily on sender configuration and the customer’s Salesforce setup.

Before launch, obtain the complete rate schedule, test opt-out behavior end to end, confirm which data leaves Salesforce, and place usage alerts or caps where available. The sender must maintain valid consent and follow the applicable rules. This is a source-based product assessment, not a legal compliance certification, deliverability benchmark or hands-on implementation review.


## Features and decision criteria

- Salesforce-based SMS, MMS and additional messaging channels
- One-to-one, batch, scheduled and automation-triggered messages
- Templates, inbound keyword handling, opt-in/opt-out fields and analytics
- Carrier, A2P/10DLC, phone-number, segment and administrative fees

## Sources and further reading

- [360 SMS App website](https://360smsapp.com/)
- [360 SMS terms of service](https://360smsapp.com/terms-of-service/)
- [360 SMS configuration user guide](https://360smsapp.com/knowledge-base/configuration-user-guide/)
- [360 SMS batch texting guide](https://360smsapp.com/knowledge-base/batch-texting-techniques/)
- [360 SMS opt-in and opt-out guide](https://360smsapp.com/manual/opt-in-opt-out-compliance/)
- [360 SMS API integration guide](https://360smsapp.com/wp-content/uploads/2024/05/Open-API-Guide-Integration.pdf)
- [Salesforce AppExchange guidance](https://360smsapp.com/manual/appexchange/)
- [saashub listing](https://www.saashub.com/360-sms-app)

For the complete Roseram buyer guide, see [360 SMS App review](https://roseram.com/reviews/scams/360-sms-app-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
