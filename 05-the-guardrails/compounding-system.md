# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning| Founder submissions, investor feedback, funding outcomes |Improved assessment accuracy and matching relevance | Y | active |
|Cross-Domain Transfer |Market intelligence, competitor analysis, geographic and sector data |Better opportunity scoring across industries and regions | Y | active |
| Network Intelligence| Investor interactions, introductions, acceptance/rejection patterns|Stronger investor-founder matching and recommendation quality | Y | active |

**Broken loop identified by partner:** Funding outcome feedback loop

Current assessments and matches improve from submission and engagement data, but the platform may not consistently learn whether introductions resulted in meetings, due diligence, investment offers, or funding.

Without this feedback, the system optimizes for introductions rather than successful funding outcomes.

**Fix plan:** capture post-introduction outcomes

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->
Where knowledge silos:

Investor matching ↔ funding outcomes

The platform may know:
- Which investors were matched.
- Which introductions were accepted.

But not:
- Which introductions led to meetings.
- Which meetings led to due diligence.
- Which opportunities received funding.

Connecting these datasets creates the proprietary outcome-data loop identified as a strategic advantage in the platform strategy.

## Freeze Test
If you froze the AI models for 3 months, would the platform still improve? Yes.

The platform would continue improving through:
- New investor preference data.
- Introduction acceptance/rejection data.
- Funding outcome tracking.
- Founder progression signals.
- Human reviewer corrections.

This indicates the business is compounding through proprietary network and outcome data rather than model improvements alone, which aligns with the strategy's goal of building defensibility beyond the AI model itself.

## Governance Policy

**Scope:** AI-powered startup assessment, investment intelligence, opportunity scoring, and investor-founder matching. The AI may recommend opportunities and investor matches but may not make investment decisions on behalf of users.
**Autonomy boundaries:**
- Can analyse submissions, market signals, competitor data and investor preferences.
- Can recommend investor matches and risk flags.
- Cannot approve funding, reject founders, or represent investment decisions as guarantees.
- Cannot automatically initiate investor introductions when confidence is below approved thresholds
  
**Escalation triggers:**
- Confidence below 50%.
- Potential fraud or manipulated submissions.
- Missing critical financial information.
- Regulatory or compliance concerns.
- Investor disputes or founder challenges to recommendations.

 
**Audit cadence:**
- Weekly monitoring of accuracy and hallucination metrics.
- Monthly golden-dataset evaluation.
- Quarterly bias, matching-quality and outcome-data review.
- Annual governance and model-risk assessment.
  
**Regulatory exposure (EU AI Act / other):**
- Likely limited-risk to high-risk adjacent depending on use of AI in investment recommendations.
- Requires transparency, explainability, auditability and human oversight.
- Investment decisions remain with human investors, not the platform.

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

**Agent 1: Opportunity Assessment Agent**

Can do
- Analyse startup submissions.
- Assess market attractiveness.
- Identify risks and opportunities.

Cannot do
- Approve investments.
- Guarantee funding outcomes.

Approval
- Human reviewer for low-confidence cases.
  

**Agent 2: Investment Intelligence Agent**

Can do
- Research competitors.
- Analyse market, geographic and industry signals.
- Generate assessment evidence.

Cannot do
- Create unsupported facts.
- Override verified source data.

Approval
- Human reviewer for high-risk recommendations.
  

**Agent 3: Investor Matching Agent**

Can do
- Match founders to investors based on preferences, stage and sector.
- Rank likely investor interest.

Cannot do
- Force introductions.
- Commit investors to opportunities.

Approval
- Investors approve or reject introductions.
  

**Agent 4: Governance & Review Agent**

Can do
- Monitor confidence thresholds.
- Trigger escalation.
- Audit recommendations.

Cannot do
- Modify investment outcomes.
- Override human decisions without review.

Approval
- Platform administrator.

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
|Opportunity Assessment Agent |Product Team | H| govern|
|Investment Intelligence Agent |Product Team | M | govern|
|Investor Matching Agent |Product Team | H | govern |
|Pitch Deck / Business Plan Generator|Product Team | L | keep|
|Governance & Review Agent | Risk & Compliance| H | govern|

**Total tools found:** 5
**Tools after triage:** 4
**Estimated hidden spend:** 40% of total AI operating costs (human review, data licensing, governance, monitoring, compliance, and evaluation).
