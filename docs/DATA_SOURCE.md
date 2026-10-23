# Data source decision

Research date: 2026-10-23 (Australia/Sydney). Status: official metadata reviewed; workbook audit pending.

## Selected source

- Publisher: UCI Machine Learning Repository.
- Dataset: Online Retail II, ID 502.
- Attribution: Chen, D. (2012). Online Retail II [Dataset]. DOI: https://doi.org/10.24432/C5CG6D.
- [Official page](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- [Official archive](https://archive.ics.uci.edu/static/public/502/online%2Bretail%2Bii.zip)
- [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- Published coverage: 2009-12-01 through 2011-12-09; 1,067,371 records, not independent orders.
- Published workbook: `online_retail_II.xlsx`, approximately 43.5 MB.
- Documented concepts: invoice, product, description, quantity, invoice timestamp, unit price in GBP, customer identifier and country.

The original workbook headers and sheet names must be inspected before writing mappings. Website variable names must not be assumed to match the workbook exactly.

## What this supports

The official description identifies C-prefixed invoices as cancellations. This permits a documented sales/cancellation activity analysis. There is no documented original-order reference or settled-refund ledger; strict refund-to-order attribution and cash-refund reconciliation are outside the supported scope.

Missing identifiers and source rows that appear identical require investigation. A transaction-derived customer summary is permitted, but is not independent customer master data.

## Why not reuse Olist

The existing Olist project is useful for order/item/payment joins, but its published tables do not provide the refund ledger required for settled-refund claims. This project instead concentrates on cancellation classification, repeated arrivals, late data and operational maintenance.

Reference: [Olist's dataset page](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

## First-download evidence to capture

- URL, retrieval time, file size and SHA-256.
- Archive members, workbook sheets and actual headers.
- Sheet-level and total row counts, minimum/maximum timestamps.
- Nulls, parsing failures, price precision, quantity signs and invoice-prefix combinations.
- Special stock codes and descriptions; proposed inclusion/adjustment mapping.
- Invoice consistency across dates, countries and customers.
- Repeated source-row fingerprints, reported without silently removing them.

Keep the downloaded original immutable. The row identity for replay will include source workbook hash, sheet and original row number. It is a provenance identity, not a claimed business primary key.

## Honest simulation boundary

Historical transactions are real. Arrival timestamps, delayed deliveries, corrected fixture versions and scheduler dates are project-controlled simulation metadata. Keep injected cases under an explicitly synthetic fixture namespace; never mix them into published real-data business totals.

No live upstream daily feed has been identified. Do not claim that UCI generates new transactions each day.

