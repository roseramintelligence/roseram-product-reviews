# 1ty.me review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** One-time secret sharing service  
**Method:** Source-led desk review; no hands-on testing is claimed.

1ty.me is a one-time secret-sharing service that creates a short URL for text, displays the note on first access and says it then deletes the stored record. Its FAQ describes HTTPS, encrypted notes and a decryption-key portion carried in the URL; the privacy policy says unread notes are removed after 30 days and discloses submission IP, date and time. These are provider statements, not a current cryptographic audit. The privacy policy is explicitly last modified April 18, 2011, does not identify current encryption algorithms or independent assessments, and allows an optional email notification/newsletter path. Because the URL is a bearer secret and one visit consumes the note, the system should not be treated as a modern enterprise secrets manager without current technical documentation. The evidence reviewed does not substantiate calling 1ty.me a scam.

## Editorial verdict

The official site identifies 1ty.me as an ApogeeInvent service and describes a working one-time note-sharing concept: create a link, send it to a recipient, and delete the stored note after it is viewed. This evidence does not substantiate a scam claim. The design can be convenient for a low-risk, one-off message, but the assurance gap is serious for credentials or other sensitive data. The encryption and one-view deletion statements are self-published, the privacy policy dates to 2011, and the pages do not provide an algorithm, key-generation specification, current architecture, independent audit, modern retention/logging detail or organizational controls. A URL containing the decryption capability must be protected like the secret itself. No message, live cryptographic behavior, network request, deletion, or notification was tested.

## 1ty.me review: a simple one-view link for a short secret

1ty.me offers a small, focused workflow. A sender enters text, asks the site to generate a short URL and sends that URL through a chosen communication channel. The recipient opens it, reads the note and, according to the product description, the stored note is destroyed so the same link cannot be used again. The homepage frames the service around simple sensitive information that a sender does not want to put directly in an ordinary message. The product pages identify ApogeeInvent as the publisher.

This simplicity is the product’s main appeal and its main constraint. A one-time link does not make every part of a message confidential. The URL itself is a capability: anyone who obtains it may be able to retrieve the note, and the act of opening it consumes the opportunity for the intended recipient. That makes the sender’s delivery channel, the recipient’s identity and the site’s current security implementation at least as important as the reassuring phrase “self destructing.”


## The key travels with the link, so protect the URL as if it were the secret

The 1ty.me FAQ and privacy policy say that the note is encrypted and that a part of the decryption key is contained in the generated URL, while the service does not store the full key. The FAQ also says the URL is hashed so it cannot be directly linked to a note. If those details describe the current implementation, the approach aims to keep a database record from being readable without the link. The provider’s explanation is a useful starting point for understanding its design, not an independent confirmation that the implementation matches the description.

A URL containing decryption material must be treated as confidential. It can appear in browser history, clipboard history, screenshots, link previews, proxy logs, chat exports, email records or an endpoint security system depending on the environment. Do not paste a secret link into a public ticket or a shared document. If an organization uses link protection, tracking or automated scanning, ask whether those systems fetch links before a human opens them. Because the link is intended to work once, test that interaction with harmless sample text before sending anything important.


## One-view deletion solves one problem and creates another

The publisher says a retrieved note is immediately removed from the database and that the same URL will not work again. The privacy policy separately says an unread note is deleted after 30 days. Those rules can reduce the period a note remains available through the service, and the 30-day expiry is more precise than a vague promise that the content disappears eventually. The current homepage and FAQ present the one-view behavior as the core feature.

“One view” is not the same as “one intended reader.” A recipient can copy, photograph or forward the contents after opening the link, and the service cannot recall a copy already seen. Conversely, an automated preview, antivirus scanner or mail gateway may request a link before the recipient does; whether that consumes a 1ty.me note is not answered in the reviewed materials. Share a dummy note first if your delivery channel automatically checks links. For a critical credential, use an approved process with identity verification, revocation and an audit trail rather than assuming that one-time access prevents onward copying.


## Security claims are difficult to evaluate from the public documentation

The FAQ describes HTTPS and encrypted storage, and the privacy statement says that the key is not held by the service and that the note is deleted after it is retrieved. Those are meaningful design claims, but the pages do not name the encryption algorithm, mode, key size, randomness source, key-derivation process, browser-side versus server-side steps, request logging, backup deletion behavior or a versioned technical specification. The reviewed pages also do not link to an independent security assessment or public source code that would let a buyer verify these details.

This gap does not prove that the product is insecure or that its stated design is false. It does mean that a reader cannot independently judge the strength of the cryptographic claim from the material reviewed. The privacy page says it was last modified April 18, 2011; the current home page has a 2011–2026 copyright footer, but that does not establish when the underlying system was last reviewed. Do not treat age alone as proof of a vulnerability. Treat it as a reason to ask for a current security explanation before using the service for a high-value secret.


## The policy names the data it stores, and the date needs attention

The privacy policy says the service records the IP address of a submission, date and time to identify the note. It says a user may supply an email to receive a read notification, and that email is encrypted and destroyed after the notification is sent. It also says unread notes expire after 30 days. A separate checkbox can add an email to a newsletter list, where the policy says the address is retained for marketing until the user unsubscribes. This distinction is important: a read receipt and a newsletter subscription are not the same purpose.

The policy’s stated last-modified date is 2011, and it does not describe modern operational details such as log retention, backups, service providers, incident response or a process for a company to request deletion or obtain a data-processing agreement. The site says the note is encrypted, but a policy sentence does not demonstrate the complete data path. Avoid entering personal information beyond what the task requires, do not add a notification email unless it is useful, and do not opt into marketing accidentally. A business that handles regulated or customer credentials should obtain current written terms first.


## Be careful with usernames, API keys and passwords

A one-time link is often marketed for passwords, but credentials are unusually consequential if exposed. A password may grant access to email, cloud storage, an administrator panel or financial systems. The recipient may not open the note immediately, the URL can be copied incorrectly, and the sender may have no clear way to revoke it after it has been delivered. If the account supports a temporary invite, delegated access or a password manager’s secure sharing feature, those controls may provide a better fit than a one-off web note.

If the user still chooses to send low-risk text this way, make a dummy note first, confirm which device or browser must open it, ensure the recipient is expecting the URL, and send the link through a channel that is not also accessible to unintended parties. Never send a complete set of credentials in one message if a safer process is available. A secret can remain in a recipient’s clipboard or device after the service deletes its copy. The “self-destruct” label only addresses the service’s stored record, as described by the publisher.


## Read notifications and email signup are separate choices

1ty.me’s FAQ says a sender can enter an email address to receive a notification when the note has been read. The privacy policy describes the notification email as optional and says the email is encrypted and deleted after the message is opened and notification sent. It also describes an additional newsletter checkbox. A useful implementation should make these choices distinct so someone can request a one-time delivery receipt without joining a marketing list.

The public policy’s notification and newsletter descriptions are dated and were not verified against the live form interaction in this review. Before supplying an email, check the current controls, the exact label on each checkbox and whether the sender’s address is stored elsewhere for service operations. Avoid using a shared inbox if a read receipt would reveal sensitive timing or account activity. No notification or newsletter subscription was created for this review.


## Pricing and service commitments are not published clearly

The accessible public pages describe how to generate and consume a link but do not show a pricing table, plan limits, availability promise, support response target or business service contract. The form can be reached without a visible account workflow in the page text, but that alone does not establish a permanent free tier. There is not enough public information to compare the tool’s cost or operational commitments with an organization’s requirements.

A personal user sending a low-risk note may care mainly about convenience. A business should ask who the contracting entity is, whether the service is intended for company use, which countries and data processors are involved, whether the service can be disabled or revoked, how backups are handled and how security incidents are reported. If support or contractual assurances are unavailable, keep the service out of critical credential flows.


## Alternatives depend on whether the priority is convenience or control

For a casual one-time note, a short-lived link is easy to understand and avoids putting the text itself into a chat body. For a password or production API key, the better comparison is not another short-link site but the organization’s approved secrets workflow: a password manager, a secrets vault, a temporary access invitation or a secured channel with identity controls. These tools may have a different setup cost, but the workflow should match the importance of the material.

Compare access revocation, recipient authentication, audit logs, expiration controls, cross-device behavior, support and data-processing terms. A recipient-specific invitation can be preferable to a bearer URL when the sender must know who opened it. A one-view mechanism may help reduce exposure in one database; it does not replace the surrounding controls needed for access management. The right tool is the simplest one that meets the real risk requirement.


## 1ty.me scam review verdict: a real service, not enough evidence for an enterprise security endorsement

The official site is accessible, describes a specific one-time secret-link workflow and identifies ApogeeInvent as its publisher. Its FAQ and privacy page disclose claims about HTTPS, encrypted notes, URL-based key material, one-view deletion, 30-day expiry and optional read notifications. The evidence reviewed does not substantiate calling 1ty.me a scam. At the same time, the available material is not enough to endorse it for passwords, API keys or regulated information: the privacy policy was last modified in 2011, the cryptographic details are not specified, and no independent audit or current enterprise controls were identified in the pages reviewed.

This is a source-based desk review, not a cryptographic audit, penetration test, legal opinion or hands-on transaction. Public pages were checked November 17, 2026. If you are evaluating the service for a low-risk message, test the one-time behavior with dummy text and protect the URL as a secret. For operational credentials or customer information, request current security and retention documentation and use an approved process with suitable access control and revocation.


## Features and decision criteria

- Create a short link containing a note for one-time viewing
- Publisher says a viewed note is removed and cannot be retrieved through the same link again
- Privacy policy states unviewed notes are permanently removed after 30 days
- FAQ describes HTTPS, encrypted note storage and a decryption key carried partly in the URL
- Optional email notification when a recipient opens a note, according to the FAQ and privacy policy
- Optional newsletter signup is separate from a one-time read notification, according to the privacy policy

## Pricing considerations

The public pages reviewed do not establish a price, service-level commitment or commercial support plan. Do not assume that an unpriced form is a guaranteed or enterprise-grade free service.

## Sources and further reading

- [1ty.me website](https://1ty.me/)
- [1ty.me FAQ: self-published HTTPS, encryption, URL key and one-view behavior claims](https://1ty.me/faq)
- [1ty.me Privacy Policy: last modified date, submission data, expiry, optional email and newsletter disclosures](https://1ty.me/privacy-policy)
- [1ty.me About page: service origin and publisher’s explanation of intended use](https://1ty.me/about)
- [secret sharing on Wikipedia](https://en.wikipedia.org/wiki/Secret_sharing)
- [saashub listing](https://www.saashub.com/1ty-me)

For the complete Roseram buyer guide, see [1ty.me review](https://roseram.com/reviews/scams/1ty-me-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
