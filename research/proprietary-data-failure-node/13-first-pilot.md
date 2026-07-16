# First Pilot Design

**Research date:** 2026-07-16  
**Posture:** Falsification-first. The pilot should test the actual thesis, not prove that one API can be wrapped.  
**Verdict tie-in:** **Pursue only through a narrow pilot.**

## Bottom line

The first pilot should be a **Compliance/KYB coding-agent workflow** using **OpenSanctions** plus **one complementary KYB attribute source**. It should target a buyer building supplier, customer, or counterparty screening automation with coding agents. The pilot succeeds only if it proves that the broker can detect real data-caused failure nodes, identify missing information, route to licensed minimal-access sources, improve measurable code/automation quality, preserve data-owner moats, and earn buyer willingness to pay above direct data cost.

Do **not** run a pilot that merely wraps one API in MCP. That would prove a connector, not the thesis.

## Recommended pilot in one paragraph

Run a 90-day paid pilot with a compliance/KYB SaaS team or enterprise supplier-screening automation team using Cursor, Claude Code, Copilot, Devin, Codex, or a comparable coding-agent workflow. The agent must implement or modify a KYB/supplier-screening workflow that screens companies, officers, and beneficial owners. Baseline runs use public lists, public registries, buyer-provided requirements, and direct model reasoning. Intervention runs use a broker tool that classifies data-caused failure nodes, maps them to a missing-info schema, checks entitlement, calls OpenSanctions at its published EUR 0.10/successful-query anchor where applicable, calls one complementary KYB attribute source where licensed, returns a bounded answer with provenance, and logs outcome evidence. Success is a paid renewal after about 90 days at a fee above underlying data cost, plus a measurable reduction in incorrect screening logic, missed audit evidence, or compliance-review defects. Kill if buyers refuse a broker fee once they see direct API pricing.

## Why Compliance/KYB first

Compliance/KYB is the best 90-day test because it combines:

- identifiable rights holders;
- public pricing anchor from OpenSanctions;
- relatively low privacy burden compared with healthcare claims;
- concrete coding/automation workflows;
- objectively reviewable outputs;
- real buyer pain from false positives, false negatives, audit gaps, and onboarding friction;
- potential need for multiple sources, not just one API.

It is still a skeptical choice. Many serious buyers already have direct screening vendors. The pilot must prove broker-specific value: failure detection, multi-source routing, provenance, rights enforcement, budget control, and outcome measurement.

## What actual thesis must be tested

The pilot must test all of the following:

1. **Detection of a real data-related failure node.** The system identifies a failure caused by missing, stale, low-authority, or entitlement-gated KYB/compliance data, not by bad prompts, bugs, missing credentials, unclear requirements, or weak reasoning.
2. **Identification of missing information.** The broker converts vague agent uncertainty into a specific missing-info schema: entity, jurisdiction, list/source type, identifier, ownership question, adverse-media need, source currency, or confidence threshold.
3. **Controlled access to at least one proprietary/paid source.** OpenSanctions provides a usage-priced anchor; the complementary source should add company registry, ownership/control, adverse-media, or firmographic attributes not already covered.
4. **Preferably two complementary sources.** One source alone risks proving a wrapper. Two sources test routing, normalization, rights differences, and incremental value.
5. **Measurable code/automation quality improvement.** The intervention improves implementation correctness, audit trail completeness, false-positive/negative handling, or case-review workflow quality.
6. **Buyer willingness to pay above direct data cost.** The buyer pays a platform/service fee or renewal that exceeds pass-through provider cost.
7. **Rights-holder willingness.** Providers accept subject-bounded, agent-mediated access with no bulk export, provenance, and usage reporting.
8. **Moat preservation.** The access pattern does not leak lists, registries, or source corpus through bulk responses or repeated enumeration.
9. **Repeatable licensing.** Terms are not a one-off consulting exception; they can be repeated with at least one more buyer or provider.
10. **Positive economics.** Data-owner payout, payment processing, model/tool costs, infra, security, legal/licensing, support, failed/refunded calls, and evaluation costs leave positive contribution after a platform minimum or service fee.

## Pilot definition

### Buyer

Primary target:

- Compliance/KYB SaaS vendor, fintech onboarding team, marketplace supplier-risk team, procurement/KYB SaaS, or enterprise building supplier screening automation with coding agents.

Good outreach targets by class:

- Supplier-risk/procurement automation teams.
- KYB/compliance SaaS engineering teams.
- Fintech onboarding engineering teams.
- Enterprise vendor-risk teams experimenting with coding agents.

Named examples are **outreach targets only**, not claimed partners. A Zip-class procurement/KYB workflow is a useful target pattern because supplier screening and vendor onboarding can require company identity, sanctions, ownership, and audit logic. Do not claim any partnership or buyer commitment.

### Rights holders

Minimum:

- **OpenSanctions** for sanctions/PEP/watchlist matching, using hosted API pricing where applicable. OpenSanctions lists EUR 0.10/query for match/reconcile/search style API usage and bills only successful calls.

Complementary source, preferably one:

- company registry/commercial entity source;
- beneficial ownership/control source;
- adverse-media/risk signal source;
- firmographic/supplier identity source;
- D&B/Moody's Orbis/LexisNexis/LSEG/Dow Jones-class premium source if obtainable under narrow terms;
- public registry baseline plus paid normalization provider if premium source cannot be signed inside the pilot.

If no complementary source can be licensed, the pilot should continue only as a **negative test** of whether a single-source wrapper is too weak to monetize.

### Coding workflow

The agent is asked to build or modify a KYB/supplier-screening workflow:

1. Accept a company and associated persons/officers/beneficial owners.
2. Normalize names, aliases, jurisdictions, identifiers, and transliterations.
3. Screen against sanctions/PEP/watchlists.
4. Retrieve or validate company status, registration, and ownership/control attributes.
5. Generate decision logic: clear, possible match, escalate, reject, or missing evidence.
6. Store provenance and source/version metadata.
7. Produce audit artifacts for reviewer/case-management workflow.
8. Implement tests for edge cases: aliases, transliterations, inactive entities, similar names, jurisdiction ambiguity, date/version changes, and beneficial-owner links.

### Failure node

The specific failure node:

> The coding agent can implement generic API plumbing and matching code, but fails to decide when a screened subject is an authoritative match or when the audit trail is sufficient because it lacks current, source-versioned, licensed KYB/compliance data and company/risk attributes.

Examples:

- The agent uses stale public list data.
- The agent treats a fuzzy name match as definitive without source evidence.
- The agent misses a beneficial-owner sanctions relationship.
- The agent cannot distinguish inactive/dissolved/renamed company records.
- The agent cannot produce source/version provenance for audit.
- The agent encodes screening thresholds without jurisdiction/source justification.
- The agent fills logic with placeholders: `TODO: compliance data`.

### Baseline

Baseline conditions:

1. Model/agent only, with repo context and user requirements.
2. Public web/search and public sanctions lists.
3. Public registries where available.
4. Existing generic documentation tools.
5. Buyer-provided static fixtures.
6. Direct OpenSanctions API call if buyer already knows to call it, as a hard substitute baseline.

The pilot should compare against direct API use. If direct provider documentation plus a normal API key achieves the same outcome, the broker is not needed.

### Intervention

Broker intervention:

1. Capture agent run/failure trace or explicit reviewer label.
2. Classify candidate data-caused failure with precision-first rules.
3. Populate missing-info schema:
   - subject type;
   - name;
   - aliases;
   - jurisdiction;
   - registration number or identifier;
   - related persons/entities;
   - screening reason;
   - needed answer type;
   - acceptable source types;
   - public/free sources checked.
4. Check buyer entitlement and budget.
5. Call OpenSanctions and complementary source through source-hosted API or approved endpoint.
6. Return bounded result:
   - match/no-match/possible match;
   - evidence summary;
   - source/version/date;
   - confidence;
   - provenance receipt;
   - permitted-use constraints;
   - human-review flag.
7. Feed result into agent as structured tool output.
8. Measure code/test/audit improvement.

### Evaluation dataset

Build a rights-cleared eval set of **50-100 screening implementation tasks**:

- 30-50 company screening tasks.
- 10-20 officer/beneficial-owner relationship tasks.
- 10-20 ambiguous/fuzzy-match edge cases.
- 5-10 stale/public-source trap cases.
- 5-10 audit/provenance completeness tasks.

Each task should include:

- task prompt;
- expected code or workflow behavior;
- source truth label;
- permitted sources;
- public baseline result;
- expert reviewer rubric;
- expected provenance/audit artifact;
- allowed data retention status.

Use synthetic or rights-cleared subjects where needed. Do not copy premium source content into the eval dataset unless explicitly licensed.

### Success metrics

Minimum success thresholds:

| Metric | Target |
| --- | --- |
| Data-failure classifier precision | At least 70-80% of broker-triggered events are confirmed as data-caused by expert review. |
| Incremental task quality lift | 25-40% improvement over baseline on blocked KYB implementation tasks, or a statistically credible smaller lift with high-value defects reduced. |
| Audit completeness | At least 90% of intervention outputs include source/version/provenance/allowed-use metadata required by reviewer rubric. |
| False-positive control | Broker-triggered paid calls that do not address a real data gap stay below 10-20% after first tuning period. |
| Buyer WTP | Buyer pays or signs renewal at a platform/service fee above direct provider cost. |
| Rights-holder comfort | At least one source renews or agrees to continue under agent-mediated terms after usage review. |
| Multi-source value | Complementary source changes outcome in at least 10-20% of evaluated tasks where OpenSanctions/public-only is insufficient. |
| Positive contribution | Unit economics are positive after data cost and variable support, with fixed overhead covered by pilot fee/minimum. |

### Pricing

Recommended pilot pricing:

- **90-day platform pilot:** `$30k-$75k` total, or `$10k-$25k/month`.
- **OpenSanctions-like source:** pass through actual usage cost, with EUR 0.10/successful-query as the public anchor where applicable.
- **Complementary source:** capped pilot data budget, e.g. `$2k-$10k`, depending on provider.
- **Broker service fee:** transparent 20-30% on data spend, or included in platform fee during pilot but priced explicitly for renewal.
- **Renewal ask:** annual platform contract plus usage, not pure per-query resale.

Do not rely on card-per-call payments. Use monthly invoicing or ACH/cloud marketplace billing.

### Timeline

#### Weeks 0-2: design and commitments

- Secure buyer team and named workflow.
- Confirm agent host and trace access.
- Sign pilot terms with buyer.
- Confirm OpenSanctions terms and API access.
- Identify complementary source and either sign narrow pilot terms or define fallback.
- Draft data-use, no-training, no-redistribution, retention, and audit terms.
- Define evaluation rubric and kill criteria.

#### Weeks 3-4: baseline

- Run baseline agent tasks.
- Label failures as data-caused, non-data, ambiguous, credentials, requirements, bugs, or public-doc issue.
- Measure public/free/direct-source alternatives.
- Freeze eval dataset and source truth labels.

#### Weeks 5-7: build intervention

- Build missing-info schema for KYB.
- Build MCP/API proxy tools:
  - `screen_entity_with_provenance`;
  - `validate_company_attribute`;
  - `explain_screening_audit_gap`.
- Add entitlement gateway, budget controls, provenance receipt, and usage ledger.
- Add response shaping and raw-content redaction.

#### Weeks 8-10: intervention runs

- Run agent tasks with broker.
- Record paid calls, source versions, costs, outputs, and outcomes.
- Compare against baselines and direct-provider API use.
- Tune classifier only with held-out evaluation protection.

#### Weeks 11-12: decision

- Produce buyer-facing outcome report.
- Produce rights-holder usage/extraction report.
- Reconcile invoice and data-owner payout.
- Ask for paid renewal and expanded data-source/buyer scope.
- Decide continue/narrow/kill.

### Budget

Illustrative 90-day pilot budget:

| Item | Range | Notes |
| --- | ---: | --- |
| Engineering build | `$40k-$120k` | One or two engineers; narrow schema/proxy/eval. |
| Legal/licensing | `$10k-$40k` | Buyer terms, provider terms, privacy review, reseller/OEM risk. |
| Data-source usage | `$1k-$15k` | OpenSanctions-like usage plus complementary source pilot access. |
| Evaluation/expert review | `$10k-$40k` | Compliance SME labels and rubric review. |
| Security/admin | `$5k-$25k` | SSO/secrets/logging/vendor review. |
| Support/success | `$10k-$30k` | Buyer onboarding, troubleshooting, reporting. |
| Total cash effort | `$76k-$270k` | Must be justified by paid renewal evidence, not demo value. |

The pilot fee should cover a meaningful share of this cost. If the buyer will not pay anything upfront, the pilot is likely discovery, not commercial validation.

## Legal requirements

Minimum legal terms:

- Buyer is the authorized beneficial user.
- Agent-mediated access is expressly permitted.
- Approved agent host/model provider/observability providers are listed.
- No training, fine-tuning, or model improvement from source content.
- No raw list/corpus export.
- Subject-bounded queries only.
- Retention TTLs for raw tool outputs and traces.
- Permitted derived work product defined: generated code, tests, internal audit artifacts.
- Provenance retention required.
- Provider audit and anomaly suspension rights.
- Refund/dispute handling for failed or erroneous calls.
- Liability disclaimers and human-review requirements.
- GDPR/privacy review where personal data appears in sanctions/PEP/person screening.

Avoid:

- browser automation under human-only subscriptions;
- scraping paid portals;
- generic sublicensing language;
- consumer-style wallets;
- sending raw proprietary content to unapproved LLM providers.

## Moat preservation controls

Required controls:

- Source-hosted API calls.
- No bulk list export.
- Query templates with minimum specificity.
- Per-buyer daily/monthly query budgets.
- Similar-query clustering and anomaly review.
- Bounded response shapes.
- Redaction of raw content from traces.
- Provider-visible usage reports.
- Provenance receipts with source/version/license constraints.
- Revocation path for future access.

The data owner must be able to see that the broker is not a hidden extraction channel.

## Kill criteria

Kill the pilot or narrow it to a connector/services offering if:

1. Buyers refuse a broker/platform fee once direct API pricing is disclosed.
2. Most "failures" are bad requirements, credentials, prompt issues, code bugs, or missing internal data.
3. One direct provider API solves the task as well as the broker.
4. Complementary source adds no measurable lift.
5. Paid calls do not improve expert-reviewed correctness or audit completeness.
6. Classifier false positives exceed 20-30% after tuning.
7. Rights holders refuse agent-mediated terms or demand uneconomic minimum guarantees.
8. Data-owner extraction concerns force response limits that make the tool useless.
9. Variable contribution margin is negative after payouts, support, eval, and refunds.
10. Buyer will not renew after 90 days.

## Healthcare claims as second-pilot candidate

Healthcare RCM/claims edit automation has higher upside because claim denials, payer edits, eligibility, prior authorization, and CPT/HCPCS/ICD/modifier logic are economically meaningful and measurable. It is worse as the first 90-day pilot because:

- Optum/Change and clearinghouse sales cycles can be long.
- HIPAA/PHI and BAA requirements can dominate the experiment.
- Payer contracts and AMA CPT licensing complicate downstream use.
- Security review and liability expectations are higher.
- Buyer-owned claims/denial data may be the real blocker, not externally brokered data.

Healthcare should be pursued after the KYB pilot only if a buyer brings existing entitlements, synthetic/deidentified claims, and a narrow precheck/edit workflow.

## Decision rule

Proceed beyond the pilot only if the answer to all of these is yes:

- Did the system detect real data-caused failures?
- Did the paid source improve code/automation quality over public/free/direct alternatives?
- Did two-source routing or audit add value beyond one API?
- Did the buyer pay above data cost?
- Did the rights holder accept the controls after seeing usage?
- Did unit economics survive support, legal, eval, and refunds?
- Is the same failure class repeatable with another buyer or source?

If not, the right conclusion is not "build marketplace harder." It is either stop, sell a narrow vertical connector/control-plane product, or move to a different vertical with clearer multi-source pain.
