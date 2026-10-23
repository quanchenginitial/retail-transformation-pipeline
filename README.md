# Retail Transformation Pipeline

A guided SQL and Python engineering project using historical retail records to build, test and maintain a daily sales and cancellation analysis table.

**Status: stage 0 guided business-rule checkpoint completed on 2026-10-23.** See the [checkpoint record](docs/STAGE_00_CHECKPOINT.md). Source auditing, SQL/Python implementation and scheduled automation have not started. Independent invoice-count and table-grain checks remain part of the practical stages.

## Business purpose

Help an operations analyst review recorded sales, cancellation activity and customer identification coverage by day and country. The first output will be `mart.daily_country_sales`, with one row per business date and country.

Cancellation records are not evidence of settled cash refunds. The proposed net activity measure is not accounting revenue, cash receipts or profit. The rules are project decisions, not verified policies of the original retailer.

## Source and scope

Use [UCI Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii), a historical UK retail dataset attributed to Daqing Chen under CC BY 4.0. See [source notes](docs/DATA_SOURCE.md).

The source is a static historical snapshot. Daily arrivals will be simulated by replaying its real records. Synthetic fault fixtures will be labelled and kept separate from source data. A customer summary derived from transactions will not be described as an independent CRM feed.

## Planned implementation

- Python: source reading, batch manifests, validation, orchestration, structured logs and exports.
- DuckDB SQL: typed staging, business classifications, aggregation and reconciliation.
- pytest: small, independently calculated business examples and failure/recovery cases.
- GitHub: stage branches, pull requests, checks and a daily replay workflow.
- Snowflake: a later, bounded practical exercise to load data, execute a transformation and inspect load/query history.

DuckDB and GitHub Actions alone do not establish cloud data warehouse experience. Snowflake exposure remains planned until practical evidence exists.

## Start here

1. [Learning roadmap (中文)](docs/ROADMAP_ZH.md)
2. [Business rules and target table (中文)](docs/BUSINESS_RULES_ZH.md)
3. [Daily refresh design (中文)](docs/AUTOMATION_DESIGN_ZH.md)
4. [First exercise (中文)](docs/FIRST_STEP_ZH.md)

Each lesson follows: explain one concept → learner performs one action → inspect the result → save evidence → publish the completed stage to GitHub. Implementation will be added through those lessons.

## Completion evidence

The project will be complete when a clean setup can rebuild the table, repeated and late batches behave correctly, failed checks preserve the prior valid output, a scheduled refresh has run successfully, and another person can follow the English runbook and review the change history.

Large source files, databases, environments and credentials will remain outside Git. Reviewed samples and aggregate stage reports may be committed; daily run outputs belong in versioned workflow artifacts.

