# 01 — Product Definition

**Research date:** 2026-07-15  
**Posture:** Definitional clarity only. Commercial viability is judged elsewhere.

---

## One sentence

A neutral discovery, rights, routing, metering, attribution, and settlement layer that lets AI agents buy narrow, licensed machine access to proprietary datasets without negotiating separately with every rights holder.

## One paragraph

The product sits between agent applications and proprietary information owners. It observes or is told about repeated information gaps in agent workflows (failed retrievals, paywalls, missing citations, low confidence, human escalation), matches those gaps to licensable sources, and delivers paid access through APIs, MCP servers, secure feeds, or publisher-controlled proxies. It handles agent and enterprise identity, license scope, spending limits, usage metering, attribution, audit logs, billing, and publisher payouts. It ranks sources on relevance, quality, freshness, latency, price, and permitted uses — and may later offer clearly labeled sponsored discovery that cannot secretly override quality floors. The strongest form is not “agents pay websites”; it is a trusted machine-readable information exchange with enforceable rights and settlement.

## One page

### Problem the product claims to solve

As agents replace some human browsing, two frictions collide:

1. **Demand side:** Agent apps need proprietary, structured, or paywalled information but cannot scrape legally, cannot negotiate hundreds of publisher deals, and often lack machine-readable licenses.
2. **Supply side:** Rights holders want to monetize machine access without cannibalizing subscriptions or training models on their content for free.

### What the product does

| Layer | Function |
| --- | --- |
| Demand detection | Detect or ingest signals that an agent needs proprietary data |
| Catalog & matching | Map gaps to datasets, sources, and rights holders |
| Licensing | Encode permitted uses (retrieve, quote, summarize, embed, etc.) |
| AuthN/Z | Authenticate agents, companies, and optionally end users |
| Routing | Deliver content via API / MCP / feed / proxy |
| Ranking | Score sources on quality, rights, cost, latency |
| Metering & billing | Count usage, enforce budgets, invoice or debit wallets |
| Settlement | Pay publishers; retain platform fee |
| Attribution & audit | Cite sources; retain proof of license and use |
| Compliance | Policy engine for prohibited uses, residency, retention |

### What it is not (by default)

- Not a general web search engine.
- Not a model-training data broker (though training licenses could be a later SKU).
- Not merely an MCP registry (discovery without rights/settlement is insufficient).
- Not merely a payment rail (x402/Stripe already target payments).
- Not a horizontal “pay per crawl for news” play if that niche is already crowded (see competitive landscape).

### Product form — open design question

The research must choose among (or combine): marketplace; licensing broker; data exchange; routing engine; API gateway; MCP registry; payment layer; enterprise procurement infrastructure; advertising network for agents; vertical product.

**Working hypothesis for later judgment (inference, not conclusion):** the commercially realistic MVP is a **vertical licensing broker + MCP/API routing gateway with enterprise procurement controls**, not a broad horizontal media marketplace.

---

## Participants

| Participant | Role |
| --- | --- |
| **Agent application** | Software that needs proprietary data at inference/runtime |
| **Agent developer** | Builds/integrates the agent; often the technical buyer |
| **Enterprise customer** | Company deploying agents; often the economic buyer / budget holder |
| **End user** | Human who may authorize spend or whose identity gates access |
| **Publisher / dataset owner / rights holder** | Supplies proprietary content or data; sets license and often price |
| **Model provider** | LLM vendor; may be customer, competitor, or distribution channel |
| **Agent platform** | Host runtime (OpenAI, Anthropic, Microsoft, AWS Bedrock, etc.) |
| **Marketplace operator** | The proposed company; brokers discovery, rights, routing, settlement |

### Value flow (who supplies / buys / pays / receives)

| Question | Answer |
| --- | --- |
| Who supplies data? | Publishers, database owners, research platforms, SaaS vendors with proprietary corpora |
| Who purchases access? | Agent applications / their enterprise customers |
| Who pays? | Usually the enterprise (budget) or the agent vendor (COGS); sometimes end-user wallets |
| Who receives revenue? | Rights holder (majority) + platform (fee) + payment processors |
| Who controls pricing? | Default: rights holder sets list price; platform may add take rate or service fee |
| Who carries legal liability? | Rights holder for content accuracy/IP ownership warranties; buyer for misuse outside license; platform for brokerage/ops — **exact allocation requires counsel** |

---

## System components

| Component | Description | MVP essential? | Outsource? |
| --- | --- | --- | --- |
| Demand detection | Gap signals from agents/observability | Partial — start with explicit buyer requests | Can use partner telemetry later |
| Dataset matching | Map gaps → sources | Yes (manual OK for pilot) | Analysts + later ML |
| Publisher onboarding | Contracts, credentials, feed setup | Yes | Legal counsel + BD |
| Source discovery | Catalog browse/search | Yes (thin catalog) | — |
| Source evaluation | Quality/authority scoring | Thin MVP | External eval vendors |
| Licensing | Machine-readable rights | Yes (simple scopes) | Outside counsel drafts |
| Authentication | Agent + company identity | Yes | Auth0/Clerk/OIDC; later AP2 mandates |
| Routing | API/MCP proxy to source | Yes | Cloudflare Workers / API gateway |
| Payments | Collect buyer funds | Yes | Stripe / invoicing; optional x402 later |
| Settlement | Publisher payouts | Yes | Stripe Connect / ACH |
| Attribution | Citations in responses | Yes for trust use cases | — |
| Compliance | Policy + audit | Minimum for pilot vertical | Privacy counsel; SOC2 later |
| Reporting | Usage dashboards | Yes (basic) | — |
| Sponsored discovery | Paid placement | No — postpone | — |
| Outcome measurement | Prove data improved tasks | Pilot metric only | Customer analytics |

**MVP essentials:** thin catalog (1–3 sources), signed pilot licenses, MCP/API proxy, identity + budget controls, metering, invoice or prepaid credits, attribution, audit log.  
**Outsource first:** law firm for contracts; Stripe for payments; cloud IdP; one vertical data source’s native API rather than rebuilding their store.

---

## Delivery interfaces

1. **REST API** — retrieve / search / quote under license  
2. **MCP server** — tool calling for agent hosts  
3. **Secure feed / webhook** — freshness updates  
4. **Publisher proxy** — traffic stays on rights-holder infrastructure where required  

MCP alone is **not** sufficient: registries discover tools; they do not encode commercial licenses, settlement, or enterprise entitlement (see architecture and competitive files).

---

## Success definition for a product pilot

A pilot succeeds only if **all** of the following are true:

1. A real buyer pays (not free pilot forever).  
2. A real rights holder licenses machine access (not scraped content).  
3. The agent workflow measurably improves on a pre-agreed metric.  
4. The integration is reusable for a second buyer without rewriting contracts from scratch.

Anything less is a demo, not a product.

---

## Sources used

- Product definition is structural. Competitive and demand claims are deferred to `02-competitive-landscape.md` and `03-market-demand.md`.
- MCP registry scope (discovery, not commerce): https://modelcontextprotocol.org/registry/about (accessed 2026-07-15).
- Agent payment rails exist separately from content licensing (x402 Foundation / Stripe ACP / Google AP2) — treated as adjacent infrastructure, not the product core. See competitive landscape for dated citations.
