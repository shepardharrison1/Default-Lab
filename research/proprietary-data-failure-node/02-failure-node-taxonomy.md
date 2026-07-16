# Failure-Node Taxonomy

**Research date:** 2026-07-16  
**Purpose:** Separate failures that can plausibly be resolved by purchasing external proprietary data from failures that a proprietary-data resolution layer cannot solve.

## Core distinction

A failure node is **data-related** when the agent's next correct action depends on information that is missing, stale, incomplete, low-authority, conflicting, unavailable under the user's current entitlements, or legally restricted from agent use. A failure node is **non-data** when the blocker is caused by unclear intent, weak reasoning, poor implementation, missing permissions, bad architecture, insufficient tests, context limitations, or tool execution problems. The distinction matters because a broker can buy or license information; it cannot buy better requirements, replace engineering judgment, or grant software permissions the buyer does not have.

The product thesis requires a stricter subtype: **externally purchasable proprietary-data-resolvable** failures. Many data failures are not in that subtype. Some can be solved with public docs, customer-owned internal data, asking the user, better retrieval, or a normal API key. Others involve data that exists but cannot legally be used by an agent. The opportunity is the residue where (1) the missing information is materially blocking the task, (2) a rights holder can lawfully provide it, (3) minimal access is sufficient, (4) the answer can be protected against extraction, and (5) the buyer will pay.

## Data-related failure taxonomy

| Data type | Can purchasing external proprietary data help? | Typical rights holder | Free substitutes | Coding-agent relevance | Detection signals |
| --- | --- | --- | --- | --- | --- |
| Missing domain rules | Yes | Payers, standards bodies, compliance vendors, insurers, trade associations, regulators' licensed distributors | Public summaries, outdated PDFs, community examples, human SME | High in vertical automation; low in generic app coding | Agent asks for rule, generates placeholders, tests fail on domain edge case, reviewer says "depends on payer/policy/jurisdiction" |
| Technical standards | Partial | Standards bodies, consortia, certification labs | Public excerpts, open implementations, blog posts, old drafts | Medium-high when implementing protocols, EDI, safety, healthcare, construction, telecom | Unknown field semantics, conflicting standard versions, model cites non-public standard text, conformance tests fail |
| Schemas/dictionaries | Yes | API vendors, EHR/ERP/fintech platforms, standards maintainers, data aggregators | OpenAPI files, public code lists, reverse-engineered examples | High for integration work | Unknown enum/code, mapping failures, validation errors, outdated schema, missing field dictionary |
| API docs | Partial | API provider, SaaS vendor, developer platform | Public docs, Context7, source code, SDKs, Stack Overflow | High, but public-doc gap is already served by Context7-style tools | Hallucinated endpoint, deprecated method, auth mismatch, SDK version conflict, docs unavailable behind login |
| Historical edge cases | Partial | Large operators, vendors, claims processors, incident databases, support systems | GitHub issues, forums, postmortems, synthetic tests | Medium; high in mature operational domains | Agent handles happy path only, failures appear only in rare variants, tests lack examples, SME requests "known exceptions" |
| Workflow examples | Partial | Domain software vendors, implementation consultants, enterprise operators | Tutorials, sample repos, public playbooks | Medium-high for automating business workflows | Agent can code primitives but misorders steps, misses approval gates, asks for "example real workflow" |
| Eval/benchmark data | Partial | Benchmark providers, enterprises, test-data vendors, standards labs | Open benchmarks, unit tests, generated fixtures | Medium; helps verify but not always generate | No test oracle, agent cannot judge correctness, repeated regressions, human says "we need representative cases" |
| Regulatory requirements | Partial | Governments, legal publishers, compliance vendors, standards bodies | Public statutes/regulations, agency guidance, blogs | Medium-high in regulated automation | Jurisdiction/date ambiguity, agent cites stale rule, conflicting interpretations, compliance review failure |
| Product compatibility | Yes | Manufacturers, distributors, certification bodies, parts databases, e-commerce data vendors | Manuals, forums, open product pages | Medium in industrial, construction, hardware, IT ops | Agent cannot decide compatible version/part, conflicting specs, missing certification, runtime/integration mismatch |
| Pricing/market info | Partial | Market-data vendors, distributors, procurement platforms, exchanges, resellers | Public price pages, scraped listings, user input | Low-medium for coding; higher for automation that quotes or procures | Agent needs current price, quote, availability, lead time, benchmark, or SKU mapping |
| Operational telemetry | Rarely | Buyer organization, cloud vendor, observability vendor, device fleet operator | Internal logs/metrics, public status pages | Medium, but usually internal not external | Agent cannot reproduce prod issue, needs traces/logs, asks for runtime evidence, external purchase not relevant unless vendor telemetry sold |
| Real-world environment data | Partial | GIS providers, weather vendors, IoT/fleet operators, local authorities, sensor networks | OpenStreetMap, NOAA/weather, public GIS, user photos | Low in generic coding; high in field automation | Task depends on location, weather, route, site condition, asset state, or local constraint |
| Stale info | Partial | Current-data providers, API vendors, documentation services, news/market feeds | Web search, public docs, Context7, official release notes | High for API drift; often public rather than proprietary | Deprecated API use, version mismatch, model cites old behavior, tests pass locally but fail against current service |
| Incomplete coverage | Partial | Aggregators, domain vendors, data consortiums | Multiple public sources, user-provided samples | Medium | Agent succeeds on common cases, fails on geography/vendor/category not covered, missing mapping rows |
| Conflicting sources | Partial | Authoritative publishers, standards bodies, primary data vendors | Public source comparison, human judgment | Medium | Agent retrieves contradictory docs, cites blogs over official source, uncertain answer, reviewer asks for authoritative source |
| Low-authority sources | Partial | Primary rights holder, regulator, certified vendor | Public blogs/forums, model memory | Medium | Agent relies on Stack Overflow/blog, no primary citation, regulated or contractual task requires authority |
| Unavailable customer entitlements | No / Partial | Customer's existing SaaS, data vendor, internal system | Ask user/admin, existing enterprise contract | High, but broker may only route/check, not "purchase" | 401/403, SSO missing, license exists but not connected, user says company already subscribes |
| Data exists but cannot legally be used by an agent | No / Rarely | Data subject, employer, data controller, restricted licensor | Redacted/synthetic data, legal review, human-only process | Medium in regulated enterprise work | License prohibits automated use, PII/PHI/export-control flag, contract says no AI processing, policy denial |

## Non-data failures this platform does not solve

| Failure type | Why proprietary data does not solve it | More appropriate remedy | Common detection signals |
| --- | --- | --- | --- |
| Bad prompts | The agent was asked the wrong thing or with missing intent. | Clarify task, improve prompt, write acceptance criteria. | Vague request, shifting goals, overbroad instruction, no success condition. |
| Weak reasoning | The information is available but the model draws the wrong conclusion. | Better model, decomposition, tests, review, tool use, constrained planning. | Contradicts retrieved source, invalid logic, ignores evidence. |
| Unclear requirements | The product decision is absent, not hidden in a proprietary source. | Human product/engineering clarification. | Multiple valid implementations, "should it do X or Y?", no owner decision. |
| Missing software permissions | The agent lacks repo, environment, SaaS, database, or deployment access. | Grant credentials, configure secrets, approve tool permissions. | 401/403, missing token, sandbox denial, access-request loops. |
| Poor architecture | The design is inappropriate even with complete data. | Engineering design review, refactor, architecture constraints. | Tight coupling, wrong abstraction, scaling/security issues. |
| Coding bugs | The agent wrote incorrect code unrelated to missing facts. | Tests, debugging, static analysis, code review. | Type errors, failing unit tests, syntax errors, off-by-one logic. |
| Insufficient testing | No oracle proves whether the change works. | Test design, fixtures, CI, eval harness. | "Looks done" without tests, untested branch, missing regression coverage. |
| Tool-call failures | The environment or integration failed, not the data source. | Retry, tool fix, network/debugging, better error handling. | Timeout, malformed JSON, server 500, local process crash. |
| Context-window limits | Relevant information exists but was not in context or was evicted. | Retrieval, summarization, memory, smaller task decomposition. | Agent forgets earlier constraints, repeats work, loses file context. |
| Weak human specs | The human has not specified business rules, priorities, or acceptable tradeoffs. | Spec writing, stakeholder review, examples. | "Use common sense", no edge cases, no owner for ambiguity. |

## Evidence anchors

- **API drift paper:** The arXiv-indexed paper summarized as "When LLMs Lag Behind: Knowledge Conflicts from Evolving APIs in Code Generation" reports a benchmark of 270 real-world API updates across eight Python libraries and 11 models. Executability was about **42.55% without comprehensive documentation** and rose to about **66.36% with structured documentation**. This supports two points: current docs materially help coding agents, and documentation does not fully solve reasoning/context-memory conflict. [Secondary summary of paper; numbers treated as cited research.]
- **Context7:** Context7/Upstash provides up-to-date, version-specific documentation and code examples through MCP/CLI, directly targeting stale public-library/API-doc failures. This compresses the generic public-docs opportunity. [Verified for product positioning.]
- **Augment/Osmani 80% problem:** The published framing says agents often deliver the visible functional code while omitting non-functional requirements such as security, observability, error handling, rate limits, audit logging, and architectural consistency. Those omissions are mostly not purchasable external data. [Secondary/company-claimed framing; inference for taxonomy weighting.]

## Resolvability estimate

**Inference:** Across serious coding-agent failures, only **10-20%** are plausibly resolvable by purchasing external proprietary data.

Reasoning:

1. **General coding is dominated by non-data blockers.** Many serious failures are caused by vague requirements, weak design, bugs, insufficient tests, missing credentials, or context loss. Buying a dataset does not fix these.
2. **Public documentation is important but not the proprietary-data wedge.** API drift research shows that docs can raise executability from roughly 42-66%, and Context7-style tools provide current public docs inside the agent workflow. That leaves a smaller proprietary-doc gap.
3. **Project/internal context is not externally purchasable.** Customer-specific schemas, production telemetry, logs, entitlements, and business rules often live inside the buyer's organization. A broker may route access, but it is not buying external proprietary data.
4. **Regulated verticals create a real but narrow residue.** Healthcare claim edits, payer policies, sanctions/compliance data, construction codes, standards, product compatibility, and local regulatory interpretation can be externally licensed and can materially change task success.
5. **Legal usability further narrows the set.** Some data exists but cannot be used by an agent under privacy, contract, copyright, or sector rules. Minimal access helps only when rights can be granted.

### Range by workflow

| Workflow type | Estimated share of serious failures resolvable by purchasing external proprietary data | Notes |
| --- | --- | --- |
| Generic web/app coding | 2-8% | Mostly public docs, project context, reasoning, tests, and requirements. |
| API-heavy SaaS integration | 5-15% | Some private docs/schemas help, but public docs and customer credentials dominate. |
| Enterprise internal automation | 5-15% | Many data issues are internal entitlements, not external purchases. |
| Regulated vertical automation | 15-35% | Strongest wedge: payer rules, compliance data, standards, local rules, certification data. |
| Data/compliance product implementation | 20-40% | Purchasable watchlists, benchmarks, dictionaries, and regulatory feeds may be central. |

The overall 10-20% estimate assumes a mixed serious-failure population with far more general coding and SaaS integration than high-stakes vertical automation. A pilot should intentionally over-sample the vertical rows, because that is where the thesis has any chance of becoming a company rather than a connector library.

## Practical classification rules

Treat a failure as a candidate for paid proprietary-data resolution only when most of these are true:

- The agent can name the missing data class, jurisdiction, provider, standard, code set, date, version, or rights holder.
- Free public docs, Context7-style retrieval, and repo search have been tried or are clearly insufficient.
- The answer depends on authority, coverage, freshness, entitlement, or license rights.
- A minimal answer can unblock the task without exposing the whole corpus.
- The buyer has a budgeted reason to pay, such as denied claims, compliance risk, failed certification, bad quote, or operational rework.
- The output can carry provenance and license constraints into the generated code or automation artifact.

Reject paid resolution when:

- The agent is guessing because requirements are unclear.
- The missing source is inside the buyer's own systems.
- The blocker is credentials or software permission.
- The answer is available in public official docs.
- The data license prohibits agent use.
- The task requires human judgment rather than data access.
