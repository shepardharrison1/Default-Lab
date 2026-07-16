# Go-to-Market Plan

**Research date:** 2026-07-16  
**Posture:** Narrow, skeptical, evidence-seeking. Do not sell a horizontal marketplace before the vertical proof exists.  
**Verdict tie-in:** **Pursue only through a narrow pilot.**

## Bottom line

The go-to-market motion should not start with "a marketplace for all proprietary data agents need." It should start with one vertical workflow where coding/automation agents demonstrably fail because licensed data is missing and where buyers pay above direct source cost for routing, rights, audit, and measurable improvement.

Recommended first market:

- **Compliance/KYB and supplier-screening automation.**
- Buyer class: KYB/compliance SaaS, fintech onboarding teams, procurement/supplier-risk teams, or enterprises building supplier screening automations with coding agents.
- Supply: OpenSanctions plus one complementary KYB/company/risk source.
- Channel: direct enterprise pilot first; coding-agent integrations as workflow surface, not primary buyer.

Do **not** sell:

- horizontal data marketplace;
- demand-graph ML;
- generic MCP registry;
- ads or publisher monetization;
- public documentation retrieval;
- one-off API wrappers;
- autonomous procurement wallet;
- training-data exchange.

## Positioning

### What to say

> We help coding and automation agents resolve narrow compliance/KYB failure nodes by routing them to licensed, source-versioned data with entitlement checks, provenance, budget controls, and outcome measurement.

### What not to say

Avoid:

- "Agents will buy data autonomously."
- "A marketplace for every missing fact."
- "We monetize the agent demand graph."
- "We let data owners expose data safely to all agents."
- "We are x402/Stripe for data."
- "We are an MCP registry."
- "We replace direct data contracts."
- "We guarantee compliance decisions."

The credible claim is smaller: for one vertical workflow, the broker may reduce incorrect automation logic and audit gaps by connecting a failure to a licensed minimal answer.

## Target customer profiles

### Primary buyer

Compliance/KYB SaaS or procurement/supplier-risk software team using coding agents to build:

- company screening;
- supplier onboarding;
- beneficial-owner checks;
- sanctions/PEP screening;
- adverse-media/risk workflow;
- case management or audit evidence.

### Secondary buyer

Enterprise automation team in:

- fintech;
- banking;
- marketplace operations;
- procurement;
- vendor risk;
- crypto/compliance;
- regulated B2B SaaS.

### Avoid initially

- Horizontal coding-agent platforms as first buyer.
- Giant banks with long model-risk/procurement cycles unless they bring a ready pilot.
- Premium data owners without buyer pull.
- Healthcare RCM unless the buyer brings existing entitlements and deidentified/synthetic eval data.
- General market-intelligence or research teams.

## Channel strategy

### Direct enterprise first

Direct enterprise is necessary because the buyer must:

- approve the data use;
- provide real coding/automation workflow traces;
- pay above direct data cost;
- participate in evaluation;
- accept audit/legal terms;
- judge whether outputs improve quality.

Without buyer pull, a data-owner or agent-platform channel will likely reduce the product to a connector.

### Coding agents as workflow channels

Cursor, Claude Code, GitHub Copilot/VS Code, OpenAI Codex, Devin, and Windsurf are important surfaces because the failure occurs there. They are not the first customer unless they agree to a vertical paid pilot.

Use them as:

- MCP/API integration surfaces;
- trace/event sources;
- approval UX;
- distribution proof for later.

Do not depend on them for defensibility. They can internalize generic diagnosis.

### Data owners as supply partners

Approach data owners only with a narrowly scoped buyer use case:

- subject-bounded queries;
- no bulk export;
- no training;
- source-hosted access;
- provenance;
- usage reports;
- anomaly controls;
- a named buyer/pilot budget.

Do not ask a premium provider to join a speculative horizontal marketplace.

## Pricing and packaging

### Pilot package

**KYB Failure-Node Pilot**

- 90 days.
- `$30k-$75k` pilot fee.
- One buyer workflow.
- One agent host.
- OpenSanctions plus one complementary source if obtainable.
- 50-100 eval tasks.
- Monthly data pass-through.
- 20-30% buyer service fee on data spend or explicit platform fee allocation.
- Final outcome report and renewal proposal.

### Production package after successful pilot

**Vertical Resolution Gateway**

- `$50k-$250k/year` platform contract.
- Included:
  - entitlement gateway;
  - rights registry;
  - agent/MCP/API integration;
  - provenance receipts;
  - budget controls;
  - source registry;
  - audit exports;
  - eval harness;
  - usage and extraction reports.
- Usage:
  - data pass-through at source cost;
  - transparent 20-30% service fee;
  - overage tiers for high-volume sources;
  - optional provider minimums only after demand is proven.

### What not to package

- `$0.01` per call self-serve.
- Card-per-retrieval pricing.
- General wallet for autonomous agents.
- "Unlimited proprietary data."
- Marketplace take rate without source transparency.
- Outcome guarantees without expert review and provider warranties.

## First 30 days

### Goal

Validate whether the market has enough pain and urgency to justify a 90-day paid pilot.

### Interview quotas

Minimum interviews:

- 15 buyer interviews:
  - 5 KYB/compliance SaaS;
  - 5 fintech/onboarding/compliance engineering teams;
  - 3 procurement/supplier-risk teams;
  - 2 enterprise teams using coding agents in regulated automation.
- 8 rights-holder/supply interviews:
  - OpenSanctions;
  - 2 company/registry/firmographic providers;
  - 2 adverse-media/risk/compliance providers;
  - 1 public registry/open data expert;
  - 2 data licensing/legal experts.
- 6 channel interviews:
  - 2 coding-agent/platform teams or ecosystem contacts;
  - 2 agent observability/eval teams;
  - 2 API/MCP/payment/gateway providers.

### Questions to answer

Buyer:

- What coding/automation agents are actually used?
- Which KYB/screening workflows are being built or modified?
- Where do agents fail?
- Are failures caused by missing external data or by requirements, credentials, bugs, or internal systems?
- What direct data providers are already contracted?
- Would a broker fee above direct data cost be approved?
- Who owns budget: engineering, compliance, procurement, product, or data team?
- What audit evidence is required?

Rights holder:

- Can agent-mediated access be licensed explicitly?
- Is subject-bounded access acceptable?
- Can the provider return source/version/provenance metadata?
- Are per-query terms possible?
- Can usage be reported without exposing buyer confidential details?
- What extraction thresholds are required?
- Would they allow output into generated code/tests/audit artifacts?

Channel:

- Can an MCP/API tool run inside the target agent host?
- Can traces be captured with redaction?
- Can enterprise policy approve data-source calls?
- Is there a path to marketplace/channel distribution later?

### LOI target

By day 30:

- 2-3 serious buyer candidates.
- 1 paid pilot LOI or procurement path.
- 1 source commitment from OpenSanctions-like provider or confirmed terms.
- 1 complementary-source candidate with written interest or clear fallback.

### 30-day kill criteria

Stop or narrow if:

- fewer than 3 buyers can name real data-caused agent failures;
- buyers only want one provider MCP wrapper;
- buyers will not pay any platform fee;
- all likely data is already under direct buyer contracts with no broker role;
- rights holders refuse agent-mediated terms;
- no evaluation dataset can be built.

## First 90 days

### Goal

Complete one paid pilot that proves or falsifies the core thesis.

### Workstreams

1. **Buyer pilot**
   - Sign pilot agreement.
   - Define workflow and evaluation tasks.
   - Integrate with one coding-agent environment.
   - Run baseline and intervention.

2. **Supply**
   - Use OpenSanctions as priced anchor where applicable.
   - Add one complementary source or document why not.
   - Establish no-training/no-redistribution/retention/provenance terms.

3. **Product**
   - Build KYB missing-info schema.
   - Build entitlement gateway.
   - Build MCP/API proxy.
   - Build usage ledger and provenance receipts.
   - Build evaluation harness.

4. **Measurement**
   - Label data-caused vs non-data failures.
   - Compare direct API, public-source, and broker routes.
   - Measure correctness, audit completeness, false positives/negatives, and cost.

### Interview/commitment quotas by day 90

- 1 completed or near-completed paid pilot.
- 20 additional buyer discovery calls.
- 5 follow-on renewal/expansion conversations.
- 5 rights-holder conversations beyond first source.
- 2 channel conversations with coding-agent or observability partners.

### Success evidence

- Paid pilot customer asks for renewal or expansion.
- Buyer accepts platform/service fee above data cost.
- At least 70-80% classifier precision on broker-triggered events.
- Measurable improvement over baseline.
- Complementary source adds value or direct evidence shows single-source scope is too weak.
- Rights holder accepts post-pilot usage/extraction report.

### 90-day kill criteria

Kill if:

- no paid renewal path;
- buyer says direct API is enough;
- paid calls do not improve evaluated output;
- legal/security cost overwhelms unit economics;
- source access cannot be licensed repeatably;
- most failures are non-data failures.

## Six months

### Goal

Decide whether there is a repeatable vertical product.

### Targets

- 2-3 paid pilots completed or active.
- 2 renewed customers or one annual contract.
- 2 complementary rights-holder sources signed or in legal review.
- 150-300 labeled failure events.
- 100-200 rights-cleared eval tasks.
- Evidence that at least two buyers share the same failure class.

### Product milestones

- Stable KYB source registry.
- Entitlement gateway with buyer/project/source policies.
- Automated usage reports for data owners.
- Audit export for buyers.
- Basic anomaly detection for extraction-like query patterns.
- Direct comparison mode: public/free vs direct provider vs broker.

### GTM motion

- Founder-led sales only.
- Sell to teams with active coding-agent automation work.
- Use case-specific demos built from rights-cleared tasks.
- No broad self-serve marketplace.
- No long-tail provider onboarding.

### Six-month decision

Continue only if:

- more than one buyer pays;
- source terms are repeatable;
- contribution economics are positive after support/eval;
- buyer renewal is driven by audit/routing/outcome value, not custom integration labor.

## Twelve months

### Goal

Scale one vertical package or stop.

### Targets

- 5-8 paying customers in compliance/KYB/supplier screening.
- `$500k-$1.5M` ARR run-rate if enterprise contracts close.
- 3-5 data-owner/source integrations.
- 500+ labeled failure events.
- 300+ eval tasks.
- At least one channel integration with a coding-agent, observability, or cloud marketplace partner.
- Documented buyer case studies, anonymized if necessary.

### Product expansion

- More source types:
  - sanctions/PEP;
  - adverse media;
  - company registry;
  - beneficial ownership/control;
  - firmographics/supplier identity.
- Better rights policy language.
- Buyer self-service budget controls.
- Source ranking based on outcome evidence.
- Security/compliance package: SOC 2 path, DPA templates, retention controls.

### Sales motion

- Still vertical and founder/early-sales led.
- Sell annual platform contracts.
- Use data pass-through plus transparent service fee.
- Avoid large banks unless inbound with a ready use case.
- Expand from supplier screening/KYB SaaS into adjacent procurement/vendor-risk workflows only if same source stack applies.

### Twelve-month kill criteria

- ARR below threshold and pilots remain services-heavy.
- No second source type becomes material.
- Data-owner economics or legal terms prevent margin.
- Coding-agent hosts internalize the workflow and push startup to commodity connector pricing.
- Buyers keep bypassing broker through direct APIs.

## Twenty-four months

### Goal

Either become the vertical resolution gateway for KYB/compliance agent workflows, expand carefully to one adjacent vertical, or sell/partner as a feature.

### Targets

- `$3M-$8M` ARR if the thesis is working.
- 15-30 enterprise customers.
- 8-12 source integrations in one vertical family.
- 2-3 major channel partnerships.
- Proven renewal rates above 80%.
- Provider retention and low extraction incident rate.
- Source-outcome ranking evidence credible enough to influence routing.

### Possible expansion paths

Only expand if the first vertical has renewal evidence.

Adjacent options:

1. Procurement/supplier risk and SKU compliance.
2. Legal citation validation.
3. Construction code/check citation workflow.
4. Healthcare RCM claims edit pilot, only with existing entitlements and deidentified/synthetic data.

Do not expand into horizontal data marketplace until there is proof of repeatable multi-source vertical demand.

### Strategic outcomes

If successful:

- vertical enterprise SaaS/control-plane company;
- acquisition target for coding-agent platform, cloud marketplace, data marketplace, compliance vendor, or data owner;
- channel partner for Cursor/Copilot/Claude Code/Devin/AWS/Snowflake/Databricks.

If only partially successful:

- specialized MCP/API connector suite;
- compliance data integration services;
- audit/provenance add-on;
- data-owner distribution channel.

If unsuccessful:

- kill before building a marketplace.

## Sales assets to create

### Must have

- One-page pilot brief.
- Failure-node taxonomy specific to KYB.
- Eval rubric.
- Source-control diagram.
- Legal/data-flow diagram.
- Unit economics calculator.
- Sample provenance receipt.
- Sample buyer audit report.
- Sample rights-holder usage/extraction report.

### Do not build yet

- Public marketplace website.
- Provider self-serve onboarding.
- Demand-graph dashboard.
- Ads/monetization pitch.
- Generic MCP registry.
- Consumer wallet UI.
- Broad vertical landing pages.

## Qualification checklist

A lead is qualified only if most are true:

- Uses coding/automation agents for real workflow development.
- Has a specific KYB/compliance/supplier-screening task.
- Can produce failure traces or failed implementation examples.
- Believes missing external data may be the blocker.
- Has or can approve data-source spend.
- Accepts audit/provenance requirements.
- Can participate in 50-100 task eval.
- Can sign a paid pilot within 30-60 days.
- Has a direct-provider baseline to compare against.
- Agrees that a renewal decision will be based on measured lift and economics.

Disqualify if:

- wants generic RAG;
- only needs public docs;
- only needs an API wrapper;
- lacks budget owner;
- cannot share traces or eval tasks;
- the missing data is internal/customer-owned;
- procurement/legal cannot fit a 90-day pilot.

## Messaging by stakeholder

### Engineering leader

"We reduce agent rework in a narrow KYB automation workflow by routing missing licensed data into the agent with structured provenance and tests."

### Compliance leader

"We preserve source/version/audit evidence and prevent unsourced screening logic from entering automation."

### Data/procurement leader

"We check existing entitlements before new spend and expose transparent data pass-through plus service fee."

### Rights holder

"We do not export your corpus. We provide subject-bounded access, budgets, response shaping, provenance, usage reports, and anomaly review."

### Agent platform/channel

"We bring vertical licensed sources and outcome evidence; you keep the developer workflow."

## Final GTM recommendation

For the first year, sell only a **KYB/compliance vertical resolution gateway**. The GTM should be deliberately boring: founder-led enterprise pilots, explicit pricing, signed rights, monthly invoices, measured outcomes, and fast kill gates. If the first two or three buyers will not pay above direct data cost, the startup should not rebrand as a horizontal marketplace. It should stop, become a narrow connector/control-plane product, or move to a different vertical with stronger multi-source demand.
