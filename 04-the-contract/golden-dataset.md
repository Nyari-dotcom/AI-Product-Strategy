# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | SaaS startup seeking R2m seed funding, B2B HR platform, ARR R500k, targeting SMEs in South Africa.|Classified as a viable early-stage SaaS opportunity; matched to seed-stage SaaS investors interested in African B2B software. | N | rule / LLM |
| 2 |Founder submits only an idea: "Uber for pets" with no financials, market data, or traction. |Opportunity marked as insufficient information; recommends additional information before investor matching. | Y | rule |
| 3 |FinTech startup with 5,000 active users, R100k MRR, requesting Series A investment. |Assessment identifies mismatch between traction and funding stage; suggests seed/pre-Series A investor profile. | Y | LLM |
| 4 | AgriTech business operating in rural South Africa with strong revenue growth but limited digital presence.|Opportunity recognised as investable despite weak online footprint; matched to impact and AgriTech-focused investors. | N | LLM |
| 5 |Startup claims projected revenue of R500 million within 12 months with no supporting evidence. | Assessment flags unrealistic assumptions and high-risk financial projections; confidence score reduced.| Y | rule |

**Adversarial rows included:** 3
**Coverage gaps identified by partner:**
- International investor matching scenarios.
- Businesses with missing financial data.
- Fraudulent or fabricated submissions.
- Multi-founder/team quality assessment.
- Cross-border regulatory and compliance considerations.
- Repeat founder or serial entrepreneur evaluation.
- Post-introduction funding outcome tracking.

## Confidence UX Design

**Approach:** Tiered confidence + uncertainty disclosure + human-in-the-loop trigger
- The platform should present AI-generated assessments with visible confidence levels.
- High-confidence recommendations can be shown directly, medium-confidence recommendations should include uncertainty indicators and additional context
- Low-confidence recommendations should be escalated for human review before influencing investor decisions.

**High confidence (>90%):**
UI + copy when you're sure:analysis indicates a strong alignment between this opportunity and investor preferences based on market, sector, funding stage, traction and investment history.

Confidence: 94%

Recommended action:

- Show investor matches
- Allow founder introduction request
- Display supporting evidence and key signals
  
**Medium confidence (70-90%):**

What visibly softens? Some signals support this recommendation, but important information is missing or conflicting.

Confidence: 71%

Factors affecting confidence:

- Limited financial history
- Missing market validation data
- Investor preference data incomplete

Recommended action:

- Request additional founder information
- Allow manual investor review
- Highlight assumptions used by the AI
  
**Low confidence (<70%):**
Block • escalate • human queue? The platform cannot reliably assess this opportunity using available information.

Confidence: 42%

Possible causes:

- Missing critical business information
- Contradictory financial inputs
- Unverifiable market claims
- Insufficient evidence for matching

Recommended action:

- Do not generate investor introductions
- Route submission to human review queue
- Request additional documentation before reassessment

**User control surface:**
- Users adjust threshold
- See AI reasoning
- Correct & override
- Corrections → model

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy |≥90% correct opportunity assessments and investor matches |Golden dataset evaluation + human reviewer validation | <85% |
| Hallucination rate |≤5% unsupported claims in market, financial, or competitor analysis |Sampled audit of AI outputs against source data | >10%|
| Latency (p95) |<5 seconds per assessment request |Application monitoring dashboard | >8 seconds|
| Drift velocity |<10% degradation in accuracy month-over-month |Monthly benchmark tests against golden dataset |>15% decline |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

Human-in-the-Loop Escalation Path

Automatic approval
- Confidence >90%
- Sufficient founder data supplied
- Strong investor-match signals
- No anomalies detected

Human review required
- Confidence between 50%-90%
- Missing financial data
- Conflicting business information
- High-value funding requests
- Unusual market or revenue projections

Mandatory human escalation
- Confidence <50%
- Potential fraud indicators
- Unrealistic financial assumptions
- Regulatory or compliance concerns
- Investor complaint or dispute

Escalation flow

AI Assessment → Confidence Check → Risk Check → Human Review Queue → Final Approval/Override → Investor Introduction

This aligns with the platform's principle that AI provides intelligence while humans remain accountable for investment decisions.

## Red-Team Findings
*What failure mode did your partner find that you missed?*
The AI may incorrectly favor startups with strong documentation and polished pitch materials while undervaluing credible opportunities with limited documentation or weaker presentation quality.

Potential impact
- Bias toward well-resourced founders.
- Lower visibility of early-stage or underserved founders.
- Reduced diversity of investment opportunities presented to investors.

Mitigation
- Separate business quality signals from presentation quality signals.
- Weight traction, revenue, market opportunity, and founder evidence more heavily than pitch quality.
- Periodically audit recommendations for investor-matching bias.

This is a particularly relevant failure mode because the platform's success depends on surfacing genuinely promising opportunities rather than simply rewarding founders who produce the best AI-generated content.
