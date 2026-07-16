# Data-Moat Preservation

**Research date:** 2026-07-16  
**Posture:** Skeptical. The default assumption is that access becomes leakage unless constrained technically, contractually, and economically.  
**Recommendation tie-in:** **Pursue only through a narrow pilot** where a rights holder accepts measurable residual leakage risk.

## Bottom line

Controlled agent access can reduce leakage compared with bulk dataset delivery, but it does not magically preserve a rights-holder moat. The phrase "only the agent sees it" is not a sufficient control. The enterprise operating the agent benefits from the answer, may store traces and outputs, may route content through its infrastructure, may send content to model providers, and may use repeated calls to approximate the underlying dataset. A data owner should treat every licensed agent call as a controlled disclosure to the buyer organization and its subprocessors, not as a private conversation between data and model.

The strongest practical pattern is not raw retrieval. It is **source-hosted, entitlement-gated, query-limited, short-retention, provenance-rich answers with anti-extraction thresholds and audit rights**. Even then, the system protects value only when the useful answer is naturally narrow: a validation result, rule decision, code-set mapping, yes/no eligibility check, ranked citation, aggregate, or transformation. If the customer's task requires many row-level facts, broad excerpts, or corpus-scale exploration, the moat will erode.

**Verified control anchor:** Snowflake Cortex Knowledge Extensions support content protection thresholds: providers can limit the percentage of indexed corpus that a consumer can retrieve within a rolling 24-hour period; Snowflake's documentation shows `cke_content_protection` with `threshold: 0.2`, meaning 20% of the indexed corpus, and blocks queries after the threshold is hit until the window refreshes. This is a real anti-extraction control, not just a promise. It is also incomplete: it is corpus-level, not per-document, and does not prevent a licensed consumer from retaining and exploiting the answers they were allowed to receive. [Verified from Snowflake CKE overview and listing manifest documentation, accessed 2026-07-16.]

## Control comparison

| Control | What it preserves | What it fails to prevent | Pilot suitability |
| --- | --- | --- | --- |
| Source-hosted queries | Raw corpus stays with rights holder; buyer receives bounded result. | Buyer can retain outputs; repeated queries can extract slices; logs may leak query intent. | High. Default pattern for pilot. |
| Row/field APIs | Limits access to specific fields and predicates; easier to price and audit. | A determined caller can enumerate rows unless rate-limited and anomaly-detected. | High if the answer can be represented as fields, validations, or decisions. |
| MCP tools | Fits agent workflow; exposes controlled functions rather than files. | MCP is an interface, not a protection boundary; tool responses still enter agent context and logs. | High as integration surface, low as standalone protection. |
| Secure enclaves / TEEs | Protect data and code in use from cloud operators and some infrastructure compromise; support attestation. | Do not stop authorized enterprise from retaining outputs; do not solve policy, licensing, or prompt extraction by themselves. | Medium. Useful for high-sensitivity pilots, overkill for many MVPs. |
| Confidential computing GPUs | Protect model/data execution with attestation and encrypted data paths in supported hardware stacks. | Do not prevent the model or user from receiving permitted outputs; operationally complex; vendor-specific maturity. | Low for MVP unless rights holder demands it. |
| Clean rooms | Allow constrained joins/analytics without raw bilateral sharing. | Less natural for interactive coding-agent lookups; aggregate outputs can still leak under weak query rules. | Medium for analytics/eval, not first-line for coding-agent answer retrieval. |
| Differential privacy | Protects individual-level privacy in aggregate queries by adding calibrated noise and budget limits. | Often inappropriate for deterministic coding/domain-rule answers; does not protect non-personal IP value well. | Low for MVP except healthcare/marketing/consumer aggregates. |
| Short-retention retrieval | Reduces trace/log accumulation; limits accidental secondary use. | Enterprise may still save generated code, screenshots, answers, or audit artifacts. | High. Required. |
| Query-only / no bulk export | Prevents obvious dataset transfer. | Repeated-query extraction and semantic reconstruction remain possible. | High. Required. |
| Aggregated answers | Reduces row-level leakage and individual facts. | May be unusable for tasks requiring exact rule or citation; aggregates can leak through differencing. | Medium. Use where task allows. |
| Output filtering | Blocks long excerpts, raw rows, identifiers, copyrighted text, PHI, or restricted fields. | Filters are bypassable; semantic summaries can still transfer value. | High, but must be combined with budgets and review. |
| Rate limits | Slows extraction and controls cost. | Does not stop slow extraction over time or multi-account abuse. | High. Required. |
| Corpus retrieval thresholds | Caps total content returned over a window, similar to Snowflake CKE content protection. | Thresholded content may still be valuable; caps must account for aliases, accounts, and output retention. | High. Required for corpus/RAG-style access. |
| Watermarking | Helps detect copied text or sourced outputs downstream. | Does not prevent use; unreliable for transformed facts, code, or paraphrases. | Medium. Useful for enforcement evidence. |
| Provenance receipts | Records source, version, license, time, policy, and permitted downstream use. | Does not stop misuse; depends on downstream systems preserving receipts. | High. Required. |
| No-training contracts | Blocks training/fine-tuning use contractually. | Weak against determined extractors unless backed by logging, audit rights, technical separation, and model-provider terms. | Required but not sufficient. |
| Deletion/revocation | Allows rights holder to cut off future access and require deletion of stored outputs/traces. | Cannot reliably recall facts already learned by humans, models, generated code, or customer systems. | Required but limited. |

## Threat-by-threat analysis

### Dataset reconstruction

**Best controls:** source-hosted query execution, no bulk export, row/field scoping, corpus-retrieval thresholds, query-shape restrictions, rate limits, anomaly detection, and output filtering.

**Residual risk:** A buyer can reconstruct material portions of a dataset through systematic enumeration if queries are expressive enough. For example, a tool that answers "what is the rule for payer X, code Y, modifier Z, date D?" can be called across the cross-product of payers, codes, modifiers, and dates. Snowflake-style corpus thresholds help because they cap total content retrieval over a rolling window. They do not solve semantic reconstruction where the answer is a compact decision rather than a retrieved document excerpt.

**Pilot implication:** Choose a failure class where each call returns a narrow decision or validation, not a long excerpt. Set per-buyer daily, weekly, and monthly budgets below the level needed to recreate a commercially meaningful corpus.

### Repeated-query extraction

**Best controls:** account-level and organization-level budgets, rate limits, deduplication, query similarity clustering, query templates, minimum specificity, randomized challenge/review for suspicious patterns, and provider-side cutoffs.

**Residual risk:** Slow extraction can look like legitimate high-volume use. Multi-seat enterprise accounts and multiple projects can distribute the pattern. Determined extractors can vary prompts to avoid exact-duplicate detection.

**Pilot implication:** Treat extraction monitoring as a product feature, not a legal appendix. Report suspicious query clusters to the rights holder and reserve the right to suspend access.

### Model memorization

**Best controls:** no-training/no-fine-tuning terms, provider subprocessors with zero-retention or enterprise no-training commitments, isolation between retrieval context and training pipelines, short trace retention, and output minimization.

**Residual risk:** If retrieved data enters prompts, completions, traces, eval datasets, or fine-tuning corpora, it can be memorized or re-emitted. Even absent formal training, agents and humans can store answer patterns in code, tests, comments, docs, and internal knowledge bases.

**Pilot implication:** Do not send raw proprietary passages to general model APIs unless the model-provider contract explicitly covers no training, retention, subprocessors, abuse monitoring, and deletion. Prefer source-hosted decision APIs that return compact answers.

### Customer retention

**Best controls:** limited retention, field-level redaction, encrypted logs, trace sampling, TTLs, deletion workflows, license receipts, and downstream-use restrictions.

**Residual risk:** The customer necessarily retains something: generated code, test fixtures, business decisions, reviewer notes, issue comments, and audit records. If the proprietary source is used to implement business logic, some value is embodied in that implementation.

**Pilot implication:** Contracts must distinguish allowed retention of derived work product from prohibited retention of source content. Rights holders should expect leakage through derived logic and price accordingly.

### Unauthorized fine-tuning

**Best controls:** no-training terms, technical separation from training data stores, audit logs, model-provider enterprise contracts, explicit prohibition on adding retrieved answers to eval/fine-tune datasets without approval, and watermark/provenance tags.

**Residual risk:** Fine-tuning misuse is hard to detect after the fact. A determined buyer can copy outputs into a private training set unless outputs are too narrow or low-volume to matter.

**Pilot implication:** The pilot should not allow raw excerpts or broad labels that are attractive as supervised training data. Evaluation datasets should use synthetic or rights-cleared cases unless separately licensed.

### Output laundering

**Best controls:** provenance receipts, answer watermarking where feasible, restrictions on paraphrase/redistribution, review of generated artifacts, and citation requirements for code comments/docs generated from licensed answers.

**Residual risk:** Facts can be paraphrased, embedded in code, converted into tests, or summarized as "domain knowledge." Watermarks are weaker once content becomes executable logic or a yes/no decision.

**Pilot implication:** Measure resolved tasks but keep licensed outputs concise. Do not claim that laundering can be technically eliminated.

### Competitor access

**Best controls:** enterprise entitlement checks, KYC/KYB, buyer allowlists/blocklists, field-of-use restrictions, competitive-use exclusions, provider approval for high-risk buyers, and per-customer pricing.

**Residual risk:** Competitors may access through subsidiaries, vendors, integrators, trial accounts, or customers. Data owners may not want a broker deciding who is a competitor.

**Pilot implication:** Provider must retain final approval over buyer eligibility and allowed field of use.

### Log leakage

**Best controls:** structured logging with redaction by default, separation of query metadata from content, encrypted storage, short TTLs, access controls, audit trails, least-privilege support tooling, and no raw prompt retention unless required.

**Residual risk:** The query itself may reveal sensitive business intent: "payer X rejects code Y under condition Z" can be valuable even without the answer. Observability providers, agent hosts, and broker support staff may see traces.

**Pilot implication:** Treat prompts, tool inputs, tool outputs, and error messages as licensed and confidential data. Observability integrations must support content redaction and retention controls.

### Leakage through model providers

**Best controls:** enterprise model-provider terms, zero-data-retention or no-training API settings where available, subprocessor disclosure, regional processing controls, content filters that keep raw source out of prompts, and source-side computation before model summarization.

**Residual risk:** If a model provider receives proprietary text, it becomes a subprocessor or independent recipient depending on contract structure. Abuse monitoring, safety logging, and debugging may retain content even when training is excluded.

**Pilot implication:** The architecture should minimize proprietary content sent to general LLMs. When unavoidable, the buyer and rights holder must approve the model provider and retention setting.

## Why "agent-only" access is not enough

An "agent-only" claim hides the real beneficiaries and data paths. In a coding workflow:

1. The enterprise user asks the agent to complete work.
2. The agent invokes a proprietary source.
3. The answer enters the agent context, tool trace, generated code, review diff, comments, tests, or ticket.
4. The enterprise retains the useful artifact and may run it in production.
5. The model provider, observability provider, IDE host, broker, and data owner may each log part of the event.

The agent is therefore not the only recipient in any meaningful economic sense. The enterprise benefits from the licensed information. Its infrastructure and subprocessors may process it. The correct control objective is **least-privilege, auditable enterprise use**, not "only the agent saw it."

## Controls that should be mandatory for a pilot

- Source-hosted queries or provider-approved APIs; no raw corpus delivery.
- Buyer and project entitlement checks before every paid call.
- Explicit field-of-use and no-training/no-fine-tuning policy attached to each response.
- Response templates that return decision, citation, confidence, version, and allowed-use metadata.
- Per-buyer rate limits and rolling corpus/query budgets.
- Corpus retrieval thresholds for RAG-like providers, modeled on Snowflake CKE content protection.
- Redaction of raw content from traces by default; short retention for prompts/tool outputs.
- Provider-visible usage reports and anomaly alerts.
- Provenance receipts carried into generated artifacts.
- Revocation path for future access and deletion path for stored traces.
- Audit rights for rights holder and buyer compliance teams.

## Controls that should not be oversold

- **Contracts alone:** necessary, but weak against a determined extractor without technical budgets, logs, and enforcement.
- **TEEs alone:** useful for protecting data in use from infrastructure operators, but they do not stop authorized outputs from being retained.
- **Watermarking alone:** helps with evidence, not prevention.
- **Differential privacy:** valuable for aggregate personal-data analytics, usually mismatched to deterministic coding-agent rule answers.
- **MCP alone:** convenient integration, not a security model.
- **No raw download buttons:** insufficient if the API can be enumerated.

## Scoring of access patterns

| Pattern | Moat preservation | Buyer utility | Operational complexity | Recommended role |
| --- | --- | --- | --- | --- |
| Raw dataset delivery | Low | High for buyer | Medium | Exclude from MVP. |
| RAG over hosted corpus with thresholds | Medium | Medium-high | Medium | Use only with strict thresholds and excerpt limits. |
| Source-hosted decision API | High | High when task is rule-like | Medium | Best default. |
| Source-hosted row/field API | Medium-high | High | Medium | Accept with enumeration controls. |
| Secure enclave evaluation | Medium-high | Medium | High | Reserve for sensitive enterprise pilots. |
| Clean-room aggregate query | Medium-high | Low-medium for coding | High | Use for evals/analytics, not primary MVP path. |
| Public-doc retrieval | Not a moat | High for generic coding | Low | Treat as free substitute, not proprietary wedge. |

## Evidence label summary

- **Verified:** Snowflake CKE content-protection thresholds; AWS Clean Rooms controls and differential privacy positioning; NVIDIA H100 confidential-computing attestation/data-in-use claims; OpenSanctions reseller/OEM licensing pattern from official pages.
- **Company-claimed:** Vendor descriptions of confidential AI agents, publisher licensing gateways, and inference-time monetization tools.
- **Inference:** Agent-only access is economically insufficient; TEEs do not prevent authorized-output retention; most effective pilot pattern is source-hosted decision APIs plus budgets and provenance.

## Conclusion

Controlled access can preserve a rights-holder moat only if the answer shape is narrow, query volume is bounded, and the rights holder can see and enforce usage. The platform should not promise that agent mediation prevents leakage. It should promise a more modest and testable thing: compared with bulk licensing or ad hoc browser/subscription use, it can reduce extraction surface, meter usage, preserve provenance, and stop access when behavior looks like dataset reconstruction. That is enough for a narrow pilot. It is not enough to support a broad claim that proprietary data can be safely opened to all coding agents.
