# 04 - Vertical Ranking for Agent Proprietary-Data Exchange

**Date:** 2026-07-15  
**Posture:** Skeptical. Scores favor a vertical only when (a) agents repeatedly need proprietary data, (b) bad answers are economically costly, (c) licensable data owners exist, and (d) a first pilot can be sold without waiting for a mega-platform or a rights consortium.  
**Companion CSV:** `vertical-ranking.csv`

## Scoring rubric

All raw criteria are scored 1-10, where 10 means "high." Some high values are good for the exchange thesis and some are bad:

- Positive demand/supply signals: frequency of proprietary-data need, economic cost of bad information, data scarcity, willingness to pay, likelihood of publisher cooperation, suitability for initial pilot.
- Friction signals: availability of free substitutes, rights-holder fragmentation, sales-cycle length, technical integration difficulty, regulatory complexity.
- `overall_score` in the CSV is a judgment score that rewards demand and pilotability while penalizing friction. It is not a purely arithmetic average.

## Ranked result

| Rank | Vertical | Overall | Why it ranks here |
|---:|---|---:|---|
| 1 | Compliance | 7.9 | Repeated agent workflow, high cost of stale or wrong screening, public per-query pricing from OpenSanctions, and an MCP/API path make it the cleanest test. The downside is that the best rights holder already sells direct, so this tests distribution more than unique brokerage. |
| 2 | Logistics | 7.4 | Freight procurement agents need rate benchmarks and capacity signals where bad data changes real quotes. SONAR's Bulk Rates API is evidence of an information gap, but SONAR's license terms are restrictive for third-party agent redistribution. |
| 3 | Private-company research | 7.3 | Diligence and sales agents need private-company coverage that web search and SEC filings cannot provide. Tracxn's redistribution packs and PrivCo-style data are commercially plausible, but the buyer may go direct once volume is proven. |
| 4 | Procurement | 7.1 | Supplier discovery and risk agents have an obvious need for Thomasnet-like supplier data, sanctions data, and certifications. The risk is that procurement suites monetize via workflow/ad models and may resist external data routing. |
| 5 | Cybersecurity | 7.0 | Very frequent, costly, machine-native need. However, many threat-intel owners already expose APIs/MCP directly (GreyNoise, VulnCheck), leaving little core brokerage work. |

## Top 3 initial vertical recommendations

### 1) Compliance - supplier / counterparty screening

- **Exact agent workflow:** A procurement or onboarding agent receives a new supplier request, extracts entity name, jurisdiction, registration number, owners, and bank-country signals, calls a sanctioned/PEP/watchlist matching endpoint, explains the match score and evidence, and routes only ambiguous/high-risk cases to a human reviewer.
- **Exact information gap:** Generic web search and raw OFAC-list checks are not enough for aliases, beneficial ownership, PEP status, fuzzy matching, source lineage, and continuous updates. False positives also consume analyst time; false negatives create regulatory exposure.
- **Likely data owner:** OpenSanctions Datenbanken GmbH for consolidated sanctions/PEP/watchlist data; potentially LexisNexis Risk Solutions, Dow Jones Risk & Compliance, ComplyAdvantage, Sayari, or Equifax for heavier enterprise enrichment.
- **Likely buyer:** Procurement/risk orchestration platforms with AI agents, e.g. Zip Risk Orchestration (named as a target, not a confirmed participant), Tonkean/Coupa-style procurement intake platforms, and mid-market fintech compliance agents.
- **Potential pricing:** **Inference:** start with OpenSanctions' public hosted API price of EUR 0.10 per successful `/match`, `/search`, or `/reconcile` query; charge the buyer EUR 0.12-EUR 0.15/query or a 20%-30% exchange fee only if the exchange adds audit logs, entitlement routing, and consolidated billing. This is inference, not a quoted OpenSanctions reseller price.
- **Why existing alternatives are inadequate:** Direct OpenSanctions integration is already easy, which weakens the exchange thesis. The residual gap is not data access; it is packaging multiple watchlist/risk sources into a governed procurement-agent tool with audit, budget limits, and one contract. A pilot must prove that packaging is worth paying for.

### 2) Logistics - freight-rate intelligence inside quoting/procurement agents

- **Exact agent workflow:** A shipper's procurement agent prepares a lane bid or spot/contract quote, calls a freight-rate benchmark source, compares the quote to current market indices, flags outlier bids, and drafts a negotiation note for the procurement manager.
- **Exact information gap:** Bulk freight and some specialized modes lack standardized, public rate references; carrier quotes and anecdotes dominate.
- **Likely data owner:** FreightWaves SONAR for tender/rate indices and Bulk Rates API; DAT Freight & Analytics, Xeneta, Drewry, OAG/Cirium for adjacent modes.
- **Likely buyer:** TMS vendors, freight-procurement platforms, 3PL quoting agents, and procurement teams in commodities, construction materials, chemicals, and energy.
- **Potential pricing:** **Inference:** if SONAR enterprise API pricing is unavailable publicly, pilot pricing should be subscription-plus-metering (e.g. a small fixed pilot fee plus per-quote usage). Do not invent a SONAR price; current public evidence only confirms API availability and restrictive terms.
- **Why existing alternatives are inadequate:** General web/search agents cannot infer current contract-rate benchmarks. However, SONAR's agreement limits third-party use, sublicensing, competing applications, and benchmark construction, so the exchange would need a negotiated agent-access rider before a pilot can run.

### 3) Private-company research - deal sourcing and diligence agents

- **Exact agent workflow:** A VC/PE/corp-dev agent receives a thesis ("US industrial AI inspection startups under 200 employees"), retrieves candidate companies, funding, ownership, and comparable acquisitions, then drafts a short diligence brief with citations and confidence levels.
- **Exact information gap:** Private-company revenue, funding, ownership, and categorization are sparsely disclosed, stale on the open web, and hard to normalize across geographies.
- **Likely data owner:** Tracxn for broad private-company APIs and explicit redistribution/commercial license packs; PrivCo for US private-company financial estimates; Cyndx/Grata/CB Insights-style owners where available.
- **Likely buyer:** Deal-sourcing agents, sales-intelligence agents, market-mapping tools, and boutique advisory firms that cannot afford every premium terminal.
- **Potential pricing:** **Inference:** Tracxn already describes volume-based commercial redistribution pricing by unique companies accessed; a pilot should meter unique company profiles and field depth, not raw API calls. Actual pricing is not public.
- **Why existing alternatives are inadequate:** Crunchbase/free web data is often incomplete for bootstrapped/private companies, and search agents confuse PR, stale directory entries, and similarly named firms. The risk is that serious finance buyers already buy PitchBook/CB Insights/FactSet/Capital IQ direct, while smaller buyers may not pay enough.

## Why not legal as the first pilot?

Legal has high need and high cost of bad information, but it is not the cleanest first pilot. Court data is fragmented across PACER, state courts, proprietary normalizers, and open substitutes like CourtListener/RECAP. UniCourt and Trellis are promising API-first data owners, but legal buyers have long procurement cycles, malpractice concerns, and entrenched incumbents (LexisNexis, Westlaw, vLex/Clio). Legal is a strong second wave after the exchange proves a smaller, cleaner compliance pilot.

## Source appendix

Sources were accessed on 2026-07-15 unless otherwise noted.

1. OpenSanctions, "What uses of the API are metered and cost money?" Last updated 2026-07-13. https://www.opensanctions.org/faq/api/metering/
2. OpenSanctions, "Data licensing." https://www.opensanctions.org/licensing/
3. OpenSanctions, "Getting started with the API." https://www.opensanctions.org/docs/api/
4. OpenSanctions, "Open source software components." https://www.opensanctions.org/docs/opensource/
5. Zip, "Risk Orchestration." https://zip.com/products/risk-orchestration
6. Zip, "Supplier Onboarding." https://zip.com/products/supplier-onboarding
7. yente-client documentation, "yente-client documentation." https://yenteclient.followthemoney.tech/
8. FreightWaves, "SONAR Launches Bulk Trucking Contract Rate Benchmarks via API," 2026-04-08. https://www.freightwaves.com/news/sonar-launches-bulk-trucking-contract-rate-benchmarks-via-api-bringing-pricing-transparency-to-one-of-freights-most-opaque-segments
9. FreightWaves SONAR Agreement v5.0, 2025-09-09. https://gosonar.com/wp-content/uploads/SONAR-Agreement-v5.0-2025-09-09-1.pdf
10. Tracxn, "Data solutions." https://w.tracxn.com/offerings/api
11. UniCourt, "API-first Platform for Legal Data." https://unicourt.com/solutions/enterprise-api
12. Trellis, "Trial Court Data API." https://trellis.law/legal-data-api
13. ATTOM, "ATTOM Introduces MCP Server for AI Applications and Expands Its Cloud Data Delivery through Databricks," 2026-01-27. https://www.attomdata.com/news/most-recent/attom-introduces-mcp-server-and-databricks-delivery/
14. Shovels.ai, "How Much Does Shovels Cost?" https://docs.shovels.ai/docs/knowledge-base/getting-started/pricing-structure
15. Shovels.ai, "Quick Answers." https://docs.shovels.ai/docs/knowledge-base/quick-answers
16. RSMeans, "Flash AI Estimating." https://www.rsmeans.com/flash-ai-estimating
17. Similarweb, "Make Your AI Smarter with Similarweb MCP." https://www.similarweb.com/corp/ai/mcp/
18. GreyNoise, "GreyNoise Intelligence Launches Model Context Protocol (MCP) Server," 2025-09-18. https://www.greynoise.io/press/greynoise-intelligence-launches-model-context-protocol-mcp-server-power-future-of-agentic-soc
19. MOTOR, "MOTOR Automotive Repair Data." https://trydaas.motor.com/
20. MOTOR, "Developer Hub." https://www.motor.com/developer-hub/
