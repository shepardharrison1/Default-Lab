# 00 — Executive Summary

**Research date:** 2026-07-15  
**Subject:** Independent marketplace / licensing / routing layer for AI agents that need proprietary information  
**Posture:** Skeptical and evidence-driven. Goal: determine commercial viability, not validate the idea.  
**Word count target:** under 2,500 words.

---

## Verdict

**Pursue only through a narrow vertical pilot.**

Do **not** build a broad horizontal “agents pay websites” marketplace. That lane is already occupied by TollBit, Cloudflare (Pay Per Crawl → Pay Per Use, plus Human Native acquisition), Microsoft Publisher Content Marketplace, Dappier, ProRata/Gist, and enterprise data marketplaces (AWS, Snowflake, Databricks). Payment rails (x402, Stripe ACP/MPP, Google AP2) are standardizing settlement without needing a new content marketplace.

The thesis that agents need licensed proprietary data is **supported**. The thesis that an independent company can own the generic discovery–rights–settlement layer for the open web is **weak**. The commercially realistic form is a **vertical licensing broker + MCP/API entitlement gateway** for high-stakes structured data — starting with compliance/sanctions screening, then logistics rates or private-company research if the first pilot closes paid renewals.

---

## What the product actually is

One sentence: a neutral discovery, rights, routing, metering, attribution, and settlement layer that lets AI agents buy narrow licensed machine access to proprietary datasets.

The strongest version is **not** “agents pay websites.” It is a **trusted machine-readable information exchange** with enforceable licenses. MVP essentials: thin catalog (1–3 sources), signed pilot licenses, MCP/API proxy, identity + budgets, metering, invoicing/prepaid credits, attribution, audit logs. Outsource contracts, payments (Stripe), and identity. Postpone sponsored discovery.

---

## Competitive reality (July 2026)

| Layer | Who already owns or contests it |
| --- | --- |
| Open-web crawl monetization | TollBit (~$31M raised; thousands of publishers claimed); Cloudflare Pay Per Crawl/Use; ScalePost |
| Hyperscaler publisher marketplace | Microsoft PCM (Feb 2026; AP, Condé Nast, Hearst, USA TODAY, Vox, etc.) |
| Attribution / licensed answer search | ProRata / Gist (50% revenue share; 500–1,000+ publishers claimed) |
| Per-query RAG + MCP | Dappier |
| Training-data marketplace | Human Native — **acquired by Cloudflare, Jan 2026** |
| Enterprise data procurement | AWS Data Exchange, Snowflake Marketplace / Cortex Knowledge Extensions, Databricks Marketplace / MCP |
| Payments for agents | x402 (Linux Foundation), Stripe ACP/MPP, Google AP2 → FIDO |
| Tool discovery | Official MCP Registry (preview; discovery only, not commerce) |
| Direct licensing | OpenAI/Anthropic/Google/Meta/Microsoft bilateral publisher deals; Reddit; Stack Overflow; Reuters MCP |

**Inference:** Human Native’s acquisition is a leading indicator that independent horizontal data marketplaces get absorbed by infrastructure platforms with enforcement power.

Remaining wedge: **vertical proprietary structured data for inference-time agent use**, where owners are too specialized to build distribution and buyers need provenance, SLAs, and audit — not generic news crawl micropayments.

---

## Demand: real pain, narrow willingness to pay an intermediary

| Evidence tier | Finding |
| --- | --- |
| Annoyance | Abundant — paywalls, Cloudflare blocks, missing citations, BYO uploads |
| Technical inconvenience | Strong — MCP connectors, institutional proxies, custom scrapers, BYO subscriptions |
| Willingness to pay | Exists for **direct** licensing and vertical APIs (legal content, clinical, finance, search APIs); weak for paying a **new horizontal marketplace** on top |

Harvey–LexisNexis, Hebbia–PitchBook/S&P, Perplexity–FactSet/Crunchbase, and OpenSanctions API metering show money already moves for proprietary data. The open question is whether mid-tail agent apps will pay a broker instead of going direct or using cloud marketplaces.

**52 agent-application targets** catalogued; **24 high-confidence**. Best clusters: legal research, financial diligence, clinical decision support, construction codes, logistics rates, sanctions/KYB screening.

---

## Best initial verticals

1. **Compliance / sanctions–PEP screening** — clearest pilot (OpenSanctions public API + MCP; Zip-style supplier onboarding agents).  
2. **Logistics** — proprietary freight rates (e.g., Freightos SONAR) with high cost of bad information; harder contracting.  
3. **Private-company research** — scarce data; serious buyers often go direct (PitchBook, Tracxn-class sources).

Avoid as first wedge: open-web news, general search, consumer travel/sports content (already contested by Cloudflare/TollBit/ProRata/Microsoft).

---

## Recommended first pilot

**Buyer target:** Zip Risk Orchestration / Supplier Onboarding (public AI supplier-risk workflows; not a confirmed customer).  
**Rights holder:** OpenSanctions Datenbanken GmbH.  
**Workflow:** Screen suppliers/owners via exchange MCP wrapping OpenSanctions `/match`.  
**Public pricing anchor:** EUR 0.10 per successful query (OpenSanctions).  
**Proposed buyer price (inference):** ~EUR 0.14/query + monthly minimum for audit/entitlement wrapper.  
**Success = paid renewal after 90 days with measurable false-positive reduction and audit completeness.**  
**Failure = buyer prefers going direct to OpenSanctions (high risk — they already have API/MCP).**

This pilot tests the *brokerage value proposition*, not whether sanctions data is useful. If buyers will not pay for the wrapper, the company thesis fails early and cheaply.

---

## Business model recommendation

**Initial:** Publishers keep posted data price; buyers pay a **transparent 20–30% platform service fee** (or monthly minimum) for audited routing, entitlement, and one-contract procurement — plus optional enterprise procurement subscription.

Avoid 80/20 publisher share as default for structured-data APIs (publishers already have list prices). Postpone sponsored discovery. Unit economics at $0.01–$0.05/retrieval are hostile after payment + support costs; viable unit economics appear nearer **$0.10–$1+** per valuable retrieval or **enterprise annual contracts**.

---

## Moats — mostly weak

| Claimed moat | Classification |
| --- | --- |
| Exclusive datasets | Potentially strong *if* obtained; usually imaginary at start |
| Demand graph | Weak initially; potentially useful later |
| Outcome / quality data | Potentially strong if measured in production |
| Network effects | Weak — multi-homing is easy |
| Legal templates / standard contracts | Weak but useful operationally |
| Payment relationships | Imaginary as moat (Stripe/x402 commoditize) |
| MCP integration | Imaginary as moat (standard) |
| Publisher relationships | Potentially strong in a vertical niche |

Multi-homing compresses take rates. Cloudflare, Microsoft, AWS, and model providers can copy the generic layer.

---

## Legal posture (non-counsel summary)

Licensed API access with chain of title is categorically safer than scraping consumer subscriptions. Existential legal risks: chain-of-title failure; antitrust if pricing tools coordinate publishers; money-transmission if wallets/payouts are mishandled; privacy/data-broker rules if personal data is brokered. All contracts require specialist counsel (see `08` and `11`).

Sponsored discovery: **postpone**. Never allow payment to override quality floors on answer-path routing. Reject for regulated compliance workflows.

---

## Investment judgment (abbreviated)

| Question | Answer |
| --- | --- |
| Independent company or feature? | **Feature of platforms at the horizontal layer; possible company only as a vertical broker.** |
| Timing | **Correct for vertical pilots; late for horizontal open-web marketplace.** |
| Best wedge | Compliance screening entitlement gateway → expand to adjacent KYB/procurement data |
| Weakest assumption | Buyers will pay an intermediary when rights holders already expose APIs/MCP |
| Strongest supporting evidence | Real licensing deals + Pay Per Crawl/Use market formation + MCP ubiquity |
| Contradicting evidence | Human Native acquired; Microsoft PCM; Cloudflare edge enforcement; direct deals |
| First buyer | Procurement/KYB agent vendors (e.g., Zip-class) |
| First rights holder | OpenSanctions (or similar mid-size structured risk data with public commercial terms) |
| Do not build initially | Horizontal publisher marketplace, demand-graph ML, ads, training-data brokerage |
| $500k justify | 2+ paid LOIs, 1 live pilot with renewal intent, measurable outcome lift |
| $5M justify | ≥3 paying customers, ≥$500k ARR run-rate, second vertical opening, exclusive or preferred supply |
| Immediate rejection | Cannot get any buyer to pay above direct API price; or platform partner forbids independent routing |
| $100M company? | Possible if vertical procurement rail for multiple high-value datasets |
| $1B company? | Only if it becomes default enterprise agent-data procurement across several verticals — low probability vs. cloud/CDN incumbents |
| Acquirers | Cloudflare, Microsoft, AWS, Snowflake, Databricks, Stripe, major compliance vendors |
| 30-day test | 10 buyer interviews + 5 publisher/data-owner calls; get written willingness-to-pay for broker fee |

### Final recommendation

**Pursue only through a narrow vertical pilot.**

Reject the horizontal marketplace as a founding strategy. If a 90-day compliance pilot cannot produce a paid renewal at a fee above the underlying data cost, **pause or reject** the company — do not raise into a crowded infrastructure war.

---

## Document map

| File | Contents |
| --- | --- |
| `01-product-definition.md` | Product, participants, MVP components |
| `02-competitive-landscape.md` + `competitor-matrix.csv` | Comparables and matrix |
| `03-market-demand.md` | Demand evidence tiers |
| `04-vertical-ranking.md` + `vertical-ranking.csv` | Vertical scores |
| `05-demand-matching-engine.md` | Demand graph and matching |
| `06-agent-targets.md` + `agent-targets.csv` | 52 agent targets |
| `07-publisher-targets.md` + `publisher-targets.csv` | 46 publisher/dataset targets |
| `08-licensing-agreements.md` | Term sheets and outlines |
| `09-business-model.md` + `unit-economics.csv` | Models and unit economics |
| `10-technical-architecture.md` | MVP and production architecture |
| `11-legal-risks.md` | US/EU legal risks |
| `12-commoditization-and-moats.md` | Displacement and moat grades |
| `13-sponsored-discovery.md` | Ads-to-agents analysis |
| `14-first-pilot.md` | Compliance pilot design |
| `15-go-to-market.md` | 30d–24m plan |
| `16-failure-modes.md` + `failure-modes.csv` | 42 failure modes |
| `17-final-investment-judgment.md` | Full Q&A judgment |
| `sources.md` | Consolidated primary sources |

---

*This summary synthesizes dated public evidence as of 2026-07-15. Marketing claims are not treated as proof of revenue or product-market fit. All commercial proposals in the pilot are labeled inference unless tied to public pricing pages.*
