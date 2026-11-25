# Clef review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Open-weight structured decision models and hosted inference  
**Method:** Source-led desk review; no hands-on testing is claimed.

Clef is Cloudflare’s family of decision models designed to map text or structured state and a schema of typed questions to constrained answers with per-option scores, rather than generate free-form prose. The family includes the 27B Clef model, 9B Clef-flash and the multimodal Clef-omni variant. Cloudflare offers hosted inference through Workers AI; the model weights are also published on Hugging Face under Apache 2.0. The current hosted price sheet lists $0.240 per million input tokens for Clef, $0.038 for Clef-flash and $0.150 for Clef-omni, with media inputs counted as input tokens. This desk review examines the model’s proper fit, schema design, uncertainty, serving costs, open-weight deployment and buyer validation steps.

## Editorial verdict

Cloudflare’s official announcement, model documentation, changelog and Hugging Face model card describe an actual model family with hosted inference and downloadable open weights. The evidence reviewed does not establish fraud or support treating Clef as a general-purpose conversational assistant. Its central proposition is schema-constrained classification and scoring, so buyers should validate the returned distributions on their own data before allowing them to trigger consequential actions. Cloudflare’s benchmark and speed claims are vendor-published and were not independently reproduced by Roseram. This is a source-based desk review, not a model benchmark, production deployment, safety certification or financial, hiring, medical or security test.

## Clef SCAM Review: what Cloudflare actually offers

A search for “Clef scam” should begin by separating the model from the claims surrounding it. Cloudflare’s public material describes a family of structured decision models, hosted through Workers AI and also released as open weights. The product documentation gives model identifiers, request formats, typed question schemas and current input prices. The reviewed material establishes an identifiable software offering; it does not establish fraud, and this review found no basis for calling Clef a scam. The title is a buyer due-diligence query, not an allegation.

The important qualifier is what kind of software this is. Clef is not designed to hold an open-ended conversation or write a free-form explanation. It evaluates text or structured state against permitted answers and returns constrained values with scores. That makes it potentially useful inside a routing or classification workflow, but it also makes schema quality, threshold selection and error consequences central to the buying decision. This review covers Cloudflare’s official announcement, model pages, release notes and model card checked on November 18, 2026. Roseram did not run the model or reproduce Cloudflare’s benchmarks.


## What a decision model does

A decision model receives a state, such as a support message or a structured record, and a set of typed questions. Cloudflare documents question types such as `noul` for a yes-or-no decision, `choice` for selecting from a bounded list, and `score` for placing the input on a defined scale. Clef returns an answer for each requested field and probabilities or scores associated with the permitted choices. The application can then use those values to route, prioritize or request human review.

The attraction is a bounded response shape. An application that needs to select one queue from three options can ask for that explicit choice instead of parsing a paragraph. But schema-bound output is not the same as correct output. A model may still misunderstand an ambiguous message, encounter a new type of case or assign a misleadingly high score. The software consuming the result must define what happens for uncertain or contradictory cases. A constrained format reduces one kind of output variability; it does not remove judgment or error.


## Clef, Clef-flash and Clef-omni

The Clef family includes multiple model variants. Cloudflare documents Clef as a 27B model with a hosted 65,536-token context window. Clef-flash is the smaller, faster 9B version, and the October 2026 pricing update lists its hosted context window at 24,576 tokens. Clef-omni adds audio and video input to text and images, allowing an application to ask structured questions about different media in one request.

The variants trade input capacity, supported media and price. The buyer should select from the actual workload rather than the model name alone. If the input is a short support note, a smaller variant may be sufficient; if the decision depends on video or audio evidence, the omni model may be relevant. A longer input may exceed the hosted context window after the schema and media tokens are included. Test representative requests and check the returned usage field instead of estimating from character count alone.


## How an application sends a Clef decision request

Cloudflare’s documentation shows a Workers AI binding and an account-level REST endpoint. A request includes a model selector, the state to evaluate, and a map of question IDs to their type and instructions. For a choice question, the developer defines the valid answer set and the meaning of each option. For a score question, the scale and its labels should reflect the decision the application actually needs.

This design makes the model’s contract visible in code. The application knows which answer fields to expect and can reject malformed or unexpected values before taking an action. Clef’s documented API supports between one and sixty-four questions per request, and the state may be a string or structured data. Inputs that exceed the model’s limit can be truncated, so the client must avoid assuming that all provided context was considered. For hosted use, protect Cloudflare credentials and apply normal access controls to any endpoint that calls the model.


## Cloudflare Workers AI pricing and token costs

On November 18, 2026, Cloudflare’s model documentation listed hosted input prices of $0.240 per million tokens for Clef, $0.038 per million for Clef-flash and $0.150 per million for Clef-omni. The documentation says output tokens are not charged for these models. Images and, for Clef-omni, audio and video are converted into input tokens, so a media-heavy request consumes more of the billable input than a short text request.

The token meter is only one part of operating cost. A production system may also pay for adjacent Workers AI services, storage, retries, human review and the engineering time needed to evaluate errors. It should budget for requests that repeat because of network failures or poor prompt/schema design. Cloudflare publishes prices for hosted inference, while self-hosted model weights avoid that API charge but require GPU compute and maintenance. Verify current account terms and rate limits before a campaign or workflow depends on a quoted per-token number.


## Open weights, licensing and self-hosting

Cloudflare publishes the Clef model card and weights on Hugging Face under the Apache-2.0 license. The model card identifies the larger model as a 27B parameter model and describes its base model and joint schema head. It also includes model files and usage examples for local Transformers workflows. This provides a route for teams that need to inspect or operate weights in their own environment, subject to their ability to provision and support the required hardware.

Open weights change the deployment boundary; they do not make infrastructure free or eliminate all license diligence. Teams must plan for model download size, compatible libraries, GPU memory, software versioning, security updates, batching and observability. They also need to retain the model card and license with their deployment. The Hugging Face page says Apache 2.0, but organizations should review the associated terms and base model details with counsel if their intended use has special requirements. Do not confuse an available download with a managed, production-ready endpoint.


## The difference between a score and useful confidence

Clef returns probabilities or scores over the options the developer supplies. Those values can be useful for ranking and thresholding, but the number should not be treated as a universal measure of confidence without validation. The score depends on the model, wording, schema, class distribution, input quality and the way the application interprets each option. A value that appears high on one test set may not remain reliable after the product or user population changes.

Before automation, evaluate the model on a representative set with labels reviewed by people who understand the task. Measure false positives and false negatives separately, inspect calibration by class, and choose a threshold based on the harm of each type of error. Keep a path for abstention or human review. For high-impact decisions, document how the model is used, what evidence is available to an operator and how a person can override a result. These are prudent controls, not claims about any benchmark Cloudflare has published.


## Where a constrained decision model can fit

A structured classifier can be useful when an application needs to assign incoming work to a known category, assess a bounded level of severity or extract a fixed set of judgments from text and media. Cloudflare’s documentation examples include triaging support requests and assessing details in photos or videos. These cases have a finite answer space and can be connected to downstream rules that already exist in the product.

Clef may also sit alongside a generative model rather than replace one. A generative assistant can draft a natural-language response while a structured model returns a routing label or risk signal. The interface between them still needs evaluation: an incorrect label can send a person down the wrong path, and a structured model cannot explain its reasoning in prose by itself. Use it where bounded answers are valuable and the consequences can be managed, not as a general substitute for a person or a language model.


## Limitations: fixed schemas, truncated inputs and hidden edge cases

The same schema that keeps outputs bounded also defines what the model is allowed to say. If a new category is missing, the model must map the case to an existing choice or fail to express that the list is incomplete. A `choice` question should therefore include a genuine fallback, such as “other” or “needs review,” where the task calls for one. Keep the answer options mutually understandable and test whether the model confuses adjacent categories.

Cloudflare’s model docs state that long text can be truncated to fit the token limit. Clef’s API also imposes request limits on media count and size; the model reference documents up to four embedded images, each with image and payload constraints, while media tokens share the context window. A client that supplies a very long case history can silently exclude the most important evidence if it places that evidence late. Summarize or select inputs intentionally and inspect usage and outputs at the boundary cases.


## What Cloudflare’s benchmarks do and do not show

Cloudflare’s announcement includes benchmark tables and latency comparisons that describe the company’s own evaluation. Those results can help a buyer identify which tasks Cloudflare chose to measure and how the models performed in those tests. The company says its 43-benchmark study showed latency advantages for the Clef variants under the specified conditions. The hosted model docs also publish context windows and price, which are concrete facts distinct from a general performance claim.

The tables do not predict performance on a buyer’s private taxonomy, production distribution or cost of error. They are not an independent Roseram test. Reproduce a small task-specific evaluation using the same criteria, prompts, thresholds and baseline you plan to deploy. Include a realistic volume and media mix. Track accuracy, calibration, latency and total cost separately. A model can be faster but still be unsuitable if it routes the wrong records, and a high average score can conceal a severe failure on a rare class.


## Data handling and deployment responsibility

Cloudflare’s model pages identify hosted Clef as Cloudflare-hosted and show a zero-data-retention designation. That is a relevant product signal, but buyers should still inspect the current Cloudflare AI and account terms that govern their particular deployment, data path and contract. Decide whether any personal, confidential or regulated information may be included in the state or media. A score output can be sensitive if it labels a person or account, even if the model does not return prose.

Teams self-hosting weights take on more direct responsibility for access, logging, retention, network isolation, update management and monitoring. Teams using Workers AI still need to protect credentials, validate inputs, limit who can call the endpoint and avoid logging unnecessary payloads. A zero-retention label should not be treated as a substitute for the organization’s own data classification, vendor review or security controls. Ask for current documentation if the answer affects a compliance decision.


## Fine-tuning and the early product direction

Cloudflare’s original Clef announcement also described a reinforcement-learning service for adapting Clef to customer workloads. It said Cloudflare was offering hands-on fine-tuning with a forward-deployed team and intended to build a self-serve platform later. The same announcement described parts of that broader AI platform as work in progress. This is a direction and service description, not a published universal feature entitlement or fixed price for every Clef customer.

A team considering tuning should ask how its data is handled, who operates the process, which deployment artifacts it receives, how model versions are evaluated and what happens when the tuned model is updated. Ask whether the service is available for the account, what minimum data quality is required and how pricing is determined. The first hosted model may work well enough with a carefully designed schema; tuning is not automatically needed just because it is offered. Measure the baseline before committing to a specialized model path.


## Alternatives and how to compare Clef

Possible alternatives include a conventional text classifier, a general-purpose LLM constrained to structured output, a rules engine or a self-hosted open model. The right comparison depends on whether the task needs image, audio or video understanding, a finite answer set, local control, free-form explanation or strict latency limits. Clef’s model card says the API is compatible with SystemOne and Jev, which may simplify a model swap for teams already using that interface, but compatibility does not guarantee equivalent scores or behavior.

Use one labeled evaluation set and one documented schema to compare candidates. Include unknown categories, conflicting evidence, long input, poor-quality media and a decision that should be deferred to a human. Measure per-class error, calibration, latency and input-token cost. Review the contract and license for hosted versus self-hosted deployment separately. A model should earn a place in the workflow by meeting the task’s acceptance criteria, not by claiming an impressive leaderboard position.


## Who should consider Cloudflare Clef?

Clef is worth evaluating for engineering teams that need structured classifications or scores, already use Cloudflare Workers AI or can operate the open weights, and are prepared to evaluate thresholds on their own data. The hosted variants offer published input pricing and multimodal options. The Apache-2.0 model card gives a path to local experimentation for teams that can provision suitable hardware and maintain it.

It is a poor fit when the requirement is to generate rich text, explain a decision in natural language, or make a high-stakes determination without a human check. It is also not a complete product workflow by itself: teams still need to design schemas, log outcomes, handle uncertain cases and maintain downstream actions. A buyer should choose another approach if its workload is mostly open-ended conversation or if a bounded category set would force materially different cases into the same answer.


## Clef buyer checklist

Before using Clef, write the decision in plain language and list every allowed answer, including how to handle unknown or unsafe cases. Confirm whether the request should use Clef, Clef-flash or Clef-omni and whether its context window and modalities match your input. Estimate token costs using sample usage output, particularly when including images, audio or video. Verify current rates, account limits and the zero-retention terms that apply to the chosen service.

Then create a labeled test set, review false-positive and false-negative costs, and define an abstention or human-review threshold. Test long inputs, missing evidence and a schema revision. If self-hosting, confirm that the model weights, license, libraries and hardware fit your operating environment. If using Cloudflare’s fine-tuning service, verify availability and obtain the current scope and cost. These are buyer checks; Roseram has not run them.


## Is Clef worth it?

Clef has a focused proposition: return structured decisions from a state and typed question schema, with hosted variants, open weights and a published token meter. That can be attractive when a conventional classifier lacks the required multimodal input or when a general LLM’s free-form answer is awkward to validate. The documentation makes the request shape tangible, so a development team can prototype a narrow, measurable workflow before committing to automation.

Its value depends on whether the scores remain useful on the buyer’s own distribution and whether the downstream action is safe. Vendor benchmarks are informative starting points, not an independent guarantee. The application must handle uncertainty, malformed or incomplete inputs, schema gaps and costs for media tokens. Teams wanting a general conversational system should compare a different class of model. Teams with a bounded decision task should validate it in shadow mode before allowing Clef to affect real users or records.


## Final Cloudflare Clef assessment

Cloudflare Clef is a documented structured decision-model family, not a general chat assistant. Its official hosted prices on November 18, 2026 were $0.240 per million input tokens for Clef, $0.038 for Clef-flash and $0.150 for Clef-omni. The models return typed, constrained outputs; media tokenization and context limits affect usage. The weights are published under Apache 2.0 for teams able to run them themselves. Cloudflare’s published performance claims remain vendor claims that Roseram did not reproduce.

A buyer should first test the actual decision on representative, labeled data, calibrate thresholds, allow uncertain cases to reach a person, and check model terms and data handling. A Roseram workspace can help draft schemas or evaluation plans, but it does not host Clef, confirm its accuracy or certify a production decision system. The sources reviewed do not establish a fraud finding, guaranteed result or hands-on test.


## Features and decision criteria

- Typed `noul`, `choice` and `score` outputs with allowed answer sets
- Probability scores for each permitted choice rather than free-form text generation
- Hosted inference through Cloudflare Workers AI APIs and bindings
- Open-weight model files published under Apache 2.0 on Hugging Face
- Clef, smaller Clef-flash and audio/video-capable Clef-omni variants
- Image inputs for vision classification and structured decisions
- Cloudflare-described compatibility with the SystemOne and Jev API shape

## Pricing considerations

Model prices and context windows were checked against Cloudflare’s official Workers AI pages and October 2026 changelog on November 18, 2026. These hosted model prices cover input tokens; the docs state output tokens are not billed. Media is converted into input tokens, so image, audio and video requests can cost more than text-only requests. Cloudflare account plan, billing credits, rate limits and product terms may also apply. Self-hosted weights have no Cloudflare inference charge, but local GPU and operational costs are not zero. Confirm current rates and tokenization rules before estimating cost.

## Frequently asked questions

### Is Cloudflare Clef a scam?

Cloudflare’s official pages document Clef as a decision-model family with hosted inference and open weights. The sources reviewed do not establish fraud. The SCAM Review title is a buyer due-diligence query, not an allegation or endorsement.

### What does Clef do?

Clef evaluates a state against a schema of typed questions and returns constrained answers with scores or per-option probabilities. It is designed for classification and routing decisions, not free-form conversational writing.

### How much does hosted Clef cost?

On November 18, 2026, Cloudflare’s docs listed $0.240 per million input tokens for Clef, $0.038 for Clef-flash and $0.150 for Clef-omni. Media tokens are billed as input; confirm current rates and account terms before deployment.

### Can I run Clef locally?

Cloudflare publishes Clef model weights on Hugging Face under Apache 2.0. Self-hosting avoids Cloudflare inference charges but still requires appropriate hardware, storage, software support and operating work.

### Does Clef provide calibrated probabilities?

Clef returns scores or per-option probabilities, but a score is not automatically a reliable confidence estimate for every application. Validate calibration, class balance and error costs on representative data before using thresholds to trigger actions.

### Has Roseram benchmarked Clef?

No. This is a desk review of Cloudflare’s public announcement, model pages, changelog and model card. Roseram did not run inference, reproduce vendor benchmarks or deploy the model.


## Sources and further reading

- [Cloudflare Workers AI Clef model reference, input format and price](https://developers.cloudflare.com/workers-ai/models/clef/)
- [Cloudflare Workers AI Clef-omni model reference](https://developers.cloudflare.com/workers-ai/models/clef-omni/)
- [Cloudflare changelog for Clef-omni, Clef-flash pricing and hosted context windows](https://developers.cloudflare.com/changelog/post/2026-10-09-clef-omni-workers-ai/)
- [Clef website](https://blog.cloudflare.com/clef-decision-models/)
- [Cloudflare Clef model card and Apache-2.0 license](https://huggingface.co/Cloudflare/clef)
- [Cloudflare Clef-flash model documentation](https://developers.cloudflare.com/ai/models/%40cf/cloudflare/clef-flash/)
- [product-hunt listing](https://www.producthunt.com/products/cloudflare-clef)

For the complete Roseram buyer guide, see [Clef review](https://roseram.com/reviews/scams/clef-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
