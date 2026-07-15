# 16 - Failure Modes

**Research date:** 2026-07-15  
**Workstream:** W8 - commoditization, sponsored discovery, and failure modes  
**Posture:** skeptical. This file assumes the concept fails unless evidence proves otherwise.

---

## 1. Bottom line

The agent data exchange can fail in three broad ways:

1. **The market is not there:** buyers do not pay enough for a neutral intermediary, publishers multi-home, and platforms/clouds internalize demand.
2. **The trust layer breaks:** chain-of-title, privacy, attribution, sponsored discovery, or source quality failures falsify the "licensed and reliable" promise.
3. **The cost structure is wrong:** legal, compliance, support, payment, tax, metering, and integration burden consumes the take rate.

The detailed table is in `failure-modes.csv` with the requested columns:

`id,failure_mode,description,probability,severity,leading_indicator,mitigation,existential,category`

This markdown summarizes the most important patterns and top existential risks.

---

## 2. Top five existential failure modes

### 1. No repeatable paid demand from agent buyers

The concept's weakest link is not that agents need better data. The weak link is whether mid-tail agent apps will pay an independent exchange instead of using direct APIs, customer subscriptions, cloud marketplaces, browser agents, or scraping workarounds.

**Leading indicator:** pilots produce technical usage but buyers refuse markup/platform fees after comparing direct source integration.

**Mitigation:** run paid pilots only; require pre-committed success metrics and post-pilot pricing before building broad marketplace features.

### 2. Platform internalization

OpenAI, Anthropic, Google, Microsoft, AWS, Snowflake, Databricks, Cloudflare, and Stripe can each absorb pieces of the stack. If the stack is only MCP + catalog + payments, it is easy to copy or commoditize.

**Leading indicator:** target buyers say they will wait for OpenAI/Claude/Copilot/AWS/Snowflake/Databricks native connectors or marketplace listings.

**Mitigation:** build vertical workflow/eval/licensing value that can also list inside those platforms.

### 3. Chain-of-title failure

If a publisher licenses content it does not own or cannot sublicense for AI retrieval, the exchange's core promise is publicly broken. One major buyer lawsuit can poison the marketplace.

**Leading indicator:** publisher catalogs contain wire content, freelance works, UGC, photos, third-party databases, or unclear geographic rights.

**Mitigation:** rights diligence, exclusions, warranties, indemnity, insurance, and narrow source slices.

### 4. Antitrust/pricing-tool defect

If the exchange pools nonpublic publisher pricing/usage data and recommends prices, it can reproduce the RealPage-style hub-and-spoke pricing risk. This is existential because it attacks core marketplace mechanics.

**Leading indicator:** product asks for "optimal publisher price" recommendations using competitor data, or publishers request market-wide floors.

**Mitigation:** publisher-set prices; no nonpublic cross-publisher pricing recommendations; antitrust review before pricing tools.

### 5. Legal rulings improve the unlicensed-access BATNA

If courts bless market-substituting AI retrieval/training or user-delegated agent access to gated sites, buyers may decide licensing is optional or only for PR-sensitive use cases.

**Leading indicator:** adverse appellate rulings in Ross/Perplexity-type cases and buyer legal teams downgrade scraping/access risk.

**Mitigation:** focus on workflows where quality, indemnity, audit, and source SLAs matter even if copyright risk is lower.

---

## 3. Failure-mode categories

| Category | Core concern |
|---|---|
| Demand | Pain exists but willingness to pay an intermediary is weak |
| Supply | Publishers/data owners go direct, multi-home, revoke, or lack rights |
| Platform | Big platforms internalize connectors, payments, and marketplaces |
| Legal | Copyright/access, antitrust, privacy, money transmission, tax |
| Technical | Cache bleed, revocation, metering, latency, source outages |
| Trust | Attribution failures, sponsored discovery, hallucinations, source quality |
| Economics | Low take rates, high compliance/support costs, microtransaction friction |
| Operations | Procurement delays, KYB/sanctions, support burden, deletion workflows |

---

## 4. Pattern analysis

### 4.1 Demand failures are most likely

The public evidence supports paid proprietary data in legal, clinical, finance, scholarly, compliance, and enterprise workflows. It does not yet prove a neutral exchange can capture enough margin. The first pilot must test "will buyer pay above direct source access?" not merely "can we route an API call?"

### 4.2 Trust failures are most damaging

The exchange sells trust: licensed access, citations, provenance, audit, and safer procurement. Chain-of-title, attribution, cache bleed, sponsored ranking, or revocation failures directly attack that trust. These failures have outsized reputational cost compared with ordinary SaaS bugs.

### 4.3 Technical failures become legal failures

In this product, technical mistakes have contractual and regulatory consequences:

- cross-tenant cache bleed = confidentiality breach;
- stale cache after takedown = license/privacy breach;
- missing citation = contract breach and trust failure;
- metering error = billing dispute and publisher distrust;
- rate-limit failure = dataset reconstruction risk;
- deletion failure = privacy/regulatory exposure.

### 4.4 Sponsored discovery is a secondary risk, not a core solution

Sponsored discovery can help revenue but creates disclosure, manipulation, and trust problems. It should not be used to solve weak transaction economics. If transaction margins are too low without ads, the product may not be viable in that vertical.

### 4.5 Multi-homing compresses every margin

Publishers will list in multiple marketplaces; buyers will use multiple source routes; protocols will be open. Assume the exchange cannot hold a toll booth position unless it owns vertical workflow integration or hard-to-reproduce outcome data.

---

## 5. Mitigation priorities

### Before MVP

1. Pick one vertical with measurable workflow value.
2. Require paid pilot terms.
3. Complete source rights diligence.
4. Implement license/policy/budget checks before routing.
5. Build append-only metering ledger.
6. Define attribution/provenance schema.
7. Avoid sponsored discovery.
8. Avoid custody of funds without a licensed payment partner.

### During pilot

1. Track baseline vs. paid-source outcomes.
2. Reconcile metering with source logs weekly.
3. Sample attribution display.
4. Monitor cost per successful workflow, not just cost per call.
5. Track whether buyer would go direct.
6. Run one revocation/deletion drill.
7. Document every manual operation required.

### Before scaling

1. Automate revocation and deletion.
2. Formalize antitrust-safe pricing governance.
3. Add privacy/data-broker determination.
4. Build publisher/buyer portals only after repeatable demand.
5. Add quality/eval programs by vertical.
6. Decide whether to list through clouds rather than compete with them.

---

## 6. Sources

- Market demand evidence: `03-market-demand.md`.
- Competitive landscape and platform/commoditization risks: `02-competitive-landscape.md`; `12-commoditization-and-moats.md`.
- Licensing and legal risks: `08-licensing-agreements.md`; `11-legal-risks.md`.
- Demand matching and architecture risks: `05-demand-matching-engine.md`; `10-technical-architecture.md`.
- Sponsored discovery trust/regulatory risk: `13-sponsored-discovery.md`.
- Model Context Protocol specification, 2025-11-25. `https://modelcontextprotocol.io/specification/2025-11-25`
- Cloudflare Pay Per Use / monetization context, 2026. `https://blog.cloudflare.com/making-ai-search-smarter/`; `https://blog.cloudflare.com/monetization-gateway/`
- Cloudflare x402 Agents docs, modified 2026-06-03. `https://developers.cloudflare.com/agents/tools/payments/x402/`
- Coinbase x402 GitHub README. `https://github.com/coinbase/x402`
- Stripe Machine Payments Protocol, 2026-03-18. `https://stripe.com/blog/machine-payments-protocol`
