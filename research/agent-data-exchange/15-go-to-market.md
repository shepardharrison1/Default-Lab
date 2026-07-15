# 15 - Go-to-Market Plan for Agent Proprietary-Data Exchange

**Research date:** 2026-07-15  
**Posture:** skeptical. The plan assumes the biggest risk is not building MCP/payment plumbing; it is proving that buyers will pay a platform premium above direct data-source access.

---

## 1. Recommended wedge

Start with **compliance / sanctions and counterparty screening for procurement and onboarding agents**.

One-liner:

> Route procurement/risk agents to licensed sanctions, PEP, watchlist, and counterparty-risk data through a governed MCP/API wrapper with audit logs, spend controls, and one-contract procurement.

### Why compliance over legal or logistics?

| Vertical | Evidence for demand | Why not first |
|---|---|---|
| **Compliance / sanctions screening** | Repeated workflow; OpenSanctions publishes commercial API metering, licensing, and MCP/yente path; procurement vendors publicly market risk orchestration, OFAC/D&B/bank checks, supplier onboarding, and audit trails; bad data has regulatory and operational cost. | The data source already sells direct, so the pilot tests whether packaging/audit/procurement is valuable. This is a feature of the test, not a bug. |
| **Legal** | Strong willingness to pay for trusted/cited legal content; Harvey/LexisNexis proves vertical AI + proprietary legal data demand. | Entrenched incumbents, malpractice concerns, long law-firm procurement, fragmented court data, and higher liability make it a better second wave. |
| **Logistics** | Freight-rate and capacity data can directly change quote/procurement economics; SONAR's Bulk Rates API shows proprietary structured data need. | Rights restrictions and reseller permissions are likely harder; buyer ROI can be strong but sales requires deep industry workflow integration. |

**Skeptical thesis:** vertical proprietary structured data beats a horizontal crawl marketplace because:

1. **Generic publisher crawl monetization is already crowded** by TollBit, Cloudflare, Microsoft PCM, Dappier, ScalePost, and ProRata-style products.
2. **Horizontal discovery alone is commoditized** by MCP registries, Postman/API networks, cloud marketplaces, and agent-platform connectors.
3. **Enterprise buyers pay for governed outcomes**: auditability, source quality, indemnity, spend controls, and workflow integration, not just a payment button.
4. **Structured vertical data supports higher value per call** than open-web pages. A $0.25-$2.00 compliance/entity/profile call can support support/legal/security cost; a $0.01 page retrieval usually cannot.
5. **The first pilot can be falsified quickly.** If a procurement/risk buyer will not pay a platform fee over direct OpenSanctions API access, the broader exchange thesis is weak.

---

## 2. ICP and positioning

### Initial buyer ICP

Primary:

- Procurement/risk orchestration platforms.
- Supplier onboarding and vendor-management platforms.
- Fintech/regtech agents that screen counterparties or merchants.
- Enterprise procurement teams experimenting with AI intake/onboarding agents.

Buyer personas:

- VP/Head of Product at procurement/risk software vendor.
- Head of Supplier Risk / Third-Party Risk.
- Compliance Operations lead.
- Procurement Transformation / AI Automation lead.
- Security/procurement owner for agent tooling.

### Initial supply ICP

Primary:

- OpenSanctions-like data owners with clear commercial API terms.
- Later: premium sanctions/risk vendors if they allow agent-access resale or direct-bill-plus-platform-fee structures.

Supplier personas:

- Founder/GM of data vendor.
- Partnerships/BD lead.
- Legal/commercial licensing lead.
- API/product lead.

### Positioning

Do not position as:

- "A marketplace where agents buy websites."
- "An x402 payment layer."
- "A universal MCP registry."
- "A cheaper sanctions database."

Position as:

- "The governed data-access layer for AI agents that need licensed proprietary records with audit receipts."
- "One contract, one tool call, multiple licensed sources, source-versioned evidence."
- "A procurement-friendly way for agent products to use vertical data without custom reseller contracts for every source."

---

## 3. 30-day plan

### Objective

Prove whether the compliance wedge has enough buyer pain and supplier willingness to justify a 90-day paid pilot.

### Interviews and demand discovery

Conduct **35-50 interviews**:

- 15-20 buyer interviews:
  - 5 procurement/risk software PMs or founders.
  - 5 third-party-risk/compliance operators.
  - 3-5 fintech/regtech agent builders.
  - 2-5 enterprise AI/procurement transformation leaders.
- 10-15 supplier/publisher interviews:
  - OpenSanctions.
  - 3-5 sanctions/PEP/risk data vendors.
  - 3-5 adjacent data sources: business registries, beneficial ownership, adverse media, vessel/aircraft, crypto-address risk.
- 5-10 ecosystem interviews:
  - procurement consultants,
  - compliance counsel,
  - data-reseller BD leads,
  - cloud marketplace operators,
  - agent-platform/MCP builders.

Interview questions:

- What data does the agent need that generic web/search cannot provide?
- What happens when the answer is wrong or stale?
- What data subscriptions does the buyer already own?
- Would the buyer route through an exchange, or only through direct vendor entitlements?
- What budget owns this: product COGS, compliance ops, procurement transformation, or data subscriptions?
- What minimum audit evidence is required for a compliance decision?
- What markup over direct source cost is acceptable for one contract, audit logs, spend caps, and support?
- What would cause security/legal to block a hosted tool?

### Design-partner outreach

Target **8-12 design-partner prospects**, aiming for 2-3 serious conversations:

- Zip-style procurement/risk orchestration vendor.
- Mid-market supplier onboarding platform.
- Fintech onboarding/compliance agent.
- Enterprise procurement transformation team.

Ask for:

- A paid discovery sprint or refundable LOI.
- Access to 50-200 historical screening cases, redacted if needed.
- Agreement to test a sandbox MCP/API wrapper.
- A named compliance/risk user for weekly feedback.

### Supplier outreach

Target:

- OpenSanctions first because public pricing/licensing and API/MCP path reduce uncertainty.
- 3-5 premium vendors to learn license objections, even if they are not first suppliers.

Ask suppliers:

- Can the exchange resell or route API calls?
- Must buyers contract directly?
- Are agent outputs allowed?
- Are caching and source-version retention allowed?
- Can the platform show supplier identity and price transparently?
- What minimum monthly volume or revenue share makes participation worthwhile?

### Product work

Build only a clickable/API-level prototype:

- Tool schema for `screen_counterparty`, `search_risk_entity`, and `get_risk_entity`.
- Example audit log with query hash, timestamp, source version, returned entity IDs, match fields, score, and human disposition.
- Spend-cap mockup.
- Buyer invoice/usage report mockup.
- Supplier payout/report mockup.

No production build until at least one paid LOI or design-partner commitment exists.

### Security/compliance

Create a lightweight security packet:

- Data-flow diagram.
- Data retention policy.
- PII handling assumptions.
- Human-in-the-loop compliance decision disclaimer.
- Draft DPA/security questionnaire answers.
- Initial threat model for prompt exfiltration, key leakage, runaway agent spend, and data resale.

### Success criteria by day 30

Proceed only if:

1. At least 3 buyer prospects rank the problem as urgent and budgeted.
2. At least 1 buyer prospect accepts a paid pilot or signs a serious LOI with price range.
3. At least 1 data supplier confirms a legally viable routing/resale/direct-bill structure.
4. Buyers say audit/procurement controls are worth a platform fee above direct API access.

Kill or pivot if:

- Buyers prefer direct OpenSanctions integration with no platform fee.
- Security teams require self-hosting before the product has budget to support it.
- Suppliers prohibit agent outputs or third-party routing.

---

## 4. 90-day plan

### Objective

Close and run one paid pilot; prove measurable workflow value and willingness to pay for the exchange layer.

### Commercial targets

- 1 signed paid pilot: $15,000-$35,000 total value for 90 days.
- 1 backup LOI or design partner.
- 1 signed supplier/routing agreement or direct-bill-plus-platform-fee agreement.

Pilot terms:

- 90 days.
- $5,000 setup/security/legal fee.
- $1,500-$5,000/month platform minimum.
- Usage pass-through or buyer-fee markup.
- Human review required for positive/ambiguous matches.
- Clear data retention and audit terms.

### Product

Build MVP:

- Hosted MCP server and REST endpoint.
- Strict tool schemas.
- Buyer API key/tenant isolation.
- Spend caps and alerts.
- Usage ledger.
- Source-version capture.
- Audit-log export.
- Basic admin dashboard.
- Monthly usage/invoice report.

### Evals

Create a test set:

- 100-300 synthetic and public counterparty cases.
- Redacted historical buyer cases if available.
- Known true positives, false positives, ambiguous matches, and no-match controls.

Measure:

- Match/no-match coverage.
- False-positive rate versus buyer baseline.
- False-negative review on known cases.
- Latency p50/p95.
- Audit completeness.
- Human reviewer time saved or consistency improved.
- Cost per screened supplier / owner / entity.

### Security/compliance

- Complete vendor security questionnaire.
- Add SSO only if required for pilot; otherwise use scoped API keys.
- Implement retention controls and deletion flow.
- Log access and admin actions.
- Draft incident response procedure.
- Counsel review of reseller/routing terms, disclaimers, and DPA.

### Hiring

Keep team tiny:

- 1 founding CEO/BD/product lead.
- 1 founding full-stack/platform engineer.
- 1 part-time compliance/legal counsel.
- 1 part-time solutions engineer or contractor if integration burden rises.

### Fundraising

Do not raise a priced seed on story alone if possible. Use the 90-day pilot to create evidence:

- signed paid pilot,
- supplier agreement,
- usage data,
- eval results,
- security packet,
- pipeline of 5+ similar buyers.

If needed, raise a small pre-seed / angel round after LOI: **$500,000-$1,000,000** to fund 9-12 months. This is an inference, not a market quote.

### Success criteria by day 90

Proceed if:

1. Pilot reaches at least 5,000 screened logical entities/month by month 2 or shows a credible path to that volume.
2. Buyer users report reduced manual source-hopping or better audit consistency.
3. Buyer agrees in writing to convert to a 6-12 month paid term if security/eval thresholds are met.
4. Contribution margin model is positive under a minimum commitment, not just under fantasy volume.

---

## 5. 6-month plan

### Objective

Convert the first pilot, add 2-3 more design partners, and decide whether to deepen compliance or pivot to legal/logistics.

### Commercial targets

- 1 converted annual contract: $25,000-$100,000 ACV.
- 2 additional paid pilots: $15,000-$50,000 each.
- 3-5 signed LOIs with named workflows and budget owners.
- 2-3 supplier agreements or source-routing structures.

### Product

Move from wrapper to managed vertical product:

- Multi-source routing abstraction, even if only one source is active initially.
- Source allowlists/blocklists.
- Buyer-specific match thresholds.
- Evidence packets for human review.
- Versioned license receipt per call.
- Budget policies by team/workflow.
- Basic dashboard for usage, cost, escalations, and audit export.
- Cache only where source license permits.

### Evals and proof

Publish private buyer-facing evidence:

- Before/after manual review time.
- Audit completeness.
- Cost per supplier screened.
- False-positive handling improvement.
- Security/privacy review outcomes.

Do not publish accuracy claims without buyer and counsel approval.

### Security/compliance

- Start SOC 2 readiness if enterprise pipeline requires it.
- Formalize access control, logging, change management, vendor management, and incident response.
- Review money-transmission/prepaid-credit issues if holding balances.
- Review sanctions/AML implications of serving global buyers.

### Hiring

Minimum viable team by month 6:

1. CEO/BD/product.
2. CTO/platform engineer.
3. Full-stack/backend engineer.
4. Solutions engineer / technical customer success.
5. Part-time counsel.
6. Part-time finance/ops.

Expected monthly burn, **inference**:

- Lean founder-led team: $45,000-$80,000/month.
- With one senior hire and counsel/security spend: $80,000-$130,000/month.
- Main cost drivers: engineering salaries, legal/security review, cloud/logging, pilot support, travel/BD.

### Fundraising

Raise pre-seed/seed only if evidence exists:

- 3+ paid design partners or 1 annual contract plus strong pipeline.
- Repeatable buyer pain in one vertical.
- A supplier contract structure that can be reused.
- Unit economics showing contribution margin under committed usage.

Target raise, **inference**:

- Pre-seed: $750,000-$1,500,000.
- Seed: $2,000,000-$4,000,000 only if 3-5 paid pilots and at least one expansion path are real.

---

## 6. 12-month plan

### Objective

Become the default governed data-access layer for one narrow workflow, or admit the wedge is not venture-scale.

### Commercial targets

- 5-10 paying customers.
- $250,000-$750,000 ARR / committed annualized revenue.
- 3-5 licensed/routed sources.
- Net revenue retention signal from expansions or higher usage.
- At least one channel/procurement path through AWS Marketplace, Snowflake, Databricks, or a procurement platform if enterprise onboarding is slow.

### Product

- Enterprise SSO/SAML.
- Tenant-level retention policies.
- Full audit API.
- Source-quality dashboards.
- Evaluation harness integrated into onboarding.
- Buyer-specific policy engine:
  - max price per call,
  - source restrictions,
  - geographic restrictions,
  - training/no-training flags,
  - human-review thresholds.
- Supplier portal:
  - usage reporting,
  - buyer approval,
  - pricing controls,
  - license-scope templates.

### Evals

Create benchmark packs for the vertical:

- Sanctions/PEP entity matching.
- Adverse-media risk summaries.
- Beneficial-ownership resolution where data rights allow.
- Procurement-agent audit packet quality.

Use evals as sales assets and source-ranking inputs.

### Security/compliance

- SOC 2 Type I by month 12 if selling to enterprise buyers.
- Formal privacy/security review process.
- Clear subprocessors list.
- Standard DPA.
- Pen test if required by enterprise customers.

### Hiring

Team size: **8-12 people**, inference.

- CEO.
- CTO.
- 3-4 engineers.
- 1 product/solutions lead.
- 1 sales/BD lead.
- 1 customer success/implementation.
- 1 compliance/security ops.
- Part-time/outsourced legal and finance.

Expected monthly burn, **inference**:

- $150,000-$250,000/month depending on seniority, geography, and security/legal load.

### Fundraising

Seed is justified if:

- ARR/committed revenue is above $250,000 and growing.
- Sales cycle and implementation cost are bounded.
- Customers use the tool in production agent workflows.
- Suppliers agree to reusable terms.
- Gross margin can exceed 20% after publisher payouts and payment/infra.

If ARR is mostly services or one-off brokerage, do not pitch as a software marketplace.

---

## 7. 24-month plan

### Objective

Either scale a vertical exchange with defensible workflow data and supplier relationships, or become a services-heavy broker and choose a different financing path.

### Commercial targets

Bullish but grounded targets, **inference**:

- $2,000,000-$5,000,000 ARR / committed annualized revenue.
- 20-40 paying customers.
- 10-25 licensed/routed sources.
- 2-3 vertical workflows if compliance wedge works:
  - supplier/counterparty screening,
  - adverse media / beneficial ownership,
  - regulated procurement intelligence.
- 50%+ gross margin on platform revenue, excluding pure data pass-through.
- 20%+ contribution margin on mature annual contracts after support/legal allocation.

### Product

- Multi-source ranking by coverage, freshness, latency, price, rights, and eval performance.
- Source fallback and ensemble matching.
- Private deployment option for regulated buyers.
- Cloud marketplace procurement listings.
- Optional x402 endpoint for crypto-native sub-dollar calls, if demand appears.
- No sponsored discovery in regulated workflows unless explicitly labeled and off by default.

### Security/compliance

- SOC 2 Type II.
- Regular pen tests.
- Formal vendor risk program.
- Data residency options if demanded by customers.
- Strong audit/export functionality for customer regulators and internal compliance.

### Hiring

Team size: **18-30 people**, inference.

- Engineering/product: 10-15.
- GTM/sales/BD: 4-7.
- Customer success/solutions: 3-5.
- Security/compliance/ops: 2-3.
- Legal mostly outside counsel, with in-house commercial/legal ops only if contract volume justifies it.

Expected monthly burn, **inference**:

- $350,000-$650,000/month.
- Lower end if remote/lean and channel-led; higher end if enterprise field sales/security/legal load is heavy.

### Fundraising

Series A only if:

- Vertical repeatability is proven.
- Net revenue retention is strong.
- Sales cycles are predictable.
- Supplier exclusivity or workflow data creates defensibility.
- Platform revenue, not pass-through GMV, supports venture margins.

If the business is primarily negotiated licenses plus integration labor, it may still be valuable but should be financed as a profitable vertical data broker, not a venture-scale marketplace.

---

## 8. Minimum viable team and cost

### Day 0-90

| Role | FTE | Why needed |
|---|---:|---|
| CEO / BD / product | 1.0 | Interviews, LOIs, supplier negotiation, pricing, fundraising. |
| CTO / full-stack engineer | 1.0 | MCP/API wrapper, usage ledger, auth, audit logs. |
| Legal/compliance counsel | 0.1-0.2 | Reseller/routing terms, DPA, liability, prepaid-credit review. |
| Solutions engineer | 0-0.5 | Only if buyer integration is heavy. |

Estimated monthly cost, **inference:** $25,000-$60,000 if founders take reduced salary; $70,000-$100,000 if paying market salaries plus counsel.

### Month 6

| Role | FTE |
|---|---:|
| CEO / BD / product | 1 |
| CTO | 1 |
| Backend/platform engineer | 1 |
| Solutions/customer engineer | 1 |
| Part-time counsel/security/finance | 0.3-0.5 |

Estimated monthly cost, **inference:** $80,000-$130,000.

### Month 12

| Role | FTE |
|---|---:|
| CEO | 1 |
| CTO | 1 |
| Engineers | 3-4 |
| Product/solutions | 1 |
| Sales/BD | 1 |
| Customer success/implementation | 1 |
| Security/compliance ops | 0.5-1 |
| Part-time legal/finance | 0.5 |

Estimated monthly cost, **inference:** $150,000-$250,000.

---

## 9. GTM risks and mitigations

| Risk | What would prove it | Mitigation |
|---|---|---|
| Buyers go direct to data source | Prospect says "we can integrate OpenSanctions ourselves" and refuses platform fee. | Sell audit, procurement, multi-source routing, spend controls; if still no, kill the wedge. |
| Supplier forbids resale | Contract prohibits third-party routing or agent outputs. | Use direct-bill-plus-platform-fee model; do not hide supplier identity. |
| Low query volume | Pilot below 5,000 screened entities/month after integration. | Require minimum commitments; target platforms with repeated workflows. |
| Security blocks hosted model | Buyer requires self-hosted deployment. | Offer self-hosted only at enterprise ACV; otherwise reject. |
| Accuracy/liability concern | Compliance team rejects agent-mediated decisions. | Human-in-the-loop, audit evidence, no autonomous clearance for high-risk matches. |
| Incumbent platforms copy | Cloud/procurement vendor adds similar connector. | Own supplier terms, eval data, workflow-specific audit, and vertical implementation expertise. |
| Marketplace fantasy | Many suppliers sign up but buyers do not pay. | Sequence buyer demand before broad supplier onboarding. |

---

## 10. Stage-gate summary

| Time | Continue if | Kill/pivot if |
|---|---|---|
| 30 days | 1 paid LOI/pilot path, 3 urgent buyer signals, 1 viable supplier structure. | Buyers like idea but no budget; supplier terms block routing. |
| 90 days | Paid pilot running, usage/eval/security data collected, buyer sees platform value. | Buyer goes direct; no platform fee; low volume. |
| 6 months | 1 annual conversion, 2 more paid pilots, repeatable supplier terms. | Mostly consulting/integration revenue. |
| 12 months | 5-10 customers, $250k-$750k ARR/committed revenue, production workflows. | Long sales cycles and custom legal work dominate. |
| 24 months | $2M-$5M ARR, repeatable vertical, 20%+ mature contribution margin. | Platform GMV is pass-through and margins stay thin. |

---

## 11. Sources and evidence base

This GTM plan relies on the evidence developed in:

- `02-competitive-landscape.md`
- `03-market-demand.md`
- `04-vertical-ranking.md`
- `14-first-pilot.md`
- `09-business-model.md`
- `unit-economics.csv`

Key external sources accessed or searched on 2026-07-15:

- OpenSanctions API metering/licensing: https://www.opensanctions.org/faq/api/metering/ and https://www.opensanctions.org/licensing/
- OpenSanctions/yente docs: https://www.opensanctions.org/docs/api/ and https://yenteclient.followthemoney.tech/
- Zip Risk Orchestration / Supplier Onboarding: https://zip.com/products/risk-orchestration and https://zip.com/products/supplier-onboarding
- TollBit monetization docs: https://docs.tollbit.com/docs/setting-rates
- Cloudflare Pay Per Crawl / Pay Per Use: https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/ and https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/
- Microsoft PCM reporting: https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing
- AWS Marketplace fee benchmark: https://aws.amazon.com/about-aws/whats-new/2024/01/aws-marketplace-simplified-reduced-listing-fees/
- RapidAPI marketplace fee docs: https://docs.rapidapi.com/docs/payouts-and-finance
- Stripe pricing and ACP docs: https://stripe.com/pricing and https://docs.stripe.com/agentic-commerce/acp
- Coinbase/x402 docs: https://docs.cdp.coinbase.com/x402/welcome
- Legal/medical/finance proprietary-data examples cited in `03-market-demand.md`, including LexisNexis/Harvey, OpenEvidence/JAMA, Rogo/S&P Capital IQ, Hebbia/PitchBook, Daloopa MCP, and Scite MCP.
