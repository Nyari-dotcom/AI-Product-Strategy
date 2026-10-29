# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** |Likely reliant on one external LLM provider for idea assessment, market analysis, and pitch generation. | H| Identify the primary model, pricing, data-use terms, rate limits, and alternative providers.|
| **Abstraction** |Model-specific prompts, outputs, and scoring logic could become tightly coupled to one provider. | H |Define a common interface for model calls and standardise outputs into a consistent opportunity-assessment format. |
| **Routing** | No established mechanism yet to switch models by task, cost, quality, or availability.| H |Identify one alternative model and test it on the same assessment tasks as the primary model. |
| **Eval** |No validated benchmark yet for assessment accuracy, investor-match relevance, forecast quality, or bias across providers. | H|Create 20 representative test cases and score model outputs for evidence quality, consistency, cost, and latency. |

## Portability Score
<!-- Ready / Partial / Locked -->

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? -->

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? -->
