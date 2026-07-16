# Moat Scorecard

**Research date:** 2026-07-16  
**Posture:** Skeptical. Classify claimed moats by current defensibility, not by pitch-deck attractiveness.  
**Recommendation tie-in:** **Pursue only through a narrow pilot.**

## Bottom line

The proposed company has no strong moat at inception unless it controls a scarce vertical data relationship or a workflow integration that produces audited outcome evidence. Most apparent moats are operational advantages, not durable barriers. The two most plausible future moats are:

1. **Outcome-linked evidence that specific licensed sources resolve specific agent failure classes better than alternatives.**
2. **Rights-holder relationships and machine-readable licensing terms that agent hosts and observability vendors cannot cheaply recreate.**

Even those become defensible only after scale. A "failure-node graph" or "demand graph" is not a moat just because traces are collected. It becomes valuable only if the graph is proprietary, permissioned, outcome-labeled, statistically reliable, hard to reproduce from host telemetry, and tied to supply that can be transacted.

## Classification key

- **Strong now:** defensible today with evidence of exclusivity, lock-in, scarce rights, or hard-to-replicate scale.
- **Potentially strong after scale:** could become defensible if the pilot compounds into proprietary data, supplier access, or switching costs.
- **Operational advantage only:** useful execution capability but copyable by determined competitors.
- **Weak:** low defensibility or low relevance.
- **Easily copied:** straightforward for incumbents or startups to replicate.
- **Imaginary:** attractive label without a real control point.
- **Legally dangerous:** may create regulatory, contractual, or liability risk if pursued as a moat.

## Scorecard

| Claimed moat | Classification | Evidence today | What would make it stronger | Skeptical note |
| --- | --- | --- | --- | --- |
| Proprietary failure-node telemetry | **Potentially strong after scale** | **Inference:** none yet for this proposed product. Coding-agent hosts and observability vendors already sit closer to traces. | Permissioned trace volume across multiple hosts; labels showing data-caused failures; buyer consent; outcome linkage; retention rights. | Raw failure traces are not enough. Hosts can collect better telemetry. |
| Cross-agent demand graph | **Potentially strong after scale** | **Inference:** no evidence yet. | Repeated demand patterns across hosts, buyers, verticals, and sources; evidence unavailable to any single host; rights to use aggregated signals. | Easy to overclaim. May be blocked by privacy, contracts, and host internalization. |
| Outcome-linked source rankings | **Potentially strong after scale** | **Inference:** no product evidence yet; observability/eval tools can measure outcomes generally. | Audited before/after lift by source and failure class; statistically significant tasks; controls against paid placement bias. | More defensible than a generic catalog if rankings predict resolution. |
| Exclusive dataset access | **Strong now only if actually exclusive; otherwise weak** | **No evidence for exclusivity in this pack.** Existing vertical data owners often sell direct APIs or marketplace listings. | Multi-year exclusive or semi-exclusive agent-use rights in a high-value vertical. | Do not claim without signed rights. Exclusivity may be expensive and narrow. |
| Standardized licensing contracts | **Operational advantage only** | **Inference:** useful but not unique; marketplaces and data vendors have templates. | Broad adoption by rights holders and buyers; counsel-reviewed machine-readable schedules; network standard. | Standardization can also create antitrust concerns if it coordinates prices. |
| Machine-readable rights | **Potentially strong after scale** | **Inference:** no evidence yet; rights/provenance infrastructure exists adjacent to this market. | Rights terms embedded in enforcement gateway; provider adoption; audit acceptance; host integration. | Valuable only if it controls real access, not just metadata. |
| Rights-holder relationships | **Potentially strong after scale** | **Inference:** no specific relationships evidenced. | Signed providers, renewal rates, unavailable elsewhere terms, provider trust in anti-extraction controls. | Relationship moats are slow and services-heavy. |
| Buyer integrations | **Operational advantage only** | **Inference:** no buyer integrations evidenced. Agent hosts, IDEs, and observability tools can integrate similar MCP/API tools. | Deep workflow embedding, procurement approval, audit exports, budget controls, recurring usage. | Integration is sticky only after real usage and policy dependence. |
| Workflow-specific eval datasets | **Potentially strong after scale** | **Inference:** no datasets evidenced. Eval incumbents already help build eval sets. | Rights-cleared vertical tasks with expert labels and failure/source/outcome annotations. | Legally risky if evals contain licensed source outputs without rights. |
| Historical evidence of which data improves which tasks | **Potentially strong after scale** | **Inference:** none yet; this is the best future data asset if collected lawfully. | Large labeled corpus of data-caused failures, source calls, baselines, and resolution outcomes. | Must distinguish correlation from causation. |
| Enterprise audit/compliance records | **Operational advantage only** | **Inference:** necessary for enterprise adoption. | Accepted by compliance teams; embedded in procurement and model-risk processes; long retention receipts. | Audit logs are required plumbing, not a standalone moat. |
| Budgeting/payment infra | **Easily copied** | **Verified adjacent:** Stripe, marketplace billing, x402/MPP, cloud marketplaces, Zuplo-style gateways exist. | Maybe useful if combined with rights and outcome ledger. | Payment rails are not the moat. |
| Network effects | **Potentially strong after scale / imaginary now** | **No evidence today.** | More buyers attract providers, providers improve resolution, outcome data improves routing, routing attracts hosts. | Marketplace network effects are often asserted before liquidity exists. |
| Switching costs | **Weak now; potentially strong after enterprise embedding** | **No evidence today.** | Buyer policies, audit receipts, provider contracts, eval history, and workflow integrations depend on the platform. | Switching costs require production dependence, not pilots. |
| Proprietary source discovery | **Operational advantage only** | **Inference:** curated vertical source knowledge is useful. | Coverage metadata and provider performance data not available publicly. | A catalog of APIs/data owners is copyable. |
| Confidential-computing / agent-only access tech | **Operational advantage only; "agent-only" claim is imaginary if overstated** | **Verified adjacent:** TEEs/confidential computing exist. | Rights holders require attested execution and the broker operates it reliably. | TEEs do not stop authorized enterprise retention of outputs. |

## Detailed assessment by moat

### Proprietary failure-node telemetry

**Classification:** Potentially strong after scale.

Failure telemetry could become valuable if it captures data-caused failures across multiple coding-agent hosts, repositories, vertical workflows, and data sources. The value would be knowing not only that agents fail, but that a specific missing licensed source would have changed the outcome.

**Evidence required:**

- Buyer permission to use aggregated trace-derived signals.
- Sufficient volume across more than one host.
- Expert-labeled data-causality ground truth.
- Outcomes after licensed-source calls.
- Evidence that host-native telemetry cannot reproduce the same graph.
- Retention rights compatible with privacy and data licenses.

**Current skepticism:** Coding-agent platforms and observability vendors are closer to the raw telemetry. A broker's telemetry moat exists only if it spans supply-side outcomes that hosts do not have.

### Cross-agent demand graph

**Classification:** Potentially strong after scale; imaginary now if claimed without evidence.

A demand graph would map buyers, failure classes, tasks, missing-info schemas, data sources, price points, and resolution outcomes. It is more than "many agents asked for data." It must show repeatable willingness to pay for specific sources in specific workflows.

**Evidence required before claiming defensibility:**

- At least hundreds to thousands of comparable failure events in a vertical.
- Events from multiple buyer organizations.
- Events from multiple agent hosts or workflow surfaces.
- Labels separating data-caused failures from non-data failures.
- Baselines showing free/public sources failed or underperformed.
- Paid-source calls with measured outcome lift.
- Rights to aggregate and commercialize the metadata.
- Controls proving the graph is not mostly one customer's confidential workflow.
- Evidence that source owners act on the graph by changing terms, coverage, or pricing.

**Current skepticism:** A single-host or single-buyer graph is not a market graph. It is customer analytics.

### Outcome-linked source rankings

**Classification:** Potentially strong after scale.

This is the strongest future software/data moat because it connects supply quality to workflow results. A ranking that says "Source A resolves payer-policy failures in 63% of cases where public docs fail; Source B resolves 29%; Source C is stale in jurisdiction X" would be valuable to buyers and providers.

**Evidence required:**

- Controlled task sets and live production outcomes.
- Source call attribution.
- False-positive and false-negative classification.
- Time-to-resolution and cost-per-resolution.
- Source freshness/version metadata.
- Anti-bias controls so rankings are not just commercial placement.

**Current skepticism:** The MVP can start collecting this, but cannot claim it as a moat until it predicts future outcomes.

### Exclusive dataset access

**Classification:** Strong now only if signed; otherwise weak.

Exclusive agent-use rights to a scarce dataset in a high-value vertical would be a real moat. There is no evidence in this pack of such exclusivity. Existing data owners such as compliance, healthcare, legal, market-data, and standards providers often sell direct subscriptions, APIs, or marketplace listings.

**Evidence required:**

- Signed exclusive or semi-exclusive contract.
- Clear field of use.
- Provider inability or unwillingness to expose equivalent API elsewhere.
- Buyer demand for that source specifically.
- Economic terms that allow margin.

**Current skepticism:** Exclusivity is likely narrow, expensive, and revocable.

### Standardized licensing contracts

**Classification:** Operational advantage only; potentially legally dangerous if mishandled.

Templates can reduce transaction cost, especially for no-training, no-redistribution, retention, provenance, subprocessor, and output-rights clauses. They are not a strong moat by themselves because marketplaces, law firms, and large platforms can standardize contracts.

**Risk:** If standardized contracts coordinate prices, restrict supplier competition, or impose most-favored-nation terms across competing data owners, antitrust risk rises.

### Machine-readable rights

**Classification:** Potentially strong after scale.

Machine-readable rights are useful if they drive real enforcement: "this buyer, project, model provider, and answer shape is allowed; this one is not." Rights metadata without an entitlement gateway is weak.

**Evidence required:**

- Provider adoption.
- Buyer compliance acceptance.
- Host/tool integration.
- Automated enforcement logs.
- Revocation propagation.
- Counsel-reviewed mappings from contract to policy.

### Rights-holder relationships

**Classification:** Potentially strong after scale.

Relationships can become defensible if rights holders trust the broker's anti-extraction controls and the broker brings demand they cannot reach directly. They are weak if the broker is merely another reseller asking for margin.

**Evidence required:**

- Signed data-owner agreements.
- Renewal/expansion.
- Provider willingness to expose non-public answer APIs.
- Provider-visible usage reports.
- Low extraction incidents.
- Evidence data owners prefer the broker channel over direct MCP/API exposure.

### Buyer integrations

**Classification:** Operational advantage only now.

Integrations into coding agents, observability tools, CI, ticketing, and compliance workflows are necessary distribution. They are not defensible until buyers rely on them for budgets, audit, provenance, and production workflows.

**Evidence required:**

- Active users invoking licensed calls without handholding.
- Procurement approval.
- Workflow policies requiring the broker for certain sources.
- Audit exports used by compliance teams.
- Renewal behavior tied to integration value.

### Workflow-specific eval datasets

**Classification:** Potentially strong after scale.

Rights-cleared eval datasets for vertical coding/automation tasks could become a moat. They must not be built by copying licensed outputs into benchmarks without rights.

**Evidence required:**

- Expert-labeled tasks.
- Rights-cleared fixtures.
- Representative edge cases.
- Baselines against public docs and model-only attempts.
- Outcome correlation with production performance.

### Historical evidence of which data improves which tasks

**Classification:** Potentially strong after scale.

This is the most attractive long-run data asset. It tells buyers which data is worth buying and tells providers where their data has measurable value.

**Evidence required:**

- Matched failures, source calls, and outcomes.
- Counterfactual baselines.
- Enough volume per source/failure class.
- Durable rights to retain and aggregate evidence.
- Controls for model improvements over time.

**Current skepticism:** Without counterfactuals, "the agent succeeded after the paid call" is not proof that the paid data caused success.

### Enterprise audit/compliance records

**Classification:** Operational advantage only.

Audit records help sell to enterprise buyers and reassure rights holders. They are necessary hygiene. They become stickier if compliance teams standardize on them for model-risk and data-use reviews.

**Evidence required:**

- Compliance acceptance.
- Audit exports used in real reviews.
- Low support burden.
- Integration with buyer retention and legal holds.

### Budgeting/payment infrastructure

**Classification:** Easily copied.

Payment and budget controls are required but commoditized. Stripe, cloud marketplaces, x402/MPP patterns, API gateways, and usage-based billing tools reduce build difficulty.

**Potential moat only if:** the payment ledger is inseparable from rights enforcement and outcome attribution.

### Network effects

**Classification:** Potentially strong after scale; imaginary now.

The plausible network effect:

- More buyers produce more failure/outcome evidence.
- More evidence helps rank sources.
- Better rankings attract more rights holders.
- More rights holders resolve more failures.
- Better resolution attracts more agent hosts and buyers.

**Evidence required:**

- Supply growth caused by buyer demand evidence.
- Buyer conversion improved by provider coverage.
- Source ranking improved with usage volume.
- Cross-side retention: providers stay because buyers are present; buyers stay because providers are present.

**Current skepticism:** Most data marketplaces do not achieve strong liquidity. Vertical supply often sells direct.

### Switching costs

**Classification:** Weak now; potentially strong after enterprise embedding.

Switching costs could emerge from:

- Contracted provider access.
- Enterprise policies.
- Audit history.
- Provenance receipts embedded in code/reviews.
- Evaluation history.
- Budget and approval workflows.
- Source-specific integrations.

**Evidence required:**

- Buyers cite switching burden in renewals.
- Policies depend on broker controls.
- Source integrations are costly to replace.
- Historical eval/provenance data is operationally used.

### Proprietary source discovery

**Classification:** Operational advantage only.

Knowing which data owners exist is useful, but a catalog is copyable. The defensible version includes coverage, freshness, contractability, answer schemas, cost, and outcome evidence.

**Evidence required:**

- Non-public provider metadata.
- Validated coverage maps.
- Historical reliability and resolution records.
- Provider-approved query templates.

### Confidential-computing / agent-only access tech

**Classification:** Operational advantage only; agent-only framing is imaginary if overstated.

Confidential computing can reassure data owners that raw data and code are protected from infrastructure operators. It does not prevent the authorized enterprise from retaining permitted outputs. "Agent-only" access is not a moat if the enterprise receives the benefit and the answer flows through model/provider/logging systems.

**Evidence required:**

- Attested execution accepted by rights holders.
- Architecture that keeps raw data out of buyer/model logs.
- Clear output-retention restrictions.
- Provider renewal based on technical trust.

**Current skepticism:** Large platforms can buy or build similar confidential-computing capabilities.

## Evidence required before claiming a defensible demand graph

Do not claim a defensible demand graph until the following are true:

1. **Cross-buyer:** more than one buyer organization contributes data under aggregation rights.
2. **Cross-host:** more than one agent host or workflow surface contributes events, or there is a reason host-native telemetry cannot substitute.
3. **Labeled:** failures are labeled as data-caused, non-data, ambiguous, false positive, or false negative.
4. **Specific:** events map to missing-info schemas and source categories, not vague prompts.
5. **Outcome-linked:** source calls are tied to task completion, test pass, expert review, reduced rework, or other objective outcomes.
6. **Counterfactual:** baselines exist against public docs, free search, model retry, existing subscriptions, or human clarification.
7. **Permissioned:** contracts permit aggregation and commercial use of metadata without exposing buyer confidential information.
8. **Statistically meaningful:** enough repeated cases exist per failure class/source to predict future demand.
9. **Supply-actionable:** rights holders use the graph to price, package, or expose data.
10. **Hard to reproduce:** no single host, buyer, or provider can recreate the graph from its own data.

## Evidence required before claiming a defensible failure-node graph

Do not claim a defensible failure-node graph until the following are true:

1. **Ground truth:** expert labels show classifier precision and recall in the target vertical.
2. **Causal separation:** the system distinguishes missing data from bad prompts, weak reasoning, missing permissions, tool errors, and poor tests.
3. **Resolution evidence:** the licensed data call improves outcomes over alternatives.
4. **Repeatability:** the same failure class recurs across projects or buyers.
5. **Versioning:** failures and sources are versioned by date, model, tool, source version, and domain rules.
6. **Economic link:** buyers pay for resolution events, not just dashboards.
7. **Rights to retain:** the platform can lawfully retain the failure metadata.
8. **Host independence:** the graph contains source/outcome relationships not visible to coding-agent hosts alone.
9. **Extraction-safe:** graph construction does not store raw licensed content beyond allowed retention.
10. **Operational use:** the graph changes routing, pricing, evaluation, or source onboarding decisions.

## Moat ranking

### Best candidates

1. Historical evidence of which data improves which tasks.
2. Outcome-linked source rankings.
3. Rights-holder relationships.
4. Machine-readable rights tied to entitlement enforcement.
5. Cross-agent demand graph, but only after scale and permissions.
6. Workflow-specific eval datasets.

### Necessary but not durable alone

1. Buyer integrations.
2. Enterprise audit/compliance records.
3. Source discovery.
4. Budgeting/payment infrastructure.
5. Standardized licensing contracts.
6. Confidential-computing access mode.

### Overstated or dangerous

1. "Agent-only" access as a moat.
2. Generic MCP server distribution.
3. Generic data marketplace network effects before liquidity.
4. Raw failure telemetry without outcome labels.
5. Standard price coordination across providers.
6. Exclusive access claimed without signed contracts.

## Conclusion

The moat thesis is currently unproven. The narrow pilot should be designed to create the only evidence that could make it defensible: repeated, labeled, permissioned failures where licensed data outperforms free alternatives and where rights holders accept the technical/legal controls. Until that evidence exists, most moats should be described as potential future assets or operational requirements, not as defensible barriers.
