# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $3.50 | Deep contract analysis and complex reasoning |
| Inference (cascading/triage) | $1.00 | Most requests handled by smaller models |
| Infrastructure | $2.00 | Hosting, monitoring, orchestration |
| Data/storage | $1.00 | Contract history, embeddings, vector storage |
| Human-in-the-loop | $2.00 | Escalations and manual reviews |
| **Total AI COGS** | $9.50 | |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:** GPT-4o-mini
**Frontier model:** Claude Sonnet / GPT-4o
**Routing rule:**
**Expected cascade ratio:** Simple classification, summaries, and low-risk reviews stay on the triage model. High-risk contracts and deep investigations are escalated to the frontier model.

## Pricing Model
80% triage model / 20% frontier model

**Current pricing:** Traditional seat-based SaaS
**Proposed AI pricing:** Base subscription plus metered AI work
**Model:** hybrid 

**Unit of Work:**
Contracts Audited

**Base Fee:**
$30/month

**Usage Fee:**
$0.25 per contract audit

**Estimated Usage:**
80 contract audits per user per month

**Implied Revenue Per User / Month:**
$50

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Margin drops from 81% to 63% | Increase routing efficiency and optimize prompts |
| Heaviest segment doubles | AI costs increase for top users | Introduce premium usage tier |
| Model provider raises prices 50% | COGS increase moderately | Switch workload through abstraction layer to alternative providers |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):** 
$30/user/month

Revenue:
$30/user/month

Cost Structure:
Mostly fixed infrastructure costs

Gross Margin:
80%

Value Capture:
Users pay for software access

**After (AI-enabled):**
Mostly fixed infrastructure costs

After (AI-enabled)

Revenue:
$30 base subscription + usage fees

Cost Structure:
Variable AI inference costs plus infrastructure

Gross Margin:
73%

Value Capture:
Customers pay for completed contract audits and reduced operational risk

**Net margin shift:** 
Margin percentage decreases slightly due to AI costs, but total gross profit and expansion opportunities increase because pricing is aligned with customer outcomes rather than software access alone.
