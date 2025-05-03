# 🏦 Banking Analytics SQL Project

## Overview
This SQL project aims to analyze customer and account-level banking data to assess loan performance, credit risk, and payment behavior. It includes data integration, feature engineering, and advanced financial metrics to draw insights for decision-making.

---

## Datasets Used

- **`ACCOUNT_PERFORMANCE_D1`**: Contains account-level data including SSN, loan amount, FICO scores, and payment history.
- **`EMPLOYEE_DETAILS_D1`**: Holds company and customer-level data such as industry, revenue, and customer ID.

---

## Key Steps

### 1. Data Integration
- Merged both datasets using `LEFT JOIN` on `ACCOUNT_NUMBER` into a new table `ACCOUNT_PERFORMANCE`.

### 2. Metric Calculations
- **MOB (Month-on-Book)**: Calculated the number of months an account has been active.
- **Delinquency Days**: Assigned `0` for non-defaulted loans; otherwise calculated the days since last payment.
- **FICO Score % Change**: Evaluated how much the current FICO deviates from the origination FICO.
- **Outstanding Balance %**: Determined the ratio of current outstanding balance to the original loan amount.

---

## Planned Enhancements

- **Delinquency Buckets**: Classification based on overdue days:
  | Delinquency Days | Category     |
  |------------------|--------------|
  | 0                | Current      |
  | 1–30             | X Days       |
  | 31–60            | X+1 Days     |
  | 61–90            | X+2 Days     |
  | 91–120           | X+3 Days     |
  | 121–150          | X+4 Days     |
  | 151–180          | X+5 Days     |
  | >180             | Charge Off   |

- **Risk Segmentation**: Based on FICO decline, delinquency buckets, and outstanding balance ratio.

---

## SQL Concepts Used

- `SELECT INTO`
- `JOIN`
- `CASE WHEN` logic
- `DATEDIFF()`
- Arithmetic operations
- Bucket segmentation strategy

---

## Business Impact

- Identify customers at risk of default.
- Measure credit score degradation and recovery.
- Classify loans based on risk level.
- Provide inputs for risk mitigation, collections, and underwriting.

---

