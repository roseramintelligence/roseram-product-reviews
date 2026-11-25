# 2FA Authenticator review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Two-factor authentication and credential security  
**Method:** Source-led desk review; no hands-on testing is claimed.

2FA Authenticator is an open-source authenticator for Chrome, with separate Mac and Apple-platform applications described on the publisher’s site and terms. Its technical documentation says TOTP secrets and codes are generated locally and are not included in the daily billing check-in. The extension requests a limited permission set, while optional password protection encrypts local data and Pro cloud backup is described as encrypted with a recovery key the vendor does not hold. Those are detailed publisher claims that can be checked against source code, but this review did not independently audit the implementation. By default, stored codes are not encrypted beyond the user’s computer and Chrome profile protection; enabling the optional vault materially changes that. New installs may face a free account limit, while existing codes, exports and local backups continue to work if Pro ends. Pro removes the add-account limit and adds optional cloud backup; prices vary by offer and checkout. The product’s own docs explain an account-loss hazard: without an export, usable backup or recovery code, support cannot restore secrets. The evidence reviewed does not substantiate a scam claim.

## Editorial verdict

The publisher identifies its company, provides open-source code, a technical architecture page, a security policy and detailed support instructions. Its local-data and encryption claims are not an independent security certification; users should verify them against the released build and keep recovery material outside the extension. The product documents limitations that matter, including unencrypted-by-default storage and loss that the vendor cannot reverse. Nothing reviewed substantiates calling it a scam.

## 2FA Authenticator review: what it is and where the codes live

2FA Authenticator is a browser-based authenticator from the publisher at authenticator.sh. Its principal job is to generate time-based one-time passwords for other services. The company also describes Mac and Apple-device editions, but this review focuses on the Chrome extension and the account data it handles. The publisher says codes are calculated on the user’s device and that secret keys, account names and generated codes are never sent to its server. Its published architecture describes the storage and network behavior in greater detail than a short store listing usually does.

Two-factor authentication protects accounts that belong to other companies. It does not give the authenticator vendor the ability to recover those accounts. A buyer should therefore evaluate the product partly as a recovery system: where are the secret keys stored, how are they backed up, what credentials unlock an encrypted copy, and what happens after a browser profile is lost? A six-digit code that appears quickly is only one part of a dependable setup.


## The extension’s declared permissions deserve a careful read

The technical page lists five Chrome permissions: storage, activeTab, contextMenus, scripting and sidePanel. It says there are no broad host permissions, persistent content scripts, cookies or webRequest access. The right-click “insert code” action is described as injecting one function into a selected editable field only after the user chooses that action. The page also explains that capturing a QR code from the screen occurs after a user opens the scanner and grants the browser’s camera prompt. This limited-permission design is a positive property in the publisher’s description.

The same page says the active tab’s hostname can be read when the extension is opened, to highlight a matching account, and when the user chooses a context-menu action. That behavior may be reasonable for the feature, but users should understand it rather than treating “no website access” as “the extension never interacts with a page.” Compare the permissions in the installed release with the published explanation. If a future update adds new capabilities, review the new permission prompt before accepting it.


## What happens to a secret by default

The FAQ says codes are stored in Chrome storage and, by default, are not encrypted within the extension; they rely on the operating-system login and Chrome profile for protection. If Chrome Sync is enabled, the user may have a second copy through their own Google account. This is a meaningful limitation for a shared computer, a compromised browser profile or a device whose operating-system account is not protected. An authenticator can keep data local and still leave it readable to someone who controls that local profile.

The publisher offers optional password protection that encrypts the vault and local backups. Its technical document specifies AES-256-GCM and PBKDF2-HMAC-SHA256 with 600,000 iterations, but these are the vendor’s implementation details, not proof of a third-party cryptographic audit. Password protection also introduces a recovery responsibility: the user must preserve the recovery code. The vendor states it cannot reset the password or open the vault if both the password and recovery code are lost. That limitation is deliberate, but it makes backup planning essential.


## Cloud backup has a different trust boundary

The publisher describes Pro cloud backup as opt-in and encrypted in the browser before upload. It says the recovery code used to unlock the backup never reaches the server, so the vendor cannot read the backup or restore it without that code. The technical materials further describe how the user proves possession before a copy can be added, fetched or deleted. This architecture aims to reduce server-side access to the stored secrets, but it also means a lost recovery code can make the cloud copy unusable even when the vendor still has the encrypted bytes.

The terms say cloud backup is not guaranteed to be the only safe copy. They describe deletion of existing copies 90 days after Pro ends, and immediate deletion when cloud backup is switched off. Sync also carries deletions between devices, so removing an entry on one device can remove it elsewhere. Keep an exported backup in a secure location you control, store the recovery code separately, and test restoration on a spare profile before relying on the cloud copy for a critical account.


## Daily check-in: account secrets are excluded, usage metadata is not

Since version 1.14.0, the extension checks in with its service once daily for free-plan and Pro operation. The technical document lists the fields: a random installation identifier, version and language, install timing, account and group counts, a set of interface settings, operating system, policy/license state, daily open counts and a small list of billing events. It says the check-in does not contain secret keys, account names, issuers, generated codes or the sites where accounts are used. It also says the server derives country from the request and does not store the IP address.

That is a more precise disclosure than a simple “no data collected” badge. It describes anonymous installation telemetry and billing-related events while distinguishing them from the authentication secrets. The published policy and source code make these statements inspectable, but this review did not capture network traffic from the current store build or verify its retention systems. A privacy-sensitive organization should compare the installed version, source tag, build and request implementation before deployment, then decide whether the check-in metadata is acceptable under its rules.


## Free limits, Pro and the consequence of a subscription ending

The FAQ says the extension is free to install and that new installations may have a limit on the number of accounts they can add. Legacy installations predating version 1.14.0 are described as retaining unlimited accounts. Pro removes the current limit and adds cloud backup. The publisher says the limit can only stop adding an account; existing codes, exports, local backups, restore and sync continue to work without Pro and after a subscription ends. This distinction matters: a plan limit is not described as locking existing codes behind a paywall.

The terms say Pro may be offered as a monthly or yearly subscription or a one-time purchase; the exact options and prices can vary. The web checkout is described as Stripe Checkout with Link acting as merchant of record, while Apple handles in-app purchase on its platform. Subscriptions renew automatically until canceled. Since price availability can change, rely on the checkout screen for the actual price and term. Save the receipt and confirm the cancellation path before purchasing, especially if the license key is meant to be entered on another installation.


## License sharing and moving to a new computer

The published terms say a web-purchased license works on up to five installations at once, with a slot freed when an installation has not checked in for 60 days. The publisher’s FAQ explains that the license key can be restored through the browser where the purchase was made and entered manually on another computer. That process links a paid license to the email used at checkout. It is separate from moving account secrets, which requires sync, export/import or cloud backup. A license key does not itself restore the authenticator vault.

If an employee leaves or a laptop is replaced, plan the sequence before the old device is wiped. Verify that the new installation shows the expected accounts and produces codes accepted by the underlying services. Exporting before a move reduces reliance on browser sync. Do not send secret keys, recovery codes, QR images or backup files to support; the publisher explicitly warns that anyone holding them can generate codes and that support does not need them.


## Browser and device compatibility is narrower than “use anywhere”

The Chrome extension does not run as an extension in Chrome on a phone. The FAQ recommends pairing it with a phone authenticator when setting up two-factor authentication if the user wants codes available on a phone. The publisher describes a separate Mac application and says its account list does not automatically sync with the extension; users must move data using export/import. The terms also describe iPhone and iPad versions. These are related products, but they should not be assumed to share one seamless vault or one subscription entitlement without checking the exact platform workflow.

Before migrating all accounts, confirm which build is supported on each device, where its data is stored, and whether the same license applies. Test a low-risk account first. Keep each service’s own recovery codes until the replacement authenticator has produced a valid code and the service confirms the setup. Avoid disabling the old authenticator until the new path is proven. An authenticator migration can lock a user out of multiple third-party accounts if it is treated as a routine app reinstall.


## Account loss, local backups and uninstall hazards

The support documentation says automatic local snapshots cover the last seven days, but uninstalling the extension or wiping the browser profile can remove those files. The vendor cannot reconstruct secrets it never received. Users who have no export, no accessible backup and no recovery code may need to disable and reconfigure two-factor authentication separately on each underlying service, using that service’s recovery process. That can be time-consuming, and some providers impose extra identity checks.

A buyer test should include a deliberate restore before the vault becomes critical. Create a test entry, export it, store the file securely, remove a disposable profile and restore into a clean one. If password protection is enabled, verify that the recovery code works without relying on memory or the same device. Keep printed or offline service recovery codes in a separate safe location. Do not treat browser sync as the only backup: it depends on the Google account, sync settings and browser profile remaining accessible.


## Open source, security claims and what remains unverified

The publisher links an MIT-licensed source repository, documents its manifest permissions, describes its encryption design and provides a security reporting policy. Those materials improve reviewability and give a technically capable buyer a path to inspect the code and compare it with a published release. The vendor says production builds trust only the production signing key and that limits are checked locally from signed tokens. Such details are useful, but they remain publisher-authored explanations unless independently reproduced or audited.

This review did not perform a source audit, reproduce the build, inspect the signed release, test encryption, monitor network traffic, review a penetration test or verify a bug-bounty response. A prudent organization should verify the exact release and permissions, inspect dependencies, test export and recovery, and obtain any required external assessment before storing high-value credentials. Users should also keep their operating system and browser profile protected. Local storage shifts some risk away from a vendor database but does not remove endpoint security risk.


## Alternatives and choosing an authenticator workflow

Compare 2FA Authenticator with a phone authenticator, a password manager with built-in TOTP, a desktop vault or a hardware security key. These options trade convenience, device availability, recovery, portability and phishing resistance differently. A browser extension can make code entry convenient during desktop sign-in. A phone app keeps a second device involved. A password manager may consolidate credentials and codes while increasing the importance of protecting one vault. A hardware key can resist phishing on services that support it, but it is not a universal replacement for TOTP.

Use the same sample account and backup plan to evaluate each option. Ask how an account is added, where the secret is stored, how recovery works, what permissions are requested, how the data can be exported and what happens if the vendor disappears. Choose the approach that fits your threat model and ability to maintain backups. For an organization, document who owns account recovery and how staff changes are handled before standardizing any authenticator.


## 2FA Authenticator scam review verdict: transparent design, user-owned recovery

The evidence reviewed identifies an operating security product with a named publisher, open-source code, a technical architecture description, a security policy, support routes and published terms. Its own documents disclose that codes are unencrypted by default, optional encryption requires user-held recovery material, new installs may face an account limit, the extension sends limited daily check-in metadata, and the vendor cannot recover secrets after certain loss scenarios. Those disclosures do not amount to an independent security audit, but the available record does not substantiate a scam allegation.

The main purchase decision is whether the user can maintain a safe export and recovery process, and whether the exact browser or platform version fits the way they sign in. This is a source-based desk review, not a penetration test, cryptographic audit, hands-on migration trial or endorsement. Product terms and technical pages were checked November 17, 2026. Verify the extension permissions and checkout details in the installed version, save recovery material separately, and test a restore before moving high-value accounts.


## Features and decision criteria

- On-device TOTP code generation
- Optional password-protected local vault and encrypted cloud backup
- Open-source extension with documented permissions and network requests

## Sources and further reading

- [2FA Authenticator website](https://www.authenticator.sh/)
- [Technical architecture, permissions, cryptography and network-egress documentation](https://www.authenticator.sh/how-it-works)
- [2FA Authenticator FAQ: free-plan limits, Pro, recovery and daily check-in](https://www.authenticator.sh/faq)
- [Security policy and responsible disclosure process](https://www.authenticator.sh/security)
- [Terms effective November 14, 2026: publisher, billing, backup and cancellation rules](https://www.authenticator.sh/terms)
- [Support guide: account recovery, billing and security reporting](https://www.authenticator.sh/support)
- [Published extension source repository](https://github.com/authenticator-sh/2fa)
- [time-based one-time password on Wikipedia](https://en.wikipedia.org/wiki/Time-based_one-time_password)
- [product-hunt listing](https://www.producthunt.com/products/modern-2-factor-authentication-in-chrome/launches/2fa-authenticator)

For the complete Roseram buyer guide, see [2FA Authenticator review](https://roseram.com/reviews/scams/2fa-authenticator-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
