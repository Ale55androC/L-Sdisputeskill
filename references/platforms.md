# Platform-Specific Submission Guide

## Stripe

### Process
1. Go to **Dashboard → Payments → Disputes**
2. Click the disputed payment
3. Review the reason code and deadline
4. Upload evidence in the structured form (Stripe has specific fields per reason code)
5. Write rebuttal in the "Additional information" field
6. Submit — you get ONE chance, no edits after submission

### Key Details
- **Response window**: 7-21 days (varies by card network)
- **Fees**: Dispute received fee ($15) + dispute countered fee ($15, June 2025+). Countered fee refunded if you win. Received fee is NEVER refunded.
- **Enquiries/Retrievals**: Pre-chargeback info requests. Respond to these to prevent escalation — no counter fee.
- **Stripe Radar**: Use for fraud prevention (3D Secure, risk scoring)
- **API**: `stripe.disputes.update()` for programmatic evidence submission
- **Tip**: Stripe's dashboard shows recommended evidence per reason code — follow it

### Dispute Withdrawals (Critical)
Even if the customer agrees to withdraw the dispute with their bank:
- **YOU MUST STILL SUBMIT EVIDENCE** — many issuers treat no evidence as acceptance of liability. You can lose even if the customer withdrew.
- A withdrawn dispute does NOT resolve faster than normal disputes
- A withdrawn dispute still counts against your dispute rate with the card network
- You get ONE evidence submission — wait for customer conversation to play out but don't miss the deadline
- If customer provides withdrawal confirmation (bank email, screenshot), include it in your evidence
- **Cannot refund a disputed charge** until the issuer decides in your favor (can take weeks/months)
- **Late withdrawals**: Customers can withdraw even after you lose, but issuers may take weeks/months to process the reversal

### Evidence Format
- PDF, JPEG, PNG accepted
- Max 4.5MB per file
- Combine multiple docs into single PDF when possible

---

## PayPal

### Process
1. Go to **Resolution Center** (paypal.com/disputes)
2. Respond to the open case within 10 days
3. Provide evidence via the case interface
4. If dispute → claim escalation, PayPal decides

### Key Details
- **Dispute → Claim pipeline**: Buyer opens dispute → 20 days to escalate to claim → PayPal decides
- **Seller Protection**: Covers "unauthorized" + "not received" IF:
  - Transaction marked as eligible
  - Shipped to PayPal-confirmed address
  - Proof of delivery provided (signature for >$750)
- **Dispute fees**: Standard fee applied. Higher rate if dispute ratio >1.5%
- **Tip**: Respond ASAP — buyers can escalate after 4 days of silence

### Evidence Format
- Upload directly in Resolution Center
- Screenshots, PDFs, tracking links accepted

---

## Square

### Process
1. Go to **Square Dashboard → Disputes**
2. Review the dispute details and deadline (7 days)
3. Upload evidence and write response
4. Square's Dispute Resolution Team forwards to card issuer
5. Resolution takes up to 90 days

### Key Details
- **No fees** — Square covers dispute fees
- **Square Risk Manager**: Configure automatic fraud blocks
- **Limitation**: Square no longer reimburses lost disputes
- **Tip**: Square's team is helpful — use their guidance

### Evidence Format
- Upload via Disputes Dashboard
- Standard document formats accepted

---

## Wise (TransferWise)

### Process
1. Contact **Wise Support** via the app or help center
2. Provide transaction details and your version of events
3. Wise coordinates with the recipient's bank
4. Resolution timeline varies (can be weeks)

### Key Details
- **No formal dispute dashboard** — handled via support tickets
- **Limited seller tools** — Wise isn't designed as a merchant processor
- **Bank-to-bank disputes**: Wise may reverse the transfer if the sending bank demands it
- **Tip**: Keep all communication with the counterparty as evidence

---

## GHL (GoHighLevel) Payments

### Process
1. Disputes are handled by the **underlying payment provider** (Stripe Connect, Authorize.net, etc.)
2. Check the provider's dashboard for dispute notifications
3. GHL may surface disputes in the Payments section
4. Submit evidence through the provider's interface

### Key Details
- **GHL is a wrapper** — the real dispute happens at the processor level
- **Stripe Connect**: Most common GHL payment backend — use Stripe's dispute process
- **Tip**: Set up webhook alerts for dispute notifications so you don't miss deadlines

---

## General Timeline

```
Day 0:   Dispute filed by cardholder
Day 1-3: Merchant notified (email + dashboard)
Day 1-7: Gather evidence
Day 7-21: DEADLINE — submit response (varies by network)
Day 21-90: Card network/issuer reviews and decides
Day 90+:  Pre-arbitration (if you want to challenge the decision)
```

## When NOT to Fight

Consider accepting the chargeback when:
- Amount is under $50 and evidence is weak
- Stripe fees ($30 total if you lose) exceed the transaction value
- Customer has a legitimate complaint you missed
- You have no delivery proof or signed agreement
- The chargeback ratio is approaching 1% (Visa/MC monitoring threshold)

Fighting every chargeback can be counterproductive. Win rate across the industry averages ~30-40%. Focus resources on high-value disputes with strong evidence.
