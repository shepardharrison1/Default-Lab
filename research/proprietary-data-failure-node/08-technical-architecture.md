# Technical Architecture

**Research date:** 2026-07-16  
**Posture:** MVP architecture for falsification, not a platform maximalist design.  
**Recommendation tie-in:** **Pursue only through a narrow pilot.**

## Architecture thesis

The product should start as a **vertical entitlement and resolution gateway** that plugs into existing coding-agent and observability systems. It should not start as a new observability platform, data marketplace, payment protocol, clean-room system, or autonomous procurement agent. The MVP must prove one thing: a specific class of coding/automation failure can be classified as data-caused, routed to a licensed source, resolved with a minimal answer, protected against extraction, and measured for outcome lift.

The production architecture can later become a multi-provider control plane. The MVP should be deliberately narrower:

- One vertical.
- One or two data owners.
- One or two host surfaces.
- One failure-node classifier optimized for precision.
- One entitlement gateway.
- One metered retrieval path.
- One evaluation loop.

## Reference architecture

```text
Coding agent / automation host
  |  traces, tool calls, failures, reviewer labels
  v
Observability intake + hooks
  |  normalized run events
  v
Failure-node classifier
  |  data-caused candidate + missing-info schema
  v
Source discovery + rights registry
  |  candidate source + buyer entitlement
  v
Entitlement gateway
  |  allow / deny / quote / human approval
  v
MCP/API proxy
  |  provider-specific source-hosted query
  v
Licensed data owner
  |  bounded answer + version + license constraints
  v
Response shaper + output filter
  |  minimal answer + provenance receipt
  v
Agent / generated artifact / audit log
  |
  +--> Metering, budgets, settlement, anomaly detection
  +--> Evaluation loop and outcome-linked ranking
```

## Core components

### 1. Coding-agent observability hooks

**Purpose:** Capture enough evidence to identify candidate data-caused failures without becoming a full observability product.

**Inputs:**

- Agent run ID, host, model, repo/project, user/team, timestamp.
- Tool calls and errors.
- Test failures or validation failures.
- Agent uncertainty markers.
- Human reviewer annotations.
- Retrieval attempts and free-source attempts.
- Final outcome: accepted, rejected, retried, escalated, abandoned.

**Implementation pattern:**

- MVP: webhook/SDK plus MCP server wrapper that receives explicit failure events.
- Production: OpenTelemetry-compatible spans and events, with adapters for Langfuse, LangSmith, Braintrust, Phoenix, Datadog, Cursor/Copilot/Claude Code where available.

**Build vs buy:**

- **Buy/integrate:** Langfuse OTel/OpenTelemetry traces, LangSmith/Braintrust/Phoenix eval hooks, Datadog logs if the buyer already uses them.
- **Build:** domain-specific event schema, redaction policy, failure labels, and bridge from trace to licensed-data resolution event.

**Do not build in MVP:** general-purpose tracing UI, prompt playground, model-router observability, or full replay system.

### 2. Failure-node classifier

**Purpose:** Decide whether a failure is plausibly caused by missing licensed data rather than bugs, weak reasoning, credentials, unclear requirements, or public-doc gaps.

**MVP classifier:**

- Conservative rules plus human-in-the-loop review.
- Optimize for precision over recall.
- Require evidence that public/free sources were insufficient or legally unusable.
- Require a specific missing-info schema instance.

**Signals:**

- Error mentions unknown payer edit, jurisdiction rule, code set, standard, coverage criterion, restricted API doc, or proprietary compatibility matrix.
- Agent attempted public docs but produced stale/conflicting answer.
- Reviewer label: "needs payer policy," "requires authoritative code," "not in public docs," "licensed source required."
- Tests fail on domain-rule fixture.

**Outputs:**

- `candidate_data_failure: true/false`
- `confidence`
- `failure_class`
- `missing_info`
- `recommended_source`
- `free_substitute_attempted`
- `human_approval_required`

**Do not build in MVP:** a fully automated root-cause model. The classifier is the riskiest assumption and should be treated as an experiment.

### 3. Missing-info schema

The missing-info schema turns vague agent uncertainty into a bounded query.

Example:

```json
{
  "vertical": "healthcare_rcm",
  "failure_class": "payer_claim_edit_rule",
  "task_id": "agent-run-123",
  "jurisdiction": "US",
  "payer": "example_payer",
  "code_system": "CPT",
  "procedure_code": "00000",
  "diagnosis_code": "A00.0",
  "modifier": "XX",
  "place_of_service": "11",
  "date_of_service": "2026-07-16",
  "needed_answer_type": "validation_decision",
  "acceptable_sources": ["licensed_payer_policy_api", "licensed_claim_edit_api"],
  "public_sources_checked": ["payer_public_pdf", "cms_public_rule"],
  "output_constraints": {
    "no_raw_policy_excerpt": true,
    "max_explanation_tokens": 200,
    "citation_required": true
  }
}
```

Fields should be vertical-specific. A generic natural-language "what data do you need?" interface is too permissive and too hard to meter.

### 4. Source discovery

**Purpose:** Map a missing-info schema to candidate data owners or APIs.

**MVP:**

- Curated registry for one vertical.
- Manual provider onboarding.
- Deterministic mapping from failure class to provider endpoint.
- Free-substitute list for comparison.

**Production:**

- Provider catalog with coverage metadata, jurisdictions, dates, source authority, license terms, query shapes, SLAs, and price schedules.
- Ranking model based on historical resolution evidence, not paid placement alone.

**Build vs buy:**

- **Build:** workflow-specific source registry and source ranking based on outcomes.
- **Buy/integrate:** existing data marketplaces or provider APIs where procurement is already handled, e.g., Snowflake Marketplace/CKE, AWS Data Exchange, Databricks Marketplace, direct vendor APIs.

### 5. Rights registry

**Purpose:** Represent who can use what, for what purpose, under which conditions.

**Entities:**

- Buyer organization.
- User/team/project.
- Agent host.
- Data owner.
- Source product/API.
- Contract/license.
- Field of use.
- Model-provider constraints.
- Retention limits.
- Output constraints.
- Price schedule.
- Revocation/deletion state.

**MVP:**

- Static contracts and per-buyer allowlists.
- Manual entry of rights terms.
- Simple policy engine: allow, deny, require approval.

**Production:**

- Machine-readable rights terms.
- Contract versioning.
- Subprocessor approvals.
- Usage-dependent rights.
- Automated revocation propagation.

### 6. Entitlement gateway

**Purpose:** Enforce buyer, project, and use-case permissions before data access.

**Required checks:**

- Is the buyer approved by the data owner?
- Is the use case within field of use?
- Is the user/team allowed to spend?
- Is the model provider approved for this data?
- Are retention and logging settings compatible?
- Has the account exceeded extraction, spend, or query budgets?
- Is human approval required?

**Output states:**

- `allow`
- `deny`
- `allow_with_redaction`
- `allow_with_human_approval`
- `quote_required`
- `existing_subscription_required`

**Do not build in MVP:** autonomous negotiation. Use pre-negotiated pilot terms.

### 7. MCP/API proxy

**Purpose:** Provide a stable agent-facing tool while keeping provider-specific credentials, schemas, and protections behind the gateway.

**MVP interface:**

- One MCP server or HTTP API.
- Few domain-specific tools, not a generic "search proprietary data" tool.
- Query templates tied to missing-info schema.

Example tool names:

- `check_claim_edit`
- `lookup_authoritative_code_status`
- `validate_sanctions_screening_result`
- `check_building_code_requirement`

**Proxy responsibilities:**

- Authenticate buyer and agent host.
- Validate schema.
- Attach rights policy.
- Call provider source-hosted API.
- Enforce response shaping.
- Log provenance and metering.
- Return bounded answer to agent.

**MCP caveat:** MCP is a workflow interface, not a protection mechanism. Security must live in authentication, policy, provider-side controls, budgets, logging, and response shaping.

### 8. Metering

**What to meter:**

- Query count.
- Resolution events.
- Provider calls.
- Returned content units.
- Source versions.
- Buyer/team/project.
- Spend.
- Budget consumption.
- Corpus threshold consumption.
- Outcome status.

**Build vs buy:**

- **Buy:** Stripe Billing/usage-based billing for invoicing, payment collection, tax support where appropriate; existing cloud marketplace billing if channel requires it.
- **Build:** domain-specific usage ledger, data-owner payout calculation, content-threshold counter, anomaly detection, and refund/failed-resolution attribution.

**Do not build in MVP:** custom payment rails, x402 wallet infrastructure, money custody, or dynamic clearinghouse unless the pilot specifically requires it.

### 9. Budgets and anti-extraction controls

Budgets should be enforced before provider calls:

- Per-user query limit.
- Per-project query limit.
- Per-organization daily/weekly/monthly limit.
- Per-source corpus-retrieval threshold.
- Per-field and per-answer token caps.
- Similar-query clustering.
- Velocity checks.
- Geographic/jurisdiction coverage checks.
- Manual review queue for anomalous access.

Production should support Snowflake-CKE-style content-protection thresholds where a provider can cap the percentage of corpus retrieved by a consumer within a rolling window. The MVP can implement a simpler account-level counter if the provider API does not expose corpus-level accounting.

### 10. Provenance

Every returned answer should include a machine-readable receipt:

```json
{
  "receipt_id": "prov_123",
  "source_id": "provider.claim_edit_api",
  "source_version": "2026-07-15",
  "rights_holder": "provider_name",
  "license_id": "lic_456",
  "buyer_org": "buyer_789",
  "field_of_use": "internal_automation_development",
  "retrieved_at": "2026-07-16T09:28:00Z",
  "retention": "tool_output_ttl_30_days",
  "training_use": "prohibited",
  "redistribution": "prohibited_except_generated_work_product",
  "model_provider_allowed": true,
  "citation": "provider citation or opaque source reference",
  "answer_hash": "sha256:..."
}
```

Provenance should travel with:

- Tool response.
- Generated code comments if appropriate.
- Pull request metadata.
- Audit export.
- Billing event.
- Evaluation record.

### 11. Settlement

**MVP settlement:**

- Monthly invoice to buyer.
- Monthly report and payout calculation to data owner.
- Manual reconciliation for disputed calls.
- Refund only for provider errors or non-resolution if contract says so.

**Production settlement:**

- Automated invoices and data-owner statements.
- Revenue share, minimum guarantees, usage tiers.
- Credit memos and dispute workflow.
- Channel marketplace integration.

**Build vs buy:**

- **Buy:** Stripe, marketplace billing, accounting exports.
- **Build:** the ledger that says which licensed-data call resolved which failure and how much should accrue to which data owner.

### 12. Evaluation loop

**Purpose:** Prove whether licensed data changes outcomes.

**MVP eval design:**

- Predefined task set in one vertical.
- Baselines: no broker, public search, Context7-style docs where relevant, existing buyer subscription, human clarification.
- Outcomes: task completion, test pass, expert review, time to resolution, rework rate, cost per resolved task.
- Labels: data-caused, non-data, ambiguous, false positive, false negative.

**Production loop:**

- Convert recurring failures into eval cases.
- Track source-level lift over time.
- Rank sources by outcome contribution, not just availability.
- Detect diminishing returns and extraction-like behavior.

**Important:** Outcome-linked source ranking is potentially valuable only after statistically meaningful, audited usage. In MVP, it is a measurement plan, not a moat.

## Security model

### Trust boundaries

1. **Buyer enterprise:** users, repo, agent host, generated code, internal logs.
2. **Broker:** policy engine, proxy, metering, provenance, minimal traces.
3. **Data owner:** hosted source, provider API, content protection.
4. **Model provider:** LLM inference, safety logs, abuse monitoring, subprocessors.
5. **Observability provider:** traces, spans, evals, logs.
6. **Payment provider:** billing and payment metadata.

### Security requirements

- SSO/SAML/OIDC for enterprise buyers.
- Service-to-service authentication for host integrations.
- Per-tool and per-source API keys or OAuth client credentials.
- Secrets stored in managed secret manager.
- Provider credentials never exposed to the agent.
- TLS everywhere; private networking where required.
- Encryption at rest for logs, receipts, and usage ledgers.
- Redaction before observability export.
- Role-based access control for broker admin/support.
- Immutable audit log for entitlement decisions and provider calls.
- Data retention TTLs by source/license.
- Incident response path for over-disclosure, provider breach, buyer misuse, and erroneous output.

### Data minimization rules

- Do not store raw provider responses unless required for audit and permitted by contract.
- Store hashes, receipt IDs, source references, and bounded summaries where possible.
- Avoid sending raw licensed content to the model. Prefer source-hosted computation and compact decisions.
- If model processing is required, attach model-provider approval and retention setting to the entitlement decision.

## MVP build list

Must build:

1. Domain-specific missing-info schema.
2. Conservative failure-node classifier with human review.
3. Curated source registry for one vertical.
4. Static rights registry and entitlement gateway.
5. MCP/API proxy for one or two provider endpoints.
6. Metering ledger and budget enforcement.
7. Provenance receipts.
8. Minimal admin console or config files for buyers/providers.
9. Evaluation harness and labeling workflow.
10. Redaction and retention controls for traces.

Should buy or integrate:

1. Stripe or existing marketplace billing for invoices/payments.
2. Langfuse/OpenTelemetry, LangSmith, Braintrust, Phoenix, or Datadog for traces/evals if buyer already uses them.
3. Cloud secret manager and KMS.
4. Existing provider APIs/CKEs/data marketplace listings.
5. Existing identity provider for enterprise auth.
6. Cloud logging/SIEM exports.

Should not build in MVP:

- Horizontal data marketplace.
- Dynamic price negotiation.
- Autonomous procurement agent.
- Custom payment protocol.
- Money custody wallet.
- General observability product.
- Fine-tuning pipeline.
- Clean room.
- Confidential-computing runtime.
- Broad MCP registry.
- Web crawler or pay-per-crawl product.
- Synthetic data factory.
- Multi-vertical source discovery.
- Self-serve data-owner onboarding.

## Production roadmap only if pilot works

Production architecture is justified only if the pilot proves classifier precision, resolution lift, buyer willingness to pay, and rights-holder comfort. Production additions:

- Multi-tenant policy engine with machine-readable rights.
- Provider self-service onboarding with security review.
- Coverage-aware source ranking.
- Cross-host integrations.
- Corpus-threshold enforcement across providers.
- Formal anomaly-detection models.
- Contract lifecycle management integration.
- Audit/compliance exports.
- Enterprise procurement integrations.
- Optional confidential-computing or clean-room mode for high-sensitivity sources.
- Automated settlement and revenue-share reporting.

## Key architectural risks

| Risk | Why it matters | Mitigation |
| --- | --- | --- |
| Classifier false positives | Wastes money and annoys developers. | Precision-first rules, human approval, free-source comparison. |
| Provider extraction risk | Rights holder refuses access. | Source-hosted queries, budgets, thresholds, response shaping. |
| Model-provider leakage | Proprietary data enters third-party logs/training paths. | No-training terms, approved subprocessors, source-side computation. |
| Agent-host internalization | Host copies classifier/control flow. | Vertical data-owner relationships and outcome evidence, not generic tooling. |
| Settlement complexity | Small transactions may not cover operational cost. | Monthly invoicing, batch settlement, avoid custom rails. |
| Liability for wrong answers | Bad data can produce bad code or compliance failures. | Disclaimers, provenance, expert review, limited pilot use. |
| Enterprise retention | Buyer retains useful outputs. | Define permitted derived work product and forbidden source retention. |

## Conclusion

The MVP architecture should be a narrow control plane around existing agents, provider APIs, observability tools, and billing systems. Build the parts that express the thesis: failure classification, missing-info schema, entitlement enforcement, protected retrieval, provenance, metering, and outcome evaluation. Buy the commodity rails. Do not build marketplace, payment, clean-room, or observability infrastructure until the narrow pilot proves that licensed data resolves real failures often enough to matter.
