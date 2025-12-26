# FIN_MONTHLY_REV_REC_TBL

## Purpose

Accrues a fixed revenue amount evenly by **calendar day** across a contract period and returns **monthly recognised revenue totals**.

This is designed for:
- SaaS revenue recognition
- contract accrual modelling
- month-level movement explanations

---

## Signature

```excel
    FIN_MONTHLY_REV_REC(start_date, end_date, arr)
```
## Inputs

| Argument | Type | Description |
|----------|----------|----------|
| start_date | Date | Contract start date (inclusive) |
| end_date | Date | Contract end date (inclusive) |
| tcv | Number | Total revenue to be accrued across the period |

## Output

A 2-column table with headers:

| Column | Description |
|--------|-------------|
| year_month | Month start date (YYYY-MM-01) |
| sum_value | Revenue recognised in that month |

## Accrual logic
1. Calculate total number of calendar days in the contract
2. Allocate revenue evenly per day
3. Assign each day to its calendar month
4. Sum daily values by month

All calculations are:
- calendar-day based
- linear
- inclusive of both start and end dates

## Example
### Input
| start_date | end_date | tcv |
|------------|----------|-----|
| 2025-01-15 |2025-03-14| 1200 |

### Output
| year_month | sum_value |
|------------|-----------|
| 2025-01-01 | 548.39    |
| 2025-02-01 | 387.10    |  
| 2025-03-01 | 264.52    |

## Assumptions & limitations
- No business-day weighting
- No proration by partial months beyond daily allocation
- Dates must be valid Excel date values
- Returns a table, not a scalar

## Common pitfalls
- Passing text instead of dates
- Expecting fiscal-month logic
- Forgetting the function includes headers
- Using it where a single-month scalar is required

## Related functions

(Future) FIN_MONTHLY_REV_REC_SCALAR