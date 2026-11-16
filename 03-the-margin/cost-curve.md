# Cost Curve & Pricing Strategy

## Packaging Decision

### Leader - the feature that they come for:
- AI-powered validation
- Investment opportunity assessment
- Intelligent investor matching

### Filler - nice add, bumps ARPU:
- AI-generated pitch decks
- Executive summaries
- Pitch translations into different languages
- AI-generated business plans

### Killer - sell separately or die:
- Advanced financial simulations
- Deep market intelligence
- Autonomous due diligence agents
- Continuous investment monitoring
------------------------------------------

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) |R21 | Advanced AI reasoning for idea validation, financial analysis and investment assessments.|
| Inference (cascading/triage) |R9 |	Lower-cost AI for categorisation, information extraction and initial screening. |
| Infrastructure |R8 |Cloud hosting, computing, APIs and application maintenance. |
| Data/storage |R12 |Market research, competitor intelligence, geographical data and document storage. |
| Human-in-the-loop |R15 |Manual verification, quality assurance and review of high-risk investment assessments. |
| **Total AI COGS** |R65 |Total estimated monthly operating cost per paying user. |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:** Lower-cost AI model
**Frontier model:** Advanced reasoning AI model
**Routing rule:** 	Simple requests go to the triage model; complex financial, market and investment assessments go to the frontier model.
**Expected cascade ratio:** 70% triage / 30% frontier

## Pricing Model

**Current pricing:** R299/month
**Proposed AI pricing:** R299/month for core functionality
**Model:** Hybrid: subscription + usage-based premium features

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x |COGS rises from R65 to R125. Gross margin drops from 78.3% to 58.2%. |Introduce usage limits, optimise model routing and charge for intensive AI features. |
| Heaviest segment doubles |Assuming usage doubles, COGS increases from R65 to R95. Gross margin drops to 68.2%. |Introduce segment-specific pricing and usage caps. |
| Model provider raises prices 50% |Inference COGS increases from R30 to R45. Total COGS rises to R80. Gross margin drops to 73.2%. | Negotiate pricing, diversify providers and route tasks to cheaper models.|

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

| Metric | Before (traditional SaaS)| After (AI-enabled)|
|----------|-----------------|----------|
|Monthly revenue/user |R299	 | R299	|
| Monthly AI COGS/user |R0 | R65|
| Gross profit/user |R299| R234|
| Gross margin |100%| 78.3%|

**Net margin shift:** The P&P platform generates an estimated R234 gross profit per paying user per month, with a 78.3% gross margin after the modelled costs.
