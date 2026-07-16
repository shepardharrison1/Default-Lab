# Product Definition

**Research date:** 2026-07-16  
**Posture:** Narrow, falsification-seeking definition for pilot design.

## One sentence

An on-demand proprietary-data resolution layer detects when a coding or automation agent is blocked by a specific missing licensed data asset, obtains least-privilege access to that asset from an authorized rights holder, returns only the minimal answer needed for the task, meters usage, preserves provenance, and settles payment.

## One paragraph

The product is a workflow-embedded entitlement and data-access broker for agent failure nodes, not a general data marketplace. It sits inside a coding/automation run through MCP, SDK, API, or host integration; observes failed or uncertain steps; classifies whether the blocker is plausibly data-caused; maps the missing data to an approved provider; checks whether the buyer already has rights; obtains or confirms transaction terms; retrieves only the bounded response required for the task; prevents bulk extraction; records provenance and policy constraints; charges the buyer; and pays the data owner. Its best use case is not public library documentation but vertical domain-rule and reference data that changes outcomes in regulated or high-value workflows, such as healthcare RCM claim edits, construction code checks, compliance screening, product compatibility, local regulations, payer policy, or other entitlement-gated operational knowledge.

## One page

The proposed product is a **licensed minimal-access resolution layer for data-caused agent failures**. It begins with a coding or automation agent attempting a task: implement a claim-precheck workflow, generate a compliance-screening integration, validate a construction-code rule, map an EDI schema, or automate a domain-specific business process. The agent hits a failure node: tests fail, a tool returns an unknown code, the model expresses uncertainty, generated logic uses stale assumptions, retrieved public docs are insufficient, or a human reviewer flags that the answer depends on a proprietary rule set. The product's job is to decide whether the failure is a data problem, whether the missing data is externally obtainable, whether the buyer has or can obtain rights, and whether a minimal licensed answer can unblock the task.

The product is **not** the data corpus. It is the routing, rights, access-control, metering, and provenance layer that connects a failure event to a rights holder without giving the agent or buyer the whole dataset. The core unit is a **resolution event**, not a dataset sale: "For payer X, CPT Y, modifier Z, place of service Q, and date D, does this rule set permit the claim and what edit code applies?" or "For product A in jurisdiction B, what standard or compatibility constraint blocks installation?" The answer should be scoped, logged, attributable, and priced.

The strategic requirement is to preserve both sides' incentives. Buyers need agent workflows that complete correctly without ad hoc procurement or manual research. Data owners need revenue without losing their moat through extraction or unlimited redistribution. Agent hosts need a clean tool call that respects enterprise policy. The broker earns money only if the licensed call resolves failures that free search, public docs, existing entitlements, or human clarification cannot resolve.

## What it is

- A **failure-triggered data-access broker** embedded in coding and automation workflows.
- A **rights and entitlement gateway** that checks buyer permissions before new purchases.
- A **least-privilege retrieval service** that returns bounded answers or transformations rather than complete datasets.
- A **metering and settlement layer** for per-query, per-resolution, or contracted usage.
- A **provenance and audit layer** that records source, license, time, version, policy constraints, and downstream use.
- A **content-protection layer** that rate-limits, thresholds, redacts, aggregates, or transforms responses to reduce extraction risk.
- A **vertical-domain connector layer** for data owners whose APIs or datasets are hard for coding agents to discover, license, or safely call.

## What it is not

Explicit exclusions:

- Not a **generic dataset marketplace**.
- Not a **training-data marketplace**.
- Not **pay-per-crawl**.
- Not an **MCP registry**.
- Not an **API marketplace**.
- Not generic **RAG**.
- Not **x402** or a payment protocol company.
- Not a **consulting firm**.
- Not an **observability-only platform**.
- Not a business for **selling complete datasets**.
- Not a replacement for Context7-style public documentation retrieval.
- Not a broad search engine for agents.
- Not a universal procurement layer for all enterprise data.

## The ten-step loop

1. **Detect**: Observe an agent run, trace, test failure, tool error, uncertainty marker, reviewer note, or repeated failed attempt.
2. **Classify**: Decide whether the failure is plausibly caused by missing, stale, low-authority, conflicting, legally unavailable, or entitlement-gated data.
3. **Discover**: Map the missing data need to candidate data owners, APIs, listings, internal entitlements, or free substitutes.
4. **License check**: Determine whether the buyer already has rights through existing contracts, subscriptions, enterprise accounts, or public licenses.
5. **Negotiate**: If rights are absent, price and authorize use through pre-negotiated terms, dynamic quote, buyer policy, or human approval.
6. **Minimal access**: Retrieve only the narrow answer, transformation, validation, or citation needed to unblock the task.
7. **Prevent extraction**: Apply thresholds, row limits, response shaping, redaction, aggregation, watermarking, caching policy, and anomaly detection.
8. **Meter**: Record query count, resolution event, data volume, rights holder, buyer, project, and price basis.
9. **Provenance**: Attach source, timestamp, version, license terms, permitted downstream uses, confidence, and audit trail to the agent output.
10. **Settle**: Invoice the buyer, pay the data owner, reconcile refunds/failed calls, and report usage to both sides.

## Participants and value flow

### Coding or automation user

Wants a task completed correctly. Receives a bounded answer, code patch, validation result, or implementation guidance with provenance. Pays directly or through an employer budget only when the licensed data changes outcome quality.

### Agent host or IDE

Owns the workflow surface and approval UX. Sends failure traces or tool calls to the broker. Gains higher task completion in vertical workflows without building every data-owner relationship itself. May take a platform fee or require the broker to run as an MCP/tool integration.

### Buyer organization

Controls policy, budget, data-use permissions, audit needs, and procurement constraints. Values fewer failed automations, reduced compliance risk, fewer denied claims, faster implementation, and traceable source use.

### Data owner / rights holder

Provides proprietary rules, standards, dictionaries, schemas, benchmarks, market data, compatibility data, or operational reference data. Receives metered revenue while limiting extraction and preserving dataset value.

### Broker

Performs classification, routing, entitlement checks, minimal retrieval, policy enforcement, metering, provenance, and settlement. Captures margin on paid resolution events or charges SaaS fees for enterprise control-plane use.

### Observability/eval provider

May provide traces and failure clusters. Receives integration value but does not necessarily participate in data revenue unless bundled.

## MVP

The MVP should be one vertical and one failure class. A plausible MVP:

- Host surface: MCP server plus lightweight SDK/webhook for trace intake.
- Vertical: healthcare RCM claim edits or compliance screening.
- Data supply: one or two licensed providers with pre-negotiated terms.
- Trigger: failed implementation/test/reviewer annotation that requires a domain-rule answer.
- Classifier: conservative rules plus human-in-the-loop confirmation, optimized for precision over recall.
- Entitlement check: buyer API key/subscription check before paid purchase.
- Retrieval: provider API call or curated lookup returning a bounded answer.
- Output: agent-readable result with citation, version, license constraints, and confidence.
- Protection: rate limits, per-account thresholds, no bulk export, logging, and anomaly review.
- Commercial: per-query or per-resolved-event fee, with explicit free-substitute comparison.
- Evaluation: before/after completion rate on a known task set.

## Deferred

- Dynamic multi-provider negotiation.
- Large horizontal data-owner network.
- Fully automated failure-causality classification.
- General-purpose dataset search.
- Training-data licensing.
- Cross-agent portable identity and wallet.
- Complex revenue-share clearinghouse.
- Open-ended natural-language procurement.
- Autonomous spend without enterprise policy.
- Long-tail vertical support.
- On-premise data clean rooms unless required by the first pilot.
- Model fine-tuning or synthetic-data generation.

## Success metrics

### Metrics that would prove the thesis

- **Classifier precision:** At least 70-80% of broker-triggered events are confirmed as data-caused by expert review in the pilot vertical.
- **Incremental resolution lift:** Licensed calls resolve at least 25-40% more blocked vertical tasks than free search, public docs, Context7-style docs, or asking the model to retry.
- **Buyer willingness to pay:** Buyers approve paid calls or contracts at prices that support data-owner payouts, broker margin, and support costs.
- **Repeatable supply:** More than one rights holder agrees to minimal-access terms with extraction controls.
- **Cross-provider routing:** The same detection and entitlement loop works across at least two data owners in the same vertical.
- **Moat preservation:** Data owners accept that responses do not leak enough corpus value to undermine their core business.
- **Workflow pull:** Agent users invoke the broker during real implementation work, not just in demos.
- **Platform tolerance:** At least one coding/automation host allows the integration without immediately replacing it with a first-party equivalent.

### Metrics that would prove only that wrapping one API works

- One Optum-like or OpenSanctions-like API is easier to call through an MCP wrapper.
- A demo agent can call one provider endpoint when explicitly instructed.
- Users like having one curated connector.
- A single buyer pays for integration labor.
- The broker improves documentation for one API.
- The system logs provenance for one provider but cannot classify failures or route alternatives.
- Success depends on human consultants deciding when to call the data source.
- Revenue is services-heavy or entirely tied to one data-owner reseller agreement.

If the pilot achieves only the second set, it supports a vertical integration business, not the broader data-failure resolution thesis.
