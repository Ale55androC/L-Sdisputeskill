# 🛡️ Dispute & Chargeback Skill for OpenClaw

Handle payment disputes and chargebacks across **Stripe, PayPal, Square, Wise, and GHL Payments** — with AI-guided evidence gathering, reason code lookup, and response letter drafting.

## What's Inside

- **SKILL.md** — Main workflow: gather details → identify reason code → evidence checklist → draft response → submit
- **references/reason-codes.md** — Full Visa, Mastercard & AMEX reason code tables
- **references/evidence-guide.md** — Evidence checklists per dispute category
- **references/platforms.md** — Platform-specific submission guides, deadlines & fees
- **assets/response-templates/** — Ready-to-customize response letters:
  - Fraud / Unauthorized
  - Product Not Received
  - Cancelled Recurring
  - Not As Described / Defective
  - Pinpoint Scaling master dispute template (13-page PDF + fill-in guide)

## Install

Copy the `dispute-chargeback` folder into your OpenClaw skills directory:

```bash
git clone https://github.com/Ale55androC/L-Sdisputeskill.git
cp -r L-Sdisputeskill ~/.openclaw/workspace/skills/dispute-chargeback
```

Or download the `.skill` file from [Releases](https://github.com/Ale55androC/L-Sdisputeskill/releases) and drop it in your skills folder.

Verify it's installed:

```bash
openclaw skills list
```

You should see `dispute-chargeback` as ✓ ready.

## Usage

Just tell your OpenClaw agent something like:

> "I got a chargeback on Stripe for $2,500. Customer says unauthorized. Help me fight it."

The skill will automatically trigger and walk you through:
1. Identifying the reason code
2. Generating a tailored evidence checklist
3. Drafting a response letter
4. Platform-specific submission instructions

## Key Features

- **Multi-platform** — Stripe, PayPal, Square, Wise, GHL
- **Reason code mapping** — Visa, Mastercard, AMEX with cross-reference table
- **Smart cost-benefit** — Tells you when it's worth fighting vs. accepting
- **Stripe 2025 fees** — Updated for the new $15+$15 dispute fee structure
- **Withdrawal handling** — Always submit evidence even if customer says they'll withdraw

## Built by

[License & Scale](https://licenseandscale.com) — Marketing agency for aesthetic & medical clinics.

---

*Built with [OpenClaw](https://openclaw.ai)*
