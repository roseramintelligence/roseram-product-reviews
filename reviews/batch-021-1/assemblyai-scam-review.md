# AssemblyAI review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-18  
**Category:** Speech recognition and voice AI developer platform  
**Method:** Source-led desk review; no hands-on testing is claimed.

AssemblyAI offers APIs for recorded and live speech transcription, speech understanding, and voice-agent workflows. Its pricing page currently lists Universal-3.5 Pro at $0.21 per hour and Universal-2 at $0.15 per hour for prerecorded transcription, with add-on charges for prompting, diarization, and medical mode. The page also lists free monthly allowances and a bundled Voice Agent API rate. Billing for prerecorded audio is prorated to the processed seconds and multichannel audio is billed per channel. Data handling varies by API and account settings: the documentation describes file and transcript retention periods, a paid-plan training opt-out, and a separate BAA path. Buyers should confirm model version, add-ons, retention controls, and the correct use of speaker consent before sending recordings.

## Editorial verdict

The official sources reviewed document AssemblyAI's speech APIs, rate card, billing rules, model-training controls, and retention guidance. They provide no source-based reason to call the service a scam. This is a source-based desk review, not an accuracy benchmark or hands-on test. The useful buyer questions are whether a model handles the relevant audio and language, what add-ons and channels will cost, and which retention and training settings apply to the chosen endpoint. A transcript can be plausible while still mishearing a name or number, so a buyer should validate important outputs against the recording.

## AssemblyAI is a speech API suite for recorded files and live audio

AssemblyAI's API catalog separates prerecorded transcription from realtime streaming and adds tools for speech understanding and voice agents. A prerecorded job uploads an audio or video file and returns a transcript after processing. A streaming job sends live audio through a persistent connection and returns interim or final transcript events. Those are different engineering workflows with different billing units, timing, and retention considerations. Choosing the endpoint is part of designing the product, not just selecting a model name.

The pricing page describes Universal-3.5 Pro and Universal-2 for asynchronous transcription, alongside streaming models and a Voice Agent API. Add-ons include speaker diarization, medical mode, prompting, keyterms, and related speech features, with eligibility depending on model. A developer should check language coverage and endpoint support against the actual audio. The presence of a language on a broad marketing page does not establish that every model and realtime mode handles it identically.


## The rate card is usage-based, but add-ons and channels change the total

When checked on November 18, 2026, the official pricing page listed Universal-3.5 Pro prerecorded transcription at $0.21 per hour and Universal-2 at $0.15 per hour. It listed a free allowance of up to 185 hours of prerecorded transcription and 333 hours of streaming transcription. The page says signup does not require a credit card. These figures should be attached to their model, endpoint, and date; a rate for one transcription mode does not represent the cost of every speech service.

The page listed speaker diarization at $0.02 per hour for both prerecorded models, medical mode at $0.15 per hour, and some prompting features at $0.05 per hour. It notes that keyterms prompting is included with Universal-2. Multichannel audio is billed per channel, so one hour of two-channel audio can consume two billed hours. A workflow that processes multiple channels, uses a paid add-on, and retries low-confidence passages should be budgeted from those actual components rather than a single headline figure.


## Voice Agent bundles should be compared with the same complete call path

AssemblyAI lists a Voice Agent API at $4.50 per hour on its pricing page. The page describes a bundle that includes realtime speech recognition, prompting and Voice Focus, turn and interruption detection, an LLM, text-to-speech voices, and hosting over a WebSocket, with recordings and transcripts available through the dashboard or API. It also says billing is based on connected conversation time, by the second. This bundle is not the same service as transcription alone, so comparing its rate with an isolated speech-recognition rate would be misleading.

A buyer should map which pieces the bundle actually replaces. If the application already has an LLM, telephony provider, and text-to-speech service, compare the incremental cost of AssemblyAI's speech layer against the bundled alternative. If the team needs SIP or Twilio, check the terms of the carrier account and the specific integration. Estimate the cost from representative call durations, silence, retries, and human escalations. A per-hour price cannot predict the full invoice without a realistic usage profile.


## Streaming and prerecorded audio use different concurrency and timing rules

The current pricing page describes streaming concurrency as automatically scaling without a concurrency fee. It lists different connection-opening limits for free and pay-as-you-go accounts, with production capacity able to rise as use approaches the existing limit. That does not mean an application can ignore connection management. Clients still need to reconnect safely, handle service interruptions, control queued audio, and avoid treating a partial transcript as a final answer.

For prerecorded work, the account documentation says billing is based on audio duration and is prorated to the processed second. It also says failed transcripts are not charged. Keep job identifiers, submitted file duration, selected model, completion status, and billed usage so an operations team can reconcile the account. Test errors, cancelled jobs, malformed audio, and repeat requests in a low-risk environment. Do not assume a retry is free unless the provider's current billing record confirms it.


## Transcription quality has to be checked against the source recording

A transcript is an interpretation of audio, not a certified record. Speaker overlap, weak microphones, background noise, uncommon names, domain vocabulary, code-switching, and accents can all make errors consequential. Universal-3.5 Pro and Universal-2 are presented with different model capabilities and costs; the buyer must decide whether those distinctions matter for their recordings. A model description is not an independent comparison on the company's own call mix.

A practical evaluation should take a representative and authorized sample, create a human-corrected reference transcript, and measure the kinds of errors that matter. Review names, prices, negation, dates, speaker labels, and sensitive terms separately. For a legal or medical process, define who reviews the transcript before anyone acts on it. This proposed evaluation is not a test Roseram has performed. It gives a buyer a way to compare error patterns rather than relying on a demo excerpt selected by a vendor.


## Retention and training settings differ by endpoint and account

AssemblyAI's data-retention documentation says that some API files may be used to train its models when permitted by the applicable contract. It says those files undergo a redaction process intended to remove personally identifiable information. The documentation also says customers can opt out through Data Controls on a paid plan, that a signed Business Associate Addendum opts the customer out automatically, and that the option applies to new requests. European servers are listed as another condition where submitted files will not be used for model training.

The security page describes prerecorded uploads as deleted within 24 to 48 hours and transcripts as retained for 30 days by default, with a time-to-live as short as one hour or deletion on demand. It describes streaming retention differently and says audio and transcripts are not stored after opting out of training. Those details are endpoint-specific and can change. Before processing sensitive calls, identify the API route, server region, plan, account setting, BAA status, and transcript expiry; then test deletion and keep the applicable agreement on file.


## Audio collection still requires a lawful basis and speaker notices

AssemblyAI's terms say the customer must have the rights and consents needed to provide customer data and inputs, and must use the service in line with applicable law. A transcription API does not itself secure consent from callers or meeting participants. Before uploading an archive or opening a live stream, determine who recorded it, what notice was given, how the audio may be reused, and who can access the resulting transcript. An organization's internal permission to run software is different from a participant's permission to record or process their voice.

A sound workflow limits access to raw audio, retains only what is required, and gives a responsible person a way to correct a transcript or remove data. For regulated work, confirm which agreement and controls apply before sending any real records. Do not use a privacy feature from one endpoint as proof that another endpoint has the same behavior. These are proposed buyer checks, not findings that AssemblyAI mishandles data or that a particular use is lawful.


## A useful AssemblyAI pilot measures the whole task, not just recognition

Choose a small sample that reflects the real mix of speakers, channels, lengths, and environments. Write a reference transcript, run the intended endpoint and model, and compare errors by category. If the application uses diarization, evaluate speaker assignment separately from word accuracy. If it uses streaming, measure how quickly useful text arrives and what happens when the speaker pauses or interrupts. Record both the billed units and the human review effort required to produce an accepted result.

Include operational cases: a file with no speech, an upload that fails, a multi-channel recording, a time-to-live request, and an explicit deletion. Check usage in the billing account after the test. Then rerun with add-ons only when they solve a measured problem. This is a proposed buyer protocol, not a report of Roseram's experience or an accuracy claim. A successful test should be repeatable by another engineer and tied to a written acceptance threshold.


## Who may choose AssemblyAI, and what alternatives should be compared?

AssemblyAI may suit developers who want a usage-priced speech API with separate choices for file transcription, live streams, and voice-agent infrastructure. It may be less attractive to teams that require a specific unsupported language-model combination, strictly local inference, or a complete call-center workflow with no external orchestration. The right choice depends on endpoint, rights, retention, throughput, and the human cost of correcting outputs, not the product category alone.

Compare other transcription APIs and self-hosted speech models using the same recordings, expected languages, and acceptance rules. For a voice agent, compare the complete STT, LLM, TTS, hosting, and telephony bill. For a transcription archive, include diarization and storage. Ask each provider the same questions about retention, training controls, data residency, BAA availability, and failure billing. Select the path whose real output and operating obligations fit the job.


## Features and decision criteria

- Asynchronous transcription for prerecorded audio and video files.
- WebSocket streaming transcription for live audio, with model-dependent language support and session billing.
- Speaker diarization, keyterms, prompting, formatting and speech-understanding add-ons.
- Voice Agent API that combines speech recognition, an LLM, text-to-speech and conversation infrastructure.
- Usage-based billing with free monthly allowances, no minimum commitment on pay-as-you-go, and documented failed-request billing behavior.
- Endpoint-specific retention, data-training controls, and business associate agreement options.

## Pricing considerations

These are the public rates displayed on AssemblyAI's pricing page when checked. The page lists up to 185 hours of prerecorded and 333 hours of streaming transcription in the free tier, with no credit card required. Add-ons can change the bill: diarization was listed at $0.02/hour, medical mode at $0.15/hour, and Universal-3.5 Pro keyterms prompting at $0.05/hour; some features are included on Universal-2. Multichannel files are billed per channel. The Voice Agent rate includes multiple components and should not be compared directly with transcription alone. Model names, allowances, prices, and supported languages can change; confirm the current endpoint and checkout details before production use.

## Frequently asked questions

### Is AssemblyAI a scam?

The official sources reviewed describe a speech API product, public pricing, account billing, and data controls. This desk review found no source-based reason to call AssemblyAI a scam; it does not claim that Roseram tested transcription accuracy or verified a customer transaction.

### How much does AssemblyAI cost?

The pricing page checked November 18, 2026 listed prerecorded Universal-3.5 Pro at $0.21 per hour and Universal-2 at $0.15 per hour. Streaming, voice-agent, and add-on rates are different. Multichannel transcription is billed per channel, so calculate the full audio duration and chosen features.

### Does AssemblyAI have a free tier?

The current pricing page lists up to 185 hours of prerecorded and 333 hours of streaming transcription on the free tier, with no credit card required. Confirm current account limits and the specific endpoint before relying on a free allowance.

### Does AssemblyAI use uploaded audio to train models?

The documentation says certain files may be used for model training when permitted by the applicable plan and contract. It also describes a paid-plan opt-out, an automatic opt-out with a signed BAA, and a separate rule for European servers. Verify the data controls for the exact account before sending recordings.

### How long does AssemblyAI retain audio and transcripts?

Its security page says prerecorded uploads are deleted within 24 to 48 hours and transcripts are kept for 30 days by default, with shorter time-to-live settings and deletion controls. Streaming retention differs, especially when training is disabled. Consult the current endpoint-specific retention documentation.


## Sources and further reading

- [AssemblyAI official pricing](https://www.assemblyai.com/pricing/)
- [AssemblyAI data retention and model training documentation](https://www.assemblyai.com/docs/data-retention-and-model-training)
- [AssemblyAI security and data retention overview](https://www.assemblyai.com/security)
- [AssemblyAI pay-as-you-go account billing FAQ](https://www.assemblyai.com/docs/faq/how-to-get-your-api-key)
- [AssemblyAI speech-to-text model documentation](https://www.assemblyai.com/docs/speech-to-text)
- [AssemblyAI realtime speech-to-text product and pricing](https://www.assemblyai.com/products/streaming-speech-to-text)
- [AssemblyAI privacy policy](https://www.assemblyai.com/legal/privacy-policy)
- [AssemblyAI terms of service](https://www.assemblyai.com/legal/terms-of-service)
- [AssemblyAI website](https://www.assemblyai.com/)
- [saashub listing](https://www.saashub.com/assemblyai)

For the complete Roseram buyer guide, see [AssemblyAI review](https://roseram.com/reviews/scams/assemblyai-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
