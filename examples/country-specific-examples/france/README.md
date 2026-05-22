# PUF Tax Report — France Examples

Example files for French payment reporting (Flux 10, sub-streams 10.2 and 10.4).

## Example Files

| File | Classification | Type | Description |
|------|---------------|------|-------------|
| `PUF_payment_received_on_Invoices_and_transactions.xml` | INCOME | — | Payment reporting for sales. Covers B2B invoice payments with mixed VAT rates (20% + 5.5%) and B2C receipt transaction payments with aggregated daily POS data (20%, 10%, 5.5%). |
| `PUF_FR_payment_income_invoices_and_transactions.xml` | INCOME | — | Same as above with FR naming convention. |
| `PUF_FR_payment_rectification.xml` | INCOME | RECTIFICATION | Rectification of a previously reported payment period. Demonstrates `Type` = RECTIFICATION with `ReportPeriod`. |
| `PUF_FR_UC43_international_b2b_payment.xml` | INCOME | — | UC43: Payment reporting for international B2B services (Flux 10.2). Demonstrates payment received on invoices for services performed in France for EU clients. Includes full and partial payment examples. |

## Key Concepts

- **ClassificationIdentifier**: `INCOME` for sales/revenue reporting, `EXPENSE` for purchase reporting. Only `INCOME` is relevant in France. 
- **PaymentDataType**: `INVOICE` for B2B invoice payments (sub-stream 10.2), `RECEIPTTRANSACTION` for B2C/POS payments (sub-stream 10.4).
- **Type**: `NEW`, `ADDITIONAL`, `CORRECTIVE`, or `RECTIFICATION` — indicates the nature of the submission.
- **ReportPeriod**: The reporting period (`StartDate` / `EndDate`) the payment data covers.
- **Currency**: Must be `EUR` for French payment reporting.
- **IssuerParty**: The declaring party, identified by SIREN (`schemeID="0002"`).
