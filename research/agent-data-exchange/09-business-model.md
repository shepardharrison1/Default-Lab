# 09 - Business Model for Agent Proprietary-Data Exchange

**Research date:** 2026-07-15  
**Posture:** skeptical. This file treats "agents will pay for data" as a hypothesis that must survive payment fees, publisher power, procurement friction, and incumbent marketplaces.

---

## 1. Bottom line

The best initial business model is **not** an 80/20 open marketplace for every retrieval. It is:

> **Enterprise procurement subscription plus prepaid usage credits for a narrow compliance/sanctions-screening agent tool, where publishers keep their posted data price and the platform charges buyers a transparent 20%-30% service fee or minimum monthly platform fee for entitlement, audit, routing, and one-contract procurement.**

Why:

- **TollBit has trained publishers to expect 100% of their posted price.** Its docs say publishers set rates and TollBit does not take a percentage of those rates; it charges AI customers a transaction fee on top.
- **AWS Data Exchange/AWS Marketplace sets a low enterprise marketplace-fee anchor.** AWS reduced public SaaS/Data Exchange listing fees to 3%, private offers to 1.5%-3%, and renewals to 1.5%. A new startup cannot justify a high take rate merely for billing.
- **RapidAPI is the cautionary high-take developer marketplace.** Rapid's current marketplace docs say it takes a flat 25% fee on API Hub payments, covering processing, infrastructure, and admin, plus PayPal payout fees. That can work for long-tail developer APIs, but it is a weak benchmark for enterprise data owners with alternatives.
- **Cloudflare and Microsoft are compressing generic publisher economics.** Cloudflare controls the edge and is moving Pay Per Crawl toward Pay Per Use; Microsoft PCM gives major publishers a hyperscaler-operated rights marketplace. A generic publisher-content exchange will be late.
- **Payment rails are infrastructure, not the moat.** x402, Stripe MPP, Stripe ACP, Cloudflare Monetization Gateway, and Stripe Connect reduce settlement friction. They do not solve rights, data quality, procurement, source ranking, indemnity, or buyer demand.

**Implication:** price the company as a vertical managed exchange / procurement-and-audit layer, not as a generic tollbooth.

---

## 2. Comparable pricing and take-rate evidence

| Comparable | Public evidence | Skeptical implication |
|---|---|---|
| **TollBit** | Publishers set rates per 1,000 pages; TollBit says it does not take a percentage of publisher rates and instead charges AI customers a small transaction fee on top. | Publisher-friendly buyer-fee framing is likely necessary in AI content licensing. A platform-side take from publisher payout will be resisted. |
| **Cloudflare Pay Per Crawl / Monetization Gateway** | Pay Per Crawl is in closed beta, minimum price $0.01 per crawl, Cloudflare is merchant of record, uses Stripe for payments, aggregates charges and pays publishers monthly; take rate is not disclosed. 2026 Monetization Gateway extends charging to pages, datasets, APIs, and MCP tools via x402/stablecoins. | Cloudflare has edge enforcement and payment aggregation. A startup should not fight Cloudflare on generic web crawling. |
| **Microsoft PCM** | Publishers set usage terms/pricing and get paid based on delivered value; Microsoft take rate is not disclosed. | Major publishers may prefer hyperscaler distribution despite neutrality concerns. Startup wedge must avoid broad premium news/content. |
| **AWS Data Exchange / AWS Marketplace** | Public SaaS and AWS Data Exchange listings carry a 3% fee; private offers are 1.5%-3%; renewals 1.5%; no listing fee without transactions. | Enterprise buyers/sellers have a low-fee procurement benchmark. The exchange must add vertical value beyond listing and billing. |
| **RapidAPI** | Current docs state a flat 25% marketplace fee on API Hub payments; PayPal payout fees can also apply. | A 20%-30% take is possible only when the platform supplies demand, docs, billing, quota enforcement, and developer distribution. It is not automatically acceptable for scarce proprietary data. |
| **ProRata / ad-answer products** | ProRata says it shares 50% of revenue with content partners. | Ad-funded answer products are a different model: useful publisher-side monetization, but weak fit for enterprise agents needing auditable data calls. |
| **Stripe payments** | Standard US card processing is 2.9% + $0.30; ACH Direct Debit is 0.8% capped at $5; disputes cost $15; refunds do not return card processing fees. | Never process $0.01-$1 retrievals as individual card charges. Batch through prepaid credits, monthly invoicing, ACH, or x402/stablecoins. |
| **x402** | Coinbase/CDP facilitator free tier: 1,000 transactions/month, then $0.001/transaction; x402 uses HTTP 402 and stablecoin settlement; Cloudflare examples use the public Coinbase facilitator. | Technically attractive for sub-dollar machine payments, but crypto/stablecoin custody, tax, refunds, KYC, and enterprise acceptance remain product risks. |
| **Stripe ACP / Agentic Commerce** | ACP is an open standard by Stripe, OpenAI, and Meta for agent checkout using shared payment tokens; no protocol fee is disclosed, standard Stripe economics apply unless a platform adds fees. | Useful for commerce/auth delegation, but retail checkout is not data licensing. Do not build the core around ACP first. |

---

## 3. Business model options evaluated

### 3.1 80/20 publisher/platform share

**Mechanic:** buyer pays $1.00; publisher receives $0.80; platform keeps $0.20 before payment/ops costs.

**Pros**

- Simple marketplace language.
- Matches old app-store / media-distribution mental model.
- Can fund support and sales if price per retrieval is high enough.

**Cons**

- Weak against TollBit's "publisher keeps 100%" positioning.
- Weak against AWS's 1.5%-3% enterprise marketplace benchmark.
- At $0.01-$0.05 retrievals, the platform's 20% share is only $0.002-$0.01 before infra/support/fraud/legal.
- Scarce data owners will ask why the intermediary deserves 20%.

**Verdict:** acceptable only for long-tail API/data suppliers that receive meaningful incremental demand. Not the recommended initial default.

### 3.2 Publisher keeps asking price + buyer platform fee

**Mechanic:** publisher sets $0.10/retrieval; buyer pays $0.125; publisher receives $0.10; platform keeps $0.025.

**Pros**

- Aligns with TollBit framing.
- Avoids publisher trust problem.
- Lets the platform present its fee as payment for routing, procurement, audit, source normalization, SLA, support, and consolidated invoicing.
- Easier to vary by buyer segment: 20%-30% fee for self-serve; lower fee plus annual platform subscription for enterprise.

**Cons**

- Buyers see explicit markup and may go direct if the data source is easy to integrate.
- Harder to hide weak unit economics.

**Verdict:** **recommended initial transaction framing.** Use a buyer fee plus minimum commitment; do not call it a publisher take.

### 3.3 Publisher SaaS

**Mechanic:** charge data owners monthly for listing, analytics, controls, metering, bot detection, or licensing operations.

**Pros**

- SaaS revenue is predictable.
- Publishers may pay for analytics/control before demand matures.

**Cons**

- Publisher willingness to pay is weaker than publisher willingness to receive money.
- Cloudflare already gives site owners crawl-control/edge leverage; TollBit gives monitoring/monetization tools.
- For vertical structured data owners, the issue is not building a listing page; it is finding qualified buyers and managing contracts.

**Verdict:** useful later as a premium supplier portal, not the initial model.

### 3.4 Buyer SaaS

**Mechanic:** charge agent builders/enterprises monthly for source discovery, procurement controls, audit logs, spend limits, evaluation reports, and private routing.

**Pros**

- Matches enterprise procurement and security value.
- Does not depend on individual micropayment economics.
- Can coexist with publisher asking-price pass-through.

**Cons**

- Must prove workflow value beyond "we proxy an API."
- Longer sales cycle; needs security and compliance posture.

**Verdict:** strong initial model when paired with a narrow vertical. For the compliance wedge: $1,500-$5,000/month pilot minimum or $25,000-$100,000/year enterprise subscription plus usage.

### 3.5 Usage fees

**Mechanic:** per retrieval, per match, per query, per document, per field, or per successful answer.

**Pros**

- Aligns cost with value and data-owner payouts.
- Familiar to API buyers.
- Lets buyers start small.

**Cons**

- Micropayment processing destroys economics if charged individually on card rails.
- Usage volatility makes publisher revenue uncertain.
- Buyers dislike uncapped AI-agent spend.

**Verdict:** necessary, but batch into prepaid credits, monthly invoices, or minimum commitments.

### 3.6 Enterprise procurement subscriptions

**Mechanic:** annual contract for entitlement, security, audit, support, source evaluation, and a committed usage pool.

**Pros**

- Solves procurement once.
- Makes SOC 2/security/legal spend recoverable.
- Can use ACH/invoice rails with negligible payment cost.
- Fits regulated verticals.

**Cons**

- Slower to sell.
- Requires credible security, SLAs, and support.

**Verdict:** best path to meaningful margin. Even a $50,000 annual contract with 500,000 included retrievals creates more useful economics than millions of $0.01 ad hoc calls.

### 3.7 Minimum commitments

**Mechanic:** buyer commits to $1,500/month pilot, $25,000/year starter, or $100,000/year enterprise; usage burns down a balance.

**Pros**

- Protects against low-volume pilots.
- Funds integration and legal work.
- Gives publishers a reason to onboard.

**Cons**

- Adds sales friction.
- Smaller developers may reject it.

**Verdict:** required for any vertical/proprietary data pilot. A no-minimum exchange risks becoming a demo catalog.

### 3.8 Brokerage commissions

**Mechanic:** charge 5%-15% of negotiated enterprise data-license contracts, or a success fee on net-new publisher revenue.

**Pros**

- Works when the platform originates a bilateral deal.
- Lower perceived risk than recurring take rate.

**Cons**

- Services-like, lumpy, hard to scale.
- Data owners may bypass after introduction unless contracts prevent it.

**Verdict:** acceptable for first 5-10 design-partner deals, but should transition into platform subscription + usage.

### 3.9 Lead-gen fees

**Mechanic:** suppliers pay for qualified buyer leads or introductions.

**Pros**

- Familiar B2B marketplace monetization.
- Avoids touching content revenue.

**Cons**

- Misaligns incentives if low-quality suppliers pay for exposure.
- Weakens neutrality and ranking credibility.
- Hard to charge before demand is proven.

**Verdict:** avoid initially.

### 3.10 Compliance fees

**Mechanic:** charge for audit logs, license receipts, source-version retention, security review packets, DPA/BAA-style addenda where relevant, sanctions/PEP workflow evidence, and regulatory reporting exports.

**Pros**

- Strong fit with compliance/sanctions screening wedge.
- Differentiates from simple API resale.
- Supports buyer SaaS pricing.

**Cons**

- Increases legal/security obligations.
- Must not imply the platform itself makes regulated decisions.

**Verdict:** recommended as part of enterprise subscription, not as a nickel-and-dime add-on.

### 3.11 Sponsored discovery

**Mechanic:** suppliers pay for promoted placement in source search/ranking.

**Pros**

- Marketplace revenue independent of usage.
- Could matter if catalog becomes crowded.

**Cons**

- Dangerous for agent trust, especially legal/compliance/medical.
- Could create liability if a sponsored source causes a bad answer.
- Not needed before organic supply/demand exists.

**Verdict:** postpone. If ever used, label clearly, separate from quality ranking, and forbid in regulated workflows by default.

### 3.12 Outcome-based pricing

**Mechanic:** charge based on avoided manual review, successful compliance clearance, reduced false positives, won bid, answered legal question, or conversion.

**Pros**

- Aligns price to business value.
- Can support high ACVs when value is measurable.

**Cons**

- Attribution is hard.
- Buyers resist sharing outcome data.
- Data owners may not accept variable payout.
- Creates liability if the platform appears to guarantee compliance/legal/clinical outcomes.

**Verdict:** useful for enterprise ROI case studies, not for initial contracts.

---

## 4. Unit economics by retrieval price

The companion CSV (`unit-economics.csv`) contains scenario-level calculations. This section gives the intuition.

### Key cost assumptions

All values are **inference** unless sourced above.

- **Publisher payout:** 70%-85% of buyer price, or 100% of supplier asking price when platform fee is added on top.
- **Payment processing:** standard cards 2.9% + $0.30; ACH 0.8% capped at $5; x402 facilitator $0.001/transaction after free tier plus stablecoin/network/compliance overhead; enterprise invoice/ACH modeled near 0.1%-0.8% of invoice.
- **Cloud/infra per retrieval:** $0.0005-$0.003 for routing/caching/logging on simple text/API responses; $0.01+ for large documents, heavy transformations, or low cache hit rates.
- **Bandwidth:** small text/API responses are usually sub-cent; large PDFs, legal filings, market-data files, or repeated full-content display can dominate infra if not cached and normalized.
- **Caching:** can lower retrieval infra cost, but may violate freshness or license terms. Cache rights must be explicit.
- **DB/logging:** audit logs, license receipts, source-version retention, and per-event metering are low per request but not zero; compliance retention increases storage and support burden.
- **Security/fraud:** budget for bot abuse, stolen API keys, spend-limit bypasses, chargebacks, false buyer identities, and data exfiltration monitoring.
- **Support:** early enterprise support is not variable; allocate at least $0.002-$0.10 per retrieval depending on volume and ticket load.
- **Legal/compliance:** initial contracts, DPAs, reseller rights, privacy review, sanctions workflow disclaimers, and source indemnities are fixed costs; allocate through minimum commitments.
- **Sales commissions:** 10%-15% of first-year ACV for enterprise deals; include in contribution margin, not gross margin.
- **Refunds/credits:** assume 0.5%-2% of GMV for failed calls, bad matches, disputes, and goodwill credits unless source quality is heavily tested.

### $0.01 per retrieval

**Verdict:** uneconomic unless batched or x402/stablecoin-based and very high volume.

- Card per-request fee alone is about $0.30029, roughly 30x revenue.
- An 80/20 split leaves $0.002 gross platform revenue before any processor, infra, support, fraud, or legal cost.
- Even x402's $0.001 facilitator fee consumes 10% of a $0.01 retrieval before publisher payout.
- This price can work only for:
  - cached, low-risk content,
  - prepaid monthly aggregation,
  - no human support,
  - low/no publisher payout, or
  - a strategic loss-leader.

### $0.05 per retrieval

**Verdict:** possible for commodity API-style calls with prepaid billing; weak for proprietary data brokerage.

- 80% publisher payout leaves $0.01 platform gross revenue.
- Support/legal/security allocation can wipe out margin unless volumes are large and self-serve.
- Better as a buyer-fee-on-top model: supplier asks $0.04, buyer pays $0.05, platform keeps $0.01.

### $0.25 per retrieval

**Verdict:** first price point where real exchange economics can work for simple vertical data calls.

- With 75%-80% publisher payout, platform gross revenue is $0.05-$0.0625.
- If payment is batched via invoice/ACH and infra is below $0.003, gross margin can be 15%-20% of GMV.
- Contribution margin still depends on support and legal allocation.

### $1.00 per retrieval

**Verdict:** attractive if data value is real and buyer workflow tolerates the cost.

- 70%-80% publisher payout supports 14%-24% gross margin after batched payments/infra.
- Payment method matters less, though per-request cards still waste $0.329.
- Works for legal snippets, sanctions/entity checks, private-company profiles, freight-rate benchmarks, or high-value answer grounding.

### $10.00 per retrieval

**Verdict:** viable for high-value documents, filings, expert datasets, legal/court records, or complex enriched profiles, but demand volume will be lower.

- Card processing becomes tolerable if batched, but ACH/invoice remains better.
- Publisher power rises; a 20% take may be too high unless the platform supplies qualified demand and indemnity/audit.
- Support/legal cost can be covered if minimums exist.

### Enterprise annual contracts

**Verdict:** best starting economics.

Example:

- $100,000 annual contract.
- 500,000 included retrievals (effective $0.20 each) or a smaller number of high-value queries.
- $70,000 data-owner pool / pass-through.
- $5-$50 ACH processing cost if invoiced.
- $10,000-$15,000 sales commission on first-year ACV.
- $5,000-$15,000 support/security/legal allocation depending on customer burden.

This can produce **10%-20% contribution margin in year one** and better renewal margin if onboarding/legal costs do not repeat. A pure $0.01 retrieval marketplace cannot fund this.

---

## 5. Cost stack to include in pricing

| Cost | Why it matters | Initial modeling treatment |
|---|---|---|
| Publisher payout | Largest cost of goods sold; publishers/data owners have alternatives. | Treat as 70%-85% of usage GMV or 100% of posted supplier price with buyer fee on top. |
| Payment processing | Fixed card fee kills micropayments; ACH/invoice or x402 reduces cost. | No per-request cards. Use prepaid credits, ACH invoices, wallets, or x402 only for sub-dollar agent-native calls. |
| Cloud/API gateway | Routing, auth, rate limiting, transformations, retries, logs. | $0.0005-$0.003/simple call; higher for large files. |
| Bandwidth | Full-content retrievals can become expensive; structured records are cheap. | Prefer field-level/summary retrieval and explicit cache licenses. |
| Caching | Improves margin but can violate freshness/rights. | Cache only with source permission and versioned audit. |
| Database/audit | Usage ledger, source versions, license receipts, buyer budgets. | Include in infra/security allocation; not zero for compliance. |
| Security/fraud | Stolen keys, bot loops, overspend, unauthorized resale, prompt exfiltration. | Build spend caps and anomaly detection from day one. |
| Support | Data mismatches and workflow failures create tickets. | Allocate per retrieval only after minimums; otherwise treat as fixed pilot cost. |
| Legal/compliance | Reseller rights, indemnity, DPA, retention, privacy, regulated-use disclaimers. | Recover through setup fees/minimum commitments. |
| Sales commissions | Enterprise ACV requires direct sales. | 10%-15% of first-year ACV; lower on renewals. |
| Refunds/credits | Failed calls, stale data, buyer disputes, false positives. | Reserve 0.5%-2% of GMV depending on SLA. |

---

## 6. Payment model recommendation

### Do not start with per-request cards

At $0.01, $0.05, and even $0.25 retrievals, standard card processing is irrational if each retrieval is a separate transaction. The $0.30 fixed fee overwhelms revenue. Even at $1.00, card cost is roughly $0.329 per transaction, before publisher payout.

### Use these payment paths by segment

| Segment | Recommended payment path | Why |
|---|---|---|
| Enterprise pilot | Monthly invoice / ACH; annual contract; minimum monthly platform fee. | Lowest processing cost, procurement-friendly, supports legal/security work. |
| Mid-market developer | Prepaid credits with minimum balance and auto-recharge; cards only for the wallet top-up, not each retrieval. | Keeps self-serve UX while amortizing fixed card fee. |
| High-volume agent/API partner | Monthly invoicing with spend caps and committed usage. | Prevents runaway agent spend and avoids processor drag. |
| Crypto-native agent | x402/stablecoin wallet for sub-dollar calls, optional. | Technically suited for micropayments; only use where buyer accepts stablecoins and compliance burden is understood. |
| Marketplace supplier payouts | ACH/Stripe Connect monthly payout after reconciliation. | Matches Cloudflare/TollBit-style aggregation and lowers refund/dispute risk. |

### Prepaid credits

**Recommend for self-serve only.**

- Require $25-$100 minimum top-up for developers; $1,000+ for business accounts.
- Use card or ACH for top-up; debit the internal ledger per retrieval.
- Advantage: avoids per-request fixed fees and enforces budget caps.
- Risk: unused balances create accounting/unclaimed-property complexity; consult counsel.

### Monthly invoicing

**Recommend for enterprise.**

- Net 15/30 terms after credit review.
- ACH default; card allowed only with surcharge/pass-through where legal.
- Include monthly usage report and source-level audit logs.
- Use buyer-configured spend caps and alert thresholds.

### Minimum balances

**Recommend for developer and mid-market accounts.**

- Stop calls when balance reaches threshold unless buyer authorizes overdraft.
- Prevents agents from creating uncollectible usage.

### Wallets

**Use as internal accounting ledger first, not as financial custody product.**

- "Wallet" can mean a prepaid balance ledger inside the platform.
- Avoid holding customer funds in a way that triggers money-transmission complexity without counsel.
- For stablecoin wallets, use non-custodial or qualified providers and require compliance review.

### Stablecoins / x402

**Useful later, not default initial rail.**

Pros:

- Native machine-to-machine payments.
- Low fixed cost for sub-dollar calls.
- No prior buyer account needed in pure x402 flow.
- Cloudflare and x402 Foundation support create momentum.

Cons:

- Enterprise procurement, tax, refunds, KYC/KYB, sanctions controls, custody, wallet recovery, and accounting remain nontrivial.
- Stablecoin rails do not automatically handle licensed-use restrictions, audit retention, customer support, or refund policies.
- For compliance/sanctions customers, crypto payment rails may create unnecessary risk optics.

### Standard processors

**Use Stripe/ACH/Connect initially.**

- Stripe card/ACH is familiar and supports invoicing, Connect payouts, fraud tools, and accounting integrations.
- ACP is useful if agentic checkout becomes a buyer requirement, but it is not necessary for a B2B data exchange MVP.

---

## 7. Recommended initial model

### Package

**Compliance Agent Data Exchange - Pilot**

- Buyer: procurement/risk/compliance agent vendor or enterprise team.
- Supply: OpenSanctions first; later Dow Jones/LexisNexis/ComplyAdvantage/Sayari-style premium sources if licenses allow.
- Product: MCP/API wrapper, source entitlement, routing, audit log, source-version receipts, spend caps, match-threshold configuration, and monthly invoice.

### Pricing

**Pilot**

- $5,000 setup/security/legal fee.
- $1,500-$5,000/month minimum platform fee.
- Publisher asking price passed through at cost or under negotiated reseller terms.
- 20%-30% buyer platform fee on usage only if it does not duplicate a direct publisher bill.
- 90-day term; opt-out if security/integration fails.

**Post-pilot**

- $25,000/year starter subscription, includes audit/reporting/support and a small usage pool.
- $100,000/year enterprise subscription, includes committed usage, SSO/SOC2 packet, private deployment option, and negotiated data-owner pool.
- Overages priced per successful screened entity or source call.

### Revenue recognition / economics

- Treat publisher pass-through as COGS if platform is merchant/reseller.
- If publisher bills buyer direct, recognize only platform subscription/fee.
- Pay sales commission on platform ACV, not gross data pass-through if margins are thin.

### Why this model beats alternatives now

1. It avoids the generic publisher marketplace fight with TollBit, Cloudflare, and Microsoft PCM.
2. It avoids pretending $0.01 retrievals can support enterprise support/legal costs.
3. It uses AWS Marketplace's low take-rate reality as a procurement channel benchmark, not as a margin target.
4. It lets the platform prove a real value claim: "we reduce procurement/legal/integration friction for agent access to licensed vertical data."
5. It creates a kill criterion: if buyers will not pay the platform fee above direct OpenSanctions access, the exchange thesis is weak.

---

## 8. Open risks

1. **Direct integration risk:** OpenSanctions and similar sources already sell APIs; buyers may go direct.
2. **Low gross-profit pool:** Compliance screening at EUR 0.10/query leaves limited room for markup unless volume/minimums are real.
3. **License restrictions:** premium vendors may forbid resale, caching, model use, or agent outputs without direct contract.
4. **Liability risk:** compliance workflows must keep human-in-the-loop and avoid representing the platform as the final screening authority.
5. **Platform risk:** AWS, Snowflake, Databricks, Cloudflare, Microsoft, Stripe, and agent platforms can absorb pieces of the stack.
6. **Demand risk:** supply enthusiasm is easier to find than agent-side budget.

---

## 9. Sources

Accessed/searched on 2026-07-15 unless noted.

- TollBit monetization/rates docs: https://docs.tollbit.com/docs/setting-rates and https://docs.tollbit.com/docs/rates
- Nieman Lab on AI content licensing marketplaces and TollBit correction: https://www.niemanlab.org/2026/05/the-emerging-ai-content-licensing-market-puts-news-publishers-in-a-double-bind-a-new-report-warns/
- AWS Marketplace fee reduction: https://aws.amazon.com/about-aws/whats-new/2024/01/aws-marketplace-simplified-reduced-listing-fees/
- AWS Data Exchange provider financials: https://docs.aws.amazon.com/data-exchange/latest/userguide/provider-financials.html
- RapidAPI payout/marketplace fee docs: https://docs.rapidapi.com/docs/payouts-and-finance
- Stripe pricing: https://stripe.com/pricing
- Cloudflare Pay Per Crawl docs: https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/ and https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/use-pay-per-crawl-as-site-owner/set-a-pay-per-crawl-price/
- Cloudflare Pay Per Crawl payouts: https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/use-pay-per-crawl-as-site-owner/manage-payouts/
- Cloudflare Monetization Gateway: https://blog.cloudflare.com/monetization-gateway/
- Cloudflare x402 docs: https://developers.cloudflare.com/agents/tools/payments/x402/
- Coinbase x402/CDP docs: https://docs.cdp.coinbase.com/x402/welcome
- x402 Foundation / Linux Foundation announcement: https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications
- Stripe ACP docs: https://docs.stripe.com/agentic-commerce/acp
- Stripe machine payments docs: https://docs.stripe.com/payments/machine
- Microsoft PCM reporting: https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing and https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191
- OpenSanctions metering/licensing docs: https://www.opensanctions.org/faq/api/metering/ and https://www.opensanctions.org/licensing/
