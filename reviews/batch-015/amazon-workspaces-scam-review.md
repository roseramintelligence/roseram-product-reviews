# Amazon WorkSpaces review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Cloud-hosted virtual desktop service  
**Method:** Source-led desk review; no hands-on testing is claimed.

Amazon WorkSpaces delivers managed virtual desktops and application access. WorkSpaces Personal assigns a persistent desktop to a user, while WorkSpaces Pools supplies a fresh, non-persistent desktop for each session. Pricing depends on running mode, bundle, operating system, region and any related AWS infrastructure.

## Editorial verdict

AWS publishes product documentation, billing modes, a price calculator and eligibility details for a limited Free Tier offer. These sources do not support a fraud allegation. The purchase decision turns on desktop persistence, user concurrency, image and patch management, network design, license terms, data location and whether AlwaysOn or AutoStop matches actual working hours.

## Amazon WorkSpaces review: persistent desktop or pooled session?

Amazon WorkSpaces is a cloud desktop service, not a conventional desktop computer shipped to an employee. A user connects from a supported client to a virtual Windows or Linux environment running in an AWS Region. In WorkSpaces Personal, the desktop is assigned to an individual and persists between sessions. WorkSpaces Pools instead provides non-persistent desktops for groups whose users can receive a fresh environment each time. Those are different operating models, with different implications for saved state, support, software installation and cost.

Start an evaluation by writing down what the desktop must remember. A knowledge worker may need the same installed tools, files and preferences each morning. A training lab may need a clean, resettable session with no personal state left behind. Choose the WorkSpaces model only after deciding that distinction. Then list the applications, peripherals, network destinations and identity system that the user must reach. A virtual desktop can centralize a work environment, but it does not make licensing, software compatibility, endpoint security or the source data disappear from the design.


## Amazon WorkSpaces pricing: AlwaysOn versus AutoStop

WorkSpaces Personal offers two running modes. AlwaysOn uses a fixed monthly charge for a provisioned desktop and is intended for people who use it as their primary full-time workstation. AutoStop uses hourly metering plus a monthly infrastructure fee. An AutoStop desktop is billed for usage while running and can stop after a configured disconnect interval; the default interval in AWS documentation is one hour. Once the stop period has passed, billing for the additional minutes AWS takes to stop is not charged. The desktop can resume later, though connection startup may take time.

A fair budget uses the local bundle, operating system and Region, rather than a single advertised figure copied from another configuration. Use the WorkSpaces calculator for the expected number of desktops, usage hours and running mode. Add directory services, storage, applications, public internet data transfer and any other AWS resources that the desktop needs. AWS states that client-to-WorkSpace traffic is included, while traffic from the WorkSpace to the public internet is billed separately under applicable AWS transfer rates. Treat an estimate as an input to monitoring, not as a hard spending cap.


## The Amazon WorkSpaces Free Tier and its billing edge cases

The WorkSpaces FAQ describes a Free Tier offer for customers who have not previously used WorkSpaces and whose accounts are not under an AWS Partner account. The FAQ says the offer begins with the first launched WorkSpace and expires after three billing cycles. During that period, eligible users may use a combined total of 40 hours per month, with unused hours expiring when a new calendar month starts. The infrastructure fee is waived for qualifying use, but exceeding the allowance is billed at the current hourly rate. Converting an eligible desktop to AlwaysOn ends Free Tier qualification.

This is a limited trial allowance, not a general guarantee that a new AWS account receives a free desktop. Confirm eligibility and the specific terms in the current pricing page before starting. Track usage by service and Region in the AWS billing console, and set a budget alert well below the point at which a surprise charge would be disruptive. Before the three-cycle period ends, decide whether to stop, delete, or continue at a paid rate. Stopping an AutoStop desktop does not necessarily eliminate its monthly infrastructure component; removing a desktop can delete the associated environment and should follow a data-backup plan.


## What AutoStop saves and what it asks users to manage

AutoStop can reduce the hourly portion of the bill for people who work intermittently, but the model only works as expected when disconnect and stop behavior is understood. AWS says a disconnected Personal WorkSpace is one a user manually disconnects from or quits the client, a device shuts down, or connectivity is lost for more than 20 minutes. An open client session left connected can therefore continue consuming usage even if the person walks away. Agree on a sign-out routine and test the selected automatic-stop delay with real staff before using the hourly projection as a budget.

Hibernation is supported for many configurations, but AWS lists exceptions including GPU-enabled WorkSpaces and certain large GeneralPurpose sizes. For those cases, application state may not be saved on stop, so unsaved work can be lost. AWS also flags Windows versions with nested virtualization enabled as unable to hibernate. A buyer should confirm the behavior for the chosen bundle, save work before disconnection and test resume after a normal stop. The mode name alone does not tell a user whether a specific desktop preserves every process or file.


## Desktop images, applications and endpoint controls

Administrators can create a custom image from a running WorkSpace and use it to create a bundle for future desktops. This can standardize installed software and settings, but it creates an image lifecycle to manage: operating-system patches, application updates, configuration drift and image retirement. Test a custom image with a small group first, and record how a new image replaces or updates an existing desktop. For a persistent desktop, users may also install software and alter preferences after the image is applied; decide how much personal control is appropriate.

Virtualization does not remove the need to protect credentials and data. Review client device requirements, multifactor authentication, directory permissions, clipboard and printer redirection, and access to shared files. AWS documentation says text copy-and-paste between the local client and desktop is supported, while file copy is not; local and network printer behavior varies by operating system and client. Confirm each required peripheral rather than assuming the remote desktop will mirror the local workstation. Keep administrator ownership in the organization and have a second trained person able to recover access.


## Network, Region, client support and user experience

WorkSpaces is delivered as a remote pixel stream, so perceived responsiveness depends on the selected Region, connection quality, desktop capacity and workload. AWS offers a Connection Health Check to compare latency to regions. Choose a Region based on the people and data involved, then test with the applications that users will actually run. A document editor, a browser-heavy support workflow and a graphics-intensive engineering tool can place different demands on the desktop. A smooth login screen is not evidence that a full day of use will feel acceptable.

AWS lists clients for desktop systems and selected mobile devices, including iPadOS, Android phones and tablets, and Android-compatible ChromeOS devices. Verify current client and operating-system support for the intended device fleet, and confirm which languages are available for the chosen Windows bundle. Assess keyboard layouts, audio, display scaling, smart cards, printers and accessibility needs. If employees work through unreliable home connections, test reconnect behavior and identify a fallback path for urgent work.


## Security, data location and continuity questions

A WorkSpace runs in an AWS Region and connects to the directory and network environment configured by the administrator. Map the desktop’s path to file shares, databases, SaaS services and the internet. Determine which copies of data live on the desktop, which are stored in a shared system, and which are backed up. Centralizing the endpoint may make administration easier, but it does not automatically prove that the organization meets a residency, retention or sector rule. Confirm the specific AWS service terms and organizational controls that apply.

Plan for account lockout, a failed directory, a regional issue, a mistaken image update and an employee departure. Test restore or reprovisioning from the image and the organization’s file backup. Remove user access promptly, but preserve data through an approved handoff before deleting a persistent desktop. AWS documents service and client controls; this desk review has not audited a deployed WorkSpaces environment and is not a security certification. A regulated or critical system needs a review of architecture, identity, logging and recovery by the responsible technical and compliance owners.


## Amazon WorkSpaces alternatives and a buyer test

Compare WorkSpaces Personal and Pools with Azure Virtual Desktop, Windows 365, Citrix DaaS and a managed local-computer fleet. These choices differ in persistent versus pooled desktop models, identity integration, licensing, application delivery, remote-access protocol, minimum commitments, network design and support. A cloud desktop may simplify employee onboarding, but a mostly idle monthly desktop can cost more than a managed endpoint. A pooled environment can reduce per-user resource duplication while requiring additional configuration for profiles and session reset.

Run a pilot with a small set of representative users and a written task list. Measure login time, reconnect success, application launch, storage access, audio or printer needs, and the number of helpdesk interventions. Compare the bill against active usage, then repeat after including directory, transfer and support costs. This is a proposed evaluation, not a Roseram benchmark. Keep an export or backup of necessary files and document the date, bundle, Region and run mode used so another reviewer can reproduce the result.


## Amazon WorkSpaces SCAM Review: what the available evidence shows

Amazon WorkSpaces is documented by AWS as a commercial virtual desktop and application service, with published running modes, client support information, a pricing calculator and eligibility rules for a time-limited Free Tier offer. Those materials support a practical billing and operations review; they do not establish that the service is a scam. Roseram has not launched a WorkSpace, tested a client session or audited an AWS account for this article. The “SCAM Review” label is the site’s buyer-due-diligence format, not a finding of misconduct.

Before purchase, confirm the exact service variant, bundle, Region, desktop count, operating system, running mode, Free Tier eligibility, expected work hours, data-transfer destinations and external AWS dependencies. Ask whether licensing, directory infrastructure and software are included or separately billed. Define an owner for images and patches, a support route for users and a process for saving or recovering their work. Recheck the calculator and terms at checkout. A well-planned pilot can reveal whether remote desktops fit the workforce; an unexamined estimate cannot.


## Features and decision criteria

- Persistent WorkSpaces Personal desktops and non-persistent WorkSpaces Pools
- AlwaysOn monthly or AutoStop hourly running modes
- AWS-managed client applications for supported computers and mobile devices
- Custom images, directory integration and connections to AWS resources

## Pricing considerations

AWS directs buyers to the regional pricing page and WorkSpaces pricing calculator. The current FAQ describes a three-billing-cycle offer with 40 combined hours per calendar month for eligible customers who have not previously used WorkSpaces; unused hours do not roll over. The monthly infrastructure fee is waived during that offer, but use beyond 40 hours is billed. Verify eligibility, bundle, Region, operating system, tax and current checkout terms before launch.

## Sources and further reading

- [Amazon WorkSpaces pricing](https://aws.amazon.com/workspaces/pricing/)
- [Amazon WorkSpaces Personal running modes](https://docs.aws.amazon.com/workspaces/latest/adminguide/running-mode.html)
- [Amazon WorkSpaces FAQs, including Free Tier eligibility and billing](https://aws.amazon.com/workspaces-family/workspaces/faqs/)
- [AWS WorkSpaces pricing calculator](https://calculator.aws/#/addService/WorkSpaces)
- [Amazon WorkSpaces client and device documentation](https://docs.aws.amazon.com/workspaces/latest/userguide/workspaces-clients.html)
- [Amazon WorkSpaces virtual desktop on Wikipedia](https://en.wikipedia.org/wiki/Amazon_WorkSpaces)
- [Amazon WorkSpaces website](https://aws.amazon.com/workspaces/)
- [saashub listing](https://www.saashub.com/amazon-workspaces)

For the complete Roseram buyer guide, see [Amazon WorkSpaces review](https://roseram.com/reviews/scams/amazon-workspaces-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
