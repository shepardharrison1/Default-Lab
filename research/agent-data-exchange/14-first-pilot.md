# 14 - First Pilot Recommendation

**Date:** 2026-07-15  
**Recommendation:** Run a narrow compliance pilot: route Zip-style supplier-onboarding AI agents to OpenSanctions for sanctions/PEP/watchlist screening through a governed MCP/API wrapper.  
**Important caveat:** Zip is named as the recommended buyer target because its public product pages describe AI supplier onboarding, OFAC/D&B/bank-account checks, risk agents, and audit trails. This file does **not** claim Zip has agreed to participate.

## Pilot one-liner

**Buyer target:** Zip Risk Orchestration / Supplier Onboarding. **Rights holder:** OpenSanctions Datenbanken GmbH. **Workflow:** supplier onboarding agent screens new vendors and beneficial owners against OpenSanctions via API/MCP, logs evidence, and escalates ambiguous matches to a human reviewer.

## Why this pilot, not a flashier one?

Compliance is not the biggest TAM, but it is the cleanest test of the agent-data-exchange concept:

- A real buyer workflow exists: Zip publicly markets AI supplier onboarding, Supplier 360 agents, automated supplier assessment, OFAC/D&B/bank-account checks, risk scoring, and audit trails.
- A real rights holder exists: OpenSanctions publishes commercial licensing, hosted API metering, bulk/reseller options, and `yente-client`/MCP integration.
- A repeated information failure exists: sanctions and PEP screening generate high false-positive burden when names are matched without enough context; vendor screening should happen in procurement workflows before contract/payment, not as a manual afterthought.
- The pilot can be measured in weeks because the dataset, price, endpoints, and MCP path are public.

The skeptical reading is equally important: because OpenSanctions already has public metering and MCP support, the pilot will not prove that the exchange can unlock inaccessible data. It will prove, at most, that agent applications value a managed entitlement/audit/billing layer over going direct.

## Pilot design

### Buyer

- **Named buyer target:** Zip, specifically Risk Orchestration and Supplier Onboarding.
- **Evidence:** Zip's public pages state that it uses AI agents for supplier-risk workflows, including Supplier 360, automated risk scoring, AI-powered supplier assessment, OFAC, D&B, TIN, VAT, and bank-account checks, with complete audit trails.
- **No invented relationship:** This is an outreach target and pilot design, not a confirmed buyer or partnership.

### Agent workflow

1. A requester submits a new vendor or supplier intake in Zip.
2. The supplier-onboarding agent extracts structured attributes: legal name, trade names, country, registration number, website, address, known owners/officers, and bank-country signals.
3. The agent calls the exchange's `screen_counterparty` tool.
4. The exchange maps the call to OpenSanctions `/match`; optional `/entities` calls retrieve full profile details for likely candidates.
5. The agent returns:
   - match/no-match status;
   - score and matching fields;
   - source watchlist;
   - whether the entity is sanctioned, PEP, watchlist-listed, or linked;
   - evidence URL/entity ID;
   - recommended action: clear, ask supplier for more identifiers, or escalate.
6. The exchange stores usage, buyer entitlement, source version, response metadata, and audit logs. It does not store sensitive supplier documents beyond the minimum needed for audit unless contractually required.

### Repeated information failure

The recurring failure is not that agents cannot find "OFAC list" on the open web. They can. The failure is that procurement agents need current, normalized, multi-source, alias-aware matching with evidence, and they need it inside the procurement workflow with audit trails. Simple web search or naive list checks create two bad outcomes:

- **False positives:** common names or transliteration variants trigger noisy reviews.
- **False negatives:** aliases, ownership links, vessels, entities, PEP relationships, and list updates are missed or not documented.

OpenSanctions' model - source-linked entity records, matching API, four-times-daily updates claimed on its licensing page, and commercial API metering - is a better data primitive than a search result.

### Exact proprietary dataset

- **Dataset:** OpenSanctions consolidated sanctions, PEP, enforcement, securities, vessel/aircraft, crypto-address and related risk entity data, with 410+ sources and source-linked records.
- **Rights holder:** OpenSanctions Datenbanken GmbH.
- **Access route:** Hosted OpenSanctions API, or self-hosted yente with a bulk data license if the buyer requires no supplier data to leave its environment.

### Integration method

- **Phase 1:** Exchange-hosted MCP tool wrapping the OpenSanctions hosted API. It should expose only three tools:
  - `screen_counterparty` -> `/match`
  - `search_risk_entity` -> `/search`
  - `get_risk_entity` -> `/entities`
- **Phase 2:** Optional buyer-private deployment using self-hosted yente if the buyer's security team rejects hosted screening.
- **Why MCP/API:** OpenSanctions documentation says `yente-client` includes an MCP server that lets LLM agents run screening queries, and the OpenSanctions API uses simple pay-as-you-go metering.

## Commercial proposal

All commercial values below are **inference** unless explicitly labeled as public source evidence.

| Item | Proposal |
|---|---|
| Public source evidence | OpenSanctions publishes EUR 0.10 per successful `/match`, `/search`, or `/reconcile` query; volume discounts start above 20,000 requests/month; hosted API has no contract lock-in per docs. |
| Projected query volume | **Inference:** 10,000 screened logical entities/month in pilot. Assumes 2,000 supplier onboardings or reviews/month, average 5 screened entities each (supplier entity, trade names, 2-3 owners/officers). |
| Buyer price | **Inference:** EUR 0.14 per successful screened logical entity for the exchange-managed hosted API path, with a EUR 1,500/month minimum during pilot. This is a proposed buyer price, not OpenSanctions pricing. |
| Data pass-through | Public OpenSanctions API cost would be EUR 0.10/query at this volume, or EUR 1,000/month for 10,000 queries before discounts/taxes. |
| Exchange gross margin | **Inference:** EUR 0.04/query plus any monthly minimum margin, in exchange for MCP wrapper, audit logs, source-version capture, spend caps, and buyer support. |
| Contract term | **Inference:** 90-day pilot with opt-out at 30 days if integration/security review fails. |
| Revenue split | **Inference:** If structured as reseller, 70%-80% of usage revenue to rights holder and 20%-30% to exchange. If OpenSanctions requires direct billing, the exchange charges a separate platform fee and does not touch data revenue. |
| Required budget | **Inference:** EUR 3,000 data budget for 30,000 public API queries over 90 days plus USD 15,000-25,000 engineering/security/legal effort. Total required pilot budget: approximately USD 20,000-35,000 equivalent. |

## Implementation timeline

**Week 0-1: Security and scope**
- Confirm buyer can send supplier names and identifiers to hosted OpenSanctions, or decide on self-hosted yente.
- Sign a narrow data-processing/security addendum if required.
- Define allowed fields, retention period, and audit schema.

**Week 2: Tool wrapper**
- Build MCP/API wrapper with three tools and strict schemas.
- Add spend caps, per-buyer API key mapping, response logging, and source-version capture.
- Add redaction rules for prompts/logs.

**Week 3: Zip-style workflow integration**
- Connect the wrapper into a sandbox supplier-onboarding flow.
- Test on synthetic vendors plus a buyer-provided historical cleared/escalated sample if available.
- Validate match thresholds with compliance/risk users.

**Week 4-6: Controlled live pilot**
- Screen only new or renewal suppliers in one business unit.
- Human review required for all positive or ambiguous matches.
- Weekly review of false positives, latency, user friction, and spend.

**Week 7-12: Expand or kill**
- Expand to more business units only if success metrics are hit.
- Otherwise end pilot and document whether failure was data quality, integration, compliance, or lack of willingness to pay.

## Success metrics

Minimum success thresholds:

1. **Usage:** At least 5,000 screened logical entities/month by month 2. Lower volume means the exchange cannot learn enough or justify integration cost.
2. **Latency:** p95 tool call latency under 1.5 seconds for hosted API path, excluding buyer orchestration overhead. **Inference target.**
3. **Coverage:** At least 95% of submitted supplier entities receive a clear match/no-match result without manual reformatting. **Inference target.**
4. **Audit completeness:** 100% of escalated cases include query, timestamp, source/entity IDs, score, fields matched, agent decision, and human disposition.
5. **Workflow value:** Buyer risk/procurement users report that the tool reduces manual source-hopping or improves consistency versus existing checks.
6. **Commercial signal:** Buyer is willing to pay a platform fee or markup after the pilot instead of integrating OpenSanctions directly.

The last metric is the decisive one. If the buyer says "thanks, we will go direct to OpenSanctions," the pilot succeeded technically but failed the exchange thesis.

## Likely objections

### From buyer

- "We already do OFAC/D&B checks."
- "We cannot send supplier PII or ownership information to a third party."
- "Why should we pay a markup when OpenSanctions has direct API pricing?"
- "Compliance decisions require deterministic controls, not an agent deciding clearance."
- "We need LexisNexis/Dow Jones/ComplyAdvantage-grade coverage, not only OpenSanctions."

### From rights holder

- "We already have pay-as-you-go API billing and an MCP path."
- "We do not want the exchange to obscure customer identity or reduce direct relationships."
- "We need to control reseller claims, support burden, and compliance liability."
- "Agent outputs could make our data look wrong if the prompt misuses it."

### From the exchange operator

- "At EUR 0.04/query gross margin, volume must be meaningful or the business is services-heavy."
- "Compliance workflows create audit/security obligations disproportionate to early revenue."
- "The pilot may prove a data-wrapper feature, not a marketplace."

## Failure conditions

Kill or redesign the pilot if any of these occur:

1. Buyer refuses to pay any markup/platform fee above direct OpenSanctions access.
2. Query volume stays below 5,000 screened entities/month after integration.
3. Compliance/security review requires self-hosting that the exchange cannot support economically.
4. False positives or ambiguous matches overwhelm reviewers without measurable reduction in manual research.
5. The buyer needs a premium sanctions vendor whose license forbids exchange resale.
6. Rights holder requires direct customer contracting only, leaving the exchange as non-billable implementation labor.

## Source appendix

Sources were accessed on 2026-07-15 unless otherwise noted.

1. Zip, "Risk Orchestration." https://zip.com/products/risk-orchestration
2. Zip, "Supplier Onboarding." https://zip.com/products/supplier-onboarding
3. Zip, "Procurement risk management and orchestration in 2026." https://zip.com/blog/procurement-risks
4. OpenSanctions, "What uses of the API are metered and cost money?" Last updated 2026-07-13. https://www.opensanctions.org/faq/api/metering/
5. OpenSanctions, "Data licensing." https://www.opensanctions.org/licensing/
6. OpenSanctions, "Getting started with the API." https://www.opensanctions.org/docs/api/
7. OpenSanctions, "Open source software components." https://www.opensanctions.org/docs/opensource/
8. yente-client documentation. https://yenteclient.followthemoney.tech/
9. Zyphe, "Sanctions Screening Lists 2026: OFAC, UN, EU, UK." https://www.zyphe.com/resources/blog/sanctions-screening-guide
10. Retail Banker International, "Why 99% of sanctions screening alerts are false positives." https://www.retailbankerinternational.com/comment/why-99-percent-sanctions-screening-alerts-false-positives/
