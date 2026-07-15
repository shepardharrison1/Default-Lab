# 05 - Demand-Matching Engine

**Research date:** 2026-07-15  
**Workstream:** W7 - demand-matching engine and technical architecture  
**Posture:** skeptical. The "demand graph" is a product hypothesis, not a moat until it contains proprietary, outcome-linked workflow data that suppliers and buyers cannot cheaply reproduce.

---

## 1. Bottom line

The exchange should not start by claiming it can "know what agents need." It can start by collecting **explicit, auditable gap signals** from agent workflows and using them to prioritize source onboarding.

The matching engine has three jobs:

1. **Detect gaps:** identify when an agent likely needed proprietary or rights-cleared data and did not have it.
2. **Route paid access:** choose a licensed source under policy, budget, and quality constraints.
3. **Prove uplift:** show that paid access improved a pre-registered task metric enough to justify its cost.

The first version should be mostly rules + lightweight learning-to-rank. A fully automated "data demand marketplace" is premature. The hard part is not ranking; it is getting buyers to expose workflow telemetry and getting publishers to provide enough metadata, evaluation sets, and license clarity for matching to be trusted.

**Skeptical conclusion:** the demand graph is probably a weak moat at launch. It becomes potentially strong only if it accumulates cross-buyer, cross-source **outcome data** under contractual rights that platforms, clouds, and direct data vendors do not have.

---

## 2. Signals that an agent needs proprietary data

Signals should be captured as structured events, not free-text anecdotes. Each event has a task, user/company context, model/tool trace, observed failure, candidate missing source type, and business impact estimate.

| Signal | What it means | Reliability | Example instrumentation |
|---|---:|---:|---|
| Failed query / empty retrieval | Search/RAG returned no useful result | Medium | `retrieval_result_count=0`, no answer generated, fallback triggered |
| Low confidence | Model or verifier reports weak support | Medium | calibrated confidence, self-critique, verifier score, contradiction detector |
| Missing citations | Answer lacks source-backed evidence where citations are required | High in regulated workflows | citation count, citation coverage, unsupported claims |
| Stale citations | Sources exist but are too old for the task | High | source publication date vs. freshness requirement |
| Paywall / 401 / 403 / bot block | Relevant source was reachable only behind access controls or anti-bot defenses | High | HTTP status, Cloudflare/anti-bot error class, paywall marker |
| Rate-limit or quota exhaustion | Existing source has access but not enough capacity | Medium | 429s, quota remaining, retry budget exhaustion |
| Tool unavailable / connector missing | Agent could not access known system of record | High | MCP/tool discovery miss, connector auth failure |
| Human-in-the-loop escalation | Human reviewer had to complete research manually | High if labeled | escalation reason, reviewer resolution, time-to-resolution |
| User correction | User says answer missed an authoritative source | Medium | thumbs-down taxonomy, correction text, source named by user |
| Abandoned task | Workflow stops when data is missing | Medium | drop-off after retrieval failure, no downstream action |
| Expensive manual fallback | Analyst opened external databases / PDFs manually | High if browser/app telemetry is available | domain visited, time spent, manual attachment/upload |
| BYO-document upload | User supplies a document the agent could not license directly | Medium | upload type, source domain, document title/metadata |
| Existing subscription route | Customer has entitlement but agent cannot use it cleanly | Medium | SSO/OAuth failure, entitlement mismatch |
| Contradictory sources | Open web gives conflicting answers and no authoritative source wins | Medium | verifier disagreement, source reputation spread |
| Policy denial | Agent knows source exists but license/policy blocks use | High | policy engine deny event with reason |

### Signals to treat carefully

- **Self-reported model uncertainty** is noisy. Use it only when calibrated against actual outcomes.
- **Search result absence** may mean bad query formulation, not missing data supply.
- **Paywall hits** prove access friction, not willingness to pay. Users may paste documents, use institutional access, or abandon the task.
- **Human escalation** is the strongest signal only if the human resolution is captured and linked back to the agent trace.

---

## 3. Demand graph design

The demand graph should connect tasks, missing information needs, candidate sources, license rights, and measured outcomes.

### 3.1 Node types

| Node | Description | Example fields |
|---|---|---|
| `Buyer` | Legal entity buying access | company, industry, KYB tier, contracts, budgets |
| `AgentApplication` | Product/runtime making calls | app id, model/provider, host, MCP client, version |
| `EndUserRole` | Human role or service account | role, jurisdiction, entitlement, approval rules |
| `Workflow` | Repeatable business process | supplier onboarding, legal motion drafting, clinical question answering |
| `TaskInstance` | One execution of a workflow | timestamp, prompt class, risk level, outcome metric |
| `InformationNeed` | Normalized missing fact/content requirement | taxonomy label, freshness, geography, entity type, required authority |
| `GapSignal` | Observed failure or friction | signal type, confidence, trace pointer, severity |
| `Source` | Publisher/dataset/API/MCP source | owner, catalog ids, schema, coverage, freshness, license scope |
| `SourceSlice` | Subset of source relevant to a need | geography, section, endpoint, field set, time range |
| `LicenseTerm` | Machine-enforceable rights | permitted uses, retention, citation, training prohibition, revocation |
| `PolicyConstraint` | Buyer/publisher rule | allowlist, forbidden sources, data residency, human approval |
| `PriceQuote` | Cost of using a source | per call, per field, subscription, minimum, currency |
| `RetrievalEvent` | Actual source use | query, source id, content ids, latency, cost, citation metadata |
| `OutcomeEvent` | Did the answer/workflow improve? | task success, verifier score, human disposition, time saved, revenue/risk |
| `DisputeEvent` | Buyer/publisher challenge | refund, incorrect answer, citation failure, license breach |

### 3.2 Edge types

| Edge | Meaning |
|---|---|
| `buyer_owns_agent` | Buyer or vendor controls the agent application |
| `agent_runs_workflow` | Agent participates in workflow |
| `task_emits_gap` | Task generated a gap signal |
| `gap_maps_to_need` | Raw signal normalized to information need |
| `need_requires_source_slice` | Need could be satisfied by a source slice |
| `source_governed_by_license` | Source slice has machine-enforceable license |
| `license_allows_task` | License permits the requested use |
| `source_used_in_task` | Retrieval happened |
| `source_cited_in_answer` | Answer displayed source metadata |
| `source_improved_outcome` | Uplift measured vs. baseline |
| `source_failed_outcome` | Paid source did not help or harmed task |

### 3.3 Minimum viable taxonomy

Start with a small taxonomy so events are comparable across buyers:

- **Domain:** legal, clinical, finance, procurement/compliance, construction, logistics, scholarly, coding/devdocs, other.
- **Need type:** current fact, historical archive, authoritative rule, entity profile, market price, citation/evidence, full text, structured field, benchmark/comparison, identity/relationship.
- **Failure type:** unavailable, unauthorized, stale, low-quality, conflicting, uncited, incomplete, too expensive, too slow, policy-blocked.
- **Required right:** search, retrieval, quote, summarize, display, temporary context, platform-hosted index, buyer-hosted embedding, evaluation, training.
- **Decision impact:** answer quality, legal/compliance risk, time saved, conversion/revenue, operational cost, safety risk.

---

## 4. Matching formula

The engine should first filter hard constraints, then rank candidates.

### 4.1 Hard filters

Reject a source before scoring if any are false:

1. Buyer is verified and not blocked by publisher eligibility rules.
2. End-user/company entitlement exists where required.
3. License permits the requested use: retrieval, summarization, quote, display, retention, embedding, no training, etc.
4. Geography, data residency, sanctions, privacy, and category rules pass.
5. Source is available within task latency and rate-limit constraints.
6. Price is within buyer budget and per-task max.
7. Source is not on buyer blocklist and does not violate conflict rules.

### 4.2 Candidate score

For each permitted candidate source `s` for task `t`:

```text
Score(s,t) =
  0.24 * Relevance(s,t)
+ 0.16 * Authority(s,t)
+ 0.13 * Coverage(s,t)
+ 0.11 * Freshness(s,t)
+ 0.10 * LicenseFit(s,t)
+ 0.08 * ProvenanceQuality(s,t)
+ 0.07 * HistoricalOutcomeUplift(s,t)
+ 0.05 * LatencyFit(s,t)
+ 0.04 * Reliability(s,t)
+ 0.02 * CitationUsability(s,t)
- 0.10 * NormalizedCost(s,t)
- 0.08 * RiskPenalty(s,t)
- 0.05 * ConflictPenalty(s,t)
```

Weights are placeholders. The pilot should tune them against outcome metrics, not engagement or revenue.

### 4.3 Definitions

| Feature | Definition |
|---|---|
| `Relevance` | Semantic/entity/schema match between task need and source slice |
| `Authority` | Whether the source is primary, official, trusted, or contractually warranted |
| `Coverage` | Expected completeness for jurisdiction/entity/time range |
| `Freshness` | Update cadence vs. task freshness requirement |
| `LicenseFit` | How closely permitted uses match requested task without exceptions |
| `ProvenanceQuality` | Source versioning, citations, content IDs, correction/takedown support |
| `HistoricalOutcomeUplift` | Prior measured improvement for similar tasks, normalized by confidence |
| `LatencyFit` | Expected p95 latency relative to workflow budget |
| `Reliability` | Uptime, error rate, rate-limit stability |
| `CitationUsability` | Can the agent produce visible, accepted citations from returned metadata? |
| `NormalizedCost` | Expected total task cost / buyer value threshold |
| `RiskPenalty` | Privacy/IP/compliance risk, chain-of-title uncertainty, volatile terms |
| `ConflictPenalty` | Buyer/publisher conflicts, exclusivity, sponsored-discovery separation |

### 4.4 Budget-aware routing

Use a two-stage policy:

1. **Cheap-first probe:** free/open/owned sources can answer only if they satisfy quality and citation thresholds.
2. **Paid escalation:** if confidence, freshness, or citation coverage remains below threshold, call the paid source if expected value exceeds cost.

```text
CallPaidSource if:
  P(success_with_paid - success_without_paid) * TaskValue
  > SourceCost + LatencyCost + ComplianceCost + UserFrictionCost
```

This matters commercially: if the agent calls paid sources too early, buyers will see the exchange as COGS bloat. If it calls too late, publishers see little volume and buyers see no quality improvement.

---

## 5. Proving that a paid source improved outcomes

The exchange should require pre-registered evaluation metrics before claiming uplift.

### 5.1 Evidence ladder

| Evidence level | What it proves | Use |
|---|---|---|
| L0 - Anecdote | User says source helped | Marketing only; not product proof |
| L1 - Trace comparison | Same trace with and without source differs | Debugging; weak proof |
| L2 - Offline benchmark | Curated task set shows better answers with source | Supplier evaluation |
| L3 - Shadow mode | Paid source is retrieved but hidden; compare would-have-routed vs. actual | Safe pre-production |
| L4 - A/B test | Similar live tasks randomly get paid-source access or baseline | Buyer ROI proof |
| L5 - Outcome-linked commercial metric | Uplift tied to time saved, escalations avoided, conversion, compliance accuracy | Renewal/pricing proof |

### 5.2 Metrics by workflow

| Workflow | Primary metric | Secondary metrics |
|---|---|---|
| Legal research/drafting | citation correctness and authority coverage | attorney edits, hallucination rate, time saved |
| Clinical decision support | guideline-concordant answer rate | escalation rate, citation completeness, safety review |
| Finance/private markets | factual accuracy and freshness | analyst edits, retrieval latency, source conflict resolution |
| Supplier compliance | false-positive/false-negative review outcome | audit completeness, reviewer time, escalation quality |
| Construction code | jurisdiction-correct citation | plan-review defects caught, code section accuracy |
| Scholarly research | full-text evidence coverage | paywall gaps, citation diversity, retraction handling |

### 5.3 Experimental design

1. **Define task cohort:** same workflow, user role, geography, and risk tier.
2. **Freeze baseline:** existing tools/search/owned data.
3. **Pre-register metrics:** e.g., "reduce manual escalations by 20%" or "raise citation-supported answer score from 0.75 to 0.90."
4. **Randomize or shadow:** avoid cherry-picking tasks where the source obviously helps.
5. **Blind human reviewers where possible:** reviewers judge answer quality without seeing whether a paid source was used.
6. **Attribute cost:** count data cost, latency, support burden, and compliance overhead.
7. **Track negative outcomes:** paid sources can be stale, noisy, or over-authoritative.

### 5.4 Avoid false uplift

- Do not count **source usage** as success. Count task outcomes.
- Do not count **more citations** as success if citations are irrelevant.
- Do not compare paid source against a deliberately weak baseline. Compare against the buyer's actual workflow.
- Do not let sponsored or high-margin sources influence evaluation.
- Do not use aggregate "answer satisfaction" where legal/clinical/compliance correctness is the real metric.

---

## 6. Matching engine MVP

### 6.1 What to build first

For the first pilot, build:

- Event schema for gap signals and retrieval/outcome events.
- Thin source catalog with source slices and license terms.
- Rules-based hard filters for policy, license, budget, and eligibility.
- Weighted scoring for permitted sources.
- Human-reviewed source recommendations for new unmet needs.
- Offline eval harness for baseline vs. paid-source outcomes.
- Audit trail linking each paid retrieval to license, source version, citation metadata, and outcome.

### 6.2 What not to build first

- Fully automated publisher acquisition from query logs.
- Cross-buyer black-box model trained on sensitive prompts.
- Dynamic pricing recommendations using nonpublic publisher data.
- Sponsored ranking in the primary quality path.
- Expensive graph ML before there are enough labeled outcomes.

### 6.3 Privacy and commercial boundaries

Buyer task traces may include privileged, PHI, customer, or trade-secret information. The exchange should store normalized gap metadata by default, not raw prompts, and should make cross-buyer aggregation opt-in and contractually explicit.

Recommended privacy-preserving event pattern:

```json
{
  "event_type": "gap_signal",
  "workflow": "supplier_onboarding",
  "need_type": "entity_risk_profile",
  "failure_type": "low_confidence",
  "jurisdiction": "US",
  "freshness_requirement": "7d",
  "task_value_band": "medium",
  "raw_prompt_stored": false,
  "trace_pointer": "buyer_owned_trace_id",
  "aggregation_permission": "anonymized_category_only"
}
```

---

## 7. Is the demand graph a moat?

### 7.1 Claimed moat

The bullish claim: the exchange observes cross-agent demand, learns which proprietary sources improve outcomes, then uses that data to onboard supply and route demand better than anyone else.

### 7.2 Skeptical assessment

| Potential advantage | Skeptical read | Initial moat strength |
|---|---|---:|
| Query/gap logs | Buyers may not share sensitive traces; platforms already see richer logs | Weak |
| Source performance data | Valuable only after enough paid calls and outcome labels | Weak initially, potentially strong later |
| Cross-buyer demand aggregation | Contract/privacy limits may prevent useful pooling | Weak to potentially strong |
| Supplier acquisition roadmap | Useful BD input, but not hard to replicate from market demand | Weak |
| Outcome-labeled source ranking | Harder to replicate if truly workflow-linked and proprietary | Potentially strong |
| License + policy graph | Useful operational asset; clouds can imitate | Moderate |
| Network effects | Multi-homing by buyers and publishers weakens exclusivity | Weak initially |

### 7.3 When it becomes real

The demand graph becomes a real asset only if all are true:

1. Multiple buyers allow the exchange to aggregate normalized gap/outcome events.
2. The exchange sees enough volume in one vertical to learn source-specific uplift.
3. Publishers care about the graph because it directs incremental paid demand.
4. Buyers care because ranking saves money or improves measurable outcomes.
5. Data rights allow the exchange to retain and use the metadata after individual transactions.
6. Competitors cannot observe the same workflow outcomes through agent platforms, cloud logs, or direct vendor APIs.

Until then, "demand graph" is mostly a story for investors.

---

## 8. Strategic recommendation

Use the demand graph as an **internal operating system for a vertical pilot**, not as the headline product.

Good first claim:

> "We instrument where your agent lacks authoritative data, route only when license/policy/budget permit, and prove whether paid sources improve your workflow."

Bad first claim:

> "We have a proprietary demand graph for all AI agents."

The second claim will not be credible until the exchange has volume, outcomes, and contracts that let it learn across participants.

---

## Sources

- Model Context Protocol specification, 2025-11-25. Defines MCP primitives: tools, resources, prompts; also emphasizes user consent and that hosts must treat tools/resource descriptions carefully. `https://modelcontextprotocol.io/specification/2025-11-25`
- MCP Registry preview, 2025-09-08. Supports MCP discovery/registry context but not licensing/settlement sufficiency. `https://blog.modelcontextprotocol.io/posts/2025-09-08-mcp-registry-preview/`
- Cloudflare, "Making AI search smarter," 2026-07-01. Supports Pay Per Use experiments and the claim that crawling is a crude value proxy. `https://blog.cloudflare.com/making-ai-search-smarter/`
- Cloudflare, "Announcing the Monetization Gateway," 2026. Supports edge-enforced charging for pages, datasets, APIs, and MCP tools via x402. `https://blog.cloudflare.com/monetization-gateway/`
- Cloudflare Agents docs, x402 payments, modified 2026-06-03. Supports HTTP 402 payment flow and MCP paid-tool examples. `https://developers.cloudflare.com/agents/tools/payments/x402/`
- Coinbase x402 GitHub README. Defines resource server, client, facilitator, 402 payment challenge, verification, and settlement flow. `https://github.com/coinbase/x402`
- Existing project sources: `03-market-demand.md`, `06-agent-targets.md`, `08-licensing-agreements.md`, and `11-legal-risks.md`.
