# Three-Axis Vulnerability Diagnostic

## Product
<!-- Name the product you're diagnosing. Real product at your company — not a hypothetical. -->

**Product: CRS Contract Intelligence
**Your Role: Senior Product Manager

---

## Scores

### Contextual Moat — 5/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*
Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?
**Score rationale:**
The solution is embedded within contract creation, review, and approval workflows across procurement, inventory, and operational processes. Users depend on historical contract knowledge, internal policies, approval patterns, and operational relationships that are not easily transferred to another system. While the workflow integration creates meaningful switching costs, organizations could still consider alternatives if a competitor delivers comparable capabilities with minimal migration effort.
**Named attacker (from partner challenge):**
Oracle Hospitality / SAP Contract Management
---

### Data Advantage — 5/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*
Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?
**Score rationale:**
The product benefits from proprietary datasets including historical contracts, pricing benchmarks, inventory commitments, supplier performance records, approval outcomes, and operational metrics. As more contracts are processed, the system continuously improves its ability to identify risks, anomalies, and decision patterns. This accumulated knowledge is unique to the organization and cannot be replicated through public data sources or foundation models alone.
**Named attacker (from partner challenge):**
OpenAI Enterprise with customer-provided data
---

### Platform Exposure — 2/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*
Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?
**Score rationale:**

Major AI platforms can rapidly introduce generic capabilities such as contract summarization, document review, clause extraction, and anomaly detection. The product remains defensible only when it delivers organization-specific intelligence based on proprietary operational data, historical decisions, compliance requirements, and business context rather than relying solely on standard contract analysis features.
**Named attacker (from partner challenge):**
OpenAI / Microsoft Copilot
---

## Top Vulnerability
<!-- One line: what's the single biggest strategic risk? -->
The primary risk is positioning. If the product is viewed as a generic AI contract review tool rather than a contract intelligence platform powered by proprietary operational and business data, large AI providers could quickly commoditize its core features and reduce differentiation.

## Confidence Level
<!-- H / M / L — how confident are you in this bet after the diagnostic? -->
H
أ
