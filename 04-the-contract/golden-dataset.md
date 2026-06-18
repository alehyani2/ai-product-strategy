# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | Contract unit price is 25% above historical benchmark | Flag pricing anomaly and recommend review | N | rule + LLM |
| 2 | Supplier has overlapping active contracts for the same inventory | Detect duplicate commitment and escalate | N | rule |
| 3 | Contract start date is after expiration date | Reject timeline and request correction | N | rule |
| 4 | Supplier performance history shows repeated failures | Increase risk score and recommend escalation | N | rule + LLM |
| 5 | Missing mandatory compliance document | Generate compliance warning and block approval recommendation | N | rule |
| 6 | Historical benchmark unavailable for supplier | State insufficient evidence and avoid assumptions | Y | LLM |
| 7 | Conflicting quantities in contract sections | Highlight inconsistency and route to human review | Y | rule + LLM |
| 8 | OCR extracted corrupted values from scanned contract | Refuse recommendation and request verification | Y | LLM |
| 9 | Contract values and quantities imply unrealistic unit price | Identify inconsistency and request review | N | rule + LLM |
| 10 | Contract values and inventory are within expected ranges | Low-risk recommendation with approval suggestion | N | rule + LLM |

**Adversarial rows included:** __
**Coverage gaps identified by partner:**
- Currency mismatch scenarios
- New suppliers with no historical data
- Cross-contract dependencies
- Seasonal price spikes
- Multi-location contracts

## Confidence UX Design

**Approach:** Tiered confidence + evidence panel + human-in-loop trigger

**High confidence (>90%):** 
Display full recommendation with risk score and supporting evidence. Users can approve, edit, or reject the recommendation.
**Medium confidence (70-90%):**
Use cautious language, highlight key drivers, and request additional information before generating a final recommendation.
**Low confidence (<70%):** 
Do not generate recommendations. Explain missing evidence and escalate to human review.

**User control surface:**
- View evidence and risk drivers
- Override recommendations
- Mark output as accurate or incorrect
- Add comments
- Corrections feed back into the Golden Dataset

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 92% | Weekly evaluation using 300 golden rows | <88% |
| Hallucination rate | <1% | Weekly safety evaluation | >2% |
| Latency (p95) | <2 sec | Continuous monitoring by endpoint | >5 sec |
| Drift velocity | <0.5% per month | Rolling 4-week accuracy trend | >1% per month |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->
Human review is triggered when:

Confidence score is below 70%
Conflicting signals are detected
Required evidence is missing
Compliance or safety flags are raised

Escalation path:

AI Contract Audit

↓

Human Reviewer

↓

Correction

↓

Golden Dataset

↓

Future Evaluations

Reviewer corrections are stored and reused to improve future recommendations.

## Red-Team Findings
*What failure mode did your partner find that you missed?*
Failure mode missed:
The AI may confidently recommend approval when historical benchmarks are unavailable or incomplete.

Mitigation:
Require minimum evidence before generating recommendations and route low-context cases to human review.
