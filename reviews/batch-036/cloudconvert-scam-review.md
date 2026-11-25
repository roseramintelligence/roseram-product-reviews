# CloudConvert review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Online file conversion service and API  
**Method:** Source-led desk review; no hands-on testing is claimed.

CloudConvert is an online file conversion service and API for documents, images, video, audio, archives, and other formats. The service packages work as asynchronous jobs and tasks, with credits consumed according to conversion type and processing time. Its published free, package, subscription, and enterprise options have different file limits, credit expiry, concurrency and support terms.

## Editorial verdict

CloudConvert publishes a working service, API documentation, credit rules, and privacy/security information. The cited sources do not support a fraud allegation. Buyers should verify the exact conversion engine and output quality, calculate credits for their actual files, and check where sensitive data is processed and when temporary job data is removed.

## CloudConvert review: the format list is only the first test

CloudConvert handles conversions through a browser interface and API, spanning document, image, audio, video, archive, and other formats. The service can be convenient when a workflow needs a format that a desktop application cannot export directly or when a backend has to process files without installing conversion software. The key question is not simply whether a format pair appears in a catalog; it is whether the converted output preserves the information and quality the recipient needs.

Choose representative files from your real workflow and compare them before committing. For documents, inspect page breaks, tables, fonts, links, and metadata. For media, check codec, resolution, audio synchronization, color, and file size. For archives, confirm filenames and folder structure. Include unusual but legitimate inputs such as a password-protected file or a large scan. These are evaluation cases, not results claimed by Roseram; the final decision should reflect the files you actually plan to process.


## CloudConvert pricing: credits, conversion types and processing time

CloudConvert uses conversion credits rather than a single flat per-file price. Its current pricing page says a conversion generally consumes credits based on its type and processing duration. The published base table lists one credit for a general conversion, two for Office or iWork to PDF, and four for PDF to Office; extra minutes can consume additional credits. Only successful conversions are charged. File length, source complexity, output format, and processing time can therefore make two files from the same batch cost different amounts.

The Free option lists ten credits per day, a 1 GB maximum file size, a five-minute processing limit, and up to five concurrent tasks. A one-time package's credits do not expire, while subscription credits reset monthly and unused credits do not roll over. Enterprise pricing is custom. The page lets a buyer select the volume and see a quote, so a static minimum price may not be representative. Before estimating a monthly budget, run a representative batch, record successful-task credits, and include failed jobs and retries in the operational plan even when a failed conversion is not billed.


## CloudConvert API jobs, tasks and failure handling

The API organizes work as jobs containing tasks such as importing a file, converting it, and exporting the result. Job execution is asynchronous by default, which is useful for long-running video or document conversions; the documentation cautions that synchronous calls can time out while waiting for longer work. Applications should track job state and report a useful result to the user rather than keep a browser request open until the entire process finishes.

CloudConvert documents HTTP errors including 429 rate limits and a Retry-After header. Its API introduction explicitly advises clients not to automatically retry tasks because the service already retries some transient failures internally. Design the integration to inspect job status and failure codes, distinguish a retryable transport problem from an invalid file, and avoid duplicate charges or output collisions. Keep API keys on the server, limit their scopes, and use webhooks or polling intervals that respect documented limits.


## File privacy, processing region and temporary retention

CloudConvert's security pages describe isolated processing containers and configurable API access scopes. Its privacy and task documentation say jobs and tasks are deleted automatically after they have ended, within 24 hours at the latest; the service homepage also describes temporary processing and removal after a job. This is useful lifecycle information but not a substitute for reviewing the current data-processing agreement, region selection, subprocessors, and organization-specific requirements before uploading confidential material.

Do not upload customer, employee, legal, health, or financial documents to a conversion service until the owner has approved that processing path. Check whether the API sends a file by URL or uploads it directly, who controls that source URL, and whether it can be accessed by unintended users. Remove personal data from filenames and metadata where practical. A publicly accessible import URL can expose a source file independently of CloudConvert; use short-lived signed links and revoke them once the job completes. Download and validate the result promptly rather than treating the conversion task as permanent storage.


## Output quality, file limits and operational reliability

Conversion engines may differ by format pair, and settings such as page ranges, codecs, image quality, dimensions, fonts, or office rendering can affect the output. A finished job means the task completed according to the service, not that the file meets your acceptance criteria. Compare outputs visually and programmatically for the values that matter. Keep original inputs and a checksum or source ID so you can reproduce a job and identify which version produced a result.

The Free tier's size and runtime limits can make it suitable for exploration but not representative of a production batch. Paid package and subscription tiers list higher or unlimited limits in the comparison, though actual usage remains governed by the selected plan and fair-use terms. Monitor job latency, failed formats, credit consumption, and download completion. Keep a fallback converter or manual route for critical tasks. A single converter provider should not become the only keeper of documents a user cannot recreate.


## CloudConvert alternatives and the buyer test

Compare CloudConvert with desktop applications such as Acrobat or LibreOffice, cloud storage providers' conversion tools, and APIs such as Adobe PDF Services or a self-hosted LibreOffice/FFmpeg pipeline. The alternatives differ in formats, editability, privacy, batch throughput, availability, cost predictability, and the work required to maintain the software. Self-hosting may keep files within a controlled environment but transfers patching, scaling, engine compatibility, and support responsibilities to your team.

Measure a small batch across normal, difficult, and large inputs. Record the exact source and target format, settings, completion time, credit count, output size, and any correction required. Check an error response, cancel a running job, and verify that temporary source and output links stop working when intended. This is a proposed test, not a claim that Roseram ran a conversion benchmark. Choose the option whose output quality and data path meet your requirements at a cost you can forecast.


## CloudConvert SCAM Review: evidence and practical checks

CloudConvert provides public product, pricing, API, privacy, and security documentation. The cited information describes a commercial file conversion service; it does not show that the product is a scam. This page is an editorial desk review, not a claim that Roseram uploaded files, audited its security controls, or measured uptime. A user's decision should be based on test conversions and the terms that apply to the account.

Before processing production files, confirm the format pair, conversion settings, expected credit cost, maximum file size, processing-time cap, regional setting, retention policy, and API credential scopes. Verify the complete file lifecycle from upload to download and deletion. Use files you are authorized to process and keep an independent source copy. Compare the monthly subscription's expiry rule with one-time package credits, then recheck the price selector and privacy terms at checkout.


## Features and decision criteria

- Browser-based file conversions across document and media formats
- REST API jobs built from import, conversion and export tasks
- Credit-based metering with different base costs and processing-time charges
- Temporary processing with documented task/job lifecycle and security controls

## Pricing considerations

The pricing page uses a volume selector, so a fixed package price is not shown in the source snapshot. Credits generally reflect conversion type plus processing time; general conversions start at one credit, Office-to-PDF and iWork-to-PDF at two, and PDF-to-Office at four. Failed conversions are not charged. Confirm currency, credit quantity, expiry and current quote before purchase.

## Sources and further reading

- [CloudConvert pricing and conversion-credit rules](https://cloudconvert.com/pricing)
- [CloudConvert API introduction, rate limits and retries](https://cloudconvert.com/docs/getting-started/introduction)
- [CloudConvert task states and 24-hour cleanup](https://cloudconvert.com/docs/api-reference/tasks)
- [CloudConvert job API lifecycle](https://cloudconvert.com/docs/api-reference/jobs)
- [CloudConvert security and isolated processing](https://cloudconvert.com/security)
- [CloudConvert privacy policy](https://cloudconvert.com/privacy/)
- [CloudConvert on Wikipedia](https://en.wikipedia.org/wiki/CloudConvert)
- [CloudConvert website](https://cloudconvert.com/)
- [saashub listing](https://www.saashub.com/cloudconvert)

For the complete Roseram buyer guide, see [CloudConvert review](https://roseram.com/reviews/scams/cloudconvert-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
