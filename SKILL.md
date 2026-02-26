---
name: dispute-chargeback
description: Handle payment dispute and chargeback responses across Stripe, PayPal, Square, Wise, and GHL Payments. Use when a client or user receives a chargeback, payment dispute, or fraud claim and needs to draft a response, gather evidence, or understand the process. Also use for proactive chargeback prevention advice, reason code lookup, and evidence checklist generation. Covers Visa, Mastercard, and AMEX reason codes.
---

# Dispute & Chargeback Response Skill

## Overview

Guide the user through responding to a payment dispute or chargeback. The goal is to maximize win rate by providing platform-specific guidance, evidence checklists, and draft response letters tailored to the exact reason code.

## Workflow

### 1. Gather Dispute Details

Ask for (or extract from context):
- **Platform**: Stripe, PayPal, Square, Wise, GHL, or bank-direct
- **Reason code** (if available) or description of the dispute
- **Amount** and transaction date
- **Product/service type**: physical goods, digital product, recurring subscription, or service
- **What happened**: customer's claim vs. merchant's version

### 2. Identify Reason Code Category

Map the dispute to one of these categories:
- **Fraud / Unauthorized** — customer claims they didn't authorize
- **Product Not Received** — customer claims non-delivery
- **Not As Described / Defective** — quality dispute
- **Duplicate / Incorrect Amount** — processing error
- **Cancelled Recurring** — subscription dispute
- **Credit Not Processed** — refund never received

See `references/reason-codes.md` for full Visa + Mastercard code mappings.

### 3. Generate Evidence Checklist

Based on the category + platform, produce a tailored checklist. See `references/evidence-guide.md` for what evidence to gather per category.

### 4. Draft Response Letter

**For L&S / Pinpoint Scaling clients**: Use the master template at `assets/response-templates/pinpoint-scaling-dispute-template.pdf` with the fill-in guide at `assets/response-templates/pinpoint-template-guide.md`. This is a 13-page structured document covering contract proof, service delivery evidence, CRM screenshots, and no-refund policy. Fill all `[PLACEHOLDER]` fields.

**For other businesses**: Use the generic templates in `assets/response-templates/` as starting points. Customize with:
- Merchant name and transaction details
- Specific evidence references
- Rebuttal addressing the exact reason code
- Professional but firm tone

### 5. Platform-Specific Submission

See `references/platforms.md` for step-by-step submission instructions per platform, including deadlines, fees, and escalation paths.

## Key Rules

- **Deadlines are critical** — always state the response deadline prominently (typically 7-21 days)
- **Tailor evidence to reason code** — generic responses lose. Match evidence to the specific claim
- **Recommend prevention** when the dispute reveals a gap in process
- **Be honest** — never fabricate evidence or coach users to misrepresent facts
- **Consider cost-benefit** — for small amounts, sometimes accepting the chargeback is smarter than fighting (especially with Stripe's $15+$15 dispute fees)
- **Friendly fraud is common** — ~75% of chargebacks are "friendly fraud" (legitimate purchases disputed). Evidence of prior purchases, IP match, and delivery proof wins these
- **Always submit evidence** — even if the customer says they'll withdraw. Many issuers auto-rule against merchants who don't submit evidence, regardless of withdrawal
- **Customer withdrawal ≠ automatic win** — the dispute still follows normal timeline and still counts against your dispute rate
- **One shot** — you can only submit evidence once per dispute. Time it right.

## Quick Reference

| Platform | Dashboard | Deadline | Fee |
|----------|-----------|----------|-----|
| Stripe | Dashboard > Payments > Disputes | 7-21 days | $15 + $15 counter (2025+) |
| PayPal | Resolution Center | 10 days | Standard dispute fee |
| Square | Disputes Dashboard | 7 days | None |
| Wise | Support ticket | Varies | None |
| GHL | Payment provider-dependent | Varies | Provider-dependent |
