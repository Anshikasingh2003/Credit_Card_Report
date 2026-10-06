# Credit Card Financial Report

**Tools:** SQL (MySQL), Power BI

## Business questions

A credit card business wanted a weekly view of its customers and transactions for 2023:

- How much revenue, interest and transaction amount did the cards generate?
- Which customer groups (job, education, marital status, state) bring the most revenue?
- How do card categories compare?

## Data

| File | Rows | What it holds |
| --- | --- | --- |
| `credit_card.csv` | 10,108 | Weekly card data: card category, fees, credit limit, transaction amount and count, interest earned, utilisation |
| `customer.csv` | 10,108 | Customer details: age, gender, education, marital status, job, income, state, satisfaction score |
| `cc_add.csv`, `cust_add.csv` | 185 each | New week's records appended to the main tables |

## Approach

1. **SQL** (see `Credit Card Sales SQL Query.docx`):
   - `UNION` to combine the main and new-week tables inside CTEs
   - joins between card and customer tables on `Client_Num`
   - `SUM`, `AVG` and `GROUP BY` for KPIs by job, education, marital status and state
   - `ORDER BY ... LIMIT 5` for top states by revenue
2. **Power BI** (`credit card report.pbix`): two report pages, a customer report and a transaction report, with KPIs and breakdowns by week, card category and customer segment.

## Key figures

| KPI | Value |
| --- | --- |
| Customers | 10,293 |
| Total transaction amount | 45.5M |
| Interest earned | 8.0M |
| Weeks covered | 53 (2023) |

## Insights

- Blue cards make up the large majority of accounts (9,214 of 10,108), so most revenue depends on one card category.
- Revenue by job, education and state shows which customer segments to target for premium cards.

## Files

- `Credit Card Sales SQL Query.docx` – SQL queries for every KPI
- `credit card report.pbix` – Power BI report
- `credit_card.csv`, `customer.csv`, `cc_add.csv`, `cust_add.csv` – data
