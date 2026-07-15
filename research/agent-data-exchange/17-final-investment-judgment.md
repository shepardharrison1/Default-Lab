# 17 — Final Investment Judgment

**Research date:** 2026-07-15  
**Recommendation:** **Pursue only through a narrow vertical pilot.**  
**Posture:** Decisive. The horizontal version of this idea should not be funded as a founding strategy.

---

## Direct answers

### 1. Is this an independent company or a feature?

**Both — depending on scope.**

- As a **horizontal open-web discovery/rights/settlement layer**, it is a **feature** (or acquisition target) of Cloudflare, Microsoft, AWS, Snowflake/Databricks, and model platforms. Evidence: Cloudflare Pay Per Crawl → Pay Per Use (2025–2026); Human Native acquisition (2026-01-15); Microsoft Publisher Content Marketplace (2026-02); enterprise marketplaces with MCP/RAG distribution.
- As a **vertical licensing broker + entitlement/audit gateway** for high-stakes structured data that mid-tail agent apps cannot easily procure, it can be an **independent company** — with capped upside and multi-homing pressure.

**Inference:** Founders who pitch the horizontal vision will compete with CDN/cloud gravity. Founders who pitch “one procurement rail for agent-usable compliance/logistics/private-market data” have a company-shaped wedge.

### 2. Is the timing early, correct, or late?

| Scope | Timing |
| --- | --- |
| Horizontal media crawl marketplace | **Late** — TollBit, Cloudflare, Microsoft PCM, ProRata already contest it |
| Agent payment rails | **Late as a product** — x402, ACP, AP2 are being standardized by larger players |
| Vertical inference-time proprietary data for agents | **Correct** — MCP ubiquity + agent workflows create integration demand now; market not equilibrated |
| Demand-graph / automated gap detection at scale | **Early** — little public evidence anyone has productionized this as a marketplace core |

Overall: **correct for a narrow pilot; late for a horizontal marketplace company.**

### 3. What is the best wedge?

**Compliance / sanctions–PEP–watchlist screening for procurement and KYB agents**, delivered as an MCP/API wrapper with:

- entitlement and spend caps,
- audit logs and source-version capture,
- one commercial contract for the buyer,
- publisher (OpenSanctions-class) keeping list price; platform charging a service fee.

Then expand to adjacent KYB attributes (UBO, corporate registry, adverse media) before attempting logistics or private-company research.

### 4. What is the weakest assumption?

**That buyers will pay a meaningful markup to an intermediary when the rights holder already exposes a commercial API and MCP server.**

The OpenSanctions pilot is valuable precisely because it can falsify this assumption quickly. If Zip-class buyers say “we’ll just call OpenSanctions,” the brokerage thesis fails.

Secondary weak assumptions:

- Mid-size publishers/data owners prefer a marketplace over direct enterprise deals.
- A “demand graph” creates defensibility before exclusive supply and outcome data exist.
- Network effects appear before multi-homing destroys take rates.

### 5. What is the strongest evidence supporting the idea?

1. **Money already changes hands for proprietary data in agent workflows** — e.g., Harvey–LexisNexis alliance; finance agents embedding PitchBook/S&P/FactSet; OpenSanctions metering at EUR 0.10/query; enterprise search/RAG products selling citations and freshness.
2. **Market infrastructure is forming** — Cloudflare PPC/PPU, TollBit, Microsoft PCM, ProRata attribution — proving rights holders and AI companies seek settlement mechanisms.
3. **MCP is now table stakes** — official registry + 10k-class public servers + platform adoption — so delivery plumbing is available; commerce/rights remain incomplete.
4. **Scraping and BYO-subscription workarounds are fragile** — legal risk, rate limits, institutional access hacks — creating demand for clean licensed paths in regulated contexts.

### 6. What evidence contradicts it?

1. **Human Native acquired by Cloudflare (2026-01-15)** — independent marketplace absorbed by the edge enforcer.
2. **Hyperscalers building PCM and cloud data marketplaces** — buyers already have procurement homes.
3. **Direct bilateral deals dominate premium content** — OpenAI/Microsoft/Meta/Google publisher deals bypass intermediaries.
4. **Payment protocols commoditize settlement** — x402/Stripe/AP2 reduce need for a new “payment layer” company.
5. **Many “pain” signals are annoyance, not WTP for a broker** — uploads, institutional proxies, and free search often substitute.
6. **Presenc-style analyses (treat as secondary)** suggest many PPC 402 responses are declined, not transacted — open-web micropayment demand still immature.

### 7. Which buyer should be approached first?

**Procurement / supplier-risk agent products** with public AI onboarding and audit requirements — **Zip Risk Orchestration / Supplier Onboarding as primary named target** (outreach target only; no partnership claimed).

Backup buyer classes: KYB/AML SaaS adding agent features; enterprise agent platforms selling to finance/procurement; mid-market ERP/AP automation vendors.

Avoid first: foundation-model labs (they do direct deals) and pure consumer chat apps (low willingness to pay per retrieval).

### 8. Which rights holder should be approached first?

**OpenSanctions Datenbanken GmbH** — public commercial terms, API metering, MCP path via `yente-client`, reseller/OEM language, mid-size and realistic for a pilot.

Secondary: mid-size structured providers with agent-relevant APIs and incomplete agent distribution (construction codes, niche industrial catalogs, specialized logistics indexes) — see `publisher-targets.csv`. Avoid starting with news conglomerates already on TollBit/Cloudflare/Microsoft PCM.

### 9. What should not be built initially?

- Horizontal publisher crawl marketplace
- Sponsored discovery / ads-in-answers
- Model-training data brokerage (different buyers, different liabilities)
- Fully automated demand-graph ML (start with explicit buyer requests)
- Custom payment rail / stablecoin wallet product (use Stripe; optional x402 later)
- Multi-vertical catalog before one vertical renews paid
- “Neutral ranking of the entire web” quality engine

### 10. What evidence would justify investing $500,000?

All of the following within ~90 days:

1. ≥10 structured buyer interviews with **written** willingness to pay a broker fee (not just “interesting”).  
2. ≥1 rights holder signed pilot term sheet with chain-of-title representation.  
3. ≥1 live technical integration (MCP or API) in a real workflow.  
4. Pre-agreed success metric and **renewal price** named before pilot ends.  
5. Legal review of pilot contracts by counsel (budgeted).  

$500k funds: founder + eng contractor + counsel + cloud + runway for the pilot — not a marketplace build-out.

### 11. What evidence would justify investing $5 million?

1. ≥3 paying customers (not free pilots) in one vertical.  
2. ≥$500k ARR run-rate or clear path from signed contracts.  
3. Gross margin on mediated queries that survives payment, support, and legal allocation (see `unit-economics.csv`).  
4. Second dataset live with reuse of the same entitlement/audit stack.  
5. At least one preferred or exclusive distribution element **or** durable outcome data that buyers cite as switching cost.  
6. No platform policy blocking independent routing for the primary distribution channel.

### 12. What evidence would cause immediate rejection?

Any one of:

- Zero buyers will pay above the underlying API list price after a serious sales effort.  
- Rights holders refuse redistribution / reseller terms at any reasonable fee.  
- Primary distribution platforms (OpenAI/Anthropic/Microsoft/AWS) prohibit or tax away independent data routing.  
- Existential legal hit: chain-of-title failure in a live deal, or money-transmission enforcement on the payment design.  
- Founders insist on building horizontal media marketplace against Cloudflare/Microsoft without a vertical wedge.

### 13. Could this become a $100 million company?

**Yes, conditionally.**

What would need to be true:

- Default procurement rail for agent-usable data in **one** high-willingness vertical (compliance → KYB), then 1–2 adjacent verticals.
- Take rate or SaaS fee that nets healthy contribution margin at enterprise ACV (not $0.01 micropayments).
- Switching costs via audit trail, entitlement policy packs, and embedded workflows — not “network effects” theater.
- Survive multi-homing by being the easiest *compliance-grade* path, not the only path.

**Probability (inference):** low-to-moderate for a disciplined vertical company; near-zero for a horizontal crawl marketplace started in mid-2026.

### 14. Could it become a $1 billion company?

**Only under a stringent set of conditions that are currently unlikely.**

What would need to be true:

- Becomes the default **cross-vertical** agent-data procurement layer for enterprises (identity, rights, budgets, ranking, settlement).
- Achieves preferred access to scarce datasets that platforms cannot easily replicate.
- Outcome/quality data creates a real ranking advantage.
- Platforms choose partnership over internalization — or acquire the company before it reaches scale.
- Regulatory pressure forces licensed access in multiple industries, expanding TAM.

**Probability (inference):** low. More plausible exit is acquisition by Cloudflare, Microsoft, AWS, Snowflake, Databricks, Stripe, or a large compliance vendor at a price reflecting vertical traction — not organic $1B independence.

### 15. What would need to be true for each outcome?

| Outcome | Required truths |
| --- | --- |
| Fail fast | Buyers refuse broker markup; OpenSanctions-class sources already “good enough” direct |
| Lifestyle / small venture | 1–2 verticals, profitable services + SaaS, limited scale |
| ~$100M company | Multi-customer vertical rail + expanding catalog + sticky audit/entitlement layer |
| ~$1B company | Cross-platform standard for agent data commerce + scarce supply + regulatory tailwind |

### 16. Who could acquire it?

| Acquirer | Why |
| --- | --- |
| Cloudflare | Completes Pay Per Use + Human Native marketplace story |
| Microsoft | Extends PCM beyond publishers into structured data |
| AWS | Extends Data Exchange / Bedrock AgentCore payments |
| Snowflake / Databricks | Agent grounding + marketplace MCP |
| Stripe | Adds licensed-data commerce on top of machine payments |
| Large compliance / risk data vendors | Distribution into agent workflows |
| TollBit / ProRata | Consolidation among independents (less likely at scale) |

### 17. What should the founder test within 30 days?

1. **10 buyer interviews** (procurement AI, KYB, legal tech, logistics agents) — ask for dollar willingness to pay a broker fee vs going direct.  
2. **5 rights-holder calls** starting with OpenSanctions and 4 mid-size structured providers — confirm reseller/OEM terms.  
3. **Write a one-page pilot term sheet** and get at least one party to redline it (signals seriousness).  
4. **Ship a thin MCP wrapper** against one public commercial API; measure integration time.  
5. **Kill criteria:** if no buyer names a fee they would pay above list price, stop.

---

## Moat scorecard (summary)

| Moat | Grade |
| --- | --- |
| Exclusive datasets | Potentially strong if obtained; imaginary at day 0 |
| Proprietary agent demand / demand graph | Weak |
| Outcome data | Potentially strong later |
| Source reputation scores | Weak → potentially useful |
| Routing performance | Weak |
| Legal infrastructure / standard contracts | Weak (operational advantage only) |
| Enterprise integrations | Potentially strong in a vertical |
| Payment relationships | Imaginary as moat |
| Publisher relationships | Potentially strong niche |
| Network effects | Weak (multi-homing) |
| Switching costs | Weak unless audit/entitlement embedded |

---

## Failure modes that kill the company (top)

From `failure-modes.csv` / `16-failure-modes.md`:

1. No repeatable paid agent-buyer demand for the intermediary  
2. Platform internalization  
3. Chain-of-title failure  
4. Antitrust defect in pricing coordination  
5. Unfavorable legal environment reducing need to license  
6. Direct deals bypass marketplace  
7. Inability to prove data value  
8. Publisher concentration / minimum guarantees destroying margins  
9. Low take rates under multi-homing  

---

## Final recommendation

### **Pursue only through a narrow vertical pilot.**

Not “pursue immediately” as a horizontal marketplace.  
Not “pause” if founders can run a falsifiable 90-day compliance pilot with real buyers and OpenSanctions-class supply.  
**Reject** the horizontal media/crawl marketplace founding strategy — that market belongs to Cloudflare, Microsoft, TollBit, and model platforms.

If the pilot cannot produce a paid renewal above underlying data cost, convert the learning into a feature partnership discussion or stop. Do not raise a large seed to fight infrastructure incumbents on their home field.

---

## Sources for this judgment

Primary evidence compiled in `sources.md` and section files `02`, `03`, `04`, `12`, `14`. Key anchors:

- TollBit Series A / Axios (2024-10-22); TollBit site claims (accessed 2026-07-15)
- Cloudflare Pay Per Crawl (2025-07-01); Pay Per Use (2026-07-01); Human Native acquisition (2026-01-15)
- Microsoft Publisher Content Marketplace launch reporting (2026-02)
- ProRata / Gist publisher and funding claims (2025)
- Linux Foundation x402 Foundation operational launch (2026-07-14)
- MCP Registry / AAIF donation materials (2025–2026)
- OpenSanctions API metering docs (accessed 2026-07-15)
- Zip public product pages on AI supplier risk (accessed 2026-07-15)

All commercial pilot numbers not taken from public price pages are **inference**.
