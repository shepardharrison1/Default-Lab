# Competitive Landscape: Agent Data Exchange

**Research date:** 2026-07-15  
**Posture:** skeptical, evidence-driven competitive research for an AI-agent proprietary-data licensing / marketplace concept.

## 0. Evidence rules and scope

This document evaluates a proposed independent "agent data exchange": a marketplace and routing layer that would help agent applications discover and license proprietary data through API, MCP, feed, or proxy delivery, with authentication, pricing, metering, attribution, settlement, payout, controls, and possibly sponsored discovery.

Evidence handling:

- **Verified** means supported by a primary company / standards / regulatory source, or reputable secondary reporting where primary sources do not disclose the fact.
- **Not disclosed** means no reliable public source found in this research pass.
- **Inference** means a reasoned competitive interpretation, not a verified company claim.
- Marketing copy is treated as a claim, not proof of transaction volume, revenue, or product-market fit.
- No funding, revenue, customer, or pricing claims are included without a source. Where a source is a company press release or site, it is identified as company-claimed.

The detailed normalized matrix is in `competitor-matrix.csv`. This markdown emphasizes market structure, direct overlap, and strategic implications.

## 1. Bottom line

The proposed company is not entering a blank market. By July 2026, every layer of the concept has at least one active substitute:

- **Publisher / open-web monetization:** TollBit, Cloudflare Pay Per Crawl / Pay Per Use, Dappier, ScalePost, Microsoft Publisher Content Marketplace, and ProRata / Gist.
- **Vertical rights aggregation:** Created by Humans for books; Bria for licensed visual training data; Story / DATA Foundation for on-chain AI-data provenance.
- **Data owners going direct:** Reuters MCP, Stack Overflow Data Licensing / OverflowAPI, Reddit data licensing, and major bilateral publisher deals with OpenAI, Amazon, Meta, Microsoft, Google, and others.
- **Enterprise marketplaces:** AWS Data Exchange / AWS Marketplace, Snowflake Marketplace / Cortex Knowledge Extensions, Databricks Marketplace / MCP Marketplace.
- **Developer/API distribution:** RapidAPI's collapse into Nokia is a cautionary API-marketplace precedent; Postman API Network and MCP generator are discovery/integration substitutes.
- **Payment and agent-commerce rails:** Stripe ACP / MPP, x402, AP2, UCP, Web Monetization, and MCP registries can commoditize discovery, protocol, checkout, or payment layers.

**Skeptical conclusion:** the strongest remaining wedge for an independent company is **not** generic open-web crawl monetization. That lane is crowded and structurally advantaged to Cloudflare, Microsoft, CDNs, and AI-answer surfaces. The defensible wedge is narrower: **vertical, high-value, proprietary structured data** that agents need at inference time, where (a) data owners are too specialized to build distribution, (b) buyers need quality / provenance / SLAs / indemnity, and (c) use cases can support more than symbolic micropayments.

## 2. What already exists vs. what the proposed company might claim as novel

### Already exists

1. **Two-sided publisher access marketplace.** TollBit says AI agents and applications can pay websites directly, and its Series A announcement said transactions were live and over 200 publisher sites were onboarded as of 2024-10-22 ([TollBit, 2024-10-22](https://tollbit.com/blog/series-a/); [PRNewswire, 2024-10-22](https://www.prnewswire.com/news-releases/tollbit-a-two-sided-marketplace-for-ai-companies-and-publishers-closes-at-24-million-in-series-a-funding-302283475.html)).
2. **Edge-level crawler monetization and settlement.** Cloudflare Pay Per Crawl uses HTTP 402 responses, crawler payment headers, Cloudflare billing, and publisher payouts in closed/private beta ([Cloudflare blog, 2025-07-01](https://blog.cloudflare.com/introducing-pay-per-crawl/); [Cloudflare docs, modified 2026-04-23](https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/)).
3. **Pay-per-use direction.** Cloudflare announced on 2026-07-01 that it is evolving Pay Per Crawl into Pay Per Use with Ceramic.ai and You.com experiments, shifting from fetches to query/result/use events ([Cloudflare blog, 2026-07-01](https://blog.cloudflare.com/making-ai-search-smarter/); [Cloudflare press release, 2026-07-01](https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/)).
4. **AI-content licensing marketplace by a hyperscaler.** Microsoft Publisher Content Marketplace lets publishers set usage terms and AI builders license content; initial partners include AP, Business Insider, Conde Nast, Hearst, USA TODAY, Vox Media, and Yahoo as a demand partner according to launch reporting ([Search Engine Land, 2026-02-03](https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191); [The Verge, 2026-02-03](https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing)).
5. **Per-query / RAG marketplace and MCP delivery.** Dappier publicly describes an MCP server for rights-cleared, real-time data and says publishers can set their own per-query prices; TechCrunch reported its $2M seed led by Silverton Partners and per-query/ad-supported marketplace model ([Dappier MCP page, accessed 2026-07-15](https://dappier.com/dappier-mcp-improving-ai-with-real-time-data); [TechCrunch, 2024-06-26](https://techcrunch.com/2024/06/26/dappier-is-building-a-marketplace-for-publishers-to-sell-their-content-to-llm-builders/)).
6. **Attribution and revenue-sharing answer products.** ProRata says it shares 50% of revenue with content partners and has 1,000+ publications / creators; BusinessWire reported a $40M Series B and more than $75M raised ([ProRata site, accessed 2026-07-15](https://prorata.ai/); [BusinessWire, 2025-09-05](https://www.businesswire.com/news/home/20250905771340/en/ProRata-Closes-%2440-Million-Series-B-Financing-and-Launches-Gist-Answers-Creating-New-Revenue-Opportunities-for-Publishers-in-the-AI-Era)).
7. **Enterprise licensed data for agent grounding.** Snowflake Cortex Knowledge Extensions are shared Cortex Search Services on Snowflake Marketplace for licensed / proprietary RAG content ([Snowflake docs, accessed 2026-07-15](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-knowledge-extensions/cke-overview)); Databricks Marketplace supports external MCP servers governed by Unity Catalog ([Databricks docs, accessed 2026-07-15](https://docs.databricks.com/aws/en/marketplace/)).
8. **Payment protocols for machine access.** x402 standardizes HTTP 402 internet-native payments under Linux Foundation governance ([Linux Foundation, 2026-07-14](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications?hs_amp=true)); Stripe MPP and machine-payments docs support HTTP 402-style agent payments across MPP and x402 ([Stripe blog, 2026-03-18](https://stripe.com/blog/machine-payments-protocol); [Stripe docs, accessed 2026-07-15](https://docs.stripe.com/payments/machine)).

### Potentially novel, but unproven

The proposed company might still differentiate by combining elements that are mostly separate today:

- **Demand-side gap detection:** observing what agents fail to answer and turning those failures into supply acquisition signals. No primary source found showing TollBit, Cloudflare, Microsoft PCM, AWS, Snowflake, or Databricks doing this as a core marketplace product. **Inference:** this could be novel if implemented with real buyer workflow data, not generic search logs.
- **Cross-source quality ranking for proprietary data:** ranking by freshness, coverage, permissions, latency, provenance, citation quality, and economic terms. Existing marketplaces expose discovery and filters, but public evidence of neutral, multi-factor agent-source ranking is limited. **Inference:** useful, but easy for cloud marketplaces or agent platforms to replicate if it becomes important.
- **Sponsored discovery for agent data sources:** possible but risky. It overlaps advertising, creates trust issues for agents, and will require clear labeling and buyer controls. No source found proving market acceptance for sponsored data-source placement.
- **Vertical structured data brokerage:** this is the best wedge. Open-web news and crawling are crowded; domain-specific proprietary datasets with APIs, SLAs, schema quality, indemnity, and narrow per-use permissions are less solved.

## 3. Direct and near-direct competitors

### 3.1 TollBit

- **Product description:** Two-sided marketplace and bot paywall where AI agents / applications pay websites directly for content or data; publishers monitor bot traffic and set rates / rules for autonomous access ([TollBit, 2024-10-22](https://tollbit.com/blog/series-a/); [Lightspeed, 2024](https://lsvp.com/stories/investing-in-tollbit-the-internets-ai-toll-booth/)).
- **Founded:** 2023 per Lightspeed company profile ([Lightspeed profile, accessed 2026-07-15](https://lsvp.com/company/tollbit/)).
- **Funding / investors:** Verified $24M Series A led by Lightspeed; Axios reported prior $7M seed and $31M total funding ([PRNewswire, 2024-10-22](https://www.prnewswire.com/news-releases/tollbit-a-two-sided-marketplace-for-ai-companies-and-publishers-closes-at-24-million-in-series-a-funding-302283475.html); [Axios, 2024-10-22](https://www.axios.com/2024/10/22/ai-startup-tollbit-media-publishers)).
- **Customers / partners:** TollBit named Penske Media, TIME, Mumsnet, Trusted Media Brands, CANDR, and ADWEEK in its Series A release; Fastly and Akamai announced integrations/alliances with TollBit ([TollBit, 2024-10-22](https://tollbit.com/blog/series-a/); [Fastly, 2025](https://www.fastly.com/blog/how-to-control-and-monetize-ai-bot-traffic-using-fastly-and-tollbit); [Akamai, 2025](https://www.akamai.com/newsroom/press-release/no-free-crawls-akamai-tollbit-and-skyfire-turn-traffic-into-revenue)).
- **Pricing / revenue model:** Publisher-set rates and rules are verified; TollBit transaction fee/take rate is not disclosed in primary sources. Lightspeed says publishers can set rates for autonomous access to any URL ([Lightspeed, 2024](https://lsvp.com/stories/investing-in-tollbit-the-internets-ai-toll-booth/)).
- **Technical delivery:** Edge redirects to a TollBit bot paywall are described in Fastly's integration write-up; Akamai describes edge detection and redirect to TollBit paywall ([Fastly, 2025](https://www.fastly.com/blog/how-to-control-and-monetize-ai-bot-traffic-using-fastly-and-tollbit); [Akamai, 2025](https://www.akamai.com/blog/security/from-scraping-paying-monetizing-ai-bots-edge)).
- **Licensing model:** Per-access / sanctioned machine access; exact legal template not public.
- **Target customer:** Publishers, ecommerce/content-rich sites, AI companies, agents.
- **Publisher controls:** Set access terms / rates, block or monetize bots, analytics. **Buyer controls:** token/payment access; detailed buyer budget controls not public.
- **Strengths:** Closest independent comparable; has CDN partnerships and live marketplace claims.
- **Weaknesses:** Demand-side willingness to pay remains the core uncertainty. **Inference:** a crawler can refuse to pay unless the publisher or CDN can enforce scarcity.
- **Overlap:** High.
- **Likely future direction:** **Inference:** expands from bot paywall to broader agentic-web monetization, authentication, and content delivery.
- **Classification:** Competitor; possible partner if the proposed company focuses on demand intelligence / vertical data rather than open-web enforcement.

### 3.2 Cloudflare Pay Per Crawl / Pay Per Use and Human Native

- **Product description:** Cloudflare Pay Per Crawl lets site owners charge AI crawlers using HTTP 402 and payment intent headers, with Cloudflare acting as merchant of record ([Cloudflare blog, 2025-07-01](https://blog.cloudflare.com/introducing-pay-per-crawl/); [Cloudflare docs, modified 2026-04-23](https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/)). Cloudflare's 2026-07-01 announcement says it is evolving this into Pay Per Use with Ceramic.ai and You.com experiments ([Cloudflare press release, 2026-07-01](https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/)).
- **Human Native:** Cloudflare announced it acquired Human Native, a UK AI data marketplace connecting creators/publishers and AI developers, on 2026-01-15; financial terms were not disclosed ([Cloudflare press release, 2026-01-15](https://www.cloudflare.com/press/press-releases/2026/cloudflare-strengthens-content-offering-to-ai-companies-with-acquisition-of-human-native/); [Cloudflare blog, 2026-01-15](https://blog.cloudflare.com/human-native-joins-cloudflare/)). Human Native announced a GBP2.8M seed led by LocalGlobe and Mercuri on 2024-06-03 ([Human Native blog, 2024-06-03](https://www.humannative.ai/blog/seed-funding-announcement)).
- **Founded:** Cloudflare was founded before this market; Pay Per Crawl launched in 2025. Human Native founded 2024 per Cloudflare release ([Cloudflare, 2026-01-15](https://www.cloudflare.com/press/press-releases/2026/cloudflare-strengthens-content-offering-to-ai-companies-with-acquisition-of-human-native/)).
- **Funding / investors:** Cloudflare is public; Human Native GBP2.8M seed led by LocalGlobe and Mercuri; acquisition terms not disclosed ([Human Native, 2024-06-03](https://www.humannative.ai/blog/seed-funding-announcement); [CNBC, 2026-01-15](https://www.cnbc.com/2026/01/15/cloudflare-ai-human-native-acquisition.html)).
- **Customers / partners:** Ceramic.ai and You.com named as Pay Per Use partners; Human Native supplies team/technology ([Cloudflare, 2026-07-01](https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/)).
- **Pricing / revenue model:** Cloudflare merchant-of-record model verified for Pay Per Crawl; take rate and Pay Per Use rates not disclosed ([Cloudflare docs, 2026-04-23](https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/)).
- **Technical delivery:** Cloudflare edge, HTTP 402, crawler headers, AI Crawl Control, content transformation / marketplace assets from Human Native.
- **Licensing model:** Per-crawl moving toward per-query/per-result/per-use. Legal templates not public.
- **Controls:** Publishers can allow, charge, or block crawlers at zone-level in Pay Per Crawl docs; buyer controls are payment intent headers / crawler configuration ([Cloudflare docs, 2026-04-23](https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/)).
- **Strengths:** Edge distribution and default control. Cloudflare can make pay/block choices operational for millions of sites more easily than a startup.
- **Weaknesses:** Not neutral: Cloudflare is infrastructure vendor and marketplace operator. Pay Per Use is explicitly experimental; terms/rates are not public.
- **Overlap:** High.
- **Likely future direction:** **Inference:** Cloudflare becomes a default settlement and enforcement layer for web content access, compressing independent margins at the generic web layer.
- **Classification:** Competitor, infrastructure provider, and plausible acquirer.

### 3.3 Dappier

- **Product description:** Marketplace / MCP server for rights-cleared real-time data; publishers can onboard via RSS, files, or mirrors and set per-query pricing; developers get usage-based access ([Dappier MCP page, accessed 2026-07-15](https://dappier.com/dappier-mcp-improving-ai-with-real-time-data)).
- **Founded:** Not clearly verified in primary source; TechCrunch described Dappier as an early-stage Austin startup in 2024.
- **Funding / investors:** $2M seed led by Silverton Partners reported by TechCrunch and SiliconANGLE ([TechCrunch, 2024-06-26](https://techcrunch.com/2024/06/26/dappier-is-building-a-marketplace-for-publishers-to-sell-their-content-to-llm-builders/); [SiliconANGLE, 2024-06-26](https://siliconangle.com/2024/06/26/dappier-raises-2m-seed-funding-ai-data-marketplace/)).
- **Customers / partners:** Dappier's current public site names product categories and integrations; specific paying customers are not verified in primary public sources reviewed.
- **Pricing / revenue model:** Publisher-set per-query pricing and free-to-start / credits language appear on Dappier's MCP page; Medium post says real-time data access became free with native ads coming soon, which suggests a mixed licensing/ad model ([Dappier MCP page, accessed 2026-07-15](https://dappier.com/dappier-mcp-improving-ai-with-real-time-data); [Dappier Medium, 2026](https://dappier.medium.com/making-real-time-data-free-with-rag-mcp-supporting-6-major-ai-integrations-16fe03d84d17)).
- **Technical delivery:** RAG models, APIs, MCP server.
- **Licensing model:** Per-query licenses / ad-supported data access; exact legal terms not public.
- **Controls:** Publishers set prices; buyers pay for use / integrate MCP. Detailed spend controls not public.
- **Strengths:** Closest technical architecture to a per-query agent data exchange.
- **Weaknesses:** Small funding base; public messaging has shifted toward free real-time data and ads. **Inference:** pure paid data demand may be difficult at seed scale.
- **Overlap:** High.
- **Classification:** Competitor.

### 3.4 Microsoft Publisher Content Marketplace

- **Product description:** Publisher Content Marketplace lets publishers set terms, track usage, and get paid when AI systems use premium licensed content for grounding; initial reports say Microsoft co-designed it with major publishers and Yahoo is among early demand partners ([Search Engine Land, 2026-02-03](https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191); [The Verge, 2026-02-03](https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing)).
- **Founded / launch year:** Marketplace launched / announced in February 2026.
- **Funding / investors:** Microsoft is public; product-level funding not applicable.
- **Customers / partners:** AP, Business Insider, Conde Nast, Hearst, People, USA TODAY, Vox Media, and Yahoo are named in launch reporting ([Search Engine Land, 2026-02-03](https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191)).
- **Pricing / revenue model:** "Paid based on delivered value" and publisher-set terms are reported; Microsoft take rate not disclosed.
- **Technical delivery:** Marketplace for AI builders and publisher content, grounding use cases; detailed APIs not public in sources found.
- **Licensing model:** Usage-based, publisher-set terms; specific contract templates not public.
- **Controls:** Publishers set licensing and usage terms; AI builders discover/license content. Buyer spend controls not public.
- **Strengths:** Distribution through Copilot and Microsoft Advertising; enterprise trust; existing publisher relationships.
- **Weaknesses:** Microsoft is both marketplace operator and AI/content buyer. This creates a neutrality concern for publishers and competitors. **Inference:** trust may be lower than for a neutral broker, but distribution may matter more.
- **Overlap:** High.
- **Classification:** Competitor and possible acquirer.

### 3.5 ProRata AI / Gist

- **Product description:** ProRata builds AI search, advertising, and attribution products. Gist Answers lets publishers embed AI search/summarization/recommendation; Gist Ads monetizes responses ([BusinessWire, 2025-09-05](https://www.businesswire.com/news/home/20250905771340/en/ProRata-Closes-%2440-Million-Series-B-Financing-and-Launches-Gist-Answers-Creating-New-Revenue-Opportunities-for-Publishers-in-the-AI-Era)).
- **Founded:** 2024 implied by "founding last year" in 2025 BusinessWire release; founder Bill Gross is public in reporting, but not needed for classification.
- **Funding / investors:** $40M Series B led by Touring Capital; more than $75M total raised; investors include Mayfield Fund, MVP Ventures, Revolution Ventures, SBI Investment, BOLD Capital, XPV-Exponential Ventures, and Idealab Studio ([BusinessWire, 2025-09-05](https://www.businesswire.com/news/home/20250905771340/en/ProRata-Closes-%2440-Million-Series-B-Financing-and-Launches-Gist-Answers-Creating-New-Revenue-Opportunities-for-Publishers-in-the-AI-Era)).
- **Customers / partners:** BusinessWire says more than 700 high-quality publications participating; ProRata site claims 1,000+ publications / creators ([BusinessWire, 2025-09-05](https://www.businesswire.com/news/home/20250905771340/en/ProRata-Closes-%2440-Million-Series-B-Financing-and-Launches-Gist-Answers-Creating-New-Revenue-Opportunities-for-Publishers-in-the-AI-Era); [ProRata site, accessed 2026-07-15](https://prorata.ai/)).
- **Pricing / revenue model:** ProRata site says it shares 50% of revenues with content partners ([ProRata site, accessed 2026-07-15](https://prorata.ai/)).
- **Technical delivery:** Embeddable answer engine, ads, attribution.
- **Licensing model:** Licensed content network; attribution-weighted payouts.
- **Controls:** Publisher integration and content licensing; buyer controls are less relevant because model is publisher-site / ad network rather than open exchange.
- **Strengths:** Directly addresses publisher monetization without requiring every external agent to pay.
- **Weaknesses:** It is closer to AI ad/search product than neutral data exchange. **Inference:** less useful for third-party agents needing arbitrary proprietary data.
- **Overlap:** Medium.
- **Classification:** Partial competitor and potential partner for attribution.

### 3.6 ScalePost

- **Product description:** Data licensing platform connecting AI companies with premium licensing opportunities across text, image, audio, and video; official site includes a Perplexity case study ([ScalePost, accessed 2026-07-15](https://www.scalepost.ai/for-ai-llms)).
- **Founded / funding / investors:** Not verified in primary public sources reviewed; funding not disclosed.
- **Customers / partners:** ScalePost site names Perplexity as a case study; Perplexity's publisher-program blog says it works with ScalePost for collaborations and analytics ([ScalePost, accessed 2026-07-15](https://www.scalepost.ai/for-ai-llms); [Perplexity, 2024-07-30](https://www.perplexity.ai/hub/blog/introducing-the-perplexity-publishers-program)).
- **Pricing / revenue model:** Not disclosed.
- **Technical delivery:** Marketplace / licensing facilitation and analytics; implementation details not public.
- **Licensing model:** Training/retrieval licensing opportunities; terms not public.
- **Controls:** Publisher analytics and partnership facilitation; buyer controls not public.
- **Strengths:** Positioned as one-pipe licensing facilitator for AI companies.
- **Weaknesses:** Public evidence of scale, funding, pricing, or transaction volume is thin.
- **Overlap:** Medium-high.
- **Classification:** Competitor.

## 4. Vertical and adjacent rights platforms

### 4.1 Created by Humans

- **Product description:** AI Rights licensing platform for books; authors/rights holders opt in or out of licensing options, and AI developers can license training, reference, and transformative rights ([Created by Humans site, accessed 2026-07-15](https://www.createdbyhumans.ai/)).
- **Founded:** Launched publicly in January 2025 after 2024 Authors Guild partnership; company founding year not separately verified here.
- **Funding / investors:** Authors Guild release says $5M funding led by Craft Ventures and Floodgate in June 2024; PRWeb launch says additional $5M seed from Giant Ventures and angels, following the $5M pre-seed from Craft Ventures, Floodgate, Slow Ventures, Garry Tan, and others ([Authors Guild, 2024-10-09](https://authorsguild.org/news/ag-partners-with-created-by-humans-to-empower-authors-in-ai-era/); [PRWeb, 2025-01-14](https://www.prweb.com/releases/created-by-humans-ai-licensing-platform-for-books-launches-with-the-support-of-bestselling-authors-302350249.html)).
- **Customers / partners:** Authors Guild partnership and over 50 bestselling authors claimed in launch release ([Authors Guild, 2024-10-09](https://authorsguild.org/news/ag-partners-with-created-by-humans-to-empower-authors-in-ai-era/); [PRWeb, 2025-01-14](https://www.prweb.com/releases/created-by-humans-ai-licensing-platform-for-books-launches-with-the-support-of-bestselling-authors-302350249.html)).
- **Pricing / revenue model:** Site says CbH negotiates agreements and authors track payments; exact buyer pricing not public ([Created by Humans site, accessed 2026-07-15](https://www.createdbyhumans.ai/)).
- **Technical delivery:** Curated rights-cleared datasets / agreements.
- **Licensing model:** Training, reference, transformative rights for books.
- **Controls:** Authors opt in/out and approve licensing options; AI developers receive rights-cleared content.
- **Strengths:** Strong vertical legitimacy via Authors Guild.
- **Weaknesses:** Narrow vertical; demand depends on AI buyers valuing book rights enough to license rather than litigate or avoid.
- **Overlap:** Medium.
- **Classification:** Vertical competitor and potential supply partner.

### 4.2 Bria

- **Product description:** Enterprise visual generative AI platform trained on 100% licensed data; patented attribution engine compensates data owners based on influence on outputs ([Bria blog, 2025-03-13](https://blog.bria.ai/bria-awarded-40m-in-series-b); [PRNewswire, 2025-03-13](https://www.prnewswire.com/news-releases/bria-secures-40m-in-series-b-to-drive-fair-gen-ai-usage-for-enterprises-302400907.html)).
- **Founded:** Not verified in sources reviewed; do not rely on unaudited profile databases.
- **Funding / investors:** $40M Series B led by Red Dot Capital, bringing total capital raised to $65M; participating investors include Maor Investment, Entree Capital, GFT Ventures, Intel Capital, and In-Venture ([Bria, 2025-03-13](https://blog.bria.ai/bria-awarded-40m-in-series-b)).
- **Customers / partners:** Bria claims 30+ data partners including Getty Images, Envato, Alamy, Freepik, Depositphotos, and more ([Bria, 2025-03-13](https://blog.bria.ai/bria-awarded-40m-in-series-b)).
- **Pricing / revenue model:** Platform/API fees and compensation to data owners; exact pricing not public.
- **Technical delivery:** Visual GenAI models, APIs, attribution engine.
- **Licensing model:** Licensed training data with attribution-based compensation.
- **Controls:** Data partners license into Bria's model; buyer controls are enterprise GenAI platform controls, not marketplace controls.
- **Strengths:** Clear legal-safety positioning and attribution IP.
- **Weaknesses:** Training-time visual media, not inference-time agent retrieval.
- **Overlap:** Low-medium.
- **Classification:** Adjacent competitor / partner.

### 4.3 Story Protocol / DATA Foundation

- **Product description:** Story Protocol rebranded as DATA Foundation in June 2026, pivoting toward AI training-data infrastructure, including on-chain provenance / licensing / consent receipts via DATA Network and Trace ([CoinDesk, 2026-06-25](https://www.coindesk.com/business/2026/06/25/a16z-backed-crypto-firm-rebrands-shifts-focus-to-solving-ai-s-global-copyright-headache); [IP Strategy press release, 2026-06-26](https://ir.ipstrategy.co/news-events/press-releases/detail/177/ip-strategy-highlights-story-foundations-transition-to-the)).
- **Founded / funding / investors:** CoinDesk reports Story raised $140M led by a16z crypto; primary company/foundation source found for exact historical funding was limited in this pass, so use the CoinDesk figure as reputable secondary reporting.
- **Customers / partners:** Kled and Poseidon are cited as part of the DATA ecosystem; Kled record-count claims vary by secondary source, so treat scale claims as company/press claims, not independently verified.
- **Pricing / revenue model:** Token/protocol economics; exact enterprise pricing not public.
- **Technical delivery:** Blockchain registry, cryptographic receipts, data provenance/audit layer.
- **Licensing model:** On-chain consent/licensing/provenance for training data.
- **Controls:** Rights holders/contributors can register provenance/consent; buyers get audit trail. Detailed enterprise buyer controls not public.
- **Strengths:** Provenance narrative is timely; large reported funding.
- **Weaknesses:** On-chain licensing has not publicly proven enterprise demand at scale. **Inference:** crypto/token framing may be a liability for conservative enterprise buyers.
- **Overlap:** Medium for training-data provenance, lower for agent inference.
- **Classification:** Adjacent competitor / cautionary infrastructure.

## 5. Data owners going direct

### 5.1 Reuters MCP

- **Product description:** Reuters launched a Model Context Protocol server on 2026-07-08 for Reuters News Agency customers to let AI agents search, retrieve, download, and integrate Reuters content in workflows ([Editor & Publisher / Reuters announcement, 2026-07-08](https://www.editorandpublisher.com/stories/reuters-launches-model-context-protocol-server-to-bring-trusted-news-directly-into-customers-ai,262502)).
- **Founded:** Reuters dates to 1851; the MCP product launched in 2026.
- **Funding / investors:** Thomson Reuters is public; product-level funding not applicable.
- **Customers / partners:** Reuters News Agency customers; named customers not disclosed in the MCP announcement.
- **Pricing / revenue model:** Existing Reuters subscription/licensing model; MCP-specific pricing not disclosed.
- **Technical delivery:** MCP server for subscribed content.
- **Licensing model:** Subscriber access to Reuters content.
- **Controls:** Reuters controls entitlement through subscriptions; buyers access only subscribed content.
- **Strengths:** Premium trusted source with direct AI-native delivery.
- **Weaknesses:** One data owner only; not a cross-provider marketplace.
- **Overlap:** Medium as a substitute: premium owners may self-serve through MCP.
- **Classification:** Substitute and partner.

### 5.2 Reddit data licensing

- **Product description:** Reddit licenses platform data/content to partners and identifies content licensing as a revenue stream in SEC filings ([Reddit 2025 Form 10-K, filed 2026](https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/rddt-20251231.htm); [Revenue note R30, 2026](https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/R30.htm)).
- **Founded:** Reddit founded 2005; not central to this analysis.
- **Funding / revenue:** Public company. SEC note says content licensing arrangements are generally fixed-fee or usage-based; 2025 "Other revenue" was $140.0M vs. $114.7M in 2024, but Other revenue also includes products sold directly to users, so do not treat all Other revenue as data licensing ([Reddit revenue note R11, 2026](https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/R11.htm)).
- **Customers / partners:** Reuters reported Google's deal at about $60M/year; AP also reported a roughly $60M Google arrangement; Reddit later partnered with OpenAI (OpenAI/Reddit specific official source not fetched in this pass, so not quantified here) ([Reuters, 2024-02-21](https://www.reuters.com/technology/reddit-ai-content-licensing-deal-with-google-sources-say-2024-02-22/); [AP, 2024-02-22](https://apnews.com/article/google-reddit-ai-partnership-a7f131c7cb4225307134ef21d3c6a708)).
- **Pricing / revenue model:** Fixed-fee or usage-based licensing per SEC filing; specific customer terms mostly confidential.
- **Technical delivery:** Data/API access; Google deal described as Data API access in reporting.
- **Licensing model:** Bilateral platform data licenses.
- **Controls:** Reddit controls API terms and partner access; buyer controls are contract/API specific.
- **Strengths:** Unique, constantly updated conversational corpus.
- **Weaknesses:** High-value platforms can bypass exchanges and negotiate directly.
- **Overlap:** Medium substitute; potential supplier only if willing to multi-home.
- **Classification:** Substitute and potential partner.

### 5.3 Stack Overflow data licensing

- **Product description:** Stack Data Licensing gives real-time API access to Stack Overflow / Stack Exchange public datasets for AI training, fine-tuning, and grounding, with attribution ([Stack Overflow data licensing page, accessed 2026-07-15](https://stackoverflow.co/data-licensing/)).
- **Funding / ownership:** Stack Overflow is Prosus-owned; product-level funding not applicable.
- **Customers / partners:** OpenAI and Google Cloud partnerships are verified by OpenAI and Google Cloud announcements ([OpenAI, 2024-05-06](https://openai.com/index/api-partnership-with-stack-overflow/); [Google Cloud / Stack Overflow, 2024-02-29](https://www.googlecloudpresscorner.com/2024-02-29-Stack-Overflow-and-Google-Cloud-Announce-Strategic-Partnership-to-Bring-Generative-AI-to-Millions-of-Developers)). Stack Overflow data is also available on Snowflake Marketplace as a Cortex Knowledge Extension ([Stack Overflow blog, 2025-06-03](https://stackoverflow.blog/2025/06/03/stack-exchange-knowledge-is-for-everyone-and-now-available-on-snowflake-marketplace/)).
- **Pricing / revenue model:** Subscription/data licensing; exact terms not disclosed.
- **Technical delivery:** Stack Exchange API, curated datasets, Snowflake Marketplace.
- **Licensing model:** Authorized dataset/API access with attribution; original content license complexities remain a diligence issue.
- **Controls:** Stack controls data scope/curation; buyers choose full corpus or subsets per product page.
- **Strengths:** High-signal technical Q&A and metadata.
- **Weaknesses:** Direct bilateral and cloud marketplace channels reduce need for a new broker.
- **Overlap:** Low-medium substitute / potential partner.
- **Classification:** Substitute and partner.

### 5.4 Major publisher-model licensing deals

The bilateral licensing market proves large buyers will pay for some content, but it also weakens the case for a generic independent exchange because the largest rights holders and AI labs can transact directly.

- **OpenAI/AP:** AP and OpenAI reached a two-year collaboration in July 2023; OpenAI licensed part of AP's text archive and financial terms were not disclosed ([AP, 2023-07-13](https://www.ap.org/media-center/press-releases/2023/ap-open-ai-agree-to-share-select-news-content-and-technology-in-new-collaboration/); [AP News, 2023-07-13](https://apnews.com/article/openai-chatgpt-associated-press-ap-f86f84c5bcc2f3b98074b38521f5f75a)).
- **OpenAI/Axel Springer:** Partnership includes ChatGPT summaries of selected content with attribution/links and use of Axel Springer content for training ([OpenAI, 2023-12-13](https://openai.com/index/axel-springer-partnership/)).
- **OpenAI/Financial Times:** FT announced a strategic partnership/licensing agreement to enhance ChatGPT with attributed content and improve model usefulness ([OpenAI, 2024-04-29](https://openai.com/index/content-partnership-with-financial-times/)).
- **OpenAI/News Corp:** Multi-year agreement for current and archived content from major News Corp publications; deal value not disclosed by companies ([OpenAI, 2024-05-22](https://openai.com/index/news-corp-and-openai-sign-landmark-multi-year-global-partnership/); [AP News, 2024-05-22](https://apnews.com/article/openai-news-corp-a49144d381796df5729c746f52fbef19)).
- **OpenAI/Condé Nast, Hearst, Washington Post:** Display and search partnerships with attribution/links; exact financial terms not disclosed ([OpenAI/Conde Nast, 2024-08-20](https://openai.com/index/conde-nast/); [Hearst, 2024-10-08](https://www.hearst.com/-/hearst-and-openai-announce-strategic-content-partnership?p_l_back_url=%2Fnews%2Fpress-releases&p_l_back_url_title=Press+Releases); [OpenAI/Washington Post, 2025](https://openai.com/global-affairs/the-washington-post-partners-with-openai/)).
- **Meta/Reuters:** Reuters reported a 2024-10-25 deal for Meta AI to use Reuters news content for current-events answers; financial terms and training rights were not disclosed ([Reuters, 2024-10-25](https://www.reuters.com/technology/artificial-intelligence/meta-platforms-use-reuters-news-content-ai-chatbot-2024-10-25/)).
- **Amazon/New York Times:** NYT and Amazon announced a multi-year AI-related licensing agreement for NYT, NYT Cooking, and The Athletic content; includes summaries/excerpts in Amazon products and training Amazon proprietary foundation models; financial terms not disclosed ([NYT Co., 2025-05-29](https://investors.nytco.com/news-and-events/press-releases/news-details/2025/The-New-York-Times-Company-and-Amazon-Announce-Licensing-Agreement--2025-cYgtzu69ot/default.aspx); [Reuters, 2025-05-29](https://www.reuters.com/business/retail-consumer/new-york-times-amazon-sign-ai-licensing-deal-2025-05-29/)).
- **Microsoft/Informa:** Reporting says Informa / Taylor & Francis granted Microsoft access to advanced learning content for AI-related uses through 2027; reported first-year value above $10M, but primary Informa filing/source was not directly fetched here, so treat value as secondary reported ([The Conversation, 2024-07-25](https://theconversation.com/an-academic-publisher-has-struck-an-ai-data-deal-with-microsoft-without-their-authors-knowledge-235203); [Inside Higher Ed, 2024-07-29](https://www.insidehighered.com/news/faculty/research/2024/07/29/taylor-francis-ai-deal-sets-worrying-precedent)).

**Implication:** large content owners prefer direct deals when they have bargaining power. An independent exchange must serve the long tail or vertical specialists that do not have direct-market leverage.

## 6. Enterprise data marketplaces and cloud substitutes

### 6.1 AWS Data Exchange / AWS Marketplace

- **Product description:** AWS Data Exchange lets AWS customers find, subscribe to, and use third-party data files, tables, and APIs in AWS; AWS Marketplace also has an AI Agents and Tools category for agents, tools, MCP/A2A-supporting listings, and AgentCore deployment ([AWS Data Exchange, accessed 2026-07-15](https://aws.amazon.com/data-exchange/); [AWS AI Agents & Tools, 2025-07-16](https://aws.amazon.com/about-aws/whats-new/2025/07/ai-agents-tools-aws-marketplace/)).
- **Funding / investors:** Amazon public company; product-level funding not applicable.
- **Customers / partners:** AWS claims 3,500+ third-party datasets and 300+ data providers on AWS Data Exchange; AWS Marketplace agent listings are partner products ([AWS Data Exchange, accessed 2026-07-15](https://aws.amazon.com/data-exchange/); [AWS Marketplace AI Agent Solutions, accessed 2026-07-15](https://aws.amazon.com/marketplace/solutions/ai-agents-and-tools)).
- **Pricing / revenue model:** Marketplace subscriptions/pay-as-you-go/contracts through AWS Marketplace; take rates not transparent in cited sources.
- **Technical delivery:** Data APIs, files, tables, subscriptions, AWS IAM entitlement, AWS Marketplace billing, AgentCore deployment / Gateway.
- **Licensing model:** Provider-set commercial data subscriptions and marketplace terms.
- **Controls:** Providers can require subscription verification; AWS handles entitlement, billing, and access ([AWS docs, accessed 2026-07-15](https://docs.aws.amazon.com/data-exchange/latest/userguide/providing-data-sets.html)).
- **Strengths:** Procurement gravity and enterprise billing.
- **Weaknesses:** Generic marketplace discovery is not optimized for agent-workflow gap detection or niche data curation.
- **Overlap:** Medium as infrastructure/substitute.
- **Classification:** Substitute, infrastructure provider, possible acquirer.

### 6.2 Snowflake Marketplace / Cortex Knowledge Extensions

- **Product description:** Snowflake Cortex Knowledge Extensions are Cortex Search Services shared via Snowflake Marketplace to integrate licensed/proprietary third-party unstructured content into RAG and agentic systems ([Snowflake docs, accessed 2026-07-15](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-knowledge-extensions/cke-overview)).
- **Customers / partners:** Snowflake announcement names AP, USA TODAY, Stack Overflow, CB Insights, Packt, and others for AI-ready data / CKEs ([BusinessWire, 2025-06-03](https://www.businesswire.com/news/home/20250603685114/en/Snowflake-Marketplace-Adds-Agentic-Products-and-AI-Ready-Data-from-Leading-News-Research-and-Market-Data-Providers)).
- **Pricing / revenue model:** Marketplace commercial listings / Snowflake consumption; specific commission not public.
- **Technical delivery:** Shared Cortex Search Services, Cortex Agent API, Marketplace listings.
- **Licensing model:** Third-party licensed content with attribution/IP controls according to Snowflake announcement.
- **Controls:** Provider controls listing and region availability; consumer accesses in Snowflake governance.
- **Strengths:** Licensed grounding where enterprise data already lives.
- **Weaknesses:** Platform-bound; not neutral across all agent runtimes.
- **Overlap:** Medium, especially enterprise segment.
- **Classification:** Substitute / competitor in enterprise grounding.

### 6.3 Databricks Marketplace / MCP Marketplace

- **Product description:** Databricks Marketplace lists datasets, AI models, notebooks, apps, and MCP servers; external MCP servers can be installed into Unity Catalog-governed connections ([Databricks Marketplace docs, accessed 2026-07-15](https://docs.databricks.com/aws/en/marketplace/); [Databricks consumer docs, accessed 2026-07-15](https://docs.databricks.com/aws/en/marketplace/get-started-consumer)).
- **Customers / partners:** Databricks blog names You.com, Moody's, Cotality, Glean, S&P Global, FactSet, Dun & Bradstreet, and others for MCP / AI-ready data ([Databricks blog, 2026](https://www.databricks.com/blog/mcp-marketplace-brings-real-time-intelligence-agentic-applications); [Databricks blog, 2026](https://www.databricks.com/blog/accelerate-ai-development-databricks-discover-govern-and-build-mcp-and-agent-bricks)).
- **Revenue model / pricing:** Marketplace commercial listings; exact commission not public.
- **Technical delivery:** MCP servers, Unity Catalog connections, AI agents / Agent Bricks.
- **Licensing model:** Provider-set listing terms inside Databricks.
- **Controls:** Unity Catalog governance and connection privileges.
- **Strengths:** Governance and secure enterprise MCP distribution.
- **Weaknesses:** Platform-bound; may not solve cross-agent marketplace needs outside Databricks.
- **Overlap:** Medium.
- **Classification:** Substitute / competitor in enterprise MCP distribution.

## 7. API networks, MCP discovery, and marketplace cautionary tales

### 7.1 RapidAPI / Rapid

- **Product description:** Rapid operated a public API marketplace and enterprise API hub; Nokia acquired Rapid's technology assets and R&D unit on 2024-11-13 to support Nokia Network as Code ([Nokia, 2024-11-13](https://www.nokia.com/newsroom/nokia-acquires-rapid-technology-and-rd-unit-to-strengthen-development-of-network-api-solutions-and-ecosystem/)).
- **Funding / investors:** Historical funding/valuation not necessary to the current competitive claim; TechCrunch notes Rapid was once valued at $1B and deal terms were undisclosed ([TechCrunch, 2024-11-13](https://techcrunch.com/2024/11/13/nokia-acquires-rapid-the-api-company-once-valued-at-1b/)).
- **Pricing / revenue model:** API subscription/marketplace commissions historically; current Nokia integration terms not public.
- **Technical delivery:** API hub, public marketplace, enterprise services.
- **Strengths:** Demonstrated developer appetite for API discovery.
- **Weaknesses:** Independent horizontal API marketplace struggled; acquisition of assets is a warning that discovery alone may not be durable.
- **Overlap:** Medium cautionary substitute.
- **Classification:** Substitute / cautionary precedent.

### 7.2 Postman API Network

- **Product description:** Postman API Network exposes public APIs; Postman's MCP Generator can turn public API requests from the API Network into MCP servers; Postman also offers a Postman MCP server and Agent Mode ([Postman docs, accessed 2026-07-15](https://learning.postman.com/docs/postman-ai/mcp-servers/generate); [Postman MCP server GitHub, accessed 2026-07-15](https://github.com/postmanlabs/postman-mcp-server)).
- **Funding / investors:** Not relevant to product-level competitive analysis here; not re-verified.
- **Revenue model:** Dev-tool SaaS; API Network/MCP generator monetization specifics not public.
- **Technical delivery:** Public API collections, generated MCP servers, Postman workspace MCP.
- **Licensing model:** Discovery and integration tooling, not brokered data licensing.
- **Controls:** API publishers control APIs/collections; developers generate tools.
- **Strengths:** Distribution and developer trust.
- **Weaknesses:** No built-in licensing, metering, settlement, or source ranking for proprietary data exchange.
- **Overlap:** Low-medium.
- **Classification:** Partner / substitute for discovery and integration.

### 7.3 MCP registries

- **Product description:** Official MCP Registry launched in preview on 2025-09-08 as an open catalog/API for publicly available MCP servers ([MCP blog, 2025-09-08](https://blog.modelcontextprotocol.io/posts/2025-09-08-mcp-registry-preview/); [MCP registry about, accessed 2026-07-15](https://modelcontextprotocol.io/registry/about.md)).
- **Funding / investors:** Open-source/community project; not a company.
- **Revenue model:** None for official registry; third-party registries may use freemium/sponsored models, not analyzed here.
- **Technical delivery:** Registry API and metadata repository.
- **Licensing model:** Discovery only; no payment/licensing settlement by default.
- **Controls:** Server publishers list metadata; clients consume registry/sub-registries.
- **Strengths:** Free/open discovery layer can commoditize the "catalog" part of the proposed exchange.
- **Weaknesses:** No licensing, QA, entitlement, SLA, or settlement.
- **Overlap:** Medium on discovery; low on marketplace transactions.
- **Classification:** Infrastructure / substitute / partner.

## 8. Payment and agent-commerce protocols

### 8.1 Stripe ACP and Agentic Commerce Suite

- **Product description:** Agentic Commerce Protocol (ACP) is an open standard created by Stripe, OpenAI, and Meta for AI-agent commerce; Stripe powers Instant Checkout in ChatGPT and provides ACP documentation ([Stripe docs, accessed 2026-07-15](https://docs.stripe.com/agentic-commerce/acp); [Stripe newsroom, 2026](https://stripe.com/newsroom/news/stripe-openai-instant-checkout); [OpenAI, 2026](https://openai.com/index/buy-it-in-chatgpt/)).
- **Funding / investors:** Stripe is private; no product funding claim.
- **Customers / partners:** Stripe/OpenAI announcement says Etsy businesses live first and over a million Shopify merchants coming soon; OpenAI is first platform in ACP docs / site ([Stripe newsroom, 2026](https://stripe.com/newsroom/news/stripe-openai-instant-checkout); [ACP site, accessed 2026-07-15](https://www.agenticcommerce.dev/)).
- **Pricing / revenue model:** Stripe payment processing; ACP itself open-source/standard. Exact agentic-commerce fee beyond Stripe processing not public.
- **Technical delivery:** REST checkout sessions, Shared Payment Tokens, merchant-controlled endpoints, optional MCP publication ([ACP checkout docs, accessed 2026-07-15](https://www.agenticcommerce.dev/docs/reference/checkout)).
- **Licensing model:** Retail checkout, not content licensing.
- **Controls:** Merchants remain merchant of record, control inventory/pricing/fulfillment; agents initiate checkout within protocol.
- **Strengths:** Payment/merchant network and ChatGPT distribution.
- **Weaknesses:** Retail-focused; not designed for data licensing.
- **Overlap:** Low-medium as infrastructure.
- **Classification:** Infrastructure; possible future settlement competitor.

### 8.2 Stripe Machine Payments Protocol (MPP)

- **Product description:** Stripe launched MPP as an open, internet-native way for agents to pay services, APIs, MCP servers, or HTTP endpoints; it supports stablecoins and fiat via Stripe infrastructure ([Stripe blog, 2026-03-18](https://stripe.com/blog/machine-payments-protocol); [MPP protocol docs, accessed 2026-07-15](https://mpp.dev/protocol)).
- **Revenue model:** Stripe payment processing; exact protocol economics not separately disclosed.
- **Technical delivery:** HTTP 402 challenge/credential flow and Stripe PaymentIntents integration ([Stripe machine-payments docs, accessed 2026-07-15](https://docs.stripe.com/payments/machine)).
- **Overlap:** Medium as payment infrastructure for paid data/API calls.
- **Classification:** Infrastructure / settlement substitute.

### 8.3 x402

- **Product description:** x402 is an HTTP 402-based payment protocol contributed by Coinbase and stewarded by the Linux Foundation x402 Foundation; it enables AI agents, APIs, and applications to send/receive payments over web interactions ([Linux Foundation, 2026-07-14](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications?hs_amp=true); [x402 docs, accessed 2026-07-15](https://docs.x402.org/core-concepts/http-402)).
- **Members / partners:** Linux Foundation says 40 organizations joined, including AWS, Cloudflare, Coinbase, Google, Mastercard, Stripe, Visa, Shopify, and others ([Linux Foundation, 2026-07-14](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications?hs_amp=true)).
- **Revenue model:** Open protocol; facilitators/payment processors may monetize. Not itself a marketplace.
- **Technical delivery:** HTTP 402, payment requirement headers, client payment signature, settlement response.
- **Licensing model:** Per-request paid access; not domain-specific licensing.
- **Strengths:** Broad payment/cloud/network support; useful primitive for paid data calls.
- **Weaknesses:** Does not solve rights, discovery, ranking, data quality, indemnity, or buyer demand.
- **Overlap:** Medium infrastructure.
- **Classification:** Infrastructure / possible commoditizer of metering/settlement.

### 8.4 AP2, ACP, and UCP

- **AP2:** Google's Agent Payments Protocol uses signed mandates for secure agent payments and was donated to FIDO Alliance on 2026-04-28; FIDO is developing agentic authentication and payments standards from AP2 and Mastercard Verifiable Intent ([Google, 2026-04-28](https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/); [FIDO Alliance, 2026-04-28](https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/); [AP2 docs, accessed 2026-07-15](https://ap2-protocol.org/)).
- **ACP:** Covered above; OpenAI/Stripe/Meta retail checkout standard ([Stripe docs, accessed 2026-07-15](https://docs.stripe.com/agentic-commerce/acp)).
- **UCP:** Universal Commerce Protocol is an open standard co-developed by Google and Shopify for AI-surface commerce, with REST API and MCP binding and compatibility with AP2, A2A, and MCP ([Google Developers, accessed 2026-07-15](https://developers.google.com/merchant/ucp); [Shopify Engineering, 2026-01-11](https://shopify.engineering/UCP); [UCP GitHub, accessed 2026-07-15](https://github.com/Universal-Commerce-Protocol/ucp?tab=readme-ov-file)).
- **Relevance:** These protocols are mostly retail/commerce rails. They are not content/data exchanges, but they shape agent authorization, merchant controls, user intent, checkout, and payment primitives.
- **Overlap:** Low for proprietary-data exchange, medium for payment/authorization infrastructure.
- **Classification:** Infrastructure.

### 8.5 Web Monetization

- **Product description:** Proposed Web Monetization standard currently incubating in WICG; web pages can advertise monetization links, but browsers need a Web Monetization agent/extension until native support exists ([WICG GitHub, accessed 2026-07-15](https://github.com/wicg/webmonetization/); [Web Monetization docs, accessed 2026-07-15](https://webmonetization.org/developers/link-element/)).
- **Status caveat:** W3C Interledger Payments Community Group was closed on 2026-06-02 ([W3C, accessed 2026-07-15](https://www.w3.org/groups/cg/interledger/)).
- **Revenue model:** Voluntary/streaming micropayments; adoption limited.
- **Technical delivery:** `monetization` link relation, Open Payments APIs via agent/extension.
- **Strengths:** Long-running open-web payment effort.
- **Weaknesses:** No native major-browser support found; adoption not comparable to Stripe/x402/cloud rails.
- **Overlap:** Low.
- **Classification:** Cautionary infrastructure.

## 9. Crowding and competitive pressure

### 9.1 Open-web crawl monetization is crowded

TollBit, Cloudflare, Microsoft PCM, ScalePost, Dappier, Perplexity's publisher program, and ProRata/Gist all target some version of publisher monetization in the AI era. Cloudflare has the strongest enforcement position because it sits at the edge and can implement crawl/payment rules directly; TollBit has independent-marketplace positioning; Microsoft has first-party AI demand and publisher relationships; ProRata bypasses agent payments by monetizing answer experiences with ads.

**Inference:** a new generic "pay publishers for crawls or citations" startup would be late unless it owns demand that incumbents cannot access.

### 9.2 Enterprise marketplaces are strong substitutes

AWS, Snowflake, and Databricks already provide entitlement, procurement, governance, billing, and deployment. They are not optimized for neutral cross-agent data routing, but enterprise buyers often prefer existing procurement channels over new vendor onboarding.

**Inference:** for enterprise data buyers, a startup must either list inside these clouds or offer data/quality/routing value so specific that cloud marketplace procurement becomes a channel rather than a competitor.

### 9.3 Payment rails are commoditizing

x402, Stripe MPP, ACP, AP2, and UCP make it easier for agents to pay APIs, merchants, or endpoints. That reduces the defensibility of "we handle payments" as a standalone moat.

**Inference:** the durable value is not settlement plumbing; it is trusted supply, buyer workflow integration, vertical schema/quality, licensing clarity, and source performance data.

### 9.4 Direct deals skim the top of the market

Reddit, Stack Overflow, Reuters, AP, NYT, News Corp, Axel Springer, FT, Conde Nast, Hearst, and Washington Post can transact directly with AI majors or through cloud marketplaces. An independent exchange is more likely to serve:

- mid-market proprietary data owners,
- regulated / technical / local / scientific / operational datasets,
- APIs too small for bilateral deals but too valuable for scraping,
- buyers needing narrow, auditable, per-use access rather than broad training rights.

## 10. Where an independent company could still differentiate

### 10.1 Best wedge: vertical proprietary structured data

Most public competition targets news, web content, creator content, or generic APIs. The proposed company should avoid "all publishers, all agents" at first. Better pilot markets have:

- high value per answer,
- structured or semi-structured data,
- clear ownership and licensing rights,
- freshness requirements,
- agents that produce measurable ROI,
- tolerance for paid data calls,
- need for audit/indemnity.

Examples to test separately: compliance data, financial reference data, insurance underwriting, healthcare operations, industrial parts/specs, logistics capacity/rates, real estate parcel/zoning, scientific protocols, legal/regulatory updates. These are examples for future diligence, not verified target recommendations.

### 10.2 Product differentiation that incumbents do not visibly offer

- **Gap-to-supply loop:** prove demand by capturing unanswered/low-confidence agent queries and translating them into data-acquisition priorities.
- **Neutral source ranking:** compare sources on freshness, latency, coverage, provenance, licensing terms, error rate, and downstream answer impact.
- **Narrow licenses:** sell "one answer, one field, one user, one session" rights rather than broad training licenses.
- **Buyer spend controls:** max price, source allowlists/blocklists, data categories, per-task budget, compliance filters, audit logs.
- **Publisher/data-owner controls:** field-level exposure, purpose restrictions, model-training prohibition, citation requirements, region restrictions, rate limits, revocation, minimum price, buyer approval.
- **Quality and SLA layer:** schema normalization, test queries, source evaluation, fallback/routing, incident handling.

### 10.3 What not to claim as novel

Do not claim novelty for:

- paid crawler access (Cloudflare/TollBit),
- publisher licensing marketplaces (Microsoft/TollBit/Dappier/ScalePost),
- per-query RAG content marketplaces (Dappier/Cloudflare experiments/Snowflake CKE),
- MCP delivery of premium content (Reuters, Databricks, Dappier, Postman tooling),
- HTTP 402 machine payments (x402/Stripe MPP/Cloudflare Pay Per Crawl),
- agent commerce checkout (ACP/AP2/UCP),
- content attribution/revenue share (ProRata/Bria).

## 11. Primary risks for the proposed company

1. **Demand risk:** public evidence shows many content owners want to be paid; less public evidence shows AI-agent developers consistently pay meaningful amounts outside top bilateral deals.
2. **Enforcement risk:** without edge/control-plane leverage, a marketplace cannot force crawlers or agents to pay.
3. **Platform risk:** Cloudflare, Microsoft, AWS, Snowflake, Databricks, Stripe, OpenAI, Google, and Shopify can internalize key layers.
4. **Supply risk:** valuable data owners may prefer direct deals, cloud marketplaces, or private APIs.
5. **Commoditization risk:** payment, MCP discovery, and checkout standards are becoming open infrastructure.
6. **Trust risk:** sponsored discovery can undermine agent/source trust unless separated from organic ranking and clearly labeled.

## 12. Strategic recommendation for competitive positioning

Pursue only through a narrow vertical pilot, not a horizontal marketplace launch.

The pilot should prove:

- at least 3-5 proprietary data suppliers with rights to license data,
- at least 2-3 agent/application buyers willing to pay now,
- a data call value high enough to support real marketplace take rate,
- buyer-side workflow integration where gap detection or source ranking is materially useful,
- audit/licensing controls that clouds/protocols do not provide out of the box.

If the first pilot is merely open-web publisher crawl monetization, the concept is likely crowded out by TollBit, Cloudflare, Microsoft, and publisher bilateral deals.

## Sources used

- https://tollbit.com/blog/series-a/ - accessed 2026-07-15; supports TollBit product, $24M Series A, live marketplace, named publishers.
- https://www.prnewswire.com/news-releases/tollbit-a-two-sided-marketplace-for-ai-companies-and-publishers-closes-at-24-million-in-series-a-funding-302283475.html - 2024-10-22; supports TollBit Series A, publisher list, Particle mention.
- https://www.axios.com/2024/10/22/ai-startup-tollbit-media-publishers - 2024-10-22; supports TollBit total funding and seed/Series A context.
- https://lsvp.com/stories/investing-in-tollbit-the-internets-ai-toll-booth/ - 2024; supports TollBit publisher-set rates and autonomous URL access.
- https://lsvp.com/company/tollbit/ - accessed 2026-07-15; supports TollBit founded 2023 and leadership.
- https://www.fastly.com/blog/how-to-control-and-monetize-ai-bot-traffic-using-fastly-and-tollbit - accessed 2026-07-15; supports Fastly/TollBit technical delivery.
- https://www.akamai.com/newsroom/press-release/no-free-crawls-akamai-tollbit-and-skyfire-turn-traffic-into-revenue - accessed 2026-07-15; supports Akamai/TollBit/Skyfire alliance and TollBit usage claims.
- https://www.akamai.com/blog/security/from-scraping-paying-monetizing-ai-bots-edge - accessed 2026-07-15; supports Akamai edge integration details.
- https://blog.cloudflare.com/introducing-pay-per-crawl/ - 2025-07-01; supports Cloudflare Pay Per Crawl, HTTP 402, merchant-of-record, publisher controls.
- https://developers.cloudflare.com/ai-crawl-control/features/pay-per-crawl/what-is-pay-per-crawl/ - modified 2026-04-23; supports Pay Per Crawl closed beta and mechanics.
- https://blog.cloudflare.com/making-ai-search-smarter/ - 2026-07-01; supports Cloudflare Pay Per Use, Ceramic.ai, You.com experiments.
- https://www.cloudflare.com/press/press-releases/2026/cloudflare-allows-the-agentic-internet-to-flourish-with-a-simple-philosophy-your-content-your-rules/ - 2026-07-01; supports Cloudflare Pay Per Use announcement and partner descriptions.
- https://www.cloudflare.com/press/press-releases/2026/cloudflare-strengthens-content-offering-to-ai-companies-with-acquisition-of-human-native/ - 2026-01-15; supports Cloudflare acquisition of Human Native and Human Native description.
- https://blog.cloudflare.com/human-native-joins-cloudflare/ - 2026-01-15; supports Human Native integration and Cloudflare content/data marketplace direction.
- https://www.humannative.ai/blog/seed-funding-announcement - 2024-06-03; supports Human Native GBP2.8M seed, LocalGlobe, Mercuri.
- https://www.cnbc.com/2026/01/15/cloudflare-ai-human-native-acquisition.html - 2026-01-15; supports Human Native acquisition terms undisclosed.
- https://searchengineland.com/microsoft-launches-publisher-content-marketplace-for-ai-licensing-468191 - 2026-02-03; supports Microsoft Publisher Content Marketplace features and partner list.
- https://www.theverge.com/news/873296/microsoft-publisher-content-marketplace-ai-licensing - 2026-02-03; supports PCM usage terms, reporting, and Microsoft pilot caveats.
- https://dappier.com/dappier-mcp-improving-ai-with-real-time-data - accessed 2026-07-15; supports Dappier MCP, publisher price setting, rights-cleared data.
- https://techcrunch.com/2024/06/26/dappier-is-building-a-marketplace-for-publishers-to-sell-their-content-to-llm-builders/ - 2024-06-26; supports Dappier $2M seed and per-query/ad-supported model.
- https://siliconangle.com/2024/06/26/dappier-raises-2m-seed-funding-ai-data-marketplace/ - 2024-06-26; supports Dappier seed and pay-as-you-go pricing claims.
- https://dappier.medium.com/making-real-time-data-free-with-rag-mcp-supporting-6-major-ai-integrations-16fe03d84d17 - accessed 2026-07-15; supports Dappier free real-time data/native ads shift claim.
- https://www.businesswire.com/news/home/20250905771340/en/ProRata-Closes-%2440-Million-Series-B-Financing-and-Launches-Gist-Answers-Creating-New-Revenue-Opportunities-for-Publishers-in-the-AI-Era - 2025-09-05; supports ProRata Series B, funding, Gist Answers, publication count.
- https://prorata.ai/ - accessed 2026-07-15; supports ProRata 50% revenue share and 1,000+ publication claim.
- https://www.scalepost.ai/for-ai-llms - accessed 2026-07-15; supports ScalePost product and Perplexity case study.
- https://www.perplexity.ai/hub/blog/introducing-the-perplexity-publishers-program - 2024-07-30; supports Perplexity publisher program and ScalePost analytics partnership.
- https://authorsguild.org/news/ag-partners-with-created-by-humans-to-empower-authors-in-ai-era/ - 2024-10-09; supports Created by Humans / Authors Guild partnership and pre-seed context.
- https://www.createdbyhumans.ai/ - accessed 2026-07-15; supports Created by Humans product, rights categories, author controls.
- https://www.prweb.com/releases/created-by-humans-ai-licensing-platform-for-books-launches-with-the-support-of-bestselling-authors-302350249.html - 2025-01-14; supports Created by Humans launch, additional funding, author support.
- https://blog.bria.ai/bria-awarded-40m-in-series-b - 2025-03-13; supports Bria product, $40M Series B, $65M total, investors, data partners.
- https://www.prnewswire.com/news-releases/bria-secures-40m-in-series-b-to-drive-fair-gen-ai-usage-for-enterprises-302400907.html - 2025-03-13; supports Bria licensed-data and attribution-engine details.
- https://www.coindesk.com/business/2026/06/25/a16z-backed-crypto-firm-rebrands-shifts-focus-to-solving-ai-s-global-copyright-headache - 2026-06-25; supports Story/DATA rebrand, reported funding, Trace/provenance focus.
- https://ir.ipstrategy.co/news-events/press-releases/detail/177/ip-strategy-highlights-story-foundations-transition-to-the - 2026-06-26; supports DATA Network/Trace/Kled/Poseidon claims from affiliated public company release.
- https://www.editorandpublisher.com/stories/reuters-launches-model-context-protocol-server-to-bring-trusted-news-directly-into-customers-ai,262502 - 2026-07-08; supports Reuters MCP launch and capabilities.
- https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/rddt-20251231.htm - filed 2026; supports Reddit content licensing strategy.
- https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/R30.htm - filed 2026; supports Reddit licensing revenue recognition model.
- https://www.sec.gov/Archives/edgar/data/1713445/000171344526000022/R11.htm - filed 2026; supports Reddit Other revenue and remaining performance obligations.
- https://www.reuters.com/technology/reddit-ai-content-licensing-deal-with-google-sources-say-2024-02-22/ - 2024-02-21/22; supports reported Reddit/Google deal value.
- https://apnews.com/article/google-reddit-ai-partnership-a7f131c7cb4225307134ef21d3c6a708 - 2024-02-22; supports Reddit/Google deal and rough value.
- https://stackoverflow.co/data-licensing/ - accessed 2026-07-15; supports Stack Overflow Data Licensing product.
- https://openai.com/index/api-partnership-with-stack-overflow/ - 2024-05-06; supports OpenAI/Stack Overflow partnership.
- https://www.googlecloudpresscorner.com/2024-02-29-Stack-Overflow-and-Google-Cloud-Announce-Strategic-Partnership-to-Bring-Generative-AI-to-Millions-of-Developers - 2024-02-29; supports Google Cloud/Stack Overflow partnership.
- https://stackoverflow.blog/2025/06/03/stack-exchange-knowledge-is-for-everyone-and-now-available-on-snowflake-marketplace/ - 2025-06-03; supports Stack Exchange data on Snowflake Marketplace.
- https://www.ap.org/media-center/press-releases/2023/ap-open-ai-agree-to-share-select-news-content-and-technology-in-new-collaboration/ - 2023-07-13; supports AP/OpenAI collaboration.
- https://apnews.com/article/openai-chatgpt-associated-press-ap-f86f84c5bcc2f3b98074b38521f5f75a - 2023-07-13; supports AP/OpenAI financial terms undisclosed.
- https://openai.com/index/axel-springer-partnership/ - 2023-12-13; supports OpenAI/Axel Springer terms.
- https://openai.com/index/content-partnership-with-financial-times/ - 2024-04-29; supports OpenAI/FT deal.
- https://openai.com/index/news-corp-and-openai-sign-landmark-multi-year-global-partnership/ - 2024-05-22; supports OpenAI/News Corp deal scope.
- https://apnews.com/article/openai-news-corp-a49144d381796df5729c746f52fbef19 - 2024-05-22; supports News Corp deal terms undisclosed.
- https://openai.com/index/conde-nast/ - 2024-08-20; supports OpenAI/Conde Nast partnership.
- https://www.hearst.com/-/hearst-and-openai-announce-strategic-content-partnership?p_l_back_url=%2Fnews%2Fpress-releases&p_l_back_url_title=Press+Releases - 2024-10-08; supports OpenAI/Hearst partnership.
- https://openai.com/global-affairs/the-washington-post-partners-with-openai/ - 2025; supports OpenAI/Washington Post partnership and partner count claim.
- https://www.reuters.com/technology/artificial-intelligence/meta-platforms-use-reuters-news-content-ai-chatbot-2024-10-25/ - 2024-10-25; supports Meta/Reuters deal.
- https://investors.nytco.com/news-and-events/press-releases/news-details/2025/The-New-York-Times-Company-and-Amazon-Announce-Licensing-Agreement--2025-cYgtzu69ot/default.aspx - 2025-05-29; supports NYT/Amazon official deal.
- https://www.reuters.com/business/retail-consumer/new-york-times-amazon-sign-ai-licensing-deal-2025-05-29/ - 2025-05-29; supports NYT/Amazon summary and terms undisclosed.
- https://theconversation.com/an-academic-publisher-has-struck-an-ai-data-deal-with-microsoft-without-their-authors-knowledge-235203 - 2024-07-25; supports reported Informa/Microsoft details and author-rights controversy.
- https://www.insidehighered.com/news/faculty/research/2024/07/29/taylor-francis-ai-deal-sets-worrying-precedent - 2024-07-29; supports reported Informa/Microsoft value and terms through 2027.
- https://aws.amazon.com/data-exchange/ - accessed 2026-07-15; supports AWS Data Exchange scale and product.
- https://aws.amazon.com/data-exchange/why-aws-data-exchange/apis/ - accessed 2026-07-15; supports AWS Data Exchange API access, entitlement, billing.
- https://docs.aws.amazon.com/data-exchange/latest/userguide/providing-data-sets.html - accessed 2026-07-15; supports AWS provider controls.
- https://aws.amazon.com/about-aws/whats-new/2025/07/ai-agents-tools-aws-marketplace/ - 2025-07-16; supports AWS Marketplace AI Agents and Tools category.
- https://aws.amazon.com/marketplace/solutions/ai-agents-and-tools - accessed 2026-07-15; supports AWS agent marketplace features.
- https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-knowledge-extensions/cke-overview - accessed 2026-07-15; supports Snowflake CKE technical model.
- https://www.businesswire.com/news/home/20250603685114/en/Snowflake-Marketplace-Adds-Agentic-Products-and-AI-Ready-Data-from-Leading-News-Research-and-Market-Data-Providers - 2025-06-03; supports Snowflake AI-ready data partners.
- https://docs.databricks.com/aws/en/marketplace/ - accessed 2026-07-15; supports Databricks Marketplace product.
- https://docs.databricks.com/aws/en/marketplace/get-started-consumer - accessed 2026-07-15; supports Databricks MCP install/governance.
- https://www.databricks.com/blog/mcp-marketplace-brings-real-time-intelligence-agentic-applications - accessed 2026-07-15; supports Databricks MCP marketplace partners.
- https://www.databricks.com/blog/accelerate-ai-development-databricks-discover-govern-and-build-mcp-and-agent-bricks - accessed 2026-07-15; supports Databricks MCP Catalog / Marketplace.
- https://www.nokia.com/newsroom/nokia-acquires-rapid-technology-and-rd-unit-to-strengthen-development-of-network-api-solutions-and-ecosystem/ - 2024-11-13; supports Nokia acquisition of Rapid assets.
- https://techcrunch.com/2024/11/13/nokia-acquires-rapid-the-api-company-once-valued-at-1b/ - 2024-11-13; supports Rapid cautionary details and undisclosed deal terms.
- https://learning.postman.com/docs/postman-ai/mcp-servers/generate - accessed 2026-07-15; supports Postman MCP Generator.
- https://github.com/postmanlabs/postman-mcp-server - accessed 2026-07-15; supports Postman MCP server capabilities.
- https://blog.modelcontextprotocol.io/posts/2025-09-08-mcp-registry-preview/ - 2025-09-08; supports MCP Registry launch.
- https://modelcontextprotocol.io/registry/about.md - accessed 2026-07-15; supports official registry status and contributors.
- https://docs.stripe.com/agentic-commerce/acp - accessed 2026-07-15; supports ACP definition and components.
- https://stripe.com/newsroom/news/stripe-openai-instant-checkout - accessed 2026-07-15; supports Stripe/OpenAI Instant Checkout and ACP launch claims.
- https://openai.com/index/buy-it-in-chatgpt/ - accessed 2026-07-15; supports ChatGPT Instant Checkout and ACP.
- https://www.agenticcommerce.dev/ - accessed 2026-07-15; supports ACP open standard and merchant controls.
- https://www.agenticcommerce.dev/docs/reference/checkout - accessed 2026-07-15; supports ACP checkout technical model.
- https://stripe.com/blog/machine-payments-protocol - 2026-03-18; supports Stripe MPP.
- https://mpp.dev/protocol - accessed 2026-07-15; supports MPP HTTP 402 protocol model.
- https://docs.stripe.com/payments/machine - accessed 2026-07-15; supports Stripe machine payments support for MPP and x402.
- https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications?hs_amp=true - 2026-07-14; supports x402 Foundation operational launch and members.
- https://www.linuxfoundation.org/press/linux-foundation-is-launching-the-x402-foundation-and-welcoming-the-contribution-of-the-x402-protocol - 2026-04-02; supports initial x402 Foundation launch intent and participant list.
- https://docs.x402.org/core-concepts/http-402 - accessed 2026-07-15; supports x402 technical model.
- https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/ - 2026-04-28; supports AP2 donation and v0.2.
- https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/ - 2026-04-28; supports FIDO agentic authentication/payments working groups.
- https://ap2-protocol.org/ - accessed 2026-07-15; supports AP2 docs/status.
- https://developers.google.com/merchant/ucp - accessed 2026-07-15; supports UCP Google guide and compatibility.
- https://shopify.engineering/UCP - 2026-01-11; supports Shopify/Google UCP architecture.
- https://github.com/Universal-Commerce-Protocol/ucp?tab=readme-ov-file - accessed 2026-07-15; supports UCP spec repository.
- https://github.com/wicg/webmonetization/ - accessed 2026-07-15; supports Web Monetization WICG status.
- https://webmonetization.org/developers/link-element/ - accessed 2026-07-15; supports Web Monetization extension / non-native support.
- https://www.w3.org/groups/cg/interledger/ - accessed 2026-07-15; supports Interledger Payments Community Group closure.
