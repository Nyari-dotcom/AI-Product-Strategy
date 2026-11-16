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

**Approach:** show uncertainty / tiered confidence / human-in-loop trigger

**High confidence (>90%):**
**Medium confidence (70-90%):**
**Low confidence (<70%):**

**User control surface:**

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | | | |
| Hallucination rate | | | |
| Latency (p95) | | | |
| Drift velocity | | | |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

## Red-Team Findings
*What failure mode did your partner find that you missed?*
