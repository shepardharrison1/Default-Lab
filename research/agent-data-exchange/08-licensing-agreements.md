# 08 - Nonbinding Licensing and Commercial Agreements Framework

**Research date:** 2026-07-15  
**Posture:** Skeptical commercial/legal research for an AI agent proprietary-data licensing and routing platform.  
**Status:** Nonbinding framework for internal discussion. Not legal advice.

> This document is not legal advice and is not a contract. It is a commercial research framework for discussion with qualified counsel. Every item marked **[SPECIALIST COUNSEL REQUIRED]** needs review by specialist counsel before use in a pilot or production agreement.  
> **Labeling rule:** statements labeled **Verified/current guidance** are grounded in public sources checked by web search on 2026-07-15. Statements labeled **Inference** are business/legal judgments drawn from those sources and should not be treated as legal conclusions.

## 0. Commercial structure and skeptical premise

**Proposed platform:** a neutral exchange that lets AI agent applications discover, route to, retrieve, meter, attribute, and pay for licensed access to proprietary content or datasets.

**Core contract stack:**

1. **Publisher agreement:** rights holder appoints the platform to administer listings, metering, access control, billing, reporting, and collections.
2. **Buyer agreement:** agent developer or enterprise buyer receives platform credentials and agrees to usage restrictions, attribution, payment, audit, and deletion terms.
3. **Per-transaction content license:** publisher-set license terms attach to each dataset, response, or retrieval transaction.
4. **Data-processing addendum:** privacy roles, transfer terms, security controls, erasure propagation, and subprocessors.

**Verified/current guidance:** AWS Data Exchange and TollBit both use structures where the marketplace/platform is not the substantive party to the content license between provider and buyer. Snowflake Marketplace similarly requires listing terms and lets providers use standard, custom, or offline terms. Microsoft Publisher Content Marketplace, announced in February 2026, is pursuing publisher-set usage terms, grounding scenarios, and usage-based reporting.

**Inference:** the platform wants the economics of a broker while avoiding the liability of a reseller. Publishers will push the other way: if the platform meters, authenticates, settles, and markets "licensed access," publishers and buyers will expect the platform to stand behind metering, security, sanctions/KYB, and basic rights-diligence operations. The hard negotiation is not the API; it is whether the platform is a neutral facilitator, limited agent, reseller, payment intermediary, or data licensee.

## 1. Clause-by-clause commercial framework

The framework below is intentionally conservative. It assumes the default product is retrieval/grounding access, not model training.

| Topic | Nonbinding framework position | Skeptical notes and counsel flags |
| --- | --- | --- |
| Licensed content definition | Define content by named feeds, endpoints, database tables, document IDs, URL patterns, update cadence, formats, and exclusions. Exclude wire content, third-party photos, user comments, freelance works not cleared for AI licensing, and confidential third-party material unless specifically warranted. | **[SPECIALIST COUNSEL REQUIRED - IP/rights clearance]** Chain-of-title failure is a core business risk. The agreement should not say "all website content" unless the publisher actually controls all rights. |
| Ownership | Publisher retains all IP and database rights. Buyer receives no ownership in content, extracts, indexes, embeddings, or licensed metadata except its independent work product that does not contain or substantially derive from licensed content. Platform owns platform code, transaction ledger, and aggregated marketplace analytics, subject to confidentiality and antitrust limits. | **[SPECIALIST COUNSEL REQUIRED - IP/contract]** US law does not protect facts as such; EU law may protect qualifying databases. Contract should license access, expression, compilation, and services rather than pretending to own facts. |
| License scope | Nonexclusive, nontransferable, revocable, limited license to retrieve, process in memory, summarize, quote within limits, attribute, and display task-specific answers for permitted users, territories, products, and time periods. Everything not expressly granted is reserved. | **[SPECIALIST COUNSEL REQUIRED - contract/IP]** Draft scope as machine-enforceable fields, not vague prose. |
| Search | Permit queries against a publisher-hosted or platform-hosted search endpoint that returns pointers, relevance signals, short snippets, and license/pricing metadata. Search rights do not imply full-text retrieval rights. | Search is a lower-risk, lower-price right. Snippet size still needs limits. |
| Indexing | Platform may create a persistent keyword, metadata, or vector index only if expressly licensed. Default pilot: platform-hosted index, license-scoped, access-controlled, deleted after termination. Buyer-hosted indexing prohibited unless premium tier. | **[SPECIALIST COUNSEL REQUIRED - copyright/database/GDPR]** Persistent indexes are copies or derived artifacts in many practical senses, even if US fair-use arguments may exist for some search indexing. |
| Retrieval | Each retrieval is a metered transaction for one end-user task or authorized business workflow. Define maximum chunk size, documents per task, per-user caps, and retries. | Retrieval is the core paid event. Treat rate limits as license terms, not only engineering controls. |
| Summarization | Permit generation and display of a task-specific summary. Default cap: no re-serving stored summaries to different users; no summary that substitutes for the source; visible attribution required. | **[SPECIALIST COUNSEL REQUIRED - copyright/fair use]** Long summaries can become substitute republication. TollBit's standard summarization license is useful precedent: one use for summary/citation/grounding, no training. |
| Quotation | Permit limited verbatim quotes, e.g. 75 consecutive words, two quotes per source per answer, and no quote compilation that substitutes for the source. | **[SPECIALIST COUNSEL REQUIRED - copyright/moral rights]** Quote limits are commercial guardrails, not automatic legal safe harbors. EU member-state quotation rules vary. |
| Attribution | Require source name, title or dataset label, publication date/version, canonical URL if available, and visible citation in the buyer UI where the UI has a display surface. Carry attribution metadata in every API response. | **[SPECIALIST COUNSEL REQUIRED - consumer protection/advertising]** If ranking is paid or sponsored, attribution may also need advertising disclosure. |
| Linking | Require canonical links when a visual UI exists. For voice or ambient agents, require a companion link, transcript citation, or spoken source disclosure where feasible. | Inference: links are commercially important to publishers but less valuable in non-browser agents; overpromising referral traffic is a sales mistake. |
| Internal business use | Permit only if purchased: internal analytics, evaluation, relevance tuning, QA, compliance review, and spend management. Exclude training, fine-tuning, resale, and building a competing corpus. | Internal use is a separate SKU for many data vendors. Do not silently include it in consumer-facing retrieval. |
| External commercial use | Permit buyer to serve content-derived answers to its own users within the licensed application and territories. Prohibit syndication of content or access to content as a standalone product. | White-label or OEM use needs named sub-licensee terms or separate buyer enrollment. |
| Resale | Prohibit resale, redistribution, sublicensing, publishing, or making licensed content available as content. Permit transformed, task-specific answers only within quotation/summarization limits. | **[SPECIALIST COUNSEL REQUIRED - IP/competition]** The boundary between "answer" and substitute content is fact-specific and contested. |
| Bulk extraction | Prohibit systematic downloads, crawl-like behavior, multi-accounting, and using authorized transactions to harvest content beyond task needs. Include catalog-percentage caps and anomaly detection. | **[SPECIALIST COUNSEL REQUIRED - EU database/US contract]** EU Database Directive art. 7(5) specifically addresses repeated and systematic extraction of insubstantial parts. US protection relies more on contract and technical controls. |
| Database reconstruction | Prohibit reconstructing, approximating, syncing, mirroring, or benchmarking a substantial part of the licensed corpus or a commercially substitutable database. | This should be a bright-line material breach. |
| Caching | Permit short operational caching only: request de-duplication, latency, resiliency, and debugging. Default TTL: 24 hours for content cache, 30 days for restricted operational logs. No durable content store disguised as cache. | **[SPECIALIST COUNSEL REQUIRED - copyright/privacy]** If chat logs contain licensed passages, those logs are retained copies. |
| Retention | Default: content retained only during the task plus the licensed operational window. Answers may persist in user history if they comply with quotation/summarization rules; full retrieved documents may not. | **[SPECIALIST COUNSEL REQUIRED - copyright/GDPR]** EU output/copying analysis is developing quickly. |
| Embeddings | Default pilot: no buyer-hosted embeddings. Tier E0: no persistent embeddings. Tier E1: platform-hosted, license-scoped embeddings only during active license. Tier E2: buyer-hosted embeddings only by negotiated premium addendum, audit, deletion certificate, and no transfer. | **[SPECIALIST COUNSEL REQUIRED - unsettled IP/privacy]** Inference: embeddings are commercially equivalent to a semantic index even if not expressive text. Whether embeddings are copies, personal data, or database extractions is unsettled. |
| Temporary context | Permit "single-task, in-context-window" use as the default low-risk tier: content enters prompt/context for the task and is not written to durable buyer storage except permitted logs. | Inference: true zero-retention is technically approximate because inference providers may have prompt caches/logs. Define allowed infrastructure persistence rather than promising none. |
| Model training | Excluded by default. If ever granted, define training broadly: pretraining, continued pretraining, RLHF, preference learning, distillation, ranker training, retrieval model training, and training on outputs containing licensed content. | **[SPECIALIST COUNSEL REQUIRED - copyright/AI Act]** Training licenses are economically and legally different because trained models cannot practically "return" the data. |
| Fine-tuning | Excluded by default. Prohibit fine-tuning on licensed content or on synthetic outputs that contain or substantially derive from licensed content unless expressly purchased. | **[SPECIALIST COUNSEL REQUIRED - auditability]** Synthetic-data laundering is easy to ban and hard to detect. |
| Evaluation | Permit limited internal evaluation/benchmarking of buyer systems using small amounts of content if no licensed content is redistributed and public results are aggregate only. | Useful buyer concession with comparatively low publisher risk if capped. |
| Subscriber verification | Platform performs KYB, beneficial ownership checks as appropriate, sanctions screening, buyer category validation, and publisher-specific eligibility rules before credentials are issued. | **[SPECIALIST COUNSEL REQUIRED - sanctions/KYB/privacy]** Verification is one of the platform's few unavoidable operational responsibilities. |
| User authorization | Buyer warrants each retrieval is triggered by an authenticated end user or authorized enterprise workflow. Buyer may not use consumer subscription credentials, shared human accounts, or synthetic query farms. | **[SPECIALIST COUNSEL REQUIRED - CFAA/ToS]** The platform's authority must come from the publisher, not from an end user lending a personal subscription login. |
| Geographic restrictions | Publisher may restrict buyer jurisdiction, end-user jurisdiction, destination territory, and source availability. Platform enforces through account data, IP signals, contractual warranties, and geo-controls. | **[SPECIALIST COUNSEL REQUIRED - territorial rights/sanctions]** Geo-controls are imperfect; contracts should say this plainly. |
| Data residency | Support region-pinned storage, processing, cache, logs, and embeddings where required. Disclose subprocessors and processing regions. | **[SPECIALIST COUNSEL REQUIRED - GDPR transfers/localization]** EU-US DPF, SCCs, and transfer impact assessments need counsel; non-personal data may still carry contractual residency terms. |
| Privacy | Allocate controller/processor roles. Require lawful basis for disclosure of personal data, erasure/rectification propagation, no special categories in pilot, and buyer compliance with downstream privacy obligations. | **[SPECIALIST COUNSEL REQUIRED - whole privacy program]** News, court, sanctions, financial, and people datasets commonly contain personal data. |
| Rate limits | Per-publisher and per-buyer caps: QPS, monthly retrievals, per-user limits, catalog-fraction limits, burst rules, and hard stops after abuse. | Treat limits as license conditions; breach should trigger immediate suspension. |
| Authentication | Platform-issued credentials, OAuth2/client credentials or signed requests, scoped tokens, rotation, revocation, declared agent identity, no browser impersonation. | **[SPECIALIST COUNSEL REQUIRED - computer access]** Amazon v. Perplexity makes disguise and post-revocation access especially dangerous. |
| Security | Encryption in transit/at rest, tenant isolation, least privilege, logging, incident response, vulnerability management, SOC 2 roadmap, pen testing for higher tiers, and 72-hour incident notice where GDPR-aligned. | **[SPECIALIST COUNSEL REQUIRED - security/privacy]** Do not promise SOC 2 Type II before it exists; say "roadmap" if pre-audit. |
| Audit rights | Publishers receive a transaction ledger for their content. Platform may audit buyers directly or through an independent auditor for retention, embedding, attribution, and training restrictions. Publisher direct audits of buyers should be limited. | **[SPECIALIST COUNSEL REQUIRED - confidentiality/competition]** Audit sharing must not leak buyer confidential usage or cross-publisher competitive data. |
| Reporting | Monthly reports: usage, revenue, refunds, taxes withheld, attribution compliance samples, correction/takedown events, and incidents. Real-time ledger for publisher's own content. | Do not give publishers nonpublic competitor pricing or usage data of other publishers. |
| Pricing authority | Publisher sets list prices and permitted-use tiers. Platform may provide neutral tooling and public or aged/aggregated benchmarks. No cross-publisher price recommendations from nonpublic data. | **[SPECIALIST COUNSEL REQUIRED - antitrust]** RealPage is the warning: algorithmic price coordination using competitors' nonpublic data can be a core product defect. |
| Revenue splits | Platform fee as negotiated percentage of net transaction value, e.g. 10%-20% for pilot placeholders. Net means after refunds, payment processing, chargebacks, and taxes withheld where applicable. | **[SPECIALIST COUNSEL REQUIRED - antitrust/tax]** Avoid collective negotiation among publishers or common minimum prices. |
| Transaction fees | Micro-payments likely require prepaid credits, monthly invoicing, or a licensed payment partner. Avoid platform custody of pooled balances if possible. | **[SPECIALIST COUNSEL REQUIRED - money transmission]** Wallet/netting flows can trigger FinCEN and state money-transmitter regimes unless structured through a partner or exemption. |
| Refunds | Refund metering errors, paid non-delivery, duplicate charges, and materially nonconforming content. No refund for buyer dissatisfaction with lawful, delivered content unless service tier says otherwise. | Refund policy should flow through publisher payouts and tax adjustments. |
| Taxes | Address sales tax, VAT/GST, marketplace facilitator obligations, withholding, W-8/W-9 collection, 1099 reporting, and tax-inclusive/exclusive pricing. | **[SPECIALIST COUNSEL REQUIRED - tax]** Taxability of data/API subscriptions varies by state and country. |
| Minimum guarantees | Optional pilot guarantee paid to publisher, recoupable against usage. Keep small and time-boxed. | Inference: guarantees may be necessary for credible publishers but can hide weak demand. |
| SLAs | Pilot: 99.5% or 99.9% target availability, support response times, metering accuracy target, correction purge target, credits as sole remedy. Do not promise five-nines. | **[SPECIALIST COUNSEL REQUIRED - liability/SLA]** Publisher feed freshness needs its own SLA. |
| Corrections | Publisher can push corrections, retractions, takedowns, and rights changes. Platform propagates to cache/index within defined SLA; buyers must purge within a defined window. | **[SPECIALIST COUNSEL REQUIRED - defamation/privacy/copyright]** Corrections are crucial for news, court, financial, and health-adjacent data. |
| Warranties | Publisher warrants authority to license, no known infringement, lawful disclosure basis for personal data, and no malware. Platform warrants metering/security/service performance. Buyer warrants compliance with license, agent identity, and no credential misuse. Accuracy generally disclaimed unless expressly purchased. | **[SPECIALIST COUNSEL REQUIRED - warranties]** Accuracy disclaimers and marketing claims must match. |
| Indemnification | Publisher indemnifies for rights failures in content as delivered and used within scope. Buyer indemnifies for misuse, training, redistribution, credential misuse, and prohibited extraction. Platform indemnifies for platform security failures, metering/billing errors, and its own IP. | **[SPECIALIST COUNSEL REQUIRED - indemnity/insurance]** Small publishers may not support meaningful indemnity. Consider rights diligence and insurance. |
| Liability | Cap ordinary liability at fees paid/payable over prior 12 months. Consider higher caps for confidentiality, data protection, security, payment, and IP indemnity; exclude consequential damages where enforceable. | **[SPECIALIST COUNSEL REQUIRED - liability]** Some data-protection, consumer, fraud, and willful misconduct liabilities cannot be cleanly capped. |
| Exclusivity | Default nonexclusive. Avoid exclusive publisher lockups and collective boycotts. If needed, use narrow launch exclusivity by vertical, dataset, and time period. | **[SPECIALIST COUNSEL REQUIRED - competition/EU P2B]** Marketplace ranking and exclusivity can trigger competition-law scrutiny. |
| Termination | Convenience termination with 30-60 days' notice; immediate suspension for sanctions, security, nonpayment, credential misuse, training breach, bulk extraction, or legal risk. Limited runoff for existing buyer integrations if publisher agrees. | Termination should automatically revoke credentials and license grants. |
| Post-termination deletion | Buyer and platform delete licensed content, caches, indexes, and embeddings within 30 days unless legal recordkeeping requires retention. Officer deletion certificate for higher-risk tiers. Audit rights survive for 12 months. | **[SPECIALIST COUNSEL REQUIRED - privacy/IP/litigation hold]** Training rights, if ever granted, need a separate survival/deletion schedule. |

## 2. One-page pilot term sheet

> **Pilot Term Sheet - Agent Data Exchange - Nonbinding**  
> **Date:** 2026-07-15  
> **Parties:** [Platform], [Publisher], and separately enrolled [Buyer(s)]  
> **Purpose:** 90-day pilot for licensed machine retrieval, attribution, metering, and settlement for publisher-controlled content used by AI agents.

| Term | Pilot position |
| --- | --- |
| Licensed content | Named feeds/datasets only: [catalog IDs]. Excludes wire content, photos, UGC, third-party licensed material, and personal-data-heavy categories unless specifically cleared. **[SPECIALIST COUNSEL REQUIRED - rights clearance]** |
| Permitted uses | Search, retrieval, temporary context, task-specific summarization, limited quotation, attribution, and platform-hosted index/embedding if selected. |
| Excluded uses | Model training, fine-tuning, synthetic training data, resale, redistribution, bulk extraction, database reconstruction, buyer-hosted embeddings, and consumer-credential access. |
| Pilot buyers | Up to [5] named, KYB-verified agent developers or enterprises. No anonymous self-serve buyers. |
| Geography | [US only] or [US/EU/UK] depending on rights and privacy review. **[SPECIALIST COUNSEL REQUIRED - territorial rights/privacy]** |
| Pricing | Publisher-set placeholders: $0.005/search result, $0.02/retrieval, $0.05/premium retrieval. Final pilot rate card selected by publisher. |
| Platform fee | [15%] of net transaction value after refunds, chargebacks, processor fees, and taxes withheld. **[SPECIALIST COUNSEL REQUIRED - antitrust/tax]** |
| Minimum guarantee | $[10,000] recoupable against pilot usage, payable only if publisher meets feed/API/freshness obligations. |
| Payment structure | Monthly invoicing or payment partner-managed prepaid credits; no platform-held pooled wallet until money-transmission analysis is complete. **[SPECIALIST COUNSEL REQUIRED - payments]** |
| Attribution | Visible source, title/dataset, date/version, and link where UI supports links. Weekly attribution sampling. |
| Reporting | Real-time publisher ledger plus monthly statement: usage, revenue, refunds, taxes, incidents, purge events, buyer categories. |
| Retention | Content only for task duration plus 30-day restricted operational logs; cache TTL 24 hours; platform E1 embeddings only while pilot active. |
| Corrections/takedowns | Platform purge within 24 hours; buyer cache purge within 72 hours. Fire drill required during pilot. |
| SLA | Pilot target 99.5% availability; credits only; no consequential damages. |
| Warranties | Publisher rights/lawful-disclosure warranty; platform metering/security warranty; buyer compliance warranty. Accuracy disclaimed unless expressly marked verified. **[SPECIALIST COUNSEL REQUIRED - warranties]** |
| Indemnity/liability | Pilot caps: ordinary liability capped at fees paid/payable; IP/privacy/security carve-outs to be negotiated. **[SPECIALIST COUNSEL REQUIRED - indemnity/liability]** |
| Term | 90 days, 15-day convenience exit, immediate suspension for abuse/security/sanctions/legal risk. |
| Post-pilot | Convert to production, extend, or delete licensed artifacts within 30 days. No obligation to proceed. |
| Success criteria | At least [3] buyers integrate, attribution compliance above 98%, zero uncured security incidents, metering discrepancy below 1%, unit economics positive above payment/serving/compliance cost. |

## 3. Publisher agreement outline

**[SPECIALIST COUNSEL REQUIRED - whole agreement before signature]**

1. Parties, effective date, background, and nonexclusive nature.
2. Definitions: licensed content, dataset, endpoint, publisher data, buyer, agent application, task, answer, derived artifact, embedding, transaction, permitted use, excluded use.
3. Appointment of platform as limited commercial agent for license administration, access control, metering, reporting, billing support, and collections where legally structured.
4. Statement that publisher retains ownership and sets content scope, rights, restrictions, and prices.
5. Content catalog schedule: feeds, endpoints, URLs, tables, excluded rights, update cadence, takedown/correction path, metadata requirements.
6. License configuration: standard license tiers and custom licenses for named buyers.
7. Platform services: onboarding, KYB/sanctions screening, authentication, routing, metering, ledger, reporting, attribution sampling, audit coordination, support.
8. Publisher obligations: authority to license, accurate metadata, rights exclusions, API/feed uptime, correction/retraction notices, no malware, privacy disclosures where applicable.
9. Pricing: publisher-controlled rate card; platform fee; prohibition on platform-coordinated pricing using nonpublic competitor data. **[SPECIALIST COUNSEL REQUIRED - antitrust]**
10. Payments: collection structure, payment partner, payout timing, refunds, chargebacks, taxes, withholding, minimum payout, unclaimed funds. **[SPECIALIST COUNSEL REQUIRED - payments/tax]**
11. Data protection and security exhibit, including subprocessors, transfer terms, erasure propagation, and special-category exclusions. **[SPECIALIST COUNSEL REQUIRED - privacy/security]**
12. Audit and reporting: ledger rights, independent audit process, buyer audit coordination, confidentiality limits.
13. Warranties, disclaimers, indemnities, insurance, liability caps, and carve-outs. **[SPECIALIST COUNSEL REQUIRED - IP/liability]**
14. Confidentiality, marketplace analytics, restrictions on sharing nonpublic buyer or competing publisher data.
15. Suspension, term, termination, runoff, post-termination deletion, deletion certificates, survival.
16. Governing law, venue, dispute resolution, notices. **[SPECIALIST COUNSEL REQUIRED - jurisdiction]**
17. Schedules: content catalog, standard license text, rate card, DPA, security exhibit, attribution guide, SLA, support plan.

## 4. Buyer agreement outline

**[SPECIALIST COUNSEL REQUIRED - whole agreement before signature]**

1. Parties, account enrollment, KYB/sanctions screening, authorized users, and buyer products.
2. Definitions aligned with the publisher agreement and machine-readable license schema.
3. Access mechanics: platform credentials, signed requests, declared agent identity, no browser/person impersonation, no credential sharing.
4. License-per-transaction: the human-readable agreement and machine-readable license fields bind each retrieval; publisher terms may vary by dataset.
5. Permitted uses by tier: search, retrieval, temporary context, summarization, quotation, internal business use, evaluation, embeddings.
6. Universal restrictions: no model training, fine-tuning, resale, redistribution, database reconstruction, bulk extraction, synthetic-data laundering, circumvention, multi-accounting, or consumer credential lending.
7. Attribution and linking display obligations, including non-visual UI alternatives.
8. Retention/caching/deletion: TTLs, logs, answer history, deletion certificate, post-termination obligations.
9. Payments: invoicing, prepaid credits, payment partner terms, refunds, taxes, spend limits, suspension for nonpayment. **[SPECIALIST COUNSEL REQUIRED - payments/tax]**
10. Privacy and end-user data: buyer's controller obligations, lawful basis, notices, DSR cooperation, no special-category use unless separately approved. **[SPECIALIST COUNSEL REQUIRED - privacy]**
11. Security requirements by tier, incident notice, vulnerability management, key rotation.
12. Audit rights: platform or independent auditor may audit compliance with retention, embeddings, training restrictions, attribution, and rate-limit obligations.
13. Warranties, disclaimers, indemnity for out-of-scope use, liability caps, no consequential damages. **[SPECIALIST COUNSEL REQUIRED - liability]**
14. Suspension and termination, immediate revocation after material misuse or legal risk.
15. Governing law, venue, disputes, export/sanctions compliance. **[SPECIALIST COUNSEL REQUIRED - jurisdiction/sanctions]**

## 5. Data-processing addendum outline

**[SPECIALIST COUNSEL REQUIRED - entire DPA]**

1. **Roles.** Publisher is usually controller for personal data in source content; buyer is usually independent controller for retrieved content and downstream use; platform may be processor for routing/caching/metering and independent controller for account, billing, fraud, security, and transaction ledger data. Role mapping may change by dataset and jurisdiction.
2. **Processing description.** Subject matter, duration, nature, purpose, categories of data subjects, categories of personal data, special categories exclusion, and processing locations.
3. **Article 28 processor terms.** Documented instructions, confidentiality, security, subprocessor authorization, assistance with data-subject requests, breach notice, deletion/return, audit support.
4. **Lawful basis.** Publisher owns lawful basis for licensing disclosure; buyer owns lawful basis for retrieval and use; platform owns lawful basis for ledger/security/billing. Legitimate-interest reliance requires documented balancing analysis under EDPB Opinion 28/2024.
5. **Erasure and correction pipeline.** Publisher signals correction/erasure/takedown; platform purges caches, indexes, and embeddings; buyer purges its caches and downstream stores. Embeddings containing personal data are treated as in-scope unless counsel and technical evidence support anonymization.
6. **Transfers.** SCCs, UK IDTA/addendum if applicable, EU-US Data Privacy Framework where certified, transfer impact assessments, subprocessor regions, and data residency options.
7. **CCPA/CPRA and Delete Act.** Business/service-provider/third-party mapping; data-broker status analysis; DROP processing if in scope from 2026-08-01.
8. **Security annex.** Encryption, access controls, logging, tenant isolation, backup retention, incident response, key management, vulnerability management, pen testing, SOC 2 roadmap.
9. **Sensitive categories.** Pilot excludes PHI, consumer health data, children's data, biometric identifiers, precise geolocation, and regulated financial account data unless separately approved.
10. **Liability.** DPA breach cap or super-cap, regulatory cooperation, audit cost allocation, and indemnity.

## 6. Machine-readable license schema

The schema is illustrative and JSON-like. It should be reconciled with RSL 1.0, C2PA attribution/provenance, IPTC/TDM reservation signals, and any customer contract language before implementation.

```json
{
  "schema": "https://exchange.example/schemas/agent-content-license/v0.1",
  "license_id": "lic_20260715_example_001",
  "issued_at": "2026-07-15T00:00:00Z",
  "human_readable_terms_url": "https://exchange.example/licenses/lic_20260715_example_001",
  "rsl_compatible": true,
  "publisher": {
    "id": "pub_example_news",
    "legal_name": "Example News Co.",
    "rights_contact": "rights@example.com"
  },
  "buyer": {
    "id": "buy_example_agent",
    "legal_name": "Example Agent Inc.",
    "kyb_status": "verified",
    "allowed_products": ["example-agent-enterprise"]
  },
  "content_scope": {
    "catalog_ids": ["business_news_fulltext"],
    "endpoint_ids": ["api_articles_v2"],
    "url_patterns": ["https://example.com/business/*"],
    "excluded_categories": ["wire_content", "user_comments", "third_party_photos"],
    "version": "as_delivered",
    "territories": ["US", "EU", "UK"],
    "data_residency": {
      "required": false,
      "allowed_regions": ["us-east-1", "eu-central-1"]
    }
  },
  "permitted_uses": {
    "search": true,
    "indexing": "platform_hosted_only",
    "retrieval": true,
    "temporary_context": true,
    "summarization": {
      "allowed": true,
      "max_words": 200,
      "max_source_fraction": 0.25,
      "reuse_for_new_user": false
    },
    "quotation": {
      "allowed": true,
      "max_consecutive_words": 75,
      "max_quotes_per_answer": 2
    },
    "internal_business_use": false,
    "external_commercial_answers": true,
    "evaluation": {
      "allowed": true,
      "max_items_per_month": 1000,
      "aggregate_public_results_only": true
    },
    "full_display": false,
    "resale": false,
    "redistribution": false,
    "bulk_extraction": false,
    "database_reconstruction": false
  },
  "derived_artifacts": {
    "embeddings": {
      "tier": "E1",
      "holder": "platform_only",
      "buyer_hosted_allowed": false,
      "retention": "active_license_only",
      "delete_on_termination": true
    },
    "model_training": false,
    "fine_tuning": false,
    "synthetic_training_data_from_outputs": false
  },
  "retention": {
    "content_cache_ttl_hours": 24,
    "retrieved_document_ttl_hours": 0,
    "operational_log_days": 30,
    "answer_history_allowed": true,
    "post_termination_deletion_days": 30,
    "deletion_certificate_required": true
  },
  "attribution": {
    "required": true,
    "fields": ["source_name", "title", "published_at", "version", "canonical_url"],
    "display": "visible_citation_if_ui_supports",
    "link_required": true,
    "c2pa_manifest_available": false,
    "sponsored_source": false
  },
  "pricing": {
    "currency": "USD",
    "publisher_set": true,
    "model": "per_transaction",
    "rates": {
      "search_result": 0.005,
      "retrieval": 0.02,
      "premium_retrieval": 0.05
    },
    "platform_fee_pct": 15,
    "billing_method": "monthly_invoice_or_payment_partner_wallet"
  },
  "compliance": {
    "rate_limits": {
      "qps": 10,
      "monthly_retrieval_cap": 100000,
      "catalog_fraction_cap_pct": 5
    },
    "agent_identity": {
      "declared_user_agent_required": true,
      "signed_requests_required": true,
      "human_browser_impersonation_allowed": false
    },
    "audit": {
      "publisher_ledger": "realtime",
      "buyer_audit_by": "platform_or_independent_auditor"
    },
    "correction_purge": {
      "platform_hours": 24,
      "buyer_hours": 72
    },
    "privacy": {
      "personal_data_expected": "possible",
      "special_categories_allowed": false,
      "erasure_pipeline_required": true
    },
    "sanctions": {
      "screening_required": true,
      "blocked_jurisdictions": ["CU", "IR", "KP", "SY", "RU-sanctioned-regions"]
    }
  },
  "legal": {
    "governing_law": "placeholder_subject_to_counsel",
    "accuracy_warranty": "disclaimed_unless_verified_tier",
    "liability_cap": "12_months_fees_subject_to_carveouts",
    "specialist_counsel_required": [
      "IP rights",
      "privacy",
      "payments",
      "tax",
      "antitrust",
      "sanctions",
      "regulated verticals"
    ]
  }
}
```

## 7. 90-day pilot structure

### Phase 0 - Counsel and architecture gate (weeks -6 to 0)

- Rights diligence on the proposed publisher corpus, including third-party exclusions. **[SPECIALIST COUNSEL REQUIRED - IP]**
- Privacy role mapping, DPA, and decision on whether personal-data-heavy datasets are excluded. **[SPECIALIST COUNSEL REQUIRED - privacy]**
- Payment flow selection: invoice, licensed payment partner, agent-of-payee structure, or merchant-of-record structure. **[SPECIALIST COUNSEL REQUIRED - payments/tax]**
- Antitrust review of pricing screens, benchmark data, reporting, and any source-ranking economics. **[SPECIALIST COUNSEL REQUIRED - antitrust]**
- KYB/sanctions vendor selection and onboarding workflow. **[SPECIALIST COUNSEL REQUIRED - sanctions]**
- Build minimal ledger, attribution metadata, license schema, purge pipeline, and audit log.

### Phase 1 - Controlled E0 retrieval (days 1-30)

- Use search, retrieval, temporary context, summarization, quotation, and attribution only.
- No buyer-hosted embeddings; no model training; no fine-tuning.
- Daily reconciliation of platform ledger against publisher logs.
- Weekly attribution review.
- Confirm buyers can integrate without custom legal redlines for every dataset.

### Phase 2 - Add E1 platform-hosted index/embeddings (days 31-60)

- Add one opt-in publisher for platform-hosted embeddings.
- Run correction/retraction/erasure fire drill and measure purge times.
- Run simulated buyer audit focused on retention and training prohibition.
- Seed a metering error and test refund/clawback process.

### Phase 3 - Commercial proof (days 61-90)

- Let publishers adjust prices independently through controlled UI.
- Measure buyer willingness to pay, publisher payout satisfaction, latency, attribution compliance, and gross margin after serving/payment/compliance costs.
- Produce per-publisher pilot report and buyer integration report.

### Exit criteria

1. At least three buyers and three publishers want production terms.
2. Metering discrepancies below 1%.
3. Attribution compliance above 98%.
4. No unresolved IP, privacy, sanctions, or security incident.
5. Unit economics remain positive after payment processing, serving, support, reporting, and compliance overhead.
6. Counsel signs off on payment, privacy/data-broker, antitrust, and rights-clearance structure before public launch.

**Inference:** if the pilot only works with manual diligence, bespoke pricing, and human reconciliation, the product may still be a consultancy or vertical broker, but it is not yet a scalable exchange.

## Source appendix

Sources accessed by web search on 2026-07-15 unless otherwise noted.

1. TollBit, "Publisher Terms of Service" / Publisher Platform Agreement. https://tollbit.com/legal/publisher-platform-agreement/
2. TollBit Docs, "Licenses" (standard Summarization and Full Display licenses; no training). https://docs.tollbit.com/docs/standard-licenses
3. TollBit, "Licensed RAG access." https://tollbit.com/licensed-rag/
4. Microsoft Publisher Content Marketplace launch coverage, Search Engine Land, published 2026-02-03. https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191
5. The Verge, "Microsoft says it's building an app store for AI content licensing," published 2026-02-03. https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing
6. AWS Data Exchange / AWS Marketplace Data Subscription Agreement, standard terms. https://aws-mp-standard-contracts.s3.amazonaws.com/Data-Subscription-Agreement-for-AWS-Marketplace-2022-07-14.pdf
7. AWS Data Exchange User Guide, "Product subscriptions in AWS Data Exchange." https://docs.aws.amazon.com/data-exchange/latest/userguide/product-subscriptions.html
8. AWS Marketplace, "Standardized contracts." https://aws.amazon.com/marketplace/features/standardized-contracts
9. Snowflake Documentation, "Configure listings" (listing terms required; standard/custom/offline terms). https://docs.snowflake.com/en/collaboration/provider-listings-reference
10. Snowflake Documentation, "Legal requirements for consumers and providers." https://docs.snowflake.com/en/collaboration/collaboration-listings-legal
11. RSL, "Really Simple Licensing (RSL) 1.0 Specification." https://rslstandard.org/rsl
12. RSL, "RSL AI Licensing 1.0 Now an Official Industry Standard..." https://rslstandard.org/press/rsl-1-specification-2025
13. Cloudflare Blog, "Announcing the Monetization Gateway: charge for any resource behind Cloudflare via x402." https://blog.cloudflare.com/monetization-gateway/
14. DOJ, "Justice Department Requires RealPage to End the Sharing of Competitively Sensitive Information and Alignment of Pricing Among Competitors." https://www.justice.gov/opa/pr/justice-department-requires-realpage-end-sharing-competitively-sensitive-information-and
15. Federal Register, RealPage proposed final judgment notice, 91 Fed. Reg. issue 89, 2026-05-08. https://www.govinfo.gov/content/pkg/FR-2026-05-08/html/2026-09147.htm
16. California Privacy Protection Agency, "Information for Data Brokers." https://www.cppa.ca.gov/data_brokers/
17. California Privacy Protection Agency / privacy.ca.gov, "DROP for data brokers." https://privacy.ca.gov/drop-for-data-brokers/
18. EDPB, Opinion 28/2024 on certain data protection aspects related to AI models, adopted 2024-12-17. https://www.edpb.europa.eu/system/files/2024-12/edpb_opinion_202428_ai-models_en.pdf
19. European Commission, "The General-Purpose AI Code of Practice." https://digital-strategy.ec.europa.eu/en/policies/contents-code-gpai
20. ArtificialIntelligenceAct.eu, "Enforcement of Chapter V under the EU AI Act." https://artificialintelligenceact.eu/enforcement-of-chapter-v-under-the-eu-ai-act/
21. CyberScoop, "Appeals court temporarily pauses order blocking Perplexity's AI shopping agent on Amazon," 2026. https://cyberscoop.com/perplexity-comet-ai-shopping-agent-amazon-lawsuit-ninth-circuit-stay/
22. Jones Day, "Authorized by the User, Blocked by the Platform: Testing the Legal Limits of AI Agents," 2026-05. https://www.jonesday.com/en/insights/2026/05/authorized-by-the-user-blocked-by-the-platform-testing-the-legal-limits-of-ai-agents
23. Cooley, "Court Finds AI Agent May Violate State, Federal Law by Accessing Amazon Accounts Without Authorization," 2026-03-17. https://www.cooley.com/news/insight/2026/2026-03-17-court-finds-ai-agent-may-violate-state-federal-law-by-accessing-amazon-accounts-without-authorization
24. GOV.UK, "Report and impact assessment on Copyright and Artificial Intelligence," published 2026-03-18. https://www.gov.uk/government/publications/report-and-impact-assessment-on-copyright-and-artificial-intelligence
