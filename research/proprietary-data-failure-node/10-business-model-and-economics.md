# Business Model and Unit Economics

**Research date:** 2026-07-16  
**Posture:** Skeptical. Economics support only a narrow pilot, not a broad horizontal marketplace.  
**Verdict tie-in:** **Pursue only through a narrow pilot.**

## Bottom line

The business is not "agents spend money and the platform keeps the spread." The plausible business is a vertical control plane that charges enterprises for licensed, auditable, failure-resolving data access where the broker adds more than a wrapper around one API. Unit economics are hostile at true per-call micropayment levels, workable only when calls are aggregated through prepaid budgets, monthly invoices, ACH/cloud marketplace billing, or annual enterprise contracts, and meaningfully attractive only when the broker provides multi-source routing, provenance, budget controls, anti-extraction, and outcome evidence.

The critical distinction:

- **Agent task budget is not platform revenue.** If an agent run has a hypothetical budget of `$3 compute + $1 data`, the broker does not earn `$4`, and may not even earn `$1`. The `$3 compute` usually belongs to the model/agent host/cloud provider. The `$1 data` may mostly pass through to rights holders. The broker revenue is the explicit service fee, take rate, platform subscription, or gross margin after rights-holder payouts and transaction costs.
- **The `$3 compute + $1 data` example is illustrative only.** It is a testable hypothesis about buyer tolerance for agent spend, not an assumption. The pilot should measure whether buyers approve real paid data calls above direct data cost.
- **$0.01 retrievals are hostile after payment fees.** Stripe's standard U.S. online card rate is commonly cited as **2.9% + $0.30 per successful online card transaction**. Charging a card per retrieval would cost about `$0.30029` to collect a `$0.01` retrieval, before paying the rights holder or running infrastructure. That is structurally impossible. [Stripe pricing anchor: https://stripe.com/pricing; secondary fee summaries accessed 2026-07-16.]
- **Viability is nearer `$0.10-$1+` per retrieval, or enterprise annual contracts.** Even `$0.10` only works with aggregation and a low-cost rights-holder source; `$0.25` can work for high-volume invoice billing; `$1+` works better when the broker adds audit, routing, and multi-source value; `$10` works only for high-stakes specialized checks.
- **OpenSanctions is the best public pricing anchor for the recommended pilot.** Its hosted screening API lists **EUR 0.10/query** for match/reconcile/search patterns, with only successful HTTP 200 calls billed and entities/statements endpoints free. This proves that paid per-query compliance data can be legible, but also shows how thin the broker margin is if the underlying API already has a transparent list price. [Verified from OpenSanctions API/pricing FAQ and API page, accessed 2026-07-16: https://www.opensanctions.org/faq/api/metering/ and https://www.opensanctions.org/api/.]
- **Prefer transparent buyer service fees over opaque resale splits for structured APIs with list prices.** For an API that already charges EUR 0.10/query, the clean model is "data cost plus 20-30% buyer service fee for agent integration, provenance, budget controls, and audit." An opaque "80/20 marketplace split" is weak when the buyer can see the direct price.
- **Wrapping one API is low value.** A thin MCP wrapper around OpenSanctions, Optum, ICC, or a company-data API is likely a feature or services project. Multi-source brokerage plus entitlement checks plus audit and eval evidence is a higher-value business, but harder to prove.

## Revenue models

### 1. Per-retrieval pricing

The retrieval can be priced at `$0.01`, `$0.10`, `$0.25`, `$1`, or `$10`, but the viable payment mechanism changes by tier.

| Price | Economic read | Required collection model | Likely use case |
| ---: | --- | --- | --- |
| `$0.01` | Not viable with card-per-call. Even a no-cost data source cannot absorb fixed payment fees, support, audit, and refunds. | Must be bundled into an enterprise platform fee or prepaid volume pool; never card-per-call. | Commodity public-ish metadata or promotional free tier, not core revenue. |
| `$0.10` | Barely viable if the underlying data cost is low or if it is the direct source price. OpenSanctions EUR 0.10 is an anchor, but a broker cannot resell it at `$0.10` and also earn margin unless the buyer already pays the source separately or the broker charges a service fee. | Monthly invoice, prepaid wallet/credits, ACH, or cloud marketplace. | Compliance screening query, list match, simple lookup. |
| `$0.25` | Plausible for high-volume structured checks when payment is aggregated and rights-holder payout is controlled. Still needs hundreds of thousands of monthly calls to cover enterprise overhead. | Invoice/ACH/platform contract. | KYB screening plus provenance, code-set validation, entity enrichment. |
| `$1` | More plausible for premium multi-source checks, audit trails, or resolved failure events. Card-per-call can still be poor if rights-holder payout is high and support/eval costs are real. | Invoice/ACH/enterprise minimum. | Multi-source KYB decision support, construction code citation, logistics routing decision. |
| `$10` | Viable unit economics, but demand volume is narrower and sales/support expectations rise. | Enterprise invoice or annual contract. | High-stakes claim edit, legal citation validation bundle, permit/code review support, premium adverse-media bundle. |

### 2. Monthly enterprise minimums

Monthly minimums are the most practical early model because they absorb security review, support, legal, and evaluation work. A plausible pilot package:

- `$5k-$15k/month` platform minimum for one buyer team.
- Usage charged separately as pass-through data cost plus 20-30% service fee, or included up to a quota.
- Provider costs paid monthly after reconciliation.
- Human review and evaluation work explicitly scoped.

Minimums matter because a `$0.25` retrieval with `$0.10-$0.15` of data cost cannot support enterprise onboarding, security questionnaires, counsel review, and success engineering unless volume is very high.

### 3. Annual platform contracts

Annual contracts are economically cleaner than a pure marketplace:

- `$50k-$250k/year` for the control plane: entitlement gateway, agent integration, audit logs, budgets, provenance receipts, eval harness, and source registry.
- Usage either:
  - passed through at cost plus transparent buyer service fee;
  - discounted against a committed annual data spend;
  - bundled for one vertical with overage pricing.

This model treats the broker as enterprise software plus metered data access, not as a standalone micropayment network.

### 4. Data-owner revenue share / payout

Rights-holder payout can be structured several ways:

- **Direct pass-through:** buyer pays the data owner directly; broker charges service fee. Lowest reseller/legal risk, weakest broker revenue.
- **Cost-plus resale:** broker pays the data owner list/wholesale price and charges the buyer list price plus service fee. Best for transparent APIs like OpenSanctions.
- **Revenue share:** rights holder receives 50-80% of retrieval revenue. Works for data owners without list prices, but is opaque and may irritate buyers if a direct API exists.
- **Minimum guarantee:** broker commits to a monthly/annual provider minimum in exchange for better rates. Risky before demand is proven.
- **Provider platform fee:** rights holder pays the broker for incremental distribution/audit, while buyer still pays data cost. Possible later, unlikely in MVP.

The broker should avoid presenting "80/20" as a magic marketplace take. For scarce vertical data, the data owner has leverage. For listed APIs, the buyer can benchmark the direct price. A 20-30% buyer-side service fee is easier to defend when the broker provides routing, rights enforcement, and audit.

### 5. Buyer-side platform fees

The cleanest gross revenue is a buyer-side fee for services the data owner does not provide:

- Agent failure-node classifier.
- Missing-info schema and query templates.
- Entitlement and budget controls.
- Existing-subscription checks before new spend.
- Multi-source routing and fallback.
- Provenance receipts in code, pull requests, and audit logs.
- Outcome evaluation: did the paid call improve code/automation quality?
- Anti-extraction controls and data-owner usage reporting.

This fee can be:

- 20-30% of data spend.
- `$0.02-$0.25` per query, depending on data cost.
- A fixed platform subscription with data pass-through.
- A per-resolved-failure fee rather than per raw provider call.

### 6. Prepaid agent budgets

Prepaid budgets are useful operationally but legally and economically tricky.

Useful version:

- Enterprise approves a monthly data budget for a project, e.g. `$2,000/month`.
- Broker enforces spend limits and approval gates.
- Buyer is invoiced monthly or prepays under a contract.
- Unused budget is not treated like consumer stored value unless counsel approves the structure.

Risky version:

- User loads a general-purpose wallet and autonomous agents spend it across providers.
- Broker holds funds and pays out many suppliers.
- This may raise stored value, money transmission, tax, refund, and escheatment questions.

For the pilot, use **budget controls plus monthly invoicing**, not a consumer wallet.

### 7. Monthly invoicing

Monthly invoicing is the default settlement model:

1. Broker records every entitlement decision, provider call, price basis, source version, and outcome.
2. Buyer receives a monthly invoice with platform fee, data pass-through, service fee, credits/refunds, and overages.
3. Data owner receives a monthly usage statement and payout.
4. Failed or non-billable calls are excluded or credited according to contract.

This avoids per-call card fees and supports enterprise procurement.

## Unit economics model

### Definitions

**Gross margin** here means:

`(retrieval price - rights-holder payout - payment processing - model/tool cost - direct infrastructure) / retrieval price`

**Contribution margin** here means:

`(retrieval price - rights-holder payout - payment processing - model/tool cost - direct infrastructure - per-call security allocation - support allocation - legal/licensing allocation - evaluation allocation - failed/refund allocation) / retrieval price`

Fixed sales, security reviews, product development, and G&A are not in per-call contribution margin. They appear through monthly overhead and breakeven volume.

### Cost components to model

| Cost | Why it matters | Pilot treatment |
| --- | --- | --- |
| Rights-holder payout | Usually the largest variable cost. For OpenSanctions-like sources, list price may set a hard floor. | Track as pass-through data cost or explicit share. |
| Payment processing | Card-per-call breaks low prices; invoices/ACH/cloud billing reduce per-call cost. | No card-per-call below `$10`; aggregate billing. |
| Model/tool costs | Classification, query shaping, evaluation, and response formatting may require model calls. | Keep proprietary content out of models where possible; budget fractions of a cent to cents per call. |
| Infrastructure | Proxy, logs, secrets, KMS, policy checks, queues, storage, observability. | Low per call at scale; non-trivial fixed platform cost. |
| Security | SSO, access controls, audit logs, reviews, pen tests, vendor questionnaires. | Allocate through enterprise minimums; do not expect micropayments to cover it. |
| Legal/licensing | Data-owner contracts, buyer terms, DPAs/BAAs where needed, reseller/OEM review. | Fixed-heavy; first pilots are legal-expensive. |
| Support/success | Integration help, data-owner onboarding, buyer troubleshooting, compliance review. | High in pilot; must decline services-heavy deals that do not generalize. |
| Sales | Enterprise outreach, procurement, security review, renewals. | Covered by annual/minimum contracts, not per-call spread. |
| Failed/refunded retrievals | Classifier false positives, provider errors, non-resolution, credits. | Measure explicitly; if high, thesis fails. |
| Evaluation costs | Labeled tasks, expert review, baseline runs, outcome audits. | Core thesis cost, not optional marketing. |

## Scenario analysis

### `$0.01` retrieval

This is not a business model if charged directly. A `$0.01` card charge with Stripe-style 2.9% + `$0.30` costs roughly `$0.30029` in processing. Even if the rights-holder payout were zero, the platform loses about 30x revenue before infra and support. `$0.01` can exist only as:

- an internal accounting unit inside a prepaid enterprise commitment;
- a free/marketing tier;
- a provider-cost pass-through inside a larger annual contract;
- a very high-volume batch invoice where collection cost is near zero.

### `$0.10` retrieval

This is plausible only with aggregation. OpenSanctions' EUR 0.10/successful-query pricing is a real anchor, but it also shows the squeeze. If the underlying source costs about `$0.11` after FX, the broker cannot charge `$0.10` and have positive margin. The sellable model is either:

- buyer pays OpenSanctions directly and broker charges a platform fee; or
- broker charges roughly source cost plus 20-30%, e.g. about `$0.14` for a `$0.11` source cost; or
- annual platform fee covers the broker function and data is passed through.

At this tier, evaluation/support/legal costs must be mostly covered by minimums.

### `$0.25` retrieval

This can work for high-volume KYB/compliance checks if:

- rights-holder payout is below roughly 40-60% of revenue;
- payment is aggregated by invoice or ACH;
- the broker keeps model/tool work cheap;
- support is not per-call human review;
- volume is hundreds of thousands of calls/month or an enterprise minimum covers overhead.

It is still a thin platform unless it creates audit and routing value.

### `$1` retrieval

This is the first tier where a broker can plausibly cover rights-holder payout, infra, security allocation, support, legal, evaluation, and refunds on a per-call basis. It fits:

- multi-source KYB enrichment;
- construction-code citation decision;
- logistics rate/routing decision;
- legal citation validation;
- premium compliance adverse-media bundle.

But if the broker is merely wrapping one listed API, buyers will ask why the fee is not just a direct API subscription.

### `$10` retrieval

This can support attractive contribution margin, but the buyer expects a high-stakes answer and enterprise-grade support. Good candidates:

- healthcare claim edit/precheck bundles;
- detailed legal/regulatory citation checks;
- construction permit/code compliance decision support;
- premium adverse-media/company-risk packet;
- complex logistics quote/routing event.

Volume will be much lower, liability expectations higher, and direct data-owner competition stronger.

## Minimum viable volume

The key breakeven question is not "can a retrieval have positive gross margin?" It is "how many retrievals are needed to cover fixed monthly overhead?"

Illustrative fixed monthly overhead for one narrow enterprise pilot:

- security/compliance/admin: `$5k-$15k`;
- legal/licensing amortization: `$5k-$20k`;
- support/success/evaluation: `$10k-$30k`;
- engineering/product/infrastructure: `$20k-$80k`;
- sales/procurement overhead: `$10k-$40k`.

Even a lean pilot can have `$50k-$100k/month` of effective overhead if fully loaded. At `$0.10` per retrieval with only a cent or two of contribution, breakeven can require millions of monthly calls. At `$1` with `$0.35-$0.50` contribution, breakeven is tens to low hundreds of thousands of calls. Annual platform contracts reduce the volume requirement by charging for the control plane directly.

## What is worth charging for

Low value:

- One MCP wrapper around one public/list-priced API.
- Generic "search paid data" prompt tool.
- Per-call payment rail.
- API catalog without rights or outcome proof.
- Thin resale of OpenSanctions/ICC/Optum/PitchBook-style APIs.

Higher value:

- Detecting real data-caused failure nodes with high precision.
- Mapping failures to a missing-info schema.
- Checking whether the buyer already has rights.
- Routing across two or more complementary sources.
- Returning a bounded answer with provenance and license constraints.
- Preventing extraction through budgets, templates, thresholds, and anomaly review.
- Measuring code/automation quality improvement against a baseline.
- Producing an audit record acceptable to compliance/legal teams.

## Recommended pilot pricing

For the recommended Compliance/KYB pilot:

1. **Platform pilot fee:** `$10k-$25k/month` for 90 days, covering integration, entitlement gateway, audit receipts, evaluation harness, and support.
2. **Data pass-through:** OpenSanctions-like source at actual list/contract price, e.g. EUR 0.10/successful query for match/reconcile/search where applicable.
3. **Buyer service fee:** 20-30% on data spend for routing, provenance, audit, budgets, and settlement.
4. **Complementary source:** priced by quote or included in a capped pilot budget. Do not assume a premium company/adverse-media source will accept pure per-query economics.
5. **Success gate:** paid renewal after about 90 days at a fee above underlying data cost, with evidence of fewer incorrect screening logic paths or audit gaps.

If buyers refuse the broker fee once they see the direct API price, the brokerage thesis fails for that vertical unless multi-source routing and audit are strong enough to recover value.

## Economic kill criteria

Kill or radically narrow the thesis if any of these occur:

- Buyers accept direct provider API pricing but reject a 20-30% broker service fee.
- Most usage is just one API wrapper with no failure detection or outcome measurement.
- Paid calls do not beat public/free/BYO-subscription baselines.
- Classifier false positives generate material refunds or buyer distrust.
- Rights-holder payout plus support leaves less than 20% contribution margin at pilot scale.
- Enterprise security/legal/support effort cannot be covered by monthly minimums.
- Data owners require minimum guarantees before buyer demand is proven.
- Agent hosts or data owners internalize the integration before the broker builds outcome evidence.

## Conclusion

The economics do not support a broad pay-per-retrieval marketplace for coding agents. They support a narrow enterprise pilot where usage is invoiced, rights-holder costs are transparent, buyer service fees are explicit, and the broker proves that multi-source licensed access improves a measurable coding/automation workflow. If the pilot cannot command revenue above direct data cost, the company becomes a connector, channel feature, or services business rather than a venture-scale failure-node platform.
