# 10 - Technical Architecture

**Research date:** 2026-07-15  
**Workstream:** W7 - demand-matching engine and technical architecture  
**Posture:** skeptical. Architecture should avoid overbuilding a horizontal marketplace before one vertical proves paid demand.

---

## 1. Bottom line

The product is not "an MCP server." It is a licensed data access system with MCP as one delivery interface.

MCP can standardize how agents call tools and read resources, and x402/MPP-style HTTP 402 flows can standardize machine payment prompts. Neither solves the exchange's hardest requirements: publisher rights, buyer identity, end-user entitlement, license scope, consent, pricing authority, audit, settlement, tax, revocation, deletion, provenance, quality measurement, and disputes.

**Lean recommendation:** build a vertical MVP as a governed API/MCP gateway over 1-3 licensed sources, with manual onboarding, Stripe/ACH invoicing or Stripe Connect for money movement, Postgres for catalog/ledger, OpenTelemetry-style traces, object storage for audit artifacts, and a rules-based policy engine. Defer general marketplace UX, dynamic pricing, sponsored discovery, graph ML, and on-chain settlement until there is real transaction volume.

---

## 2. Architecture principles

1. **License before transport:** no source is callable until contract, entitlement, and machine-readable license are in place.
2. **Policy before ranking:** ranking only happens after hard license, privacy, budget, geography, and buyer/publisher rules pass.
3. **Metering is source-of-truth:** every billable retrieval must have an immutable-ish ledger event tied to buyer, source, license, price, and response.
4. **Citations travel with data:** source metadata must be returned with every answerable payload, not reconstructed later.
5. **No raw-prompt hoarding by default:** store normalized demand signals and trace pointers; avoid holding privileged/PHI/customer prompts unless contractually required.
6. **Revocation is a first-class path:** license changes, takedowns, corrections, sanctions hits, and buyer suspension must propagate quickly.
7. **Human override in risky workflows:** legal, clinical, financial, and compliance tasks need HITL gates and audit logs.

---

## 3. MVP architecture

### 3.1 MVP scope

| Area | MVP decision |
|---|---|
| Publisher onboarding | Manual KYB, rights diligence, signed pilot schedule |
| Catalog | Thin private catalog, admin-edited source listings |
| Metadata | Required source schema below; no marketplace SEO layer |
| Interfaces | REST first; MCP wrapper for agent hosts |
| Identity | Buyer org + app credentials; optional end-user subject token |
| Consent | Buyer attestation + per-tool user confirmation where needed |
| Policy/licensing | Rules engine backed by machine-readable license JSON |
| Routing | Gateway maps tool/API calls to source endpoints |
| Ranking | Hard filters + weighted scoring; manual fallback |
| Quality | Offline eval set + sampled human review |
| Pricing | Fixed rate card or negotiated pilot price |
| Budgets | Per-buyer monthly cap, per-task max, source allowlist |
| Metering | Append-only ledger table; reconcile to source logs |
| Billing | Monthly invoice or prepaid credits through regulated provider |
| Settlement | Manual monthly publisher statement/payout for pilot |
| Caching | Short TTL response cache only if license permits |
| Citations | Required returned metadata fields; UI rendering obligation in buyer agreement |
| Provenance | Source content id, version, timestamp, license id |
| Audit | Query/retrieval/decision log with retention controls |
| Analytics | Usage, cost, failure rate, uplift metrics |
| Fraud/abuse | Rate limits, anomaly alerts, buyer suspension |
| Revocation | License/source disable switch; purge queue |
| Rate limits | Per-source and per-buyer token buckets |
| Deletion | Manual request workflow + automated cache purge |

### 3.2 Lean MVP stack recommendation

| Layer | Recommendation | Rationale |
|---|---|---|
| Runtime | Cloudflare Workers or Fly.io/Render for gateway; managed container if source SDKs require it | Fast edge/API deployment without platform complexity |
| API | OpenAPI REST + JSON Schema | Easier enterprise integration and testing than MCP-only |
| MCP | Single remote MCP server exposing narrow tools | Useful agent interface; not the system of record |
| Database | Postgres | Catalog, license terms, ledger, budgets, source metadata |
| Search/index | Postgres full-text / pgvector only for metadata and eval docs | Avoid storing publisher content until rights are explicit |
| Cache | Redis/Upstash or Cloudflare Cache with license-aware keys | TTL and tenant isolation are mandatory |
| Object storage | S3/R2 for audit artifacts and source snapshots where licensed | Cheap immutable evidence store |
| Auth | OIDC/OAuth2 client credentials; Auth0/Clerk/WorkOS acceptable | Avoid building identity early |
| Policy | Open Policy Agent, Cedar, or rules tables | Machine-enforce licensing/policy decisions |
| Observability | OpenTelemetry traces + structured logs | Needed for metering, debugging, and outcome proof |
| Payments | Stripe invoices/Connect or ACH; optional x402 sandbox only | Enterprise buyers still prefer invoices; x402 useful for protocol learning |
| Admin | Retool/Forest Admin/internal Next.js admin | Manual onboarding and ops-first workflow |

**MVP anti-goal:** do not custody funds, run a token economy, or build a public app-store-like marketplace in the first pilot.

### 3.3 MVP request flow

1. Agent calls `POST /v1/tools/screen_counterparty` or MCP tool `screen_counterparty`.
2. Gateway authenticates buyer app and optional end-user context.
3. Policy engine checks buyer contract, source license, allowed use, geography, budget, rate limits, and human-approval requirement.
4. Router selects source endpoint and price quote.
5. Metering creates a pending event with idempotency key.
6. Source adapter calls upstream provider.
7. Gateway validates and normalizes response.
8. Citation/provenance metadata is attached.
9. Ledger event is finalized with cost, latency, content ids, license id, and response status.
10. Buyer receives result plus license/provenance/citation metadata.
11. Analytics and outcome hooks record whether task succeeded.

---

## 4. Production architecture

### 4.1 Logical components

| Component | Production role |
|---|---|
| Publisher portal | Onboarding, KYB, source listings, rights/price configuration, usage reports |
| Buyer portal | App registration, budgets, source allowlists, invoices, audit export |
| Catalog service | Searchable source/dataset/API/MCP catalog with schema, coverage, terms |
| Metadata service | Versioned source metadata, quality metrics, provenance, rights fields |
| Identity service | Buyer org, app, agent, end-user, publisher, service account identity |
| Entitlement service | Contract and subscription state; existing customer entitlement mapping |
| Consent service | Human approval, delegated authority, spending mandates |
| License engine | Machine-readable permitted uses and obligations |
| Policy engine | Buyer/publisher/security/privacy rules; deny/allow/explain |
| Routing service | Source selection, fallback, retries, adapter orchestration |
| Ranking service | Quality/cost/outcome-based scoring |
| Quality service | Eval sets, source testing, freshness checks, human review |
| Pricing service | Publisher rate cards, quotes, discounts, budget forecasts |
| Budget service | Pre-task authorization, monthly caps, per-user limits |
| Metering ledger | Append-only transaction records and reconciliation |
| Billing service | Buyer invoices, refunds, taxes, payment status |
| Settlement service | Publisher payouts, statements, minimum thresholds |
| Cache service | License-aware response, metadata, and index caching |
| Citation service | Source display payloads and attribution compliance sampling |
| Provenance service | Content IDs, source versions, C2PA/RSL/rights references where available |
| Audit service | Immutable logs, export, retention, investigation workflow |
| Analytics service | Demand graph, supply performance, conversion, churn, ROI |
| Fraud service | Abuse detection, multi-accounting, reconstruction attempts |
| Revocation service | Takedowns, license suspension, source disable, correction propagation |
| Rate-limit service | Buyer/source/token/user scoped limits |
| Deletion service | Cache/index/log deletion and certification workflow |

### 4.2 Production data plane vs. control plane

**Control plane:** catalog, contracts, pricing, license config, identity, budgets, analytics, admin workflows.

**Data plane:** low-latency request authentication, policy check, routing, metering, source call, caching, provenance return.

Separate them early enough that an admin/catalog outage does not break paid data calls, and a data-plane incident does not corrupt catalog/pricing state.

### 4.3 Production request path

```text
Agent/MCP Client
  -> API/MCP Gateway
  -> AuthN/AuthZ
  -> Consent/Budget Pre-Auth
  -> License + Policy Decision
  -> Ranking/Router
  -> Source Adapter(s)
  -> Normalization + Citation/Provenance
  -> Metering Finalization
  -> Cache/Revocation Hooks
  -> Response to Agent
  -> Outcome + Analytics Event
```

### 4.4 Publisher onboarding

MVP is manual; production needs a supplier workflow:

1. Legal entity verification, sanctions screening, tax forms.
2. Rights questionnaire: ownership, third-party content, territories, excluded content, personal data categories.
3. Technical connection: API, feed, MCP server, warehouse share, or publisher-hosted proxy.
4. Metadata import and test queries.
5. License configuration: uses, retention, training, embeddings, citations, pricing, approval rules.
6. Quality baseline: sample queries, freshness checks, expected response format.
7. Go-live approval and rollback plan.

Do not let self-serve publishers go live with billable sources until rights and identity checks pass.

### 4.5 Catalog and metadata

The catalog must be more than marketing copy. Agents need machine-readable descriptions, schemas, pricing, rights, freshness, and quality indicators. Buyers need procurement/security/legal metadata.

Key catalog requirements:

- Dataset/source identity and owner.
- Coverage by geography, time, entity type, topic, source type.
- Interfaces: REST, MCP, SQL/share, feed, proxy.
- Data fields and response schemas.
- Update cadence and observed freshness.
- License rights and restrictions.
- Pricing and budget predictability.
- Citation/provenance support.
- Security, privacy, residency, and deletion capabilities.
- Quality metrics and eval results.

---

## 5. Standard source listing schema

This is a standard listing schema for catalog entries. Use JSON Schema in implementation; this is the conceptual shape.

```json
{
  "schema_version": "source_listing.v0.1",
  "source_id": "src_opensanctions_demo",
  "publisher": {
    "publisher_id": "pub_opensanctions",
    "legal_name": "OpenSanctions Datenbanken GmbH",
    "display_name": "OpenSanctions",
    "rights_contact": "rights@example.com",
    "verified": true,
    "kyb_status": "verified"
  },
  "listing": {
    "title": "Sanctions, PEP, and watchlist screening API",
    "description": "Normalized entity-risk data with source-linked records and matching API.",
    "domains": ["procurement", "compliance", "financial_crime"],
    "data_types": ["entities", "relationships", "watchlists"],
    "coverage": {
      "geographies": ["global"],
      "time_range": "current_plus_history",
      "languages": ["multi"],
      "update_cadence": "multiple_daily"
    }
  },
  "interfaces": [
    {
      "type": "rest",
      "base_url": "https://api.example.com",
      "openapi_url": "https://api.example.com/openapi.json"
    },
    {
      "type": "mcp",
      "server_url": "https://mcp.example.com",
      "tools": ["screen_counterparty", "search_risk_entity", "get_risk_entity"]
    }
  ],
  "schema": {
    "primary_entities": ["person", "organization", "vessel", "aircraft"],
    "fields": ["name", "aliases", "country", "identifiers", "sources", "risk_topics"],
    "response_format": "json",
    "sample_query_url": "https://exchange.example/sources/src_opensanctions_demo/examples"
  },
  "rights": {
    "license_template_id": "lictmpl_retrieval_summary_citation_v1",
    "permitted_uses": ["search", "retrieval", "summarization", "quotation", "temporary_context", "evaluation"],
    "prohibited_uses": ["training", "fine_tuning", "resale", "bulk_extraction"],
    "embedding_policy": "platform_only",
    "retention": {
      "retrieved_copy_ttl_hours": 24,
      "operational_log_days": 30,
      "cache_ttl_hours": 24
    },
    "territories": ["US", "EU", "UK"],
    "end_user_auth_required": false,
    "publisher_approval_required": false
  },
  "pricing": {
    "currency": "USD",
    "models": [
      {
        "unit": "successful_query",
        "list_price": 0.10,
        "minimum_monthly_commit": null
      }
    ],
    "volume_discounts_available": true,
    "quote_required": false
  },
  "quality": {
    "freshness_sla": "24h",
    "availability_sla": "99.5",
    "p95_latency_ms": 1500,
    "citation_support": "source_url_and_record_id",
    "correction_takedown_api": true,
    "eval_summary_url": "https://exchange.example/sources/src_opensanctions_demo/evals"
  },
  "compliance": {
    "personal_data_categories": ["names", "identifiers", "public_records"],
    "data_residency_options": ["US", "EU"],
    "dpia_required": "maybe",
    "delete_api": true,
    "audit_export": true,
    "security_docs_url": "https://exchange.example/sources/src_opensanctions_demo/security"
  },
  "commercial": {
    "publisher_sets_price": true,
    "platform_fee_pct": 15,
    "settlement_cadence": "monthly",
    "refund_policy_id": "refund_non_delivery_v1"
  },
  "status": {
    "environment": "pilot",
    "availability": "private",
    "created_at": "2026-07-15T00:00:00Z",
    "updated_at": "2026-07-15T00:00:00Z"
  }
}
```

---

## 6. Identity, authentication, and consent

### 6.1 Agent/company identity

Required identities:

- **Publisher identity:** legal entity, rights holder, tax/payee details.
- **Buyer organization:** legal entity, contracts, KYB/sanctions status.
- **Buyer application:** registered agent app, credentials, scopes, callback URLs.
- **Agent instance:** optional runtime identity for high-risk use cases.
- **End user:** human subject where entitlement, consent, or role matters.

Use OAuth2/OIDC where possible. For machine-to-machine calls, use client credentials or signed requests with rotating keys. For high-risk tools, bind calls to an end-user subject and require explicit user or admin consent.

### 6.2 End-user authorization

Two models:

1. **License-granted access:** publisher licenses the buyer/app; end-user identity is used for buyer controls and audit.
2. **Entitlement-routed access:** end user or enterprise already has a subscription; exchange verifies entitlement and routes under that contract.

Do not rely on consumer credential lending as a default. Existing legal analysis flags agent use of end-user accounts without system-owner authorization as high risk.

### 6.3 Consent

Consent should be captured for:

- Paid data calls above threshold.
- Sharing user/company context with a third-party source.
- Retrieval of sensitive personal/health/financial data.
- Use of retrieved content in persistent conversation history.
- Any sponsored or paid-placement influence.

For low-risk enterprise workflows, admin-level policy can pre-authorize categories and budgets. For consumer/high-risk contexts, use explicit human-in-the-loop confirmation.

---

## 7. Licensing and policy engines

The **license engine** answers: "What is legally permitted under this source/buyer/task?"

The **policy engine** answers: "Even if licensed, should this call be allowed under buyer, publisher, privacy, security, budget, and regulatory policies?"

Examples:

| Decision | Engine |
|---|---|
| May the agent summarize this source? | License |
| May the buyer retain embeddings for 30 days? | License |
| May this EU user send personal data to a US-hosted source? | Policy + DPA |
| May this buyer exceed $50 on one task? | Budget/policy |
| May a competitor of the publisher access this listing? | License/publisher policy |
| Must a human approve before purchase? | Consent/policy |

All denials should be explainable. Buyers and publishers will not trust a black-box "policy denied" on billable workflows.

---

## 8. Routing, ranking, quality, pricing, and budgets

### 8.1 Routing

Routing selects the source and adapter path. It must consider:

- Hard license/policy filters.
- Source availability and rate limits.
- Query type and schema compatibility.
- Price quote and budget.
- Cacheability.
- Fallback source strategy.
- Data residency.

### 8.2 Ranking

Ranking happens only among permitted candidates. Use the demand-matching formula from `05-demand-matching-engine.md`, with weights tuned by vertical.

Do not optimize for platform margin at the ranking layer. Margin-aware ranking is legally and reputationally dangerous unless separately disclosed as sponsored/commercial placement.

### 8.3 Quality

Production quality system:

- Gold task sets by vertical.
- Source-specific evals.
- Freshness monitors.
- Citation correctness tests.
- Drift detection when upstream schema/content changes.
- Human review queues for disputed answers.
- Refund/non-delivery detection.

### 8.4 Pricing and budgets

Pricing modes:

- Per search hit.
- Per retrieval.
- Per field/entity.
- Per answer/task bundle.
- Subscription/minimum commit.
- Custom enterprise license.

Budget controls:

- Per-task max.
- Per-user max.
- Per-source max.
- Monthly org cap.
- Require HITL above amount.
- Allowlist/blocklist sources.
- Alert on burn-rate anomalies.

---

## 9. Metering, billing, settlement, and payment rails

### 9.1 Metering

Every billable event should include:

- event id and idempotency key;
- buyer org/app/end-user role;
- publisher/source/license id;
- request type, source endpoint, units consumed;
- list price, discounts, platform fee, taxes if known;
- timestamp, latency, status, refundability;
- source content ids/version and citation ids;
- policy decision id;
- response hash or metadata hash where content cannot be stored;
- outcome/event pointer.

Use append-only semantics. Corrections are reversal/refund events, not overwrites.

### 9.2 Billing

MVP:

- monthly invoices or prepaid credits;
- manual publisher statements;
- no per-call card charges;
- no platform custody without payments counsel.

Production:

- buyer invoices, tax calculation, credit balances, refunds;
- publisher payouts with tax forms and withholding;
- reconciliation against source logs;
- dispute workflow.

### 9.3 x402 and MPP

x402 is useful for machine-native per-request payments. Cloudflare's docs describe a flow where a server returns `402 Payment Required` with payment details, the client retries with a signed payment payload, and a facilitator verifies/settles. Cloudflare's Agents SDK exposes `withX402` and `paidTool` for paid MCP tools.

But an enterprise exchange should be careful:

- Stablecoin settlement may not pass procurement/security review.
- Per-call settlement is unnecessary when buyer has an enterprise invoice.
- x402 does not solve publisher contract, tax, quality, attribution, or revocation.
- Facilitator dependency becomes operational risk.

Use x402 as an optional protocol adapter, not the core settlement strategy at MVP.

---

## 10. Caching, citations, provenance, audit, and analytics

### 10.1 Caching

Cache only when license permits. Cache keys must include:

- source id;
- license id/version;
- buyer/org scope;
- end-user scope where required;
- geography/residency scope;
- query hash;
- cache scope (`private`, `tenant`, `public`) and TTL.

Cross-buyer cache bleed is a confidentiality and license breach.

### 10.2 Citations

Every response should return:

- source name;
- title/record name;
- canonical URL or source record id;
- publication/update timestamp;
- retrieved timestamp;
- license id;
- quote/excerpt boundaries if applicable;
- required display text;
- correction/takedown pointer.

The exchange should sample buyer UIs for attribution compliance where contractually allowed.

### 10.3 Provenance

Provenance is not only "where did this answer come from?" It must prove:

- source identity;
- content version;
- license at time of access;
- retrieval event;
- transformations performed;
- display obligations;
- revocation/deletion state.

Use C2PA/RSL-like references where publishers already support them, but do not depend on universal adoption.

### 10.4 Audit

Audit logs must support:

- buyer compliance export;
- publisher usage ledger;
- billing dispute resolution;
- regulator/legal hold;
- takedown propagation;
- source-quality incident investigation.

Audit retention should be explicit by data category. Holding raw content forever to "be safe" conflicts with deletion and license obligations.

### 10.5 Analytics

Analytics should answer:

- which needs are unmet;
- which sources improve outcomes;
- where paid calls are wasteful;
- where latency or quality breaks;
- which publishers produce refunds/disputes;
- which buyers are abusing access;
- whether the exchange creates enough margin after support/compliance costs.

---

## 11. Fraud, revocation, rate limits, and deletion

### 11.1 Fraud and abuse

Failure patterns:

- buyer tries to reconstruct dataset via many narrow calls;
- multi-accounting to bypass caps;
- source returns stubs/low-quality data but charges;
- publisher lacks rights to content;
- agent disguises identity;
- sponsored source tries to buy around quality floors;
- payment/reconciliation manipulation.

Mitigations:

- per-catalog fraction caps;
- anomaly detection on query diversity and sequential crawling;
- source quality monitors;
- KYB and continuous sanctions screening;
- signed agent identity;
- ledger reconciliation;
- suspension workflow.

### 11.2 Revocation

Revocation events:

- publisher takedown;
- correction/retraction;
- license expiration;
- buyer breach;
- sanctions/KYB hit;
- privacy deletion request;
- source security incident;
- payment failure.

Production needs a revocation queue with SLAs: disable new calls immediately; purge caches/indexes within license/DPA timelines; notify buyers where outputs may be affected; adjust billing/refunds.

### 11.3 Rate limits

Rate limits are both operational and contractual. Scope them by:

- buyer org;
- buyer app;
- end user;
- source;
- endpoint/tool;
- geography;
- catalog fraction per month;
- burst vs. sustained rate.

### 11.4 Deletion

Deletion must cover:

- cached source responses;
- embeddings/indexes;
- audit artifacts where deletion is legally permitted;
- buyer-side retained content via contractual notice;
- analytics derived from personal data where applicable.

MVP can use manual deletion workflows for pilots. Production needs automated propagation and evidence of completion.

---

## 12. Is MCP alone sufficient?

No.

MCP is a useful protocol for exposing tools/resources/prompts to AI applications. It does not, by itself, provide:

- commercial contracts;
- rights verification;
- publisher KYB and chain-of-title diligence;
- buyer KYB and sanctions controls;
- end-user entitlement mapping;
- license scope enforcement;
- budget controls;
- pricing authority and antitrust-safe pricing governance;
- taxes, invoices, refunds, payout statements;
- quality evaluation and source ranking;
- attribution compliance;
- audit logs and legal holds;
- revocation/deletion propagation;
- fraud detection;
- customer support and dispute resolution.

MCP should be treated as one adapter beside REST and source-native APIs. If the exchange's only product is "a catalog of MCP servers," official/third-party MCP registries, Postman, Databricks, Snowflake, and data owners themselves can commoditize it quickly.

---

## 13. Build sequence

### Phase 0 - pilot readiness

- Select one vertical and 1-3 sources.
- Complete source rights/licensing diligence.
- Define source listing schema and license JSON.
- Implement REST/MCP gateway, policy checks, ledger, budgets, admin UI.
- Write offline evals and success metrics.

### Phase 1 - controlled pilot

- One or two buyers.
- Manual publisher onboarding.
- Fixed prices.
- No sponsored discovery.
- Short TTL cache only.
- Human review for risky outputs.
- Weekly reconciliation.

### Phase 2 - repeatable vertical

- More sources in same vertical.
- Source ranking and fallback.
- Buyer portal and publisher portal.
- Automated statements and invoices.
- Quality dashboards.
- Revocation/deletion automation.

### Phase 3 - broader exchange

Only after repeatable vertical demand:

- self-serve catalog;
- multiple interfaces;
- optional x402/MPP adapters;
- cross-buyer demand graph;
- standardized contracts;
- public marketplace listing;
- carefully separated sponsored discovery if allowed.

---

## 14. Sources

- Model Context Protocol specification, 2025-11-25. Defines MCP primitives and security/consent guidance. `https://modelcontextprotocol.io/specification/2025-11-25`
- MCP Registry preview, 2025-09-08. Supports the point that MCP discovery is becoming open infrastructure. `https://blog.modelcontextprotocol.io/posts/2025-09-08-mcp-registry-preview/`
- Cloudflare Agents docs, x402, modified 2026-06-03. Supports 402 payment flow, facilitators, and paid MCP tools. `https://developers.cloudflare.com/agents/tools/payments/x402/`
- Cloudflare, "Announcing the Monetization Gateway," 2026. Supports edge-based charging for web pages, APIs, datasets, and MCP tools via x402. `https://blog.cloudflare.com/monetization-gateway/`
- Coinbase x402 GitHub README. Defines x402 resource server/client/facilitator, verify, and settle flow. `https://github.com/coinbase/x402`
- Stripe Machine Payments Protocol blog, 2026-03-18; Stripe machine payments docs. Supports HTTP 402-style machine payments as adjacent infrastructure. `https://stripe.com/blog/machine-payments-protocol`; `https://docs.stripe.com/payments/machine`
- Existing project sources: `01-product-definition.md`, `02-competitive-landscape.md`, `05-demand-matching-engine.md`, `08-licensing-agreements.md`, and `11-legal-risks.md`.
