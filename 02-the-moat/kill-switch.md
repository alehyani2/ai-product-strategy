# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | OpenAI GPT-4o as primary AI provider| H | Deploy equivalent model from Anthropic Claude or Google Gemini through the abstraction layer |
| **Abstraction** | All AI calls routed through a unified AI service layer | M | Update provider configuration without changing application code |
| **Routing** | Single-provider routing today with support for future multi-model expansion | M | Enable fallback routing to secondary providers |
| **Eval** | Contract audit test suite validates risk scoring, anomaly detection, and recommendations | L | Run automated evaluation benchmark before switching providers |

## Portability Score
<!-- Ready / Partial / Locked -->
The product is designed with provider portability in mind, but secondary providers and automated routing are not yet fully operational.

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? -->
1- Redirect new traffic to Anthropic Claude or Google Gemini.
2- Prioritize high-value contract audits while optimizing prompt efficiency.
3- Re-run evaluation benchmarks to ensure recommendation quality remains within acceptable thresholds.
4- Complete migration within 48 hours using the abstraction layer.

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? -->
OpenAI can replicate contract analysis capabilities, but cannot easily replicate:

Historical contract intelligence.
Organization-specific risk patterns.
Proprietary pricing benchmarks.
Supplier performance insights.
Approval workflow history.
Operational context accumulated through customer usage.

The defensible advantage is not the model itself, but the proprietary intelligence and workflow integration built around the model.
