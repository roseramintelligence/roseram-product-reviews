# ACE - AI Chat Exporter review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** AI chat export browser extension  
**Method:** Source-led desk review; no hands-on testing is claimed.

ACE, also branded AI Chat Exporter, is a free browser extension from Covai Labs for saving conversations from web-based AI assistants. Its published feature set includes exports to Markdown, HTML, PDF, Word, PNG, JSON and plain text, plus handoffs between selected AI services and links to note-taking apps such as Obsidian. The Chrome Web Store listing checked November 18, 2026 showed version 1.25.1, an update dated November 11, 1,000 users and 5.0 stars from seven ratings. These are store-displayed figures, not independent quality findings. Public sources make conflicting license statements: the website’s license page says MPL 2.0, while the current GitHub repository, its exception file, the privacy-page footer and the Chrome listing point to AGPL 3.0 with a FOSS linking exception. The repository build configuration also requests the <all_urls> host permission, broader than the privacy page’s plain-language description of supported sites. This source-based desk review does not establish fraud, verify privacy claims, install the extension, inspect a released binary or provide a legal opinion. Buyers should confirm the exact build, permission prompt, supported platform and governing license before adopting it.

## Editorial verdict

The public evidence supports treating ACE as an identifiable, actively maintained browser extension with a clear practical use: preserve or move AI chat content without manually rebuilding a transcript. Its local export workflow could suit people who want portable records or need a handoff between services. The reviewed sources do not establish that ACE is a scam. They also do not independently prove that every platform extractor, privacy statement, export format or update works as described. Two issues merit resolution before wider use: the website license page conflicts with the repository and store disclosures, and the repository currently declares <all_urls> host access while the privacy page describes access to named services. Review the exact installed extension’s permissions and source version, avoid exporting sensitive conversations until data flow is understood, and get written license clarification for commercial embedding or redistribution. This is an editorial desk review of public materials, not hands-on testing, a code audit, a legal assessment or a security certification.

## ACE AI Chat Exporter SCAM Review: what public evidence supports

Someone searching for an ACE AI Chat Exporter scam review is usually trying to answer several different questions at once: does the extension exist, does it do what its listing says, what happens to chat history, and what rights come with the software? Those questions should not be collapsed into a fraud verdict. Covai Labs publishes a project site, a public GitHub repository and a Chrome Web Store listing under the ACE and AI Chat Exporter names. These sources describe a browser extension for exporting or moving conversations from web AI services.

The public record reviewed on November 18, 2026 does not establish that ACE is a scam. It also does not establish that every privacy statement or feature works for every supported platform. Roseram did not install the extension, test a browser session, inspect outbound requests, audit the complete source tree, or obtain legal advice about the conflicting license notices. This is a buyer’s desk review. Its purpose is to identify what the publisher says, what a prospective user should verify, and where the public documentation leaves an open question.


## What ACE - AI Chat Exporter is designed to do

ACE is presented as a browser-based utility that turns a conversation visible in a supported AI website into a file or a handoff. The publisher lists Markdown, standalone HTML, PDF, Microsoft Word, PNG, JSON and plain text among the output choices. It also describes a toolbar popup and a side panel for starting an export without leaving the chat page. For research notes, debugging records or a personal archive, that workflow addresses an ordinary inconvenience: important context can otherwise be difficult to preserve in a portable form.

The product should be evaluated as an extension that reads content from AI websites, not as an AI model or a secure records-management system. The repository README describes transfer into another AI service and direct sending to note applications such as Obsidian, Logseq, Bear, NotePlan and Drafts. The Chrome listing mentions clipboard transfer and exports. The exact availability may depend on browser, target application, site layout and extension version, so a buyer should verify the installed build before relying on one workflow for a critical record.


## Supported AI platforms: breadth is useful, but check the exact version

The project README groups integrations into services that support extraction and one-click continuation, and services for which it offers high-fidelity extraction. Its examples include ChatGPT, Claude, Gemini, DeepSeek, Perplexity, Grok, Mistral Le Chat, Qwen and Proton Lumo, alongside NotebookLM, Copilot, Google AI Studio, Meta AI and others. The README describes 18-plus models, while the Chrome Web Store uses a 15-plus phrasing. Because the counts differ and adapters change, the safest approach is to consult the current platform matrix for the release being installed rather than treat a rounded marketing total as a guarantee.

A supported-platform label does not mean every account, chat type or feature is covered. A service may change its page structure, authentication behavior or conversation format. Some pages can include files, generated artifacts, search results or other components that do not export in the same way as ordinary text. Before depending on the extension, try a non-sensitive sample conversation from each platform you use, compare the saved output with the original, and check the project’s issue and release notes if something is missing.


## Export formats and preservation quality

ACE lists formats aimed at different kinds of reuse. Markdown is convenient for a knowledge base or version-controlled notes; HTML can preserve a navigable document; PDF and Word suit sharing or printing; PNG makes a visual snapshot; and JSON can be useful for custom data processing. The repository describes structured JSON with message roles and timestamps. It also advertises preservation of code blocks, tables and mathematical notation. These are product claims and design goals; this review did not compare files produced by the current extension with source conversations.

The distinction between an export and an archival guarantee matters. A file may contain the text the extension can access without preserving every embedded image, attachment, formatting detail, private tool output or platform-specific state. PNG and PDF exports may prioritize appearance over editability, while JSON may need a schema-aware reader. A careful workflow is to export a small test, inspect whether roles and ordering remain clear, check long chats for omissions, and retain the original platform link or account record where appropriate. Do not treat an export as a substitute for a platform’s official data download or a regulated retention system.


## Cross-model continuation and where the data goes next

One of ACE’s more distinctive advertised features is conversation continuation: extract a chat, format it as a handoff and place that context into another AI service. The README says the extension preserves roles and turn order when constructing the handoff prompt. That can save copying and reformatting when a user wants to move work from one provider to another. It can also make it easier to bring a prior discussion into a note-taking application.

A local extension and a remote AI provider are separate parts of this flow. ACE’s developer says extraction and formatting stay in the browser. If a user sends the resulting context to a different AI site, the destination site receives that submission and handles it under its own account, privacy and retention terms. Before using continuation, remove credentials, customer details, confidential source text or personal data that the destination service should not receive. The one-click design reduces friction; it does not remove the user’s responsibility to decide whether the destination is appropriate.


## ACE privacy claims and what has not been independently verified

ACE’s privacy policy says that the browser extension does not collect, store or transmit personal information or usage data to external servers. It describes reading the active page in the browser to format an export and saving local preferences in browser storage. The Chrome Web Store listing repeats the developer’s no-data-collection disclosure. The repository README similarly says chat processing happens locally and that the extension does not use telemetry. These are consistent statements across several publisher-controlled materials, but they remain developer disclosures rather than findings from an independent audit.

Roseram did not install the extension or observe network traffic, inspect all dependencies, analyze a packaged store binary, or compare telemetry behavior across updates. A privacy statement should not be treated as proof of implementation. Users with sensitive conversations can inspect the current source and build, review browser permissions, and test with non-sensitive data first. For organizations, the relevant question is not only whether the extension itself uploads content; it is also which browser profile, destination service, local storage, backup tool and export folder will handle the saved material.


## Browser permissions deserve a close look

The repository’s current WXT manifest configuration requests permissions including activeTab, tabs, scripting, storage and contextMenus, adds sidePanel for Chromium-family browsers, and lists downloads and clipboardWrite as optional permissions. It also sets host_permissions to <all_urls>. The README explicitly says broad site access supports generic article extraction and embedded chat detection. By contrast, the privacy policy describes host access in terms of named AI platforms. This is a meaningful difference in how the scope is communicated, even though broad permission by itself does not prove misuse.

A prospective installer should review the permission screen for the exact release and browser, then compare it with the current privacy and repository documentation. Optional permissions may be requested only when a user invokes related actions, but the final behavior should be checked in the store build. Ask whether broad host access can be reduced to optional, user-granted access or specific site matches if that fits your risk requirements. The extension’s code and permissions may change; a snapshot from today is not a promise about every prior or future version.


## The license disclosures conflict across official ACE pages

The most concrete documentation inconsistency found in this review concerns licensing. ACE’s website license page states Mozilla Public License 2.0. The current GitHub repository labels the project AGPL-3.0-only, its FOSS-EXCEPTION.md describes an AGPL-3.0 base license with an additional linking permission for projects under OSI-approved open-source licenses, and the Chrome Web Store description also says AGPL 3.0. The website privacy page footer points to AGPL-3.0-only as well. Those statements do not line up cleanly for a buyer trying to decide which terms apply.

This review does not resolve the conflict or determine legal rights. The exception file says direct changes to ACE source files remain subject to AGPLv3 and directs closed-source commercial users to contact the publisher for licensing terms. The website’s MPL page describes a different set of terms. Before modifying, bundling, redistributing or incorporating the extension into a commercial product, ask Covai Labs which license and notices govern the exact version and obtain the answer in writing. Individual users installing the listed free extension face a different question from a company distributing a modified derivative.


## Price, ongoing cost and product limits

The GitHub README and Chrome Web Store listing describe ACE as free, and the reviewed materials do not present a subscription tier or a paid plan. That makes the initial price straightforward: there is no listed extension charge in those sources. Users should still distinguish a free exporter from the services it connects to. ChatGPT, Claude, Gemini or another destination may require its own account, paid plan or usage allowance, and handing a transcript to a destination can use its quota.

There can also be indirect operating costs. Supported platforms change their interfaces, so browser extensions need maintenance to keep extraction working. The project README describes frequent upstream interface changes as a reason for ongoing maintenance and invites sponsorship. That is not evidence of a hidden fee, but it is a reason to review update activity and the project’s support path. For a business deployment, factor in permission review, license interpretation, testing, staff guidance and backup policy even when the extension itself has no purchase price.


## Reliability risks when AI services change

An exporter that reads live AI web pages depends on the structure and behavior of services it does not control. The ACE project itself acknowledges that platform layout changes can break parsers and require rapid maintenance. A release can work well on one date and behave differently after a provider changes its DOM, navigation, internal endpoints or conversation rendering. A successful listing, star count or release note cannot guarantee that every adapter will capture every new feature or long conversation.

This limitation is common to browser extraction tools, but it is still a practical buyer concern. Keep the original conversation available until the export has been checked. For important work, validate a sample across message types, attachments, code, tables, images, tool outputs and long threads. Check that the selected platform is explicitly supported and that the specific export target works in your browser. If an adapter fails, do not repeatedly export sensitive data to troubleshoot; use a redacted test and consult the project’s issue tracker or release notes.


## Store listing and public project signals

When checked on November 18, 2026, the Chrome Web Store displayed version 1.25.1, an update date of November 11, 2026, about 1,000 users, and a five-star average from seven ratings. The GitHub release page identifies v1.25.1 as the latest release and shows it was published on November 10. The repository displayed 99 stars and 21 forks at the time of the review. These indicators show a public distribution channel and a visible development trail, but the review count is small and the metrics can change.

Store presence and active source code are useful signals, not certifications. The Chrome listing also identifies the developer’s privacy declarations and provides a way to report concerns. Roseram did not independently confirm the publisher’s identity beyond the public links, audit the release pipeline, or assess the integrity of a downloaded package. A buyer should install from the official store or release location linked by the publisher, verify the extension name and developer, and avoid third-party repackaged copies.


## Who may benefit from ACE

ACE appears best suited to an individual who regularly works in browser-based AI chats and wants a portable working copy, clean Markdown notes or a controlled handoff to another model. Its format range could help researchers, developers, writers and students who need to retain code, structured text or math for later use. A local workflow may be attractive to users who prefer not to create another account for an exporter, provided the permissions and source disclosures meet their own standards.

It is a less obvious fit for teams that need centralized retention, administrator controls, access logs, legal holds, guaranteed preservation or a service-level commitment. The materials reviewed describe a local browser extension, not a managed enterprise archive. Users processing regulated or confidential data should evaluate the exact permission scope, destination policies, records obligations and license before adoption. If the purpose is merely to save a few conversations, a platform’s built-in export or manual copy may be easier to govern.


## Alternatives and comparison criteria

The simplest alternative is the export feature provided by the AI service itself. It may cover an account’s history without granting a third-party extension page access, though it may be less convenient for selective exports or cross-model handoffs. Manual copy and paste offers direct control over what leaves the page but can lose formatting and becomes tedious for long chats. Browser print-to-PDF can preserve visible layout, while a note app or document editor can provide a more deliberate archive.

Other browser extensions may offer overlapping export formats or platform coverage. Compare their current publisher, code availability, permission scope, data-flow documentation, update cadence, export fidelity, target platforms and license. Do not choose solely by a model-count badge or a privacy slogan. For ACE specifically, the license discrepancy and <all_urls> source permission are the two public-documentation issues that deserve a clear answer before a team adopts or redistributes the tool.


## A practical buyer checklist before installing

Start with identity: use the official store link published by ace.covai.org and verify the name and developer in the browser’s install dialog. Read the actual permission prompt rather than relying only on a marketing summary. Confirm whether your browser version and the AI services you use are supported in the current release. Make a low-risk test export, then compare roles, order, code, math and attachments against the source conversation. Keep the original until the export has been reviewed.

Next, map the data path. Separate local extraction and file creation from a continuation action that submits text to another AI service. Review that destination’s retention and account rules before transferring sensitive material. If you plan to use ACE in a product, modify it or distribute it to customers, request clarification about the website’s MPL 2.0 page versus the repository’s AGPL-3.0-only notice and linking exception. Record the version and license answer internally. These steps turn a vague “is it safe?” question into checks tied to your actual use.


## What this AI Chat Exporter review cannot prove

This page does not report an installation test, independent source review, penetration test, network capture, privacy audit, export benchmark, accessibility test or interview with the developer. It does not verify whether every listed platform integration works now, whether every exported file is complete, or whether the extension has ever mishandled user data. It also cannot establish the legal effect of inconsistent license notices. Each of those claims would require evidence beyond the public pages reviewed here.

Accordingly, a reader should not interpret the word SCAM in the page title as a conclusion that Covai Labs or ACE has committed fraud. The available official record is more useful for answering narrower diligence questions: the extension has a public distribution listing and repository; the publisher presents it as a free, local exporter; its current configuration requests broad host permission; and its official materials disagree on the license. Users can weigh those facts against their threat model and intended use.


## Final verdict: a useful concept with two items to clarify

ACE AI Chat Exporter addresses a practical need with a broad set of advertised formats and a cross-model transfer workflow. Its free price and public repository make it relatively easy for a technically capable individual to inspect further. The reviewed official materials do not establish fraud, and they offer a plausible account of a local-first extension. The product’s usefulness will depend on actual export accuracy and how quickly its platform adapters keep pace with the AI services it reads.

Before sensitive or organizational use, resolve two concrete issues: inspect the broad host permission shown in the source configuration against the exact store build, and obtain clarification about the MPL-versus-AGPL license mismatch. Treat the privacy statements as claims to evaluate rather than an independent audit, and remember that sending a transcript to another AI service moves it into that provider’s data environment. This conclusion is limited to public materials checked November 18, 2026; it is not a fraud determination, legal opinion, hands-on review or security certification.


## Features and decision criteria

- Exports web-based AI conversations to Markdown, HTML, PDF, Word, PNG, JSON and plain text, according to its public listings
- Provides a browser toolbar popup and Chromium side panel workflow
- Offers conversation continuation from selected AI platforms by placing structured context into another service
- Supports copy-to-clipboard and destinations such as Obsidian and other note-taking tools
- Claims client-side processing with no extension account, subscription, telemetry or cloud processing
- Uses platform-specific extraction from page content and, for some services, authenticated session interfaces, as disclosed by the developer
- Lists Chromium-family and Firefox builds in its repository and release materials
- Current source configuration requests activeTab, tabs, scripting, storage, contextMenus, sidePanel where supported, optional downloads and clipboardWrite, and <all_urls> host permission

## Pricing considerations

No subscription price or paid tier was listed in the sources reviewed. The free price does not remove the need to check extension permissions, the downstream AI service’s data terms, or open-source obligations. The official site license page says MPL-2.0, while the current GitHub README, FOSS exception, privacy footer and Chrome Web Store description say AGPL-3.0 with a linking exception. Roseram cannot determine which disclosure governs a particular release; ask the publisher to identify the license for the exact version before incorporating or redistributing it.

## Frequently asked questions

### Is ACE - AI Chat Exporter a scam?

The sources reviewed identify a public product site, browser-store listing and active public repository. They do not establish fraud. This page uses SCAM Review as a buyer due-diligence query, not as a finding or accusation.

### What does AI Chat Exporter do?

It is a browser extension designed to export conversations from supported web AI services into formats such as Markdown, PDF, Word, HTML, PNG and JSON. It also advertises cross-service continuation and note-app handoffs.

### Does ACE upload chat content to its own servers?

The developer says the extension processes and stores exports locally and does not send chats or usage data to its servers. Roseram did not independently inspect network traffic or audit a release. If a user transfers a conversation to another AI service, that service receives the submitted context under its own terms.

### Why should I check the ACE browser permissions?

The current GitHub source configuration declares the <all_urls> host permission, while the privacy page describes access in terms of supported AI platforms. Check the permission prompt for the exact installed build and decide whether the scope fits your use.

### Is ACE free?

The Chrome Web Store and repository describe the extension as free, and no subscription tier was shown in the pages reviewed. The AI platform receiving a transferred conversation may still impose its own limits or charges.

### Which license applies to ACE?

The public website license page says MPL 2.0, while the current repository, FOSS exception, privacy footer and Chrome listing say AGPL 3.0 with a linking exception. This review does not resolve that discrepancy; request written clarification for the exact version and intended use.

### Has Roseram independently tested or audited ACE?

No. This is a desk review of public developer, repository and Chrome Web Store disclosures. Roseram did not install the extension, test its exports, inspect its network behavior, verify all platform adapters or perform a security or license audit.


## Sources and further reading

- [ACE AI Chat Exporter project overview, features, supported platforms and stated license](https://github.com/Covai-Labs/ace)
- [ACE Chrome Web Store listing, version, displayed rating, users, features, privacy and license disclosures](https://chromewebstore.google.com/detail/ace-%C2%B7-export-save-transfe/cgakhbhkplndjjknhgegfcipffflcaoj)
- [ACE privacy policy and permission explanation](https://ace.covai.org/privacy.html)
- [ACE website license page stating MPL 2.0](https://ace.covai.org/license.html)
- [ACE GitHub license file and AGPL-3.0-only repository label](https://github.com/Covai-Labs/ace/blob/main/LICENSE)
- [ACE FOSS Linking Exception and commercial-use contact disclosure](https://github.com/Covai-Labs/ace/blob/main/FOSS-EXCEPTION.md)
- [ACE release v1.25.1 and published change notes](https://github.com/Covai-Labs/ace/releases/tag/v1.25.1)
- [ACE extension manifest build configuration showing requested host permissions](https://github.com/Covai-Labs/ace/blob/main/wxt.config.ts)
- [ACE - AI Chat Exporter website](https://ace.covai.org/)
- [saashub listing](https://www.saashub.com/ace-ai-chat-exporter)

For the complete Roseram buyer guide, see [ACE - AI Chat Exporter review](https://roseram.com/reviews/scams/ace-ai-chat-exporter-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
