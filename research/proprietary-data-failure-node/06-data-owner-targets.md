# Proprietary Data Owner Targets

**Research date:** 2026-07-16  
**Posture:** Skeptical supply-side target map; no invented partnerships.  
**Recommendation context:** **Pursue only through a narrow pilot.**

This document maps candidate proprietary-data owners and distribution channels for AI coding/automation failure-node resolution. The key question is not whether the data is valuable in general. The key question is whether the data owner can provide **least-privilege, task-scoped, agent-readable access** that improves a coding or automation workflow without leaking the underlying corpus.

Named organizations are **candidate targets only**. No partnership, resale right, integration, or licensing willingness is implied unless already publicly indicated by the owner through APIs, marketplace listings, MCP servers, or licensing programs.

## Priority definitions

- **High:** Strong relevance to the top-five pilot verticals and plausible task-level value.
- **Medium:** Valuable supply, but weaker coding-specific failure fit, harder rights posture, or less suitable for a 90-day pilot.
- **Low:** Useful as public baseline, future supply, or evidence source, but weak as first paid proprietary-data target.

**Broker-friendliness** is an inference. A high broker-friendly owner has public APIs, usage-based pricing, existing data-sharing posture, or incentive to reach agent workflows through intermediaries. A low broker-friendly owner likely prefers direct enterprise contracts, strict redistribution control, or its own AI product.

## Target table

| Data owner / channel | Data type | Agent relevance | Existing API/MCP / distribution posture | Licensing posture if known | Broker-friendliness | Priority | Risks |
| --- | --- | --- | --- | --- | --- | --- | --- |
| OpenSanctions | Sanctions, PEP, watchlists, entity reconciliation, structured statements | Very high for compliance/KYB coding agents that need entity screening, match evidence, and source provenance | Hosted API; yente open-source API; community MCP server noted in prior pack | Public materials include hosted screening API pricing and bulk/on-prem options; data includes public-source material with paid service layer | High | High | Premium buyers may require broader coverage, indemnity, adverse media, or commercial databases beyond OpenSanctions; some sources are public baselines rather than proprietary moats. |
| LSEG World-Check | Sanctions, PEP, adverse media, risk intelligence | Very high for KYB/KYC screening automation | Enterprise APIs/data feeds available through LSEG ecosystem | Direct enterprise licensing | Low-to-medium | High | Strong incumbent; likely prefers direct contracts; redistribution and audit requirements may limit broker resale. |
| Dow Jones Risk & Compliance | Sanctions, PEP, adverse media, state-owned company and risk data | Very high for compliance/KYB workflows needing authoritative adverse-media and risk context | Enterprise data/API products | Direct enterprise licensing | Low-to-medium | High | Expensive direct contracts, strict usage controls, potential overlap with buyer's existing compliance stack. |
| LexisNexis Risk Solutions | Identity, business, compliance, fraud, public-record, sanctions/risk datasets | High for KYB, fraud, identity, and compliance automations | Enterprise APIs and data products; LexisNexis also has legal/news/data products | Direct enterprise licensing; custom pricing typical | Low-to-medium | High | Broad incumbent with direct buyer relationships; privacy and permissible-purpose restrictions can be severe. |
| Moody's Orbis / Bureau van Dijk | Private-company, corporate hierarchy, beneficial ownership, financials | High for KYB, supplier-risk, private-company research, and ownership automation | Enterprise data products/APIs | Direct enterprise licensing | Low-to-medium | High | Strong dataset moat but low need for broker unless task-level agent access opens new usage. |
| Dun & Bradstreet | Company identity, D-U-N-S, firmographics, supplier and risk data | High for KYB, procurement, supplier-risk, and company-enrichment automations | Enterprise APIs/data products | Direct enterprise licensing | Medium-low | High | Buyers may already subscribe; redistribution and record caching restrictions can reduce task-level margin. |
| Optum / Change Healthcare | Claim edits, Real Claim Pre-Check-style validation, eligibility/benefits, payer policy, RCM transaction intelligence | Very high for healthcare RCM/claims edit automation | APIs and healthcare transaction network products noted in prior pack | Direct enterprise and healthcare-network licensing | Low | High | HIPAA/PHI, BAAs, payer contracts, security review, Optum concentration, and incumbent power make this the highest-value but highest-risk supply target. |
| AMA CPT | CPT code set, descriptors, clinical procedure terminology, licensing | High for claims coding, RCM automations, and clinical billing tools | CPT is licensed content; no known MCP in this research pack | Strict content licensing; permission required for use/redistribution | Low | High for healthcare; poor first supply target | Copyright/licensing limits, no obvious task-level resale posture, and need to combine with payer/CMS/edit data. |
| CMS NCCI / MUE / CMS claims-rule files | National Correct Coding Initiative edits, medically unlikely edits, public Medicare policy files | High as healthcare baseline and evaluation corpus | Public CMS downloads/files; not a proprietary paid API target in this thesis | Public caveat: useful baseline, not paid proprietary supply | High as baseline; low as paid supply | High baseline; Low paid target | Because much is public, it weakens willingness to pay unless the broker adds payer-specific proprietary rules, normalization, provenance, and coding-agent workflow integration. |
| X12 | Healthcare EDI transaction standards and implementation guides | High for coding agents implementing claims/eligibility transactions | Standards/specification distribution; no known MCP in this pack | Standards licensing/membership model | Low-to-medium | Medium-high | Standards text can be licensed, but many failures are integration/testing rather than missing proprietary data. |
| HL7 / FHIR ecosystem | Healthcare interoperability standards, profiles, implementation guides | Medium-high for healthcare integration automations | Public standards/docs and ecosystem APIs; no proprietary broker need for many cases | Mixed open/public plus implementation-specific licensing | Medium as public baseline; low as paid supply | Medium | FHIR docs are largely public and Context7-style retrieval can solve many failures; proprietary value is in payer/provider-specific rules. |
| ICC | Building codes, model codes, code content, code API | Very high for construction/building-code compliance automation | ICC Code Connect API noted in prior pack with OAuth2/JSON and licensing agreements | Direct implementation/content licensing | Medium | High | Code copyright, excerpt limits, direct API strategy, and local amendment coverage can limit broker role. |
| UpCodes | Building-code research, code access, AI/code-copilot style product | High for construction code-check workflows | Subscription product and AI copilot; public docs noted in prior pack | Direct subscription/licensing | Low-to-medium | High | May be competitor/supplier rather than data owner partner; broker must add agent workflow distribution or local data normalization. |
| Municode / CivicPlus-class ordinance publishers | Local codes, ordinances, municipal code repositories | High for building-code/local-government workflows | Web platforms and municipal-code distribution; API posture varies | Public/private municipal publishing contracts | Medium | Medium-high | Local code may be public but copyrighted/structured by publisher; coverage and API rights vary by municipality. |
| Local governments / permitting departments | Local amendments, permits, forms, workflows, inspection outcomes | High for construction and civic automation | Usually web portals, legacy systems, PDFs, case-management systems; APIs uneven | Public records plus local terms; procurement-controlled | Low-to-medium | Medium | Slow procurement, fragmented systems, privacy/public-record constraints, and weak technical interfaces. |
| UL / ICC-ES / ASTM / NFPA / ISO / IEC / IEEE standards bodies | Product approvals, safety standards, technical standards, certifications | Medium-high for construction, industrial, telecom, energy, and automotive automation | Standards stores, certification databases, some APIs/data feeds; no known MCP in this pack | Strict standards/content licensing | Low | Medium | Standards bodies protect text aggressively; task-level excerpts may be hard to license, and buyers may need human engineering judgment. |
| Freightos / WebCargo | Freight quotes, FBX data, air/ocean freight APIs, market updates | Very high for logistics rate/routing automation | APIs noted in prior pack for quotes, FBX, price stats, market updates | Direct API/data licensing | Medium | High | Buyer may already contract directly; rates are time-sensitive and can be reconstructed if extraction controls are weak. |
| DAT Freight & Analytics | Truckload rates, load board, lane benchmarks, freight analytics | High for logistics automation | Data/API posture exists through DAT products; exact MCP not reviewed here | Direct subscription/licensing | Low-to-medium | Medium-high | Strong incumbent with direct logistics buyer base; resale of lane benchmarks likely restricted. |
| FreightWaves SONAR | Freight market intelligence, rates, capacity, analytics | High for logistics rate/routing and market automation | Data platform/API posture exists through products; exact MCP not reviewed here | Direct subscription/licensing | Low-to-medium | Medium-high | Similar direct-channel and redistribution risks; broker must show agent-specific resolution lift. |
| project44 / FourKites-style visibility networks | Shipment visibility, carrier status, ETA, network telemetry | Medium for logistics exception automation | Enterprise APIs/platforms | Direct enterprise contracts | Low | Medium | Data is often buyer-specific operational telemetry, not externally purchasable general data. |
| PitchBook | Private-company, private-market, funding, investor, M&A data | High for private-company research and market-intel automations | Direct Data/API and Premium Connectors for enterprise LLMs noted in prior pack | Direct enterprise licensing | Low-to-medium | Medium-high | Already building enterprise LLM access; strong direct relationships and high pricing reduce broker margin. |
| CB Insights / Crunchbase-class providers | Private-company, funding, startup, market maps | Medium-high for private-company automation | APIs/data products vary by provider | Direct subscription/API licensing | Medium-low | Medium | Data quality, coverage, and licensing vary; web substitutes exist for shallow tasks. |
| Snowflake Cortex Knowledge Extension publishers | Licensed unstructured content distributed as Cortex Search Services through Snowflake Marketplace/private listings | Medium-high across legal, market intelligence, publishing, research, and enterprise AI apps | CKE distribution and content-protection thresholds noted in prior pack | Marketplace/private-listing licensing; content owner controls access | Medium-high as channel; medium as direct source | Medium-high | Snowflake may own distribution economics; not coding-agent-specific; buyer must already use Snowflake/Cortex or accept its stack. |
| Sphere publishers | Publisher/content-owner datasets for inference/RAG with attribution and usage tracking | Medium across publisher, research, market-intel, and legal-adjacent content | Sphere positions inference-time licensed access; no coding-specific failure detection | Per-use licensing controlled by publishers, per prior pack | High as supplier/channel; also competitor | Medium | Sphere is close to the licensing layer and may compete; content focus may not match vertical domain-rule workflows. |
| Reuters News Agency MCP | Licensed Reuters news content for subscribed customers | Medium for adverse-media, market-intel, and newsroom automations | Reuters MCP server for subscribed customers noted in prior pack | Subscription/customer entitlement required | Low as broker source; useful channel evidence | Medium | Direct subscribed-customer MCP weakens broker; news is often research/content, not coding failure resolution. |
| Thomson Reuters / Westlaw | Legal full text, citator, editorial treatment, legal research products, CoCounsel/AI products | Very high for legal citation-grounding automation | Enterprise products/APIs; Westlaw/CoCounsel ecosystem; Reuters MCP exists for news customers | Direct enterprise licensing | Low | High relevance; hard supply | Strong direct AI/legal products and strict licensing; low broker leverage unless buyer needs least-privilege task-level access across sources. |
| LexisNexis legal / Nexis Data+ | Legal, news, regulatory, company, compliance, and GenAI-ready datasets | Very high for legal/compliance/company-data automations | APIs and data products noted in prior pack | Direct/custom enterprise licensing | Low-to-medium | High relevance; hard supply | Broad incumbent with direct contracts; privacy/permissible-use restrictions and high pricing may limit margin. |
| Bloomberg Law / Bloomberg / S&P Global / FactSet / LSEG market data | Legal, financial, market, reference, corporate actions, filings, pricing and analytics | High for finance/legal/market-data automations | Mature APIs/data feeds/terminals | Direct enterprise licensing | Low | Medium-high but poor pilot | Very high data costs, direct buyer contracts, audit/redistribution restrictions, and long procurement cycles. |
| Wolters Kluwer | Tax, legal, compliance, healthcare clinical content, professional workflow data | Medium-high for tax/payroll, legal, healthcare, and compliance automation | Enterprise workflow/data products | Direct enterprise licensing | Low-to-medium | Medium-high | Strong incumbent with direct products; liability and content restrictions make task-level resale hard. |
| Elsevier / Scopus / ScienceDirect | Scientific literature, abstracts, citations, full-text content, research analytics | Medium for scientific research/lab automation | APIs/content platforms | Direct institutional licensing | Low-to-medium | Medium | Research workflow relevance is real, but coding-specific failure resolution is weaker; text-mining rights and redistribution are complex. |
| Clarivate Web of Science / Derwent | Citation indexes, research analytics, patents, scientific intelligence | Medium for research, patent, and pharma intelligence automation | APIs/data products | Direct institutional/enterprise licensing | Low-to-medium | Medium | Expensive direct contracts and long procurement; better suited to research agents than coding agents. |
| OpenAlex / Crossref / PubMed | Open scholarly metadata and biomedical literature baselines | Medium as baseline for research/science workflows | Public/open APIs | Public/open caveat, not proprietary paid supply | High as baseline; low paid target | Low paid; useful eval baseline | Strong free substitutes reduce paid-data wedge unless paired with licensed full text, protocols, or proprietary assay data. |
| CoreLogic / ATTOM / MLS / county-record aggregators | Property records, parcel data, valuations, MLS/comps, title/zoning-related data | Medium for real-estate automation | APIs/data feeds vary | Direct licensing; MLS rules can be restrictive | Medium-low | Medium | Fragmented rights, privacy/fair-housing concerns, MLS restrictions, and partly public records complicate resale. |
| Gordian RSMeans / Dodge Construction Network | Construction cost data, project leads, materials, labor benchmarks | Medium for construction estimating and market intelligence | Subscription/data products; API posture varies | Direct licensing | Low-to-medium | Medium | More estimating/market intelligence than building-code compliance; buyer may already subscribe. |
| ALLDATA / Mitchell / CCC / Solera-class automotive data owners | Repair procedures, estimating, labor times, parts, claims and collision data | Medium for automotive repair/fleet automation | Enterprise/subscription products and APIs vary | Direct licensing | Low-to-medium | Medium | OEM/content licensing restrictions and low per-task WTP; useful only for narrow repair/fitment pilots. |
| Experian / Equifax / TransUnion | Credit, identity, consumer/business risk data | Medium for finance/insurance/KYB workflows | Enterprise APIs/data products | Strict permissible-purpose licensing | Low | Low-to-medium first pilot | Privacy, FCRA/permissible purpose, adverse-action obligations, and compliance review make this poor for early agent pilots. |
| National company registries and public sanctions lists | Company filings, beneficial ownership where public, OFAC/UN/EU/UK sanctions lists | High as compliance baseline | Public websites/downloads/APIs vary | Public baseline caveat; not usually paid proprietary supply | High as baseline; low paid target | High baseline; low paid target | Essential for evals and free-substitute comparison; weak proof of brokerage economics unless combined with proprietary normalization/adverse media/entity resolution. |

## Best first supply configuration

The most plausible first supply configuration is **not** one premium incumbent contract. It is:

1. **One open or usage-priced compliance data provider** with clear API economics, such as OpenSanctions.
2. **One premium company/risk enrichment source** if obtainable under narrow, subject-bounded terms.
3. **A strict response contract:** return match evidence, provenance, version, permitted use, and confidence; do not return bulk source data.
4. **A labeled KYB task set** that compares public-list-only, direct provider API, and broker-routed minimal-access outcomes.

This supply stack has the highest chance of proving or falsifying the core thesis within 90 days because it avoids PHI, avoids codebook copyright fights, has measurable outputs, and supports per-query economics.

## Healthcare supply caution

Healthcare RCM data is the highest-value supply category but should probably be the **second** pilot, not the first, unless a buyer brings existing entitlements and synthetic/deidentified data. Optum/Change, AMA CPT, clearinghouses, payers, and payer-policy vendors are high-value but hard to broker. The pilot can be overwhelmed by HIPAA, PHI, BAAs, security review, payer contracts, and incumbent concentration before it tests the failure-node thesis.

If tested, the healthcare supply stack should separate:

- **Public baseline:** CMS NCCI/MUE and other CMS files.
- **Licensed code content:** AMA CPT and other controlled coding content.
- **Proprietary edit/policy source:** Optum/clearinghouse/payer-specific rules.
- **Buyer-owned data:** deidentified claims, denial histories, internal payer contracts, and workflow logs.

The broker should be paid only for resolving failures caused by externally licensed data, not for integrating the buyer's own claims warehouse.

## Construction supply caution

Construction/building-code data is attractive because privacy is low and objective citation checks are possible. The supply-side risk is copyright and local fragmentation. A first construction pilot should use:

- One model-code publisher or code API.
- One jurisdiction's adopted-code and amendment data.
- One building type or permit class.
- Section-scoped responses with no codebook export.

The broker should avoid claiming it can replace a code official or engineer. The product should provide authoritative citations and rule checks for coding/automation workflows, not final legal/engineering determinations.

## Legal supply caution

Legal data owners already understand AI licensing and many are building direct AI products. A broker may have a narrow opening in **citation validation** and **least-privilege source checks** inside coding-agent workflows, but broad legal research brokerage is likely to be internalized by legal publishers or sold directly through enterprise contracts.

## Data owners most likely to be broker-friendly

Relative broker-friendliness, by inference:

1. **OpenSanctions** - public API/pricing posture and agent/MCP-adjacent evidence.
2. **Snowflake CKE publishers** - existing marketplace/private-listing distribution with content protection, though Snowflake may own the channel.
3. **Sphere publishers** - per-use licensed inference posture, though Sphere may be a competitor.
4. **Freightos/WebCargo** - API-forward logistics data, but direct contracts likely.
5. **Municode/local ordinance publishers** - potentially brokerable if the broker solves normalization and demand aggregation.

Least broker-friendly but strategically important:

1. Optum/Change Healthcare
2. AMA CPT
3. Thomson Reuters/Westlaw
4. LSEG World-Check
5. Dow Jones Risk & Compliance
6. Bloomberg/S&P/FactSet/LSEG market data

These are valuable because their data is scarce. They are hard because scarcity gives them leverage.

## Evaluation questions for any data owner

Before signing a supply target, answer:

1. Can the owner license **agent use** explicitly, not just human UI use?
2. Can the answer be returned narrowly enough to avoid corpus leakage?
3. Can the owner provide source/version/provenance metadata?
4. Can the owner support per-query or per-resolution economics without enterprise minimums that kill the pilot?
5. Can the broker cache anything, and if so for how long?
6. Can outputs be stored in code comments, audit logs, tests, or generated reports?
7. Can the buyer's existing entitlement be checked before paying for new access?
8. Can the data owner's API support the latency and availability expectations of an agent workflow?
9. Is the data owner's brand/source authority part of the buyer value?
10. Would the data owner prefer to expose its own MCP/API directly and bypass the broker?

If the answer to question 10 is "yes" and the broker cannot bring distribution, measurement, or multi-source routing, the broker should not spend scarce pilot time on that owner.
