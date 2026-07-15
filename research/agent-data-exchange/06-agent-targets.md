# 06 - Agent-Application Targets

**Research date:** 2026-07-15  
**Output pair:** this memo plus `agent-targets.csv`  
**Posture:** skeptical. Inclusion means "credible enough to investigate," not "likely customer" or "known buyer."

---

## 1. Method for discovery

I used four filters:

1. **Seed list from the research brief.** I verified named companies where possible: Harvey, EvenUp, Spellbook, CoCounsel/Thomson Reuters, Hebbia, Bloomberg/ASKB, PitchBook, AlphaSense/Tegus, Daloopa, Rogo, Abridge, Nabla, PathAI, Samsara, Flexport, project44, UpCodes, Procore, Autodesk, TravelPerk/Perk, Expedia, and others.
2. **Search pattern.** For each candidate I searched combinations of: company + "AI agent", "assistant", "copilot", "MCP", "connector", "data integration", "licensed data", "citations", "paywalled", "EHR", "FactSet", "PitchBook", "DynaMed", "Westlaw", "building codes", "supply chain data", "travel inventory".
3. **Evidence threshold.** I kept companies with public evidence of at least one of:
   - RAG/agent product grounded in proprietary or customer data;
   - premium API/data integrations;
   - BYO subscription or entitlement pattern;
   - citation/verification problem in a regulated/professional workflow;
   - explicit statement that data fragmentation is a bottleneck.
4. **Exclusions and downgrades.** I did not include a company merely because its industry uses proprietary data. I downgraded targets that already own the relevant dataset, already publish an MCP/API, or are large enough to internalize the exchange.

The CSV contains **52 targets**. **24 are high-confidence** as agent applications with a real proprietary-data gap. "High confidence" means high confidence in the data-gap/agent-workflow match, **not** high confidence they would buy from a new exchange.

---

## 2. Target patterns

### Pattern A - Direct evidence of paid/licensed data dependency

The cleanest demand-side evidence is where an agent product already integrates licensed data:

- **Harvey + LexisNexis** for primary law and Shepard's Citations.
- **OpenEvidence + JAMA/NEJM** for full-text clinical literature.
- **Rogo / Hebbia / Finster / Perplexity** for FactSet, S&P Capital IQ, PitchBook, LSEG, Crunchbase, or similar financial datasets.
- **Scite** for licensed scholarly publisher content and Smart Citations.
- **Avo + DynaMed** for EHR-integrated clinical decision support.

These are high-confidence needs. The skeptical issue is that the strongest examples are already solved through direct partnerships.

### Pattern B - BYO subscription / entitlement routing

Several products expose a likely exchange wedge only if the exchange can preserve customer entitlements:

- Perplexity Enterprise Pro users need separate FactSet/Crunchbase subscriptions.
- Consensus and Scite use institutional holdings/LibKey/GetFTR-style access resolution.
- Elicit can use a researcher's institutional access or uploaded PDFs.
- Enterprise agents such as OpenAI, Claude, Glean, Cursor, and Mistral rely on customer-approved connectors.

The exchange would need to act less like "we sell data" and more like "we route, meter, and audit allowed machine use under existing rights."

### Pattern C - Vertical apps with high-cost structured data gaps

The most plausible outbound set:

- **Construction/compliance:** UpCodes, Procore, Autodesk. High citation need, jurisdiction-specific data, and clear workflow pain.
- **Logistics/supply chain:** Samsara, Flexport, project44, FourKites. High real-time structured-data need, but incumbents have proprietary data graphs.
- **Clinical workflow:** Abridge, Ambience, Avo, Glass, Suki, Nabla, Hippocratic. Strong need for licensed medical knowledge, payer policies, drug data, guidelines, and EHR context, but regulatory burden is high.
- **Finance/private markets:** Rogo, Hebbia, AlphaSense, Finster, AllMind, Daloopa, PitchBook, Bloomberg. Highest WTP but heavy direct-incumbent competition.

---

## 3. Best first outreach candidates

If this were a real BD pipeline, I would not start with OpenAI, Bloomberg, Thomson Reuters, or Microsoft-scale platforms. They are relevant but structurally likely to internalize. The better initial targets are:

1. **Finster AI** - public evidence of premium data integrations; likely still building breadth.
2. **AllMind AI** - finance agent with explicit "licensed sources" language but likely smaller than Bloomberg/AlphaSense.
3. **Avo** - public evidence of DynaMed partnership; clinical guideline routing is a clear wedge.
4. **Glass Health** - clinical decision support that needs current guidelines/drug references.
5. **UpCodes** - code citations and jurisdiction-specific compliance are a natural narrow pilot.
6. **Clay** - already behaves like a demand-side data marketplace/orchestrator and may value rights-aware specialty providers.
7. **Factory AI / Devin / Cursor-like coding agents** - less about proprietary data ownership, more about licensed docs/API references and real-time package data.
8. **Perk/TravelPerk or travel-agent startups** - travel inventory, policy, fare, and disruption data are fragmented, but supplier politics are hard.

---

## 4. Reasons many targets will say no

- **They already own the data.** Bloomberg, Thomson Reuters, PitchBook, AlphaSense/Tegus, project44, FourKites, Samsara, and UpCodes have proprietary data moats.
- **They already distribute via MCP/API.** Daloopa, FiscalNote, PitchBook, Scite, Glean, OpenAI, Claude, Mistral, Cursor, Devin, and others have their own connector strategies.
- **Customer entitlements are messy.** FactSet/Bloomberg/Westlaw/DynaMed licenses are seat-based, field-restricted, and often forbid redistribution or automated output.
- **Regulated verticals require more than data.** Healthcare/legal/finance buyers need audit, privilege, PHI controls, citation verification, policy enforcement, and indemnity.
- **Scraping substitutes cap price.** Some buyers will continue to use browser agents, customer logins, or scraping providers unless the legal/compliance risk becomes intolerable.

---

## 5. CSV fields

`agent-targets.csv` uses the requested columns:

`company,product,workflow,proprietary_data_gap,likely_rights_holder,supporting_evidence_url,estimated_commercial_value,outreach_angle,confidence_level,notes`

All commercial-value entries are labeled **Inference**. No customer willingness-to-pay, price, or procurement status is asserted unless supported in public sources.

---

## Sources

Accessed or searched on 2026-07-15 unless a publication date is listed.

- Harvey / LexisNexis: `https://www.lexisnexis.com/community/pressroom/b/news/posts/lexisnexis-and-harvey-announce-strategic-alliance-to-integrate-trusted-high-quality-ai-technology-and-legal-content-and-develop-advanced-workflows`; `https://help.harvey.ai/articles/ask-lexisnexis`
- EvenUp: `https://evenuplaw.com/`; `https://www.evenuplaw.com/piai/`; `https://www.evenuplaw.com/products/demands/`
- Spellbook: `https://spellbook.com/`; `https://spellbook.com/features/review`; `https://spellbook.com/playbooks`
- Thomson Reuters CoCounsel: `https://legal.thomsonreuters.com/en/products/cocounsel-legal`; `https://ir.thomsonreuters.com/news-releases/news-release-details/one-million-professionals-turn-cocounsel-thomson-reuters-scales`
- Luminance: `https://www.luminance.com/`; `https://www.luminance.com/negotiate/`
- Robin AI: `https://robinai.com/news-and-resources/blog/robin-expands-playbooks-smarter-contract-negotiations`; `https://www.prnewswire.com/news-releases/robin-ai-raises-26-million-as-legal-sector-embraces-ai-302024900.html`
- UpCodes: `https://support.up.codes/support/solutions/articles/63000277619-intro-to-copilot`; `https://www.prnewswire.com/news-releases/upcodes-adds-ai-native-plan-review-to-its-aec-qaqc-platform-302789640.html`
- FiscalNote / PolicyNote: `https://fiscalnote.com/products/policynote`; `https://fiscalnote.com/products/policynote-api`; `https://www.businesswire.com/news/home/20260302813063/en/FiscalNote-Announces-Enhancements-to-PolicyNote-API-Expanding-Access-to-Authoritative-Policy-Intelligence-for-AI-Agents-and-Enterprises`
- Rogo: `https://rogo.ai/`; `https://rogo.ai/news/rogo-integrates-s-p-capital-iq-data-into-its-ai-powered-workflows`; `https://rogo.ai/news/announcing-our-strategic-partnership-with-lseg`
- Hebbia: `https://www.hebbia.com/blog/inside-hebbias-deeper-research-agent`; `https://pitchbook.com/blog/pitchbook-and-hebbia-skills-deliver-institutional-grade-outputs-in-seconds`
- AlphaSense / Tegus: `https://www.alpha-sense.com/resources/product-articles/what-is-alphasense/`; `https://www.alpha-sense.com/press/alphasense-ai-search-and-market-intelligence-platform-now-available-in-new-aws-ai-marketplace-agents-and-tools-category/`; `https://www.prnewswire.com/news-releases/alphasense-completes-acquisition-of-tegus-302190934.html`
- Daloopa: `https://docs.daloopa.com/docs/daloopa-mcp`; `https://daloopa.com/products/mcp`
- Fintool: `https://docs.fintool.com/introduction`
- Finster: `https://www.finster.ai/resources/news/finster-ai-announces-strategic-partnership-with-factset`; `https://www.finster.ai/solutions/investment-banking`; `https://finster.ai/resources/news/finster-faqs`
- PitchBook: `https://pitchbook.com/products/navigator`; `https://pitchbook.com/products/premium-connectors`; `https://pitchbook.com/media/press-releases/pitchbook-launches-new-generative-ai-experiences-with-the-introduction-of-pitchbook-navigator-and-upcoming-integration-with-openai`
- Bloomberg ASKB: `https://www.bloomberg.com/company/stories/meet-askb-bloomberg-introduces-agentic-ai-to-the-bloomberg-terminal/`; `https://professional.bloomberg.com/products/bloomberg-terminal/ai/`
- Perplexity: `https://www.perplexity.ai/hub/blog/introducing-finance-search-in-the-agent-api`; `https://docs.perplexity.ai/docs/agent-api/finance-search`; `https://www.perplexity.ai/hub/blog/meet-our-first-channel-partners-data-integrators`
- AllMind: `https://allmind.ai/`
- OpenEvidence / JAMA: `https://www.openevidence.com/announcements/openevidence-and-the-jama-network-sign-strategic-content-agreement`
- Abridge: `https://www.abridge.com/product`; `https://www.abridge.com/abridge-contextual-reasoning-engine`; `https://hitconsultant.net/2026/06/12/abridge-launches-clinician-intelligence-platform-nvidia/`
- Nabla: `https://nabla.com/`; `https://nabla.com/ehr`
- Ambience: `https://www.ambiencehealthcare.com/`; `https://www.businesswire.com/news/home/20260212784262/en/Ambience-Healthcare-Expands-Chart-Awareness-Across-Its-Intelligence-Platform`
- Suki: `https://suki.ai/`; `https://www.suki.ai/ehr-integrations/`; `https://developer.suki.ai/api-reference/overview`
- Hippocratic AI: `https://hippocraticai.com/polaris/`; `https://hippocraticai.com/constellation/`; `https://hippocraticai.com/safety/`
- PathAI: `https://www.pathai.com/`; `https://www.pathai.com/aisightdx-digital-pathology-solution`; `https://www.pathai.com/blog/pathais-aisight-ims-platform-an-open-digital-pathology-platform-enabling-flexible-choice-across-ai-applications`
- Glass Health: `https://glass.health/ambient-cds`; `https://glass.health/features`
- Avo: `https://www.avomd.com/ehr-integrations`; `https://www.avomd.com/resources/avo-embeds-dynamed-r-into-the-ehr-with-the-first-context-aware-ai-consult-tool-in-partnership-with-ebsco-clinical-decisions`
- Elicit: `https://elicit.com/`; `https://elicit.com/solutions/library`; `https://elicit.com/solutions/systematic-review`
- Consensus: `https://consensus.app/search/`; `https://consensus.app/home/blog/getting-started-with-consensus-university-access/`
- Scite: `https://scite.ai/`; `https://scite.ai/blog/introducing-scite-mcp`
- Glean: `https://www.glean.com/platform/connectors`; `https://docs.glean.com/connectors/about.md`
- Sierra: `https://sierra.ai/`; `https://sierra.ai/blog/agent-data-platform`
- Intercom Fin: `https://www.intercom.com/help/en/articles/9916507-data-connectors-faqs`; `https://fin.ai/updates/data-connectors`
- Clay: `https://university.clay.com/docs/clay-api-cli`; `https://www.clay.com/use-cases/crm-enrichment`
- Devin: `https://cognitionai-enterprise.mintlify.app/integrations/overview`; `https://docs.devin.ai/essential-guidelines/sdlc-integration`
- Cursor: `https://cursor.com/docs/mcp`
- Sourcegraph Cody: `https://sourcegraph.com/docs/cody`; `https://sourcegraph.com/docs/cody/capabilities/agentic-context-fetching`
- Factory: `https://factory.ai/news/factory-is-ga`; `https://factory.ai/enterprise`
- Samsara: `https://www.samsara.com/company/news/press-releases/samsara-launches-new-agentic-capabilities-to-automate-tedious-operational-tasks`; `https://www.samsara.com/blog/announcing-new-innovations-to-reduce-risk-increase-efficiency-and-digitally-transform-operations`
- Flexport: `https://www.flexport.com/technology/product-release/winter-2026/`; `https://www.businesswire.com/news/home/20260226536552/en/Flexport-Launches-Technology-to-Automate-Tariff-Refunds`
- project44: `https://www.project44.com/`; `https://www.project44.com/ai-agent-orchestration/mo/`; `https://www.project44.com/ai-agent-orchestration/`
- FourKites: `https://www.fourkites.com/press/fourkites-announces-breakthrough-generative-ai-solution-to-help-companies-respond-to-supply-chain-disruptions/`; `https://www.fourkites.com/fourkites-ai/conversational-ai/`; `https://www.fourkites.com/blogs/fourkites-loft-ai-orchestration/`
- Procore: `https://support.procore.com/products/online/user-guide/project-level/assist`; `https://en-ca.support.procore.com/products/online/user-guide/project-level/assist/faq/what-data-can-assist-access`; `https://v2.support.procore.com/faq-what-are-the-differences-between-procore-ai-assist-agent-builder-and-datagrid`
- Autodesk: `https://www.autodesk.com/blogs/aec/2026/04/22/autodesk-assistant-in-revit-tech-preview/`; `https://www.autodesk.com/blogs/construction/meet-autodesk-assistant-ai-native-intelligence-in-forma/`
- Perk / TravelPerk: `https://thebusinesstravelmag.com/perk-unveils-mcp-connector/`; `https://travelperk.com/en-us/travel-solutions/policies-approvals`; `https://www.perk.com/uk/blog/perk-control-center/`
- Expedia: `https://www.expedia.com/newsroom/spring-product-release-2024/`; `https://www.expedia.com/newsroom/expedia-group-unveils-new-ai-experiences-expands-travel-ecosystem-and-launches-philanthropy-program-at-explore-2026/`; `https://skift.com/2026/05/19/expedia-ceo-ariane-gorin-on-what-companies-get-wrong-about-ai-chatbots/`
- You.com / Cloudflare Pay Per Use: `https://blog.cloudflare.com/making-ai-search-smarter/`; `https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/`
- OpenAI / Claude / Mistral connector ecosystems: `https://developers.openai.com/api/docs/guides/tools-connectors-mcp`; `https://support.claude.com/en/articles/12489464-use-enterprise-search`; `https://mistral.ai/products/le-chat/`; `https://docs.mistral.ai/vibe/work/connectors/mcp-connectors`
