# PUF Tax Report — France Examples

Example files for French payment reporting (Flux 10, sub-streams 10.2 and 10.4).

## Example Files

| File | Classification | Type | Description |
|------|---------------|------|-------------|
| `PUF_payment_received_on_Invoices_and_transactions.xml` | INCOME | — | Payment reporting for sales. Covers B2B invoice payments with mixed VAT rates (20% + 5.5%) and B2C receipt transaction payments with aggregated daily POS data (20%, 10%, 5.5%). |
| `PUF_FR_payment_income_invoices_and_transactions.xml` | INCOME | — | Same as above with FR naming convention. |
| `PUF_FR_payment_rectification.xml` | INCOME | RECTIFICATION | Rectification of a previously reported payment period. Demonstrates `Type` = RECTIFICATION with `ReportPeriod`. |
| `PUF_FR_payment_expense_purchases.xml` | EXPENSE | NEW | Purchase payment reporting. Covers payments made on intra-community (0% reverse charge) and domestic (20%) purchase invoices. |
| `PUF_FR_UC43_international_b2b_payment.xml` | INCOME | — | UC43: Payment reporting for international B2B services (Flux 10.2). Demonstrates payment received on invoices for services performed in France for EU clients. Includes full and partial payment examples. |

## Key Concepts

- **ClassificationIdentifier**: `INCOME` for sales/revenue reporting, `EXPENSE` for purchase reporting.
- **PaymentDataType**: `INVOICE` for B2B invoice payments (sub-stream 10.2), `RECEIPTTRANSACTION` for B2C/POS payments (sub-stream 10.4).
- **Type**: `ADD`, `EDIT`, or `REPLACE_PERIOD` — indicates the nature of the submission. `ADD` adds supplementary data, `EDIT` corrects individual entries, `REPLACE_PERIOD` fully replaces a previously submitted report for the period. (During a transition period `RECTIFICATION` may still be used and should later be changed to `REPLACE_PERIOD`; the transform also accepts the legacy aliases `ADDITIONAL`/`CO` and `CORRECTIVE`/`MO`.)
- **ReportPeriod**: The reporting period (`StartDate` / `EndDate`) the payment data covers.
- **Currency**: Must be `EUR` for French payment reporting.
- **IssuerParty**: The declaring party, identified by SIREN (`schemeID="0002"`).
