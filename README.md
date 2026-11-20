# Finova360 - Corporate Finance Intelligence

Finova360 is a corporate finance analytics project built around a fictional multinational technology company. The project aims to transform synthetic financial data into meaningful business insights using Microsoft Power BI, Power Query, data modelling, and DAX. All financial records are synthetic and designed to simulate real-world corporate finance operations.

The seven CSV datasets have been organised under `Dataset/Raw/` and successfully imported into Power BI's Power Query Editor. Data cleaning, transformation, data modelling, and report development are planned as subsequent project stages.

## Tables

The project includes the following synthetic datasets, organised under `Dataset/Raw/`:

- `FactTransactions.csv`: 180,000 ledger-style financial transactions covering 2023-01-01 through 2025-12-31.
- `FactBudget.csv`: Monthly approved budget records by entity, department, account, and month.
- `FactForecast.csv`: Monthly rolling financial forecast records.
- `DimDepartment.csv`: Department information, including department names and divisions.
- `DimAccount.csv`: Chart of accounts containing account categories, financial statement classifications, and profit-and-loss signs.
- `DimEntity.csv`: Fictional legal entities, countries, and local currencies.
- `DimCounterparty.csv`: Synthetic customers and vendors.

## Important fields

- `AmountUSD`: Transaction amount converted to USD using fixed illustrative exchange rates.
- `SignedAmountUSD`: Revenue and positive non-operating income are positive; expenses are negative.
- `PLSign`: `1` for income accounts and `-1` for expense accounts.
- `Status`: Transaction posting status (Posted, Pending, or Reversed). Posted transactions will be used for actual financial reporting.
- `FiscalMonth`: Month identifier formatted as `YYYY-MM`.

## Suggested Power BI model

Implement a star schema with dimension tables connected to the relevant fact tables. Create a dedicated Date table in Power BI and establish relationships with `FactTransactions[TransactionDate]` and the month-start date fields in the budget and forecast tables. Avoid direct relationships between fact tables.

## Suggested report pages

1. Executive Overview: Revenue, expenses, operating profit, and key financial performance indicators.
2. Budget vs Actual: Monthly financial performance, budget variance, and comparisons by department, entity, and account category.
3. Expense Analysis: Expense breakdown by category, department, vendor, and cost drivers.
4. Forecast & Trends: Actual versus forecast performance and monthly financial trends.
5. Transaction Details: Detailed financial transaction records with drill-through functionality for further analysis.

## Caveats

This project uses simulated financial data for educational and portfolio purposes. It does not represent audited financial information or actual company financial performance. FX rates are fixed illustrative rates, and synthetic financial distributions may not reconcile like a real ERP export without additional modelling choices.
