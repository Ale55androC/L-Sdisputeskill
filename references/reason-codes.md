# Reason Codes Reference

## Visa Reason Codes

### Fraud
| Code | Name | Description |
|------|------|-------------|
| 10.1 | EMV Liability Shift – Counterfeit | Counterfeit chip card, merchant didn't support EMV |
| 10.2 | EMV Liability Shift – Non-Counterfeit | Non-counterfeit fraud, EMV not used |
| 10.3 | Other Fraud – Card Present | Fraudulent card-present transaction |
| 10.4 | Other Fraud – Card Absent | Unauthorized CNP transaction (most common for online) |
| 10.5 | Visa Fraud Monitoring Program | Flagged by Visa's fraud monitoring |

### Consumer Disputes
| Code | Name | Description |
|------|------|-------------|
| 13.1 | Merchandise/Services Not Received | Customer claims non-delivery |
| 13.2 | Cancelled Recurring Transaction | Recurring charge after cancellation |
| 13.3 | Not As Described / Defective | Product/service doesn't match description |
| 13.6 | Credit Not Processed | Promised refund not issued |
| 13.7 | Cancelled Merchandise/Services | Goods/services cancelled but charged |

### Processing Errors
| Code | Name | Description |
|------|------|-------------|
| 12.1 | Late Presentment | Transaction submitted too late |
| 12.2 | Incorrect Transaction Code | Wrong transaction code used |
| 12.5 | Incorrect Amount | Wrong amount charged |
| 12.6 | Duplicate Processing / Paid by Other Means | Double charge or paid differently |

## Mastercard Reason Codes

### Authorization
| Code | Name | Description |
|------|------|-------------|
| 4808 | Authorization-Related | Improper or missing authorization |

### Cardholder Disputes
| Code | Name | Description |
|------|------|-------------|
| 4841 | Cancelled Recurring Transaction | Subscription cancelled but still charged |
| 4853 | Goods/Services – Multiple Sub-reasons | Not received, not as described, defective, credit not processed |
| 4855 | Goods/Services Not Provided | Non-delivery of goods/services |
| 4860 | Credit Not Processed | Refund not issued |

### Fraud
| Code | Name | Description |
|------|------|-------------|
| 4837 | No Cardholder Authorization | Customer claims unauthorized |
| 4849 | Questionable Merchant Activity | Merchant flagged for suspicious activity |
| 4870 | Chip Liability Shift – Counterfeit | Counterfeit chip card fraud |
| 4871 | Chip Liability Shift – Lost/Stolen | Lost/stolen chip card fraud |

### Point-of-Interaction
| Code | Name | Description |
|------|------|-------------|
| 4831 | Transaction Amount Differs | Amount doesn't match receipt |
| 4834 | Duplicate Processing | Transaction charged twice |

## AMEX Reason Codes

| Code | Name | Description |
|------|------|-------------|
| F10 | Missing Imprint | No card imprint for card-present |
| F24 | No Cardholder Authorization | Unauthorized transaction |
| F29 | Card Not Present | CNP fraud |
| C02 | Credit Not Processed | Refund not issued |
| C04 | Goods/Services Not Received | Non-delivery |
| C05 | Goods/Services Cancelled | Cancelled but charged |
| C08 | Goods/Services Not as Described | Quality/description mismatch |
| C28 | Cancelled Recurring Billing | Subscription cancelled |
| P01 | Unassigned Card Number | Invalid card |
| P03 | Credit Processed as Charge | Refund applied as charge |
| P05 | Incorrect Charge Amount | Wrong amount |

## Mapping Cheat Sheet

| Category | Visa | Mastercard | AMEX |
|----------|------|------------|------|
| Unauthorized/Fraud | 10.4 | 4837 | F29 |
| Not Received | 13.1 | 4855 | C04 |
| Not As Described | 13.3 | 4853 | C08 |
| Cancelled Recurring | 13.2 | 4841 | C28 |
| Credit Not Processed | 13.6 | 4860 | C02 |
| Duplicate Charge | 12.6 | 4834 | P05 |
