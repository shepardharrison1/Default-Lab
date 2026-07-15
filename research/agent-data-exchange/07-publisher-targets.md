# 07 - Publisher / Dataset Targets

**Date:** 2026-07-15  
**Posture:** Skeptical. The goal is not to make a long logo slide. The goal is to identify data owners that are proprietary, frequently needed by agents, hard to reproduce, machine useful, commercially valuable, and realistically licensable without inventing partnerships or pricing.  
**Companion CSV:** `publisher-targets.csv`

## Method and cautions

- The CSV contains 46 candidate publishers/datasets/data owners with the exact requested fields.
- Public pricing is shown only when a source surfaced it. Otherwise the field says `not public`, `custom`, or `reported third-party` as appropriate.
- MCP availability is treated as counter-evidence when a data owner already exposes its own agent-ready server. In those cases, an exchange may still resell or normalize billing, but it is not proving the core "broker proprietary access" thesis.
- "Potential deal structure" is a proposed structure, not an existing agreement.
- "Negotiation difficulty" is 1 easy to 10 very hard, based on apparent size, business model, strategic lock-up, and cannibalization risk.

## Best near-term supply candidates

### 1) OpenSanctions

OpenSanctions is the most pilotable data owner found in this pass: public hosted API pricing, commercial licensing language, reseller/OEM license category, transparent data lineage, and an MCP path through `yente-client`. That also weakens the exchange thesis: OpenSanctions already does pay-per-query metering and agent integration without a marketplace.

### 2) Tracxn

Tracxn is unusually exchange-compatible because its public data-solutions page explicitly separates internal-use license packs from redistribution/commercial license packs and describes volume pricing based on unique companies accessed. That is almost exactly the contractual primitive an agent exchange would need for private-company research.

### 3) UniCourt / Trellis

Both are API-first legal-data companies exposing court and litigation datasets that agents often cannot reliably assemble from the open web. They are plausible data suppliers, but legal buyers have procurement friction and open substitutes such as PACER/CourtListener cap part of the value.

### 4) MOTOR

MOTOR is structurally aligned because it already sells automotive data through Data as a Service and RESTful APIs. It is a better automotive target than Mitchell 1/Identifix, whose shop-seat subscription models create higher cannibalization fear.

### 5) FreightWaves SONAR

The Bulk Rates API proves that freight-rate gaps are real and API-addressable. The hard part is contractual: SONAR's published agreement restricts third-party benefit, sublicensing, derivative works, and benchmark construction. A pilot would be a legal-paper pilot as much as a technical pilot.

## High-value but poor first-pilot targets

- **RSMeans / Gordian:** The data gap is excellent, but Gordian has launched its own Flash AI Estimating product on top of RSMeans Data. That is evidence that the data owner prefers a first-party AI product.
- **ATTOM, Similarweb, GreyNoise, Shovels.ai:** These are good evidence that agents need proprietary data, but they already expose API/MCP access directly. They are reseller/channel candidates, not proof of a missing broker.
- **Healthcare/pharma publishers:** DrugBank, Wolters Kluwer-style clinical data, Citeline/Evaluate, and other pharma intelligence vendors have valuable data but bring privacy, regulatory, and parent-company strategic friction.
- **Standards bodies and academic full text:** ASTM/ANSI/IEEE/JSTOR-like targets have extreme agent value and extreme rights complexity. They are not good first suppliers unless an incumbent aggregator such as Accuris/Techstreet wants a controlled pilot.
- **Premium finance and market intelligence:** AlphaSense, CB Insights, Similarweb, Daloopa, S&P/FactSet-class assets increasingly build their own connectors, agent APIs, or bilateral integrations.

## What the target list implies

1. **The easiest data owners already know how to sell data.** That means the exchange's value is discovery, procurement simplification, entitlement management, audit logs, and small-buyer metering - not "unlocking" data.
2. **The hardest and most valuable data owners are hard for business-model reasons, not technical reasons.** Seat subscriptions, exclusivity, contributor confidentiality, and first-party AI products are bigger blockers than API work.
3. **A first pilot should avoid giant incumbents.** The pilot should pick a supplier with a public API and either public pricing or an explicit redistribution license path.
4. **The first deal should be framed as incremental distribution.** "Let external agents replace your product" is a losing pitch. "Meter a narrow, auditable workflow you do not currently serve" is the better pitch.

## Source appendix

Sources were accessed on 2026-07-15 unless otherwise noted.

1. OpenSanctions, "What uses of the API are metered and cost money?" Last updated 2026-07-13. https://www.opensanctions.org/faq/api/metering/
2. OpenSanctions, "Data licensing." https://www.opensanctions.org/licensing/
3. OpenSanctions, "Getting started with the API." https://www.opensanctions.org/docs/api/
4. yente-client documentation. https://yenteclient.followthemoney.tech/
5. Tracxn, "Data solutions." https://w.tracxn.com/offerings/api
6. UniCourt, "API-first Platform for Legal Data." https://unicourt.com/solutions/enterprise-api
7. Trellis, "Trial Court Data API." https://trellis.law/legal-data-api
8. FreightWaves, "SONAR Launches Bulk Trucking Contract Rate Benchmarks via API," 2026-04-08. https://www.freightwaves.com/news/sonar-launches-bulk-trucking-contract-rate-benchmarks-via-api-bringing-pricing-transparency-to-one-of-freights-most-opaque-segments
9. FreightWaves SONAR Agreement v5.0, 2025-09-09. https://gosonar.com/wp-content/uploads/SONAR-Agreement-v5.0-2025-09-09-1.pdf
10. RSMeans, "Flash AI Estimating." https://www.rsmeans.com/flash-ai-estimating
11. ATTOM, "ATTOM Introduces MCP Server for AI Applications and Expands Its Cloud Data Delivery through Databricks," 2026-01-27. https://www.attomdata.com/news/most-recent/attom-introduces-mcp-server-and-databricks-delivery/
12. Shovels.ai, "How Much Does Shovels Cost?" https://docs.shovels.ai/docs/knowledge-base/getting-started/pricing-structure
13. Shovels.ai, "Quick Answers." https://docs.shovels.ai/docs/knowledge-base/quick-answers
14. Similarweb, "Make Your AI Smarter with Similarweb MCP." https://www.similarweb.com/corp/ai/mcp/
15. GreyNoise, "GreyNoise Intelligence Launches Model Context Protocol (MCP) Server," 2025-09-18. https://www.greynoise.io/press/greynoise-intelligence-launches-model-context-protocol-mcp-server-power-future-of-agentic-soc
16. MOTOR, "MOTOR Automotive Repair Data." https://trydaas.motor.com/
17. MOTOR, "Developer Hub." https://www.motor.com/developer-hub/
18. Zip, "Risk Orchestration." https://zip.com/products/risk-orchestration
19. Zip, "Supplier Onboarding." https://zip.com/products/supplier-onboarding
20. Xometry, "Thomas Launches New Platform Tools Helping Industrial Buyers Source the Right Suppliers," 2026-01-15. https://investors.xometry.com/news-releases/news-release-details/thomas-launches-new-platform-tools-helping-industrial-buyers
21. ATTOM, "MCP Server - Property Data for AI Applications." https://www.attomdata.com/solutions/delivery/mcp-server/
22. Sportradar, "Sports Data API." https://sportradar.com/media-tech/data-content/sports-data-api/
23. Stats Perform, "Pricing & licensing FAQ." https://www.statsperform.com/faqs/stats-perform-faqs-pricing-licensing/
24. OAG, "Flight Info API." https://www.oag.com/flight-info-api
25. Cirium, "Schedules and connections data." https://www.cirium.com/data/flight-schedules/schedules-and-connections-data/
