# 11 - Legal Risk Analysis

**Research date:** 2026-07-15  
**Posture:** Skeptical legal/commercial research for an AI agent proprietary-data licensing and routing platform.  
**Status:** Internal research memo. Not legal advice.

> This document is not legal advice. It summarizes public sources checked by web search on 2026-07-15 and draws commercial inferences for an AI agent data exchange. Litigation status can change quickly. Every item marked **[SPECIALIST COUNSEL REQUIRED]** requires specialist legal review before a pilot or production launch.  
> **Labeling rule:** **Verified/current guidance** means public source support was checked on 2026-07-15. **Inference** means a business/legal judgment based on that guidance, not a legal conclusion.

## 0. Executive view

The legal environment is favorable enough to justify a narrow licensed-access pilot, but not favorable enough to treat the model as de-risked.

**Verified/current guidance:** US courts and regulators are still split and unsettled on AI copyright and access issues. The Third Circuit heard argument in Thomson Reuters v. Ross on 2026-06-11 and has not yet issued a decision. Amazon obtained a district-court preliminary injunction against Perplexity's Comet agent in March 2026, but the Ninth Circuit stayed the injunction pending appeal. The EU AI Act's GPAI obligations are in force for new models, with Commission enforcement powers beginning 2026-08-02. The UK government published its March 2026 copyright/AI report without adopting a broad commercial TDM exception.

**Inference:** licensed API access is legally different from scraping or using consumer subscription credentials because it creates a direct authorization chain from rights holder to platform to buyer, attaches express machine-use terms, supports attribution and audit, and avoids the strongest computer-access fact patterns. That does not eliminate copyright, privacy, antitrust, payment, tax, or chain-of-title risk.

## 1. Copyright

### 1.1 United States

**Verified/current guidance:**

- **Thomson Reuters v. Ross Intelligence** is the most relevant US appellate matter for a professional-content AI/search product. The Third Circuit heard oral argument on 2026-06-11. The questioning reportedly focused on transformativeness and market harm, including whether Ross built a competing legal research tool and whether AI-training/data-licensing markets matter.
- **Bartz v. Anthropic** district-court proceedings and settlement materials distinguish lawful acquisition from pirated acquisition. Web search returned final-approval materials and court docket information; counsel should verify the docket before treating settlement finality as a legal fact.
- **NYT/OpenAI and publisher suits** remain central for output-side copying and alleged regurgitation, but no final appellate fair-use rule resolves AI training or retrieval.
- **Dow Jones/NYP v. Perplexity** places retrieval-augmented generation and answer substitution squarely at issue, but merits rulings remain pending.

**US risk assessment:** The platform should not rely on fair use as a product feature. Its commercial pitch is that buyers should prefer licensed retrieval over litigating fair use, especially where the buyer's product substitutes for the publisher or competes in the same information market.

**Inference:** the highest-risk US fact pattern is not "model trains on everything once." It is "agent retrieves or indexes a proprietary professional source to answer the same user need the source sells." That looks closer to Ross and publisher-vs-answer-engine litigation than to broad search indexing.

**[SPECIALIST COUNSEL REQUIRED - copyright/fair use]** for license scope, quotation limits, summarization, indexing, embeddings, model-training exclusions, and marketing claims about "safe" or "licensed" access.

### 1.2 European Union and Germany

**Verified/current guidance:**

- The EU DSM Directive permits commercial text and data mining under Article 4 only where there is lawful access and no effective rights reservation. Rights holders can reserve rights in machine-readable form.
- The EU AI Act requires GPAI model providers to adopt a policy to comply with EU copyright law and publish training-content summaries. The GPAI Code of Practice and related guidance make rights-reservation and provenance records commercially important.
- In **GEMA v. OpenAI** (Munich Regional Court I, 2025-11-11), the court held that memorized song lyrics in model parameters and near-verbatim outputs could infringe German copyright; OpenAI has appealed. The decision is first-instance and not final.

**EU risk assessment:** EU law is more favorable to rights-holder control than US law in several respects: database rights, machine-readable TDM opt-outs, and narrower fair-use-style flexibility. But the platform still needs explicit grants for copies, caches, indexes, summaries, outputs, and embeddings.

**Inference:** a licensed exchange is easier to explain in the EU than in the US because machine-readable reservations and lawful-access requirements fit the product narrative. The same EU framework also makes violations more dangerous: if a buyer exceeds the license, it may lose the TDM/lawful-access premise and face copyright, database, and privacy claims simultaneously.

**[SPECIALIST COUNSEL REQUIRED - EU copyright/TDM]** for RSL/TDM reservation handling, license terms for EU users, and any training/fine-tuning product.

### 1.3 United Kingdom

**Verified/current guidance:** the UK government's 2026-03-18 report did not adopt a broad commercial AI/TDM exception with opt-out. The existing UK position remains more licensing-dependent for commercial AI uses, subject to narrow statutory exceptions.

**Inference:** UK copyright policy currently supports a licensing-first commercial story, but policy remains unsettled and could change.

**[SPECIALIST COUNSEL REQUIRED - UK copyright]** before UK launch.

## 2. Database rights

### US

**Verified/current guidance:** under Feist, facts are not owned by anyone merely because they were compiled. The US lacks a sui generis database right. Factual and listings-heavy datasets are protected mainly by contract, trade secret where nonpublic, technical controls, and narrow unfair-competition theories.

**Risk:** if the platform licenses mostly facts, contract drafting and access controls carry the load. Overclaiming IP ownership in facts can create copyright-preemption risk.

### EU

**Verified/current guidance:** the Database Directive protects substantial investment in obtaining, verifying, or presenting database contents and prohibits extraction/re-utilization of substantial parts and repeated systematic extraction of insubstantial parts.

**Risk:** EU database law strengthens publisher claims against unlicensed systematic extraction, but it also means the platform must define extraction, re-utilization, caching, indexing, and reconstruction with precision.

**[SPECIALIST COUNSEL REQUIRED - database rights]** for any EU data product, especially financial, sports, travel, legal, market, real-estate, or people-data datasets.

## 3. Contract law, ToS, and scraping restrictions

**Verified/current guidance:** US scraping law remains a patchwork. Public-web scraping is not automatically a CFAA violation after hiQ/Van Buren-style reasoning, but account-gated access, post-cease-and-desist access, circumvention, and signed contract breach are much more dangerous. Bright Data cases show that platforms may lose broad scraping claims if terms are ambiguous or if they try to control public data they do not own.

**Risk for the exchange:** the exchange must avoid being a "scrape it anyway" service. It should route only to participating publishers or sources where the platform has legal access. Signed API terms, scoped credentials, revocation, and audit logs matter.

**Inference:** publisher ToS alone are a weak foundation for monetization. The platform's value is converting weak or ambiguous browsewrap constraints into express, authenticated, machine-use licenses.

**[SPECIALIST COUNSEL REQUIRED - contracts/computer access]** for ToS design, revocation mechanics, API terms, and anti-circumvention language.

## 4. Unauthorized account use and computer-access laws

**Verified/current guidance:** Amazon v. Perplexity is the most on-point agent-access case found by web search. A district court granted Amazon a preliminary injunction in March 2026, finding likely CFAA and California computer-access violations where Perplexity's agent allegedly accessed password-protected Amazon areas with user permission but without Amazon authorization, allegedly disguised itself, and allegedly continued after demands to stop. The Ninth Circuit stayed the injunction pending appeal.

**US risk:** CFAA exposure turns on authorization, gates, revocation, loss, and conduct. State laws such as California Penal Code section 502 can be broader. Criminal and civil theories can coexist.

**EU/UK risk:** EU member-state computer misuse laws and the UK Computer Misuse Act can apply to unauthorized access and circumvention, often without the same US damages threshold debates.

**Inference:** user permission is not enough if the system owner prohibits third-party automated access and revokes authorization. This is the strongest legal reason for an exchange to reject "bring your consumer subscription login" designs.

**[SPECIALIST COUNSEL REQUIRED - CFAA/state computer laws/international computer misuse]** before supporting agents that access third-party accounts, subscriptions, paywalls, or websites outside publisher-issued credentials.

## 5. Why licensed API access differs from scraping via consumer subscription

| Dimension | Licensed API access | Scraping or agent access via consumer subscription |
| --- | --- | --- |
| Authorization chain | Publisher expressly authorizes platform and buyer for machine access. | End user has personal access; agent provider usually lacks publisher authorization. |
| Contract assent | Buyer signs API/platform terms; scope is explicit. | Consumer ToS often prohibit credential sharing, automation, commercial use, or scraping. |
| Computer-access risk | Access credentials are issued by system owner and revocable under contract. | Post-revocation or disguised access can trigger CFAA/state-law claims. |
| Copyright/retrieval copies | Copies, summaries, quotes, caches, and indexes are licensed. | Each copy/output needs fair-use or other defense. |
| EU database rights | Extraction/re-utilization is authorized within license. | Systematic extraction may infringe database rights. |
| Privacy and audit | Parties can allocate controller/processor roles and deletion duties. | Data flows through personal accounts with poor auditability and unclear lawful basis. |
| Attribution and provenance | Metadata can travel with each response. | Scraped answers often strip attribution and rights metadata. |
| Insurance/procurement | Contracted, ledgered, and auditable; easier to insure. | Hard to insure because access authority is disputed. |

**Inference:** licensed API access turns legal risk into priced contractual risk. Scraping through consumer subscriptions leaves risk unpriced, uncertain, and injunction-prone.

## 6. Privacy and personal data

### 6.1 GDPR

**Verified/current guidance:** EDPB Opinion 28/2024 says AI models are not automatically anonymous; anonymity depends on whether personal data can be extracted or obtained through queries by reasonably likely means. Legitimate interest can be a lawful basis only after a documented three-part test: legitimate interest, necessity, and balancing.

**Risk:** news archives, court records, sanctions records, people intelligence, company data, health-adjacent content, and financial data often contain personal data. Routing, caching, indexing, embeddings, logs, and buyer answer histories can each become separate processing operations.

**EU comparison:** GDPR is materially stricter than typical US privacy law because it requires a lawful basis, transparency, data minimization, transfer controls, processor contracts, and enforceable rights such as erasure and access.

**Embeddings risk:** If an embedding store can be linked to or used to retrieve personal data, treat it as personal data unless counsel and technical evidence support anonymization.

**[SPECIALIST COUNSEL REQUIRED - GDPR/DPA/transfers]** for role mapping, lawful basis, Article 14 transparency, SCCs/DPF, erasure-to-embeddings, and subprocessor terms.

### 6.2 US privacy and CCPA/Delete Act

**Verified/current guidance:** California's Delete Act DROP system is live for consumers in 2026, and data brokers must begin processing DROP deletion requests on 2026-08-01. Penalties can be $200 per deletion request per day for failures, plus costs. Registration penalties also apply.

**Risk:** a platform that knowingly collects and sells personal information of consumers with whom it lacks a direct relationship may be a data broker, depending on data categories and exemptions. People-data and enrichment datasets are high risk. News archives are more nuanced but cannot be ignored.

**[SPECIALIST COUNSEL REQUIRED - CCPA/data broker]** before onboarding any dataset containing California personal information, people profiles, contact data, location, household, health, financial, or inference data.

## 7. Consumer protection and advertising disclosure

**US risk:** FTC Act Section 5, state UDAP laws, endorsement/native advertising rules, and AI-accuracy enforcement can apply if agent answers present paid, sponsored, or preferentially ranked sources without disclosure. If the platform markets licensed content as "verified," "accurate," or "trusted," those claims need substantiation.

**EU risk:** the Unfair Commercial Practices Directive and national consumer laws can require disclosure of material commercial influence and prohibit misleading claims.

**Inference:** sponsored discovery is legally riskier than transaction fees. If publishers can pay for placement or discounted rates affect ranking, the machine-readable license must carry a sponsored/material-connection field.

**[SPECIALIST COUNSEL REQUIRED - consumer protection/advertising]** for any paid ranking, sponsored source placement, or accuracy claim.

## 8. Competition law

**Verified/current guidance:** DOJ's RealPage enforcement and 2026 consent-judgment materials target algorithmic coordination and use of competitors' nonpublic competitively sensitive data in pricing tools.

**US risk:** an exchange has hub-and-spoke risk if it pools nonpublic publisher prices, sell-through, revenue, or demand data and uses it to recommend prices to competing publishers. It also risks facilitating collective boycotts if publishers coordinate refusals to license to particular AI buyers.

**EU risk:** Article 101 TFEU, national competition law, and platform fairness regimes can apply. The EU P2B Regulation can require transparent terms, ranking explanations, notice for changes, complaints handling, and disclosure of differentiated treatment.

**Inference:** antitrust risk is self-inflicted. The business can avoid much of it by making publishers set prices independently, using only public or sufficiently aggregated/aged benchmarks, separating confidential data, and documenting no price coordination.

**[SPECIALIST COUNSEL REQUIRED - antitrust/competition]** before building pricing recommendations, category benchmarks, dynamic pricing, publisher councils, ranking incentives, exclusivity, or collective negotiation features.

## 9. Payment regulation and money transmission

**Verified/current guidance:** payment-processor and agent-of-payee exemptions are real but narrow and fact-specific. Platforms that hold pooled funds, prepaid balances, or buyer credits before paying sellers may trigger FinCEN MSB and state money-transmitter licensing analysis. State-by-state treatment varies.

**Risk:** micro-transaction content licensing pushes toward prepaid credits or wallets, which is exactly where money-transmission risk appears.

**Safer structures to evaluate:**

1. Monthly invoicing with ordinary accounts receivable.
2. Licensed payment partner such as a marketplace/payment facilitator product where funds sit with the regulated partner.
3. Agent-of-payee structure with written publisher appointment, public notice, and buyer obligation discharged upon payment to agent, if available by state.
4. Merchant-of-record/reseller model, which may reduce money-transmission risk but increases IP, tax, and liability exposure because the platform becomes principal.

**[SPECIALIST COUNSEL REQUIRED - payments/FinCEN/state MTL]** before prepaid wallet, credit balance, netting, stored value, stablecoin, x402, or publisher-payout launch.

## 10. Taxes

**US risk:** data/API licenses may be taxable in some states and not others. Marketplace facilitator obligations, economic nexus, local taxes, exemptions, and characterization as SaaS/digital goods/data services vary. Payout reporting may require W-9/W-8 collection and 1099 treatment; non-US publisher withholding may apply if payments are royalties.

**EU/UK risk:** B2B electronically supplied services usually require VAT ID validation and reverse charge handling; B2C would create OSS/MOSS-style complexity. Marketplace deemed-supplier rules should be reviewed before any consumer product.

**[SPECIALIST COUNSEL REQUIRED - tax]** for rate determination, tax-inclusive pricing, publisher payouts, withholding, VAT/GST, invoices, and refund tax adjustments.

## 11. Healthcare and HIPAA

**US risk:** if PHI is involved, HIPAA business-associate agreements, permitted-use restrictions, de-identification standards, breach rules, and state health privacy laws become central. Washington My Health My Data and other state laws can reach consumer health data outside classic HIPAA.

**EU risk:** health data is special-category data under GDPR Article 9 and requires stricter conditions.

**Inference:** healthcare data is a bad first vertical unless the product is intentionally built as a regulated-health-data exchange.

**[SPECIALIST COUNSEL REQUIRED - healthcare/privacy]**. Launch rule: exclude PHI, consumer health data, clinical notes, claims data, genetic data, and wellness profiles from the general pilot.

## 12. Financial-data regulation

**Risk:** market data and investment research carry strict redistribution, display/non-display, per-user, derived-data, audit, and exchange/vendor licensing terms. Real-time quotes, benchmarks, ratings, and research summaries can trigger vendor-of-record requirements and expensive audits.

**US/EU comparison:** both US and EU financial-data regimes are contract-heavy, but EU financial services rules and MiFID II research/payment issues can add complexity for investment research.

**Inference:** financial data has strong agent demand but poor first-pilot fit unless supplied by a vendor that already has redistribution rights and audit workflows.

**[SPECIALIST COUNSEL REQUIRED - market data/financial regulation]** before any market data, ratings, investment research, portfolio analytics, credit, KYC, AML, or personalized financial advice use case.

## 13. Data localization, export controls, and sanctions

**Risk:** some jurisdictions require data localization for personal, public-sector, financial, or strategic data. Sanctions screening is strict liability in the US and can also apply under EU/UK regimes. Datasets may contain controlled technical data or export-sensitive information.

**Controls:** screen publishers, buyers, beneficial owners, banks, and high-risk end users; block sanctioned territories; monitor the 50 percent ownership rule; include export-control warranties; maintain audit logs.

**[SPECIALIST COUNSEL REQUIRED - sanctions/export/localization]** before cross-border launch, government/defense/technical datasets, or global self-serve onboarding.

## 14. Model-training rights, derivative works, and fair use

**Training rights:** exclude by default. If sold, price separately, define model snapshots, covered model families, retention, audit, output controls, and survival after termination.

**Derivative works:** summaries, translations, structured extracts, and synthesized answers may implicate derivative-work or reproduction rights depending on content, jurisdiction, amount taken, and market substitution.

**Embeddings/indexes:** legally unsettled. They may be argued to be non-expressive metadata, but they can also enable semantic reconstruction, search, or extraction of value from the corpus. Under GDPR, embeddings may be personal data if personal data can be linked, inferred, or extracted.

**Fair use:** in the US, fair use is the buyer's alternative to paying. That caps pricing power. If appellate law becomes more favorable to AI defendants, willingness to pay falls. If Ross-like market-substitution reasoning is affirmed, licensing demand rises.

**[SPECIALIST COUNSEL REQUIRED - AI/IP/privacy]** for training, fine-tuning, synthetic data, embeddings, generated answers, and output reuse.

## 15. Liability for inaccurate data

**Risk:** data may be wrong, stale, defamatory, incomplete, biased, or unsuitable for a buyer's task. Contracts can disclaim accuracy and consequential damages between platform, publisher, and buyer, but end users and regulators may not respect those boundaries if marketing promises reliability.

**US:** negligent misrepresentation, product-liability analogies, professional reliance, defamation, credit/consumer-reporting, and sector-specific duties can arise depending on data and use.

**EU:** national tort law, consumer law, GDPR accuracy obligations, and the revised Product Liability Directive's software/AI orientation can raise risk, especially for high-impact uses.

**Inference:** the platform should sell "licensed provenance and auditability," not "truth." A "verified data" tier is commercially attractive but increases duty.

**[SPECIALIST COUNSEL REQUIRED - liability/consumer/sector]** before accuracy warranties, verified badges, ranking by reliability, or regulated-decision use cases.

## 16. Existential legal risks

### 1. Adverse appellate law collapses buyer willingness to pay

**Risk:** if the Third Circuit reverses Ross in a way that strongly blesses market-substituting AI uses, and the Ninth Circuit blesses user-delegated agent access to gated consumer accounts, buyers may conclude licenses are optional for many use cases.

**Why existential:** the business depends on buyers preferring licensed access over scraping, fair use, and user-credential delegation.

**Status:** **Inference**; probability uncertain; impact high.

### 2. Chain-of-title failure

**Risk:** publishers may license content they do not fully control: wire services, freelancers, photos, UGC, syndicated columns, court filings with restrictions, data collected under upstream ToS, or datasets with personal-data limits.

**Why existential:** one high-profile rights failure can destroy the core promise that "licensed means safe."

**Mitigation:** catalog diligence, exclusions, metadata flags, publisher warranties, indemnity, insurance, takedown pipeline, and limiting launch to sources with clean rights.

### 3. Antitrust design defect

**Risk:** pricing tools or marketplace reports use nonpublic cross-publisher data to recommend or align prices, or the platform becomes a hub for publisher coordination against AI buyers.

**Why existential:** the risky feature could sit at the center of the marketplace, not at the edge. RealPage-style theories bring DOJ/state scrutiny and treble-damages private litigation.

**Mitigation:** publisher-set prices, no nonpublic competitor-data recommendations, aged/aggregated benchmarks only, antitrust review before launch.

### 4. Payment structure illegally holds customer funds

**Risk:** prepaid buyer balances and monthly publisher settlement create money-transmission or stored-value exposure.

**Why existential-adjacent:** solvable with a payment partner or carefully structured agent-of-payee model, but a wrong launch can trigger enforcement, refunds, and shutdown of payments.

### 5. Personal-data/data-broker obligations ignored until scale

**Risk:** the platform brokers personal-data-heavy datasets and fails to build GDPR erasure, CCPA/Delete Act, broker registration, and downstream deletion pipelines.

**Why existential-adjacent:** the risk compounds by number of data subjects and retained artifacts. California DROP penalties can scale rapidly after 2026-08-01.

### 6. Product enters regulated verticals accidentally

**Risk:** buyers use general data access for healthcare, financial advice, credit, employment, insurance, sanctions, or other regulated decisions.

**Why serious:** the buyer may be primarily regulated, but the platform can inherit contractual, reputational, privacy, and consumer-protection exposure.

## 17. Manageable risks if designed early

1. **Taxes:** painful but operational with tax engine, tax counsel, W-8/W-9, VAT ID validation, and clean invoices.
2. **Sanctions/KYB:** commodity tooling exists; failure is mostly operational discipline.
3. **Security:** serious but manageable with narrow pilot scope, tenant isolation, logs, incident process, and no overclaimed certifications.
4. **DPA mechanics:** manageable for low-personal-data datasets; much harder for people-data.
5. **Attribution compliance:** technically manageable if response metadata is mandatory and buyer audits are real.
6. **Correction/takedown propagation:** manageable if built into the API from day one; difficult if retrofitted.

## 18. Bottom line

**Inference:** the legal thesis for a licensed agent data exchange is credible but fragile. Its strongest argument is not that scraping is always illegal; it is that signed, publisher-authorized, audited, machine-readable API access is lower-risk and more procurement-friendly than contested scraping, consumer-credential delegation, and fair-use litigation.

The first pilot should avoid:

- model training and fine-tuning;
- buyer-hosted embeddings;
- PHI and consumer health data;
- real-time market data;
- people-data enrichment;
- paid source ranking;
- prepaid wallets not controlled by a regulated payments partner;
- any source without clean rights.

The first pilot should require:

- direct publisher authorization;
- scoped credentials;
- visible attribution;
- correction/deletion pipeline;
- publisher-set prices;
- antitrust-reviewed reporting;
- payment partner or invoice structure;
- counsel-reviewed DPA and rights schedule.

## Source appendix

Sources accessed by web search on 2026-07-15 unless otherwise noted.

1. LawSites, "At 3rd Circuit, Judges Press ROSS and Thomson Reuters on Fair Use, AI Training and Market Harm," 2026-06. https://www.lawnext.com/2026/06/at-3rd-circuit-judges-press-ross-and-thomson-reuters-on-fair-use-ai-training-and-market-harm.html
2. Baker Botts / JDSupra, "Third Circuit Hears Oral Argument in Ross v. Reuters AI Training Copyright Case," 2026. https://www.jdsupra.com/legalnews/third-circuit-hears-oral-argument-in-7977892/
3. Stevens & Lee, "Third Circuit Poised to Decide Whether Training an AI Model on Copyrighted Content Is Fair Use," 2026. https://www.stevenslee.com/appellate/third-circuit-poised-to-decide-whether-training-an-ai-model-on-copyrighted-content-is-fair-use/
4. Northern District of California, Bartz et al. v. Anthropic PBC case page. https://cand.uscourts.gov/cases-e-filing/cases/324-cv-05417-amo/bartz-et-al-v-anthropic-pbc
5. CourtListener, Bartz v. Anthropic proposed final approval order materials. https://storage.courtlistener.com/recap/gov.uscourts.cand.434709/gov.uscourts.cand.434709.621.0_1.pdf
6. CyberScoop, "Appeals court temporarily pauses order blocking Perplexity's AI shopping agent on Amazon," 2026. https://cyberscoop.com/perplexity-comet-ai-shopping-agent-amazon-lawsuit-ninth-circuit-stay/
7. GeekWire, "Judge blocks Perplexity's AI bot from shopping on Amazon in early test of agentic commerce," 2026. https://www.geekwire.com/2026/judge-blocks-perplexitys-ai-bot-from-shopping-on-amazon-in-early-test-of-agentic-commerce/
8. Jones Day, "Authorized by the User, Blocked by the Platform: Testing the Legal Limits of AI Agents," 2026-05. https://www.jonesday.com/en/insights/2026/05/authorized-by-the-user-blocked-by-the-platform-testing-the-legal-limits-of-ai-agents
9. Cooley, "Court Finds AI Agent May Violate State, Federal Law by Accessing Amazon Accounts Without Authorization," 2026-03-17. https://www.cooley.com/news/insight/2026/2026-03-17-court-finds-ai-agent-may-violate-state-federal-law-by-accessing-amazon-accounts-without-authorization
10. Justia, Amazon.com Services, LLC v. Perplexity AI, Inc., Ninth Circuit docket 26-1444. https://dockets.justia.com/docket/circuit-courts/ca9/26-1444
11. European Commission, "The General-Purpose AI Code of Practice." https://digital-strategy.ec.europa.eu/en/policies/contents-code-gpai
12. ArtificialIntelligenceAct.eu, "Enforcement of Chapter V under the EU AI Act." https://artificialintelligenceact.eu/enforcement-of-chapter-v-under-the-eu-ai-act/
13. Latham & Watkins, "EU AI Act GPAI Model Obligations in Force and Final GPAI Code of Practice in Place." https://www.lw.com/en/insights/eu-ai-act-gpai-model-obligations-in-force-and-final-gpai-code-of-practice-in-place
14. EDPB, Opinion 28/2024 on certain data protection aspects related to processing personal data in AI models, adopted 2024-12-17. https://www.edpb.europa.eu/system/files/2024-12/edpb_opinion_202428_ai-models_en.pdf
15. IAPP, "EDPB weighs in on key questions on personal data in AI models," 2024-12. https://iapp.org/news/a/edpb-weighs-in-on-key-questions-on-personal-data-in-ai-models
16. DOJ, "Justice Department Requires RealPage to End the Sharing of Competitively Sensitive Information and Alignment of Pricing Among Competitors," 2025/2026 materials. https://www.justice.gov/opa/pr/justice-department-requires-realpage-end-sharing-competitively-sensitive-information-and
17. Federal Register, RealPage final-judgment notice, 2026-05-08. https://www.govinfo.gov/content/pkg/FR-2026-05-08/html/2026-09147.htm
18. DOJ, RealPage settlement agreement/final-judgment materials. https://www.justice.gov/opa/media/1419406/dl
19. California Privacy Protection Agency, "Information for Data Brokers." https://www.cppa.ca.gov/data_brokers/
20. privacy.ca.gov, "DROP for data brokers." https://privacy.ca.gov/drop-for-data-brokers/
21. Fenwick, "Don't DROP the Ball on Upcoming Changes to the California Delete Act," 2026. https://www.fenwick.com/insights/publication/dont-drop-ball-upcoming-changes-california-delete-act-five-key-steps-companies
22. GOV.UK, "Report and impact assessment on Copyright and Artificial Intelligence," published 2026-03-18. https://www.gov.uk/government/publications/report-and-impact-assessment-on-copyright-and-artificial-intelligence
23. Reed Smith, "UK copyright and AI report: the opt-out is dead, but what comes next?" 2026. https://www.reedsmith.com/articles/uk-copyright-and-ai-report-the-opt-out-is-dead-but-what-comes-next/
24. AI Lawsuit Tracker, "GEMA v. OpenAI: Case Status May 2026." https://ailawsuittracker.com/cases/gema-v-openai/
25. Osborne Clarke, "GEMA vs. OpenAI: AI memorisation is a reproduction relevant to copyright law..." 2025/2026. https://www.osborneclarke.com/insights/gema-vs-openai-ai-memorisation-reproduction-relevant-copyright-law-and-tdm-exception-does
26. CMS, "GEMA vs. OpenAI: Munich Regional Court I issues landmark copyright decision," 2025-11. https://cms.law/en/deu/legal-updates/gema-vs.-openai-munich-regional-court-i-issues-landmark-copyright-decision
27. RSL, "Really Simple Licensing (RSL) 1.0 Specification." https://rslstandard.org/rsl
28. RSL, "RSL AI Licensing 1.0 Now an Official Industry Standard..." https://rslstandard.org/press/rsl-1-specification-2025
29. TollBit Docs, "Licenses." https://docs.tollbit.com/docs/standard-licenses
30. Microsoft Publisher Content Marketplace coverage, Search Engine Land, 2026-02-03. https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191
31. AWS Data Exchange standard Data Subscription Agreement. https://aws-mp-standard-contracts.s3.amazonaws.com/Data-Subscription-Agreement-for-AWS-Marketplace-2022-07-14.pdf
32. Snowflake Documentation, "Configure listings." https://docs.snowflake.com/en/collaboration/provider-listings-reference
