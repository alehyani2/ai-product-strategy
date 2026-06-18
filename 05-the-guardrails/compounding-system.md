# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | User corrections and reviewer feedback | Updated golden dataset and evaluation rules | Y | active |
| Cross-Domain Transfer | Pricing, supplier, and compliance patterns | Better recommendations across contract categories | Y | active |
| Network Intelligence | Aggregated anonymized contract patterns | Improved risk detection and anomaly benchmarks | Y | active |

**Broken loop identified by partner:** 

Supplier review outcomes are not automatically fed back into the evaluation dataset.

**Fix plan:**
Create a feedback pipeline from reviewer decisions into weekly golden dataset updates.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->
Knowledge flow:

Contract reviews → Human corrections → Golden Dataset → Evaluation Pipeline → Future Recommendations

Knowledge silos:

Supplier performance data and contract analytics are owned by different teams and are not fully connected.


## Governance Policy

**Scope:**
This policy covers AI-assisted contract analysis, risk scoring, anomaly detection, and recommendation generation within CRS Contract Intelligence.

Excluded:

Internal analytics tools and external reporting systems.
**Autonomy boundaries:**
Auto

- Risk scoring
- Contract summarization
- Anomaly detection

Human Approval

- Approval recommendations
- Escalations
- Supplier risk classification

 Never Auto

- Contract approval
- Contract rejection
- Financial commitments

**Escalation triggers:**
Human review is required when:

1. Confidence score is below 70%.
2. Conflicting signals are detected.
3. Required evidence is missing.
4. Compliance violations are identified.
5. User explicitly requests human review.

**Audit cadence:**

| Frequency | Review | Owner |
|------------|--------|--------|
| Continuous | Latency and system health | Engineering |
| Weekly | Golden dataset and evaluation metrics | Product Manager |
| Monthly | Drift and hallucination analysis | AI Team |
| Quarterly | Governance and policy review | Product + Compliance |

**Regulatory exposure (EU AI Act / other):**
Applicable regimes:

- GDPR
- EU AI Act
- Internal compliance requirements

Risk tier:

Limited Risk

## Agent Topology

### Contract Analysis Agent

**Can do:**
- Analyze contracts
- Summarize key terms
- Detect pricing anomalies
- Identify missing information

**Cannot do:**
- Approve contracts
- Reject contracts
- Modify contract data

**Approval owner:**
Contract Manager

---

### Risk Assessment Agent

**Can do:**
- Calculate risk scores
- Recommend approve, review, or escalate
- Explain risk factors

**Cannot do:**
- Execute business decisions
- Override human reviewers

**Approval owner:**
Business Owner

---

### Compliance Check Agent

**Can do:**
- Verify required documents
- Detect expired or missing documents
- Flag compliance violations

**Cannot do:**
- Grant policy exceptions
- Mark contracts as compliant without evidence

**Approval owner:**
Compliance Team
