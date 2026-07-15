# 03 - Market Demand Evidence

**Research date:** 2026-07-15  
**Question:** Do AI developers and enterprises merely complain about missing proprietary/paywalled data, or is there evidence they pay to solve it?  
**Posture:** Skeptical. Complaints and clever workarounds are not the same as paid demand for an independent licensing/routing exchange.

---

## 1. Demand verdict

The demand signal is **real but narrow**.

There is strong evidence that AI-agent builders need fresher, cited, structured, rights-cleared data in legal, finance, clinical, scholarly, construction-code, logistics, and enterprise-workflow settings. There is also verified payment for adjacent retrieval/search APIs and verified bilateral licensing deals. The weak part is not the pain. The weak part is the proposed **independent horizontal intermediary**: the best-funded buyers either negotiate direct deals, use their own connector ecosystems, or become data marketplaces themselves.

**Verdict:** demand supports **a vertical pilot or demand-routing layer for mid-tail agent apps**, not a broad assumption that every complaint about paywalls converts into marketplace spend.

---

## 2. Evidence grading

- **Annoyance:** people complain, product pages acknowledge limitations, or users must paste/upload data manually.
- **Technical inconvenience:** developers build workarounds, connectors, custom APIs, MCP servers, browser agents, retry logic, or BYO-subscription flows.
- **Actual willingness to pay:** money changes hands through subscriptions, API usage, paid add-ons, licensing agreements, or marketplace pilots.

| Hypothesized pain | Best evidence tier | Skeptical read |
|---|---:|---|
| Paywalled information blocks agents | Willingness to pay | Legal, medical, scholarly, and publisher examples are strong; generic web paywall complaints are weak. |
| Fragmented proprietary APIs | Willingness to pay | Finance and enterprise agents pay/integrate; platform owners may internalize the routing layer. |
| Unclear AI rights | Technical inconvenience / willingness to pay | Standards and marketplaces exist, but broad buyer adoption is still early. |
| Stale search / missing real-time info | Willingness to pay | Exa, Tavily, Perplexity, Daloopa, and finance products price freshness directly. |
| Weak citations | Willingness to pay | Citation-backed products sell; this is strongest in regulated/professional verticals. |
| Manual research fallback | Technical inconvenience | Upload/BYO-login patterns show pain, not necessarily third-party licensing demand. |
| Expensive direct licensing | Willingness to pay | Proven at large buyers; unclear whether mid-tail agent apps can afford it. |
| Poor structured data | Willingness to pay | Financial, logistics, and GTM products monetize structured data normalization. |
| Rate limits | Technical inconvenience / willingness to pay | Paid tiers and enterprise contracts solve this; not necessarily via a new exchange. |
| Customer-provided subscriptions | Technical inconvenience | Strong evidence of a workaround that can bypass a marketplace. |
| Legal risk from scraping | Technical inconvenience / willingness to pay | Cloudflare, Microsoft PCM, and publisher controls show market formation; litigation risk alone does not prove agent-side budget. |

---

## 3. Annoyance evidence

These examples show the problem is felt. They do **not** by themselves prove paid demand.

1. **Scholarly paywalls bias agent research.** Search results and a CEUR-WS paper on deep research limitations state that autonomous agents have no right to bypass subscriptions and therefore over-sample open-access content; mitigation includes institutional proxy resolvers and access-gap alerts. The IntuitionLabs survey similarly reports that tools relying on abstracts or open versions miss paywalled studies.  
   Source: CEUR-WS paper, 2026 (`https://ceur-ws.org/Vol-4065/paper13.pdf`); IntuitionLabs, 2026 (`https://intuitionlabs.ai/articles/full-text-access-barriers-ai-research-tools`).

2. **Deep-research tools cannot reliably reach paywalled journals.** Nature-syndicated coverage of OpenAI's Deep Research reported that paywalled journal access was a "major issue" and that Sam Altman acknowledged the limitation.  
   Source: Sri Lanka Guardian / Nature syndication, Feb. 2025 (`https://slguardian.org/openais-deep-research-tool-a-game-changer-for-scientists-or-a-work-in-progress/`).

3. **Academic tools disclose full-text limits.** Elicit says it uses full text if available and abstracts if not, and its Library page says a browser agent can use access the researcher already has through an institution to simplify finding paywalled papers. Consensus explicitly says it does not provide special access to paywalled articles and instead links to publisher pages or institutional LibKey access.  
   Sources: Elicit (`https://elicit.com/`, `https://elicit.com/solutions/library`); Consensus University Access (`https://consensus.app/home/blog/getting-started-with-consensus-university-access/`).

4. **Generic web research agents hit blocks and stale/low-quality sources.** LangChain issue #36134 says web loaders fail on Cloudflare-protected sites such as major news outlets, LinkedIn, Amazon, and government pages, causing silent failures in research chains. Older LangChain issues show 403 errors and user-agent workarounds.  
   Sources: GitHub issue #36134 (`https://github.com/langchain-ai/langchain/issues/36134`); GitHub issue #1829 (`https://github.com/langchain-ai/langchain/issues/1829`).

5. **Users manually paste or upload content.** Elicit, Glass, and similar research/clinical tools support upload of user PDFs or records. This is evidence that source gaps exist, but it is also evidence that users route around licensing by bringing their own documents.  
   Sources: Elicit pricing/search pages (`https://elicit.com/`); Glass Health ambient/CDS pages (`https://glass.health/ambient-cds`).

**Skeptical note:** complaints are abundant but cheap. They mostly prove that agents encounter friction; they do not establish that a buyer will pay an independent exchange rather than paste documents, connect an existing subscription, use an enterprise connector, or buy from a dominant data owner directly.

---

## 4. Technical inconvenience evidence

These examples show teams building workarounds or product infrastructure.

1. **Custom scraping and anti-bot workarounds.** The LangChain Cloudflare issue proposes anybrowse-style scraping because standard loaders fail on protected sites. That is a developer workaround for blocked access, but it can create legal/compliance risk and brittle operations.  
   Source: GitHub issue #36134 (`https://github.com/langchain-ai/langchain/issues/36134`).

2. **MCP/connectors are becoming the default integration layer.** OpenAI documents built-in connectors for Dropbox, Gmail, Google Drive, Teams, Outlook, and SharePoint, and remote MCP servers for third-party/private data. Anthropic's Claude supports custom remote MCP connectors and enterprise search over Slack, Microsoft 365, Google, and custom sources. Cursor, Mistral Vibe, Devin, Sourcegraph Cody, and Glean all use MCP or connector ecosystems for live context.  
   Sources: OpenAI MCP/connectors docs (`https://developers.openai.com/api/docs/guides/tools-connectors-mcp`); OpenAI MCP server guide (`https://developers.openai.com/api/docs/mcp`); Anthropic MCP announcement (`https://www.anthropic.com/news/model-context-protocol`); Claude connector help (`https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp`); Cursor MCP docs (`https://cursor.com/docs/mcp`); Mistral MCP docs (`https://docs.mistral.ai/vibe/work/connectors/mcp-connectors`).

3. **Customer-provided subscriptions are productized.** Consensus uses LibKey to show which paywalled papers a user's institution already licenses; Elicit's browser agent can use institutional access; Scite MCP resolves institutional holdings; Perplexity Enterprise Pro requires separate FactSet/Crunchbase subscriptions for those integrations.  
   Sources: Consensus University Access (`https://consensus.app/home/blog/getting-started-with-consensus-university-access/`); Elicit Library (`https://elicit.com/solutions/library`); Scite MCP (`https://scite.ai/blog/introducing-scite-mcp`); Perplexity channel partners (`https://www.perplexity.ai/hub/blog/meet-our-first-channel-partners-data-integrators`).

4. **Agent apps build proprietary data-routing layers.** Rogo embeds financial data platforms and firm data; Hebbia's Deeper Research searches private documents, PitchBook, S&P Capital IQ, and web; Glean builds a permission-aware enterprise knowledge graph from 275+ connectors; Intercom Fin and Sierra use data connectors/APIs to fetch or update customer-specific records.  
   Sources: Rogo (`https://rogo.ai/`); Hebbia Deeper Research (`https://www.hebbia.com/blog/inside-hebbias-deeper-research-agent`); Glean connectors (`https://www.glean.com/platform/connectors`); Intercom Fin data connectors (`https://www.intercom.com/help/en/articles/9916507-data-connectors-faqs`); Sierra Agent Data Platform (`https://sierra.ai/blog/agent-data-platform`).

5. **Rights and attribution plumbing is still unsettled.** Cloudflare says Pay Per Crawl was a start but "crawling is a crude measure of value," and it is experimenting with Pay Per Use. Microsoft PCM was launched to avoid one-off licensing deals. This is infrastructure creation, not proof the market has equilibrated.  
   Sources: Cloudflare, July 1, 2026 (`https://blog.cloudflare.com/making-ai-search-smarter/`); Search Engine Land on Microsoft PCM, Feb. 3, 2026 (`https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191`).

**Skeptical note:** the strongest technical-inconvenience evidence cuts both ways. It proves agents need data-routing infrastructure, but it also shows that OpenAI, Anthropic, Google, Microsoft, Cursor, Glean, Perplexity, and vertical incumbents are already making connectors/MCP a platform feature.

---

## 5. Actual willingness-to-pay evidence

This is the evidence that matters most.

### 5.1 Paid retrieval/search APIs

Agent builders already pay metered prices for search, crawling, and retrieval inside workflows.

- **Exa** publishes API pricing of **$7/1k Search requests**, **$12-15/1k Deep Search requests**, **$1/1k content pages**, and agent runs from **$0.012-$1.00/run**. Its pricing page explicitly lists coding agents, chatbots, enrichments, and voice agents as use cases.  
  Source: Exa pricing, fetched July 2026 (`https://exa.ai/pricing?tab=api`).

- **Tavily** publishes a credit model: free 1,000 credits/month; paid plans from $30/month to $500/month; pay-as-you-go at $0.008/credit; basic search costs 1 credit and advanced search 2 credits.  
  Source: Tavily docs, accessed July 2026 (`https://docs.tavily.com/documentation/api-credits`).

- **Perplexity Finance Search / Agent API** states that one tool call combines licensed financial datasets, real-time market data, and cited web sources so developers do not have to integrate each licensed provider separately. A direct fetch was blocked, but search-visible product snippets and docs confirm the product positioning.  
  Sources: Perplexity blog/docs (`https://www.perplexity.ai/hub/blog/introducing-finance-search-in-the-agent-api`, `https://docs.perplexity.ai/docs/agent-api/finance-search`).

**Read:** this proves willingness to pay for retrieval in agent loops. It does not prove willingness to pay for high-priced proprietary content across all domains.

### 5.2 Paid proprietary-data integrations and licensing deals

1. **Harvey + LexisNexis.** LexisNexis and Harvey announced a strategic alliance on June 18, 2025 to integrate LexisNexis legal technology, primary law, and Shepard's Citations into Harvey, with co-developed workflows such as motions to dismiss and summary judgment. Harvey's help page says Ask LexisNexis is a paid add-on within Harvey.  
   Sources: LexisNexis press release, June 18, 2025 (`https://www.lexisnexis.com/community/pressroom/b/news/posts/lexisnexis-and-harvey-announce-strategic-alliance-to-integrate-trusted-high-quality-ai-technology-and-legal-content-and-develop-advanced-workflows`); Harvey help (`https://help.harvey.ai/articles/ask-lexisnexis`).

2. **OpenEvidence + JAMA/NEJM.** OpenEvidence signed a multi-year content agreement with JAMA Network on June 5, 2025; the agreement includes full text and multimedia from JAMA, JAMA Network Open, and 11 specialty journals. Fierce Healthcare reports a similar NEJM deal.  
   Sources: OpenEvidence/JAMA announcement, June 5, 2025 (`https://www.openevidence.com/announcements/openevidence-and-the-jama-network-sign-strategic-content-agreement`); Fierce Healthcare (`https://www.fiercehealthcare.com/ai-and-machine-learning/jama-signs-multi-year-deal-openevidence-inform-ai-powered-medical-search`).

3. **Rogo and financial data partners.** Rogo publicly says it embeds into firm systems and the financial data platforms teams rely on. Rogo announced integrations/partnerships with S&P Capital IQ and LSEG; third-party finance-AI comparisons cite FactSet, PitchBook, Preqin, Third Bridge, and Crunchbase as part of the broader network.  
   Sources: Rogo (`https://rogo.ai/`); Rogo S&P Capital IQ announcement (`https://rogo.ai/news/rogo-integrates-s-p-capital-iq-data-into-its-ai-powered-workflows`); Rogo LSEG announcement (`https://rogo.ai/news/announcing-our-strategic-partnership-with-lseg`).

4. **Hebbia + PitchBook/S&P Capital IQ.** Hebbia says Deeper Research searches private documents, public company data, PitchBook, S&P Capital IQ, sector insights, and web. PitchBook says its private-market data powers Hebbia Skills through a Premium Connector.  
   Sources: Hebbia, "Inside Deeper Research" (`https://www.hebbia.com/blog/inside-hebbias-deeper-research-agent`); PitchBook/Hebbia (`https://pitchbook.com/blog/pitchbook-and-hebbia-skills-deliver-institutional-grade-outputs-in-seconds`).

5. **Daloopa MCP.** Daloopa publishes a remote MCP server for AI agents to access financial fundamentals, filings, transcripts, documents, and stock prices, with source location mapped to outputs.  
   Source: Daloopa docs, fetched July 2026 (`https://docs.daloopa.com/docs/daloopa-mcp`).

6. **Scite MCP / scholarly publishers.** Scite says it searches 280M+ full-text scholarly articles and is built on direct agreements with Wiley, SAGE, and 30+ publishers; its MCP lets Claude, ChatGPT, Cursor, and other tools search full text while respecting access rights.  
   Sources: Scite (`https://scite.ai/`); Scite MCP blog (`https://scite.ai/blog/introducing-scite-mcp`).

7. **Cloudflare Pay Per Use.** Cloudflare says Pay Per Crawl is evolving toward Pay Per Use, with Ceramic.ai paying when opted-in publisher content appears in results and You.com allowing agents to pay on demand for specific premium content. Cloudflare explicitly calls this an experiment.  
   Source: Cloudflare, July 1, 2026 (`https://blog.cloudflare.com/making-ai-search-smarter/`).

8. **Microsoft Publisher Content Marketplace.** Search Engine Land reports Microsoft launched PCM on Feb. 3, 2026 so publishers can set terms, track usage, and get paid when AI systems ground answers in premium licensed content. Early pilots grounded Copilot responses, with Yahoo onboarding as a demand partner.  
   Source: Search Engine Land, Feb. 3, 2026 (`https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191`).

**Read:** these examples prove paid demand exists. However, most are direct partnerships or platform-native marketplaces, not neutral third-party exchanges.

---

## 6. What evidence is weak

1. **Mid-tail willingness-to-pay is mostly inferred.** Well-funded vertical winners can pay LexisNexis, JAMA, FactSet, PitchBook, or LSEG. A smaller agent app may want the data but not afford minimums, legal review, or redistribution restrictions.

2. **No clear proof of budget for a demand-routing exchange.** Buyers pay for outcomes: accurate legal answers, clinical support, market data, logistics optimization, support resolution, or coding productivity. They may not pay separately for a marketplace unless it compresses procurement, rights, and integration time.

3. **BYO subscription can be a substitute.** If the customer already has FactSet, Lexis, Westlaw, DynaMed, UpToDate, Bloomberg, or institutional library access, the agent app can route through that entitlement rather than pay a new data broker.

4. **Large platforms internalize.** OpenAI/Anthropic/Mistral/Cursor/Glean/Perplexity can make connectors and MCP distribution a native feature. Microsoft and Cloudflare can make publisher licensing a platform rail. This weakens the standalone exchange thesis.

5. **Publisher-side revenue may be small or experimental.** Cloudflare's own framing is experimental, and no public pricing/volume for Ceramic or You.com Pay Per Use is disclosed.

---

## 7. Practical implication for the agent-data-exchange thesis

The best wedge is not "all agents need the web." The best wedge is:

> **Mid-market vertical agent applications that need a small number of expensive, rights-sensitive proprietary datasets but lack the leverage, legal capacity, or connector infrastructure to negotiate one-off data deals.**

Likely first verticals:

1. **Legal litigation and personal injury** - high citation/legal-risk need, expensive data, clear ROI.
2. **Clinical decision support** - strong need for licensed medical knowledge, but high regulatory burden.
3. **Finance / private markets** - strongest willingness to pay, but also the most direct incumbent competition.
4. **Construction compliance / building codes** - narrow, high-value, citation-heavy, less crowded.
5. **Logistics/supply chain** - strong real-time structured-data need, but major platforms own their data graphs.

---

## Sources

Accessed or searched on 2026-07-15 unless a publication date is listed.

- LexisNexis and Harvey strategic alliance, June 18, 2025: `https://www.lexisnexis.com/community/pressroom/b/news/posts/lexisnexis-and-harvey-announce-strategic-alliance-to-integrate-trusted-high-quality-ai-technology-and-legal-content-and-develop-advanced-workflows`
- Harvey Ask LexisNexis help page: `https://help.harvey.ai/articles/ask-lexisnexis`
- OpenEvidence and JAMA Network agreement, June 5, 2025: `https://www.openevidence.com/announcements/openevidence-and-the-jama-network-sign-strategic-content-agreement`
- Fierce Healthcare on JAMA/OpenEvidence and NEJM: `https://www.fiercehealthcare.com/ai-and-machine-learning/jama-signs-multi-year-deal-openevidence-inform-ai-powered-medical-search`
- Cloudflare "Making AI search smarter," July 1, 2026: `https://blog.cloudflare.com/making-ai-search-smarter/`
- Search Engine Land on Microsoft PCM, Feb. 3, 2026: `https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191`
- Exa pricing: `https://exa.ai/pricing?tab=api`
- Tavily API credits: `https://docs.tavily.com/documentation/api-credits`
- Perplexity Finance Search: `https://www.perplexity.ai/hub/blog/introducing-finance-search-in-the-agent-api`
- Perplexity Finance Search docs: `https://docs.perplexity.ai/docs/agent-api/finance-search`
- Perplexity channel partners/data integrators: `https://www.perplexity.ai/hub/blog/meet-our-first-channel-partners-data-integrators`
- Daloopa MCP docs: `https://docs.daloopa.com/docs/daloopa-mcp`
- Rogo homepage: `https://rogo.ai/`
- Rogo S&P Capital IQ integration: `https://rogo.ai/news/rogo-integrates-s-p-capital-iq-data-into-its-ai-powered-workflows`
- Rogo LSEG partnership: `https://rogo.ai/news/announcing-our-strategic-partnership-with-lseg`
- Hebbia Deeper Research: `https://www.hebbia.com/blog/inside-hebbias-deeper-research-agent`
- PitchBook/Hebbia connector: `https://pitchbook.com/blog/pitchbook-and-hebbia-skills-deliver-institutional-grade-outputs-in-seconds`
- Scite AI: `https://scite.ai/`
- Scite MCP: `https://scite.ai/blog/introducing-scite-mcp`
- Elicit: `https://elicit.com/`
- Elicit Library: `https://elicit.com/solutions/library`
- Consensus University Access: `https://consensus.app/home/blog/getting-started-with-consensus-university-access/`
- CEUR-WS deep research limitations paper: `https://ceur-ws.org/Vol-4065/paper13.pdf`
- IntuitionLabs full-text barriers survey: `https://intuitionlabs.ai/articles/full-text-access-barriers-ai-research-tools`
- LangChain issue #36134: `https://github.com/langchain-ai/langchain/issues/36134`
- LangChain issue #1829: `https://github.com/langchain-ai/langchain/issues/1829`
- OpenAI MCP/connectors docs: `https://developers.openai.com/api/docs/guides/tools-connectors-mcp`
- OpenAI MCP server guide: `https://developers.openai.com/api/docs/mcp`
- Anthropic MCP announcement: `https://www.anthropic.com/news/model-context-protocol`
- Claude custom connectors: `https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp`
- Cursor MCP docs: `https://cursor.com/docs/mcp`
- Mistral MCP connectors: `https://docs.mistral.ai/vibe/work/connectors/mcp-connectors`
- Glean connectors: `https://www.glean.com/platform/connectors`
- Intercom Fin data connectors: `https://www.intercom.com/help/en/articles/9916507-data-connectors-faqs`
- Sierra Agent Data Platform: `https://sierra.ai/blog/agent-data-platform`
