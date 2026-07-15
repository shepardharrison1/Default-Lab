# 13 - Sponsored Discovery

**Research date:** 2026-07-15  
**Workstream:** W8 - commoditization, sponsored discovery, and failure modes  
**Posture:** skeptical. Sponsored discovery can create revenue, but it can also destroy the trust that makes licensed data valuable.

---

## 1. Verdict

**Verdict: postponed.**

Sponsored discovery should not be part of the core MVP. It may become a secondary monetization product only after the exchange has:

1. organic quality ranking that buyers trust;
2. source quality floors and evals;
3. explicit disclosure UX in agent responses;
4. buyer controls to disable all sponsored influence;
5. legal review for FTC/native-advertising, EU P2B ranking transparency, antitrust, and sector-specific rules.

It should be **rejected** for regulated/high-stakes workflows where source selection materially affects legal, clinical, financial, safety, or compliance decisions unless paid placement is limited to clearly labeled marketplace merchandising outside the answer path.

---

## 2. Terms

| Model | Definition | Risk |
|---|---|---|
| Sponsored discovery | Publisher pays for visibility in catalog/search/recommendation surfaces | Medium |
| Paid inclusion | Publisher pays to be listed or onboarded faster | Medium; can be acceptable if disclosed |
| Paid ranking | Payment changes rank order among sources | High |
| Referral fee | Exchange earns fee when buyer signs with source | Medium; disclose conflicts |
| Preferred integration | Source is default or promoted partner | Medium-high; needs objective criteria |
| Ads in answers | Answer contains paid message or source influence | Very high; usually reject |

The exchange should separate **commercial merchandising** from **quality routing**. If payment can cause an agent to use a lower-quality source in an answer, trust is compromised.

---

## 3. Trust problem

The exchange's core promise is that licensed data improves agent reliability, legality, and provenance. Sponsored discovery cuts against that promise because it creates a hidden second objective: maximizing exchange or publisher revenue.

Trust risks:

- Agents may cite a sponsored source as if it were selected for quality.
- Buyers may not know price or sponsorship influenced retrieval.
- Publishers may underinvest in quality if payment can buy distribution.
- Users may treat the agent's answer as independent when it is commercially influenced.
- In regulated contexts, paid source preference can look like biased advice or undisclosed advertising.

The bar is higher than ordinary web ads because source selection can become part of the factual answer.

---

## 4. Disclosure and regulatory risk

### 4.1 FTC/native advertising

US FTC endorsement/native-advertising principles require clear and conspicuous disclosure of material connections. If a publisher pays for ranking or preferred placement, that connection is material. A hidden "sponsored source" that influences answer grounding is likely deceptive.

### 4.2 EU P2B ranking transparency

If the exchange is an online intermediation service for business users, EU P2B rules can require transparency about main ranking parameters and paid influence.

### 4.3 Sector-specific conflicts

Sponsored source selection is especially risky in:

- clinical decision support;
- legal research;
- financial advice/research;
- procurement compliance;
- insurance underwriting;
- public-sector/government workflows;
- education/scholarly research.

In those categories, sponsored discovery should be off by default and likely absent from answer routing.

### 4.4 Antitrust and unfair competition

Paid placement can become exclusionary if dominant sources buy all visibility or if the exchange uses undisclosed preferential terms. It also interacts badly with publisher pricing tools: do not combine paid ranking, nonpublic pricing benchmarks, and automated source recommendations.

---

## 5. Quality corruption modes

| Corruption mode | Description | Consequence |
|---|---|---|
| Quality floor erosion | Sponsored source passes despite weak evals | Bad answers, refunds, loss of trust |
| Citation laundering | Sponsored source gets cited to support claims it does not authoritatively cover | Misleading provenance |
| Budget waste | Agent calls paid sponsored source when cheaper sufficient source exists | Buyer churn |
| Source crowd-out | High-quality small source loses visibility to large sponsor | Worse marketplace liquidity |
| Regulatory mismatch | Sponsored source used in regulated workflow | Legal/reputational risk |
| Hidden conflict | Exchange ranks high-margin source as "best" | Buyer trust collapse |
| Feedback loop | Sponsored use generates more usage data and improves apparent reputation | Entrenched low-quality incumbents |
| Publisher gaming | Source creates broad metadata to match more sponsored slots | Relevance degradation |

---

## 6. Acceptable sponsored design

If offered later, sponsored discovery must be constrained.

### 6.1 Non-negotiable rules

1. **No override of quality floors.** A sponsored source must independently pass relevance, freshness, citation, license, latency, and quality thresholds.
2. **No override of policy/budget.** Buyer rules, end-user consent, data residency, and license restrictions always win.
3. **Disclosure travels with response.** The API/MCP response must include `sponsorship.type`, `sponsor`, and `influence`.
4. **Buyer controls.** Buyers can disable sponsored discovery globally, per workflow, per source, or per task.
5. **Separate organic rank from sponsored rank.** Return both where possible.
6. **Auditability.** Every sponsored impression/click/call is logged and exportable.
7. **No sponsored influence in high-risk categories by default.**
8. **No ads in factual answers unless the UI is explicitly an ad surface.**

### 6.2 Quality floor

Before sponsorship can apply, the source must pass:

```text
OrganicEligibility(source, task) =
  LicenseAllowed
  AND PolicyAllowed
  AND Relevance >= threshold
  AND Authority >= threshold
  AND Freshness >= threshold
  AND CitationSupport = true
  AND QualityEvalStatus in ["passed", "provisional_pass"]
  AND RiskPenalty <= max_risk
```

Only then can sponsorship affect **presentation** among eligible sources.

### 6.3 Ranking model

Use a two-list model:

1. **Organic recommendations:** ranked only by quality, fit, cost, and outcome.
2. **Sponsored suggestions:** separate module labeled "Sponsored eligible sources" or "Paid partner source - passed quality screen."

If the product insists on one combined list, sponsored influence must be bounded:

```text
FinalRankScore =
  OrganicScore
  + min(SponsoredBoost, 0.05)
```

And only among sources whose organic scores are already within a narrow band. This prevents payment from moving an inferior source above materially better sources.

### 6.4 Response metadata

Every response influenced by sponsorship should include:

```json
{
  "source_id": "src_example",
  "organic_rank": 2,
  "final_rank": 1,
  "sponsorship": {
    "is_sponsored": true,
    "type": "paid_preferred_listing",
    "sponsor": "Example Data Co.",
    "influence": "placement_boost_within_quality_floor",
    "disclosure_text": "Sponsored source; selected only after passing quality and license checks."
  }
}
```

Agent hosts should be required to display or speak the disclosure when the source is used in a user-facing answer.

---

## 7. Acceptable vs. unacceptable use cases

### 7.1 More acceptable

- Marketplace homepage/category listing: "Featured compliance datasets."
- New source announcement emails to admins.
- Sponsored trial credits where buyer opts in.
- Referral fee disclosed in procurement record.
- Preferred integration badge based on objective certification plus disclosed commercial relationship.

### 7.2 Less acceptable

- Paid rank boost in a clinical answer.
- Legal research answer that silently favors a sponsoring publisher.
- Finance agent selecting a sponsored market-data source despite lower freshness.
- Compliance screening using a sponsored source when a better source is available.
- "Ads in answers" that resemble citations.

---

## 8. Business value vs. strategic cost

### 8.1 Why it is tempting

Sponsored discovery can:

- subsidize source onboarding;
- help new publishers get discovered;
- create revenue before transaction volume scales;
- fund eval/certification programs;
- give the exchange marketplace economics beyond pass-through take rate.

### 8.2 Why it is dangerous

It can:

- make buyers doubt organic ranking;
- invite regulatory scrutiny;
- create conflicts with source-quality claims;
- push the exchange toward ad-tech incentives;
- damage publisher trust if sponsored sources crowd out quality;
- create evidence in litigation that the platform manipulated answers for revenue.

**Skeptical read:** sponsored discovery is appealing precisely because transaction margins may be weak. That is not a good reason to compromise trust before the core exchange has product-market fit.

---

## 9. Product policy recommendation

### MVP

**Postpone.** No sponsored ranking, no paid source preference, no ads in answers.

Allowed:

- neutral catalog listing;
- objective badges such as "verified rights," "passed eval," "supports deletion API";
- manual curation disclosed as editorial/operator recommendation;
- pilots where the source pays onboarding costs, but this must not affect quality ranking.

### Post-MVP

Consider a **secondary sponsored-discovery product** only for low-risk catalog surfaces:

- sponsored category cards;
- sponsored trial credits;
- admin-facing "new source" recommendations;
- referral fee disclosure in procurement workflow.

Do not introduce sponsored routing into agent answers until organic ranking and disclosure infrastructure are mature.

### Regulated workflows

Default to **rejected** in answer path. Use only objective certification and paid onboarding disclosure, not paid source preference.

---

## 10. Sources

- Legal risk file, section 10, on FTC endorsement/native-advertising and EU ranking transparency implications: `11-legal-risks.md`.
- Competitive landscape file, sections on ProRata/Gist, Dappier's ad-supported direction, and sponsored discovery risk: `02-competitive-landscape.md`.
- FTC, Endorsement Guides and native advertising policy context. `https://www.ftc.gov/business-guidance/advertising-marketing/endorsements-influencers-reviews`
- FTC, Native Advertising: A Guide for Businesses. `https://www.ftc.gov/business-guidance/resources/native-advertising-guide-businesses`
- EU Platform-to-Business Regulation overview. `https://digital-strategy.ec.europa.eu/en/policies/platform-business-trading-practices`
- Cloudflare, "Making AI search smarter," 2026-07-01. Used as context for pay-per-use experiments and source monetization. `https://blog.cloudflare.com/making-ai-search-smarter/`
- Model Context Protocol specification, 2025-11-25. Used for response/tool metadata context and consent/security posture. `https://modelcontextprotocol.io/specification/2025-11-25`
