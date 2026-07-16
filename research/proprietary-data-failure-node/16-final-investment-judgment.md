# Final Investment Judgment

**Research date:** 2026-07-16  
**Posture:** Decisive and skeptical.  
**Final recommendation:** **Pursue only through a narrow pilot.**

## One-page judgment

The broad company thesis should be rejected: a horizontal platform that detects all coding-agent failure nodes and brokers all missing proprietary data is unlikely to become an independent, durable company. Most serious coding-agent failures are not externally purchasable data failures. The coding-agent-specific detection layer is likely an infrastructure feature of Cursor, Claude Code, GitHub Copilot, Devin, Augment, OpenAI Codex, LangSmith, Langfuse, Braintrust, Datadog, or similar workflow/observability incumbents. The payment and MCP layers are also being commoditized by x402, Stripe/MPP, Zuplo, Cloudflare, xpay, and direct provider MCP endpoints.

The remaining company-shaped opportunity is narrower: a vertical licensing, entitlement, provenance, and outcome-measurement gateway for a few high-value domain-rule workflows where agents repeatedly fail because the next correct implementation step depends on licensed, externally owned, authoritative data. Even there, the likely outcome is a small-to-medium vertical software or services-heavy company unless the team proves repeatable paid demand, rights-holder trust, and outcome-linked data that incumbents cannot easily reproduce.

Therefore: **Pursue only through a narrow pilot.**

## Decisive answers

### Independent company, vertical product, infrastructure feature, or services business?

**Answer: vertical product or services-heavy vertical company; not a horizontal infrastructure company.**

- The **failure-node detection layer** is most likely an infrastructure feature inside coding-agent hosts and observability platforms because they own traces, tool calls, test failures, user accept/reject signals, repo context, identity, and policy controls.
- The **brokerage layer** could be an independent vertical product if it owns specific data-owner terms, rights enforcement, provenance, and outcome evidence in one workflow.
- If revenue comes mostly from integrating existing buyer entitlements and negotiating one-off source deals, it is a **services business** with software tooling, not a venture-scale marketplace.

### Strongest initial vertical?

**Compliance / sanctions / KYB automation coding.**

It is the cleanest first falsification vertical because:

- failures are often data-caused: entity matching, watchlist freshness, beneficial ownership, PEP/adverse-media, jurisdictional source coverage;
- outputs can be evaluated with labeled cases and compliance-review outcomes;
- privacy risk exists but is lower than PHI-heavy healthcare claims if the pilot uses company/entity screening and minimized personal data;
- OpenSanctions provides public API/pricing/licensing evidence and yente/MCP adjacency;
- premium adjacent sources exist for company data, UBO, adverse media, and risk intelligence.

Healthcare RCM is high-value but should be second unless a buyer brings existing entitlements and synthetic/deidentified claim fixtures. HIPAA/PHI, CPT licensing, payer contracts, and Optum/Change concentration can consume the pilot before the failure-node thesis is tested.

### Exact failure node to test first?

**A coding/automation agent implementing a KYB or supplier-risk screening workflow cannot determine whether a candidate entity match is current, authoritative, and disposition-ready using public sources alone.**

Narrow test:

- Task: implement or modify a KYB screening flow for companies and related officers/beneficial owners in 2-3 jurisdictions.
- Failure node: agent generates generic screening code but cannot resolve ambiguous matches, alias/transliteration conflicts, source freshness, list provenance, or jurisdiction-specific disposition rules.
- Missing data: subject-bounded sanctions/PEP/watchlist match evidence, source/version metadata, company registry or UBO enrichment where available, and provenance constraints.
- Resolution call: `validate_screening_match` or equivalent MCP/API tool returning match status, evidence, source version, confidence, and permitted-use receipt.

### First realistic buyer?

**A mid-market KYB/compliance SaaS, supplier-risk workflow company, or fintech onboarding engineering team using coding agents to build screening automations.**

Best buyer profile:

- already experimenting with Cursor, Claude Code, Copilot, Codex, Devin, or internal agents;
- lacks mature multi-provider agent access controls;
- has compliance reviewers who can label failures;
- can approve a paid pilot without full bank-scale procurement.

Named target classes, not claimed relationships: ComplyAdvantage-class KYB tools, Alloy/Persona/Middesk/Socure/Sumsub-style onboarding teams, supplier-risk teams such as Zip/Coupa/Ariba-adjacent workflows, or fintech compliance-engineering teams.

### First realistic data owner?

**OpenSanctions first, with one optional premium enrichment provider only if obtainable quickly.**

Why:

- public API/pricing evidence: hosted screening API at EUR 0.10/query;
- commercial licensing and reseller/OEM posture are visible;
- yente and yente-client provide open-source/API/MCP-adjacent implementation routes;
- the data and workflow are concrete enough to test per-query economics and direct-vs-broker behavior.

OpenSanctions may not be proprietary enough to prove the full moat. That is acceptable for the first 30-90 days because the first test is not defensibility; it is whether a data-failure resolution workflow can be detected, called, measured, and sold above source cost. A second source would test multi-provider routing and proprietary-supply leverage.

### Why buyer won't go direct?

**Only if the buyer values agent-specific workflow controls more than a single API integration.**

The buyer will not go direct if the broker provides:

1. normalized agent-readable responses across more than one source;
2. automatic entitlement checks against existing subscriptions before spending;
3. provenance receipts tied to code diffs, traces, and compliance review;
4. spend caps and approval UX inside the agent workflow;
5. outcome evidence showing which source resolved which failure;
6. lower integration and policy burden than connecting each provider's API/MCP server.

Skeptical caveat: if the buyer needs only OpenSanctions, or already has LSEG/Dow Jones/LexisNexis/Moody's/Orbis/D&B contracts, the buyer probably goes direct. The pilot must explicitly test willingness to pay for the intermediary after showing direct-source pricing.

### Weakest assumption?

**That data-caused failures can be detected with enough precision and occur often enough in one vertical to justify paid intervention.**

The second-weakest assumption is buyer willingness to pay a broker margin when the source already exposes an API, MCP server, Snowflake listing, Cloudflare route, or direct enterprise contract.

### Strongest supporting evidence?

1. **API drift research supports the value of current external documentation**: arXiv 2604.09515 reports executable code rates around 42.55% without comprehensive documentation and 66.36% with structured documentation in evolving API tasks. That supports "current context helps," while also showing context alone does not solve all failures.
2. **Context7 proves coding agents adopt context-retrieval tools**: Upstash/Context7 exposes version-specific docs through MCP/CLI for Cursor/Claude/VS Code-style workflows.
3. **Agent observability is mature enough to supply traces and evals**: LangSmith and Langfuse already trace tool calls, runs, costs, evaluations, and failure modes.
4. **Inference-time licensing and payment rails are real**: Sphere, xpay.sh, Cashmere Fiber, Redpine, Cloudflare Pay Per Crawl/Human Native, x402, and Zuplo all show pieces of paid agent/data access.
5. **Vertical data already sells per query or via APIs**: OpenSanctions EUR 0.10/query and Optum Real Claim Pre-Check/Claims Edit examples show real paid data/API economics in compliance and healthcare workflows.
6. **Snowflake CKE content protection proves enterprise packaging exists**: licensed proprietary content can be distributed with content-protection thresholds and later exposed through managed MCP-style governed tools.

### Evidence that contradicts thesis?

1. **Most coding-agent failures are not data failures**: the Augment/Osmani 80% problem points to production-readiness gaps such as security, observability, rate limits, retries, audit logging, PII handling, and architecture. Those are not solved by buying proprietary data.
2. **Public-doc failures are being commoditized**: Context7-class tools directly address stale library/API docs, shrinking the easiest coding wedge.
3. **Platforms own the detection surface**: coding agents and observability vendors see better telemetry than a broker can.
4. **Data owners can go direct**: OpenSanctions/yente MCP, Reuters MCP, Stack Overflow MCP, PitchBook connectors, ICC Code Connect, and Optum APIs demonstrate direct distribution.
5. **Cloudflare internalized Human Native**: broad AI data licensing has infrastructure-acquirer gravity.
6. **Snowflake/cloud marketplaces already solve enterprise data distribution**: they do not solve coding failure detection, but they constrain the independent broker's role.
7. **Multi-homing is natural**: buyers, data owners, and tools will use many marketplaces and protocols, compressing take rates.

### What justifies $500k?

Only a falsification-oriented pilot budget, not a company build-out.

Release $500k if, within about 90 days, the team can show:

1. one paid buyer or written paid-pilot commitment in compliance/KYB;
2. one signed data-owner pilot term sheet permitting agent-mediated use;
3. 50-100 labeled tasks/traces with expert labels for data-caused vs non-data failures;
4. a working MCP/API tool that performs entitlement check, bounded retrieval, provenance receipt, metering, and audit logging;
5. pre-agreed rejection thresholds and renewal price before the pilot begins;
6. counsel-reviewed terms for chain-of-title, no-training, retention, no-redistribution, subprocessors, and liability.

Use of funds: founder time, one senior engineer/contractor, security/legal review, pilot integration, source fees, and evaluation. Do not fund horizontal marketplace features.

### What justifies $5M?

Only clear vertical traction, not a promising demo.

Raise $5M only if all are true:

1. at least 3 paying customers in one vertical;
2. repeat usage across comparable failure classes, not one-off services;
3. broker gross margin survives source payouts, support, legal, payment, and channel costs;
4. at least two data sources reuse the same entitlement/provenance/eval architecture;
5. buyer renewals cite audit/provenance/outcome evidence, not just API convenience;
6. data owners accept anti-extraction controls and renew;
7. platform access is not blocked, taxed away, or copied into a host-native feature;
8. the company has permissioned, outcome-linked data it can aggregate without exposing buyer/source secrets.

### Immediate rejection criteria?

Reject immediately if any one occurs:

1. fewer than 70% of triggered pilot events are confirmed as data-caused by expert review;
2. licensed access does not materially outperform public/free/direct/BYO baselines;
3. no buyer will name a price above source cost after seeing direct API economics;
4. no rights holder will sign agent-use terms with no-training, no-redistribution, retention, and audit controls;
5. the first vertical requires broad corpus access that rights holders view as extraction;
6. founders insist on a horizontal marketplace, public-doc wedge, payment-protocol company, or generic observability platform;
7. legal review identifies unresolved chain-of-title, PHI/privacy, or reseller/OEM blockers in the chosen pilot.

### Can it be a $100M company?

**Yes, but only as a disciplined vertical company.**

Path to $100M:

- default compliance-grade access/control plane for agent-built KYB/supplier-risk/compliance automations;
- expansion from sanctions/watchlists to company registry, UBO, adverse media, and risk intelligence;
- enterprise contracts priced by workflow/control-plane value, not pennies per call;
- sticky audit/provenance/eval records;
- several broker-friendly data sources and one or two channels.

This is possible but far from proven.

### Can it be a $1B company?

**Unlikely as an independent company.**

A $1B outcome requires becoming the cross-vertical standard for agent-data procurement, rights enforcement, budgets, source ranking, and settlement across many platforms. That requires scarce supply, outcome data, platform tolerance, regulatory tailwinds, and multi-vertical network effects. The current evidence suggests each component is being internalized by platforms, clouds, gateways, observability vendors, or data owners.

More plausible: a $50M-$300M acquisition if the company owns one vertical's agent-data control plane and outcome evidence.

### Who commoditizes it?

- **Coding-agent hosts:** Cursor, Claude Code, GitHub Copilot, OpenAI Codex, Devin/Cognition, Augment.
- **Agent observability/eval platforms:** LangSmith, Langfuse, Braintrust, Phoenix, Datadog.
- **Cloud/data marketplaces:** Snowflake, AWS Data Exchange, Databricks Marketplace.
- **Web/gateway/payment infrastructure:** Cloudflare, Stripe, x402 facilitators, Zuplo, xpay.
- **Data owners themselves:** OpenSanctions, Reuters, Stack Overflow, ICC, Optum, LexisNexis, LSEG, Dow Jones, PitchBook.

### Who acquires it?

Most plausible acquirers if vertical traction exists:

| Acquirer | Why |
| --- | --- |
| Cursor / Anysphere | Adds vertical data-resolution tools and outcome evidence inside coding workflows. |
| Anthropic | Extends Claude Code/MCP ecosystem with governed proprietary-data access. |
| Microsoft / GitHub | Combines Copilot, repos, enterprise controls, and licensed data access. |
| Cloudflare | Extends Pay Per Crawl, Monetization Gateway, and Human Native into structured agent data. |
| Snowflake | Adds coding/agent failure-triggered demand to CKE and managed MCP. |
| Databricks | Adds agent-data procurement and MCP routing into marketplace/governance stack. |
| Stripe | Adds licensed-data commerce on top of machine payments if workflow demand is proven. |
| Compliance/KYB data vendor | Buys agent-workflow distribution and provenance for its own data products. |

### What must be tested within 30 days?

1. **Buyer WTP test:** 10 compliance/KYB/supplier-risk buyer interviews with explicit direct-vs-broker pricing. Ask: "Would you pay X above the source price for agent-specific entitlement, provenance, and outcome evidence?"
2. **Supply permission test:** 5 data-owner calls, starting with OpenSanctions. Ask for written permission or redlines for agent-mediated use, reseller/OEM, no-training, retention, and audit.
3. **Trace classification test:** collect or simulate 30-50 agent tasks and have domain experts label data-caused vs non-data failures.
4. **Thin integration:** MCP/API wrapper around one screening endpoint with entitlement check, spend cap, provenance receipt, and metering ledger.
5. **Baseline test:** run the same tasks with public sanctions lists, web search, direct OpenSanctions call, and broker-routed call.
6. **Kill review:** by day 30, decide whether enough signal exists for a 90-day paid pilot. If no buyer names a broker fee or no data owner permits agent use, stop.

## Alternatives considered

### Alternative 1: Reframe as vertical software

This is the most credible fallback. Build compliance/KYB workflow software for agent-assisted screening implementation, with data connectors, audit logs, eval suites, and provenance. The product would sell to compliance-engineering teams rather than pitch a neutral cross-agent marketplace.

**Why not choose it immediately?** It may be the right destination, but the narrow pilot can test whether brokerage/control-plane economics exist before committing to full vertical SaaS.

### Alternative 2: Reframe as feature/partnership

Package the product as an MCP tool, rights registry, or provenance plugin for Cursor, Claude Code, LangSmith, Langfuse, Braintrust, Snowflake, or Cloudflare.

**Likely truth:** the coding-agent-specific failure-node detection layer is an infrastructure feature; partnership may be the natural route.  
**Why not choose it immediately?** A feature partnership has little leverage without proof that a vertical data call resolves real failures and buyers pay.

### Alternative 3: Pause

Pause if the team cannot secure a real buyer trace set or data-owner permission in 30 days.

**Why not default to pause now?** The compliance/KYB pilot is narrow enough to test cheaply, and OpenSanctions-class supply plus MCP/observability tooling means the first falsification loop is feasible.

### Alternative 4: Reject

Reject the horizontal founding strategy now. Reject any plan centered on generic public docs, payment rails, MCP registry, training-data marketplace, or broad data marketplace.

**Why not reject the entire idea immediately?** There is enough evidence of paid data APIs, licensed inference infrastructure, agent observability, MCP adoption, and vertical domain-rule failures to justify one narrow pilot. That pilot should be explicitly designed to kill the thesis if the economics or detection fail.

## Final recommendation

**Pursue only through a narrow pilot.**

Reject horizontal founding strategy. Test one compliance/KYB failure node, one buyer, one data owner, one MCP/API path, and one outcome metric before investing beyond pilot scale.
