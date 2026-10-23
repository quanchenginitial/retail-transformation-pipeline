# Stage 0: guided business-rule checkpoint

Completed: 2026-10-23 (Australia/Sydney).

Outcome: the guided orientation is complete and the project can move to local setup. This records learning evidence, not a certification of SQL, Python or production engineering skills. No source workbook has been audited and no transformation, automated test or scheduled refresh has run.

## Exercise evidence

All amounts below come from constructed teaching examples in the conversation, not UCI business results. The conversation used GBP 35 in sales; the separate GBP 25 example in BUSINESS_RULES_ZH.md remains a valid reference example.

| Topic | Evidence and outcome |
| --- | --- |
| Sales amount | Correctly calculated GBP 35 from the three illustrative sales lines. |
| Invoice count versus units | Reviewed with guidance: three lines contain four units across two distinct sales invoices. Independent confirmation is still pending and will be repeated during SQL practice. |
| Same-day cancellation | Correctly calculated net activity of GBP 25 from sales of GBP 35 and cancellation activity of GBP 10. |
| Activity-date treatment | Correctly assigned GBP 35 to the sales day and negative GBP 10 to the following cancellation day when no new sales occurred. |
| Missing customer identifier | Correctly retained the GBP 20 valid sale while leaving the identified buying-customer count unchanged. |
| Refund evidence | Correctly explained that cancellation/reversal records cannot prove a settled cash refund without payment or refund-settlement evidence. |
| Table grain | The planned date-by-country grain is documented. Independent demonstration will be checked when building the mart. |

## Carry-forward checks

- During SQL practice, independently compute line count, unit count and distinct sales-invoice count for a small sample.
- Before accepting the mart, explain why it has one row per business date and country and verify that key's uniqueness.
- Apply the rules to real source rows only after inspecting the workbook and freezing the inclusion/exclusion mapping.
- Keep stages 1–7 marked planned until their required practical evidence exists.

## Next action

Stage 1A: prepare the local project checkout and identify the Python interpreter. Downloading source data, installing project dependencies and implementing transformations follow as separate guided steps.
