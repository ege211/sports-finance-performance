# Phase 5A: Descriptive Analysis & Longitudinal Trajectory Results

This document presents the descriptive statistics and univariate longitudinal trajectory results for Arsenal Football Club across the ten completed seasons from **2015/16 through 2024/25** ($N=10$).

In strict accordance with the non-causal research design, all metrics reflect observational summaries. No hypothesis tests, regressions, or causal inferences are conducted.

---

## 1. Scope & Dimensional Control

To prevent degrees-of-freedom depletion in a small-$N$ single-club setting, analysis is anchored around the **17-Variable Recommended Core Analytical Subset**, supplemented by 1 reinvestment ratio:

1. **Financial Capacity (5 Core Variables):** `football_turnover`, `staff_costs`, `net_debt`, `operating_profit_loss`, `net_profit_loss`.
2. **Transfer Investment (3 Core Variables):** `permanent_gross_transfer_spend` (primary investment metric for SQ2/SQ3), `permanent_net_transfer_spend`, `permanent_transfer_income`.
3. **Sporting Performance (9 Core Variables):** `points`, `ppg`, `league_position`, `goal_difference`, `xg`, `xga`, `xgd`, `xpts`, `ppda`.
4. **Supplementary Descriptive Metric (1 Variable):** `primary_transfer_spend_to_revenue_pct` (monitoring capital reinvestment intensity).
5. **Contextual Indicator (1 Variable):** `covid_disruption_flag` (1 for 2019/20 and 2020/21; 0 otherwise).

---

## 2. Descriptive Statistics Summary Table ($N=10$)

*All financial and transfer monetary figures in GBP Millions (£m) unless otherwise specified. $N=10$ completed football seasons (2015/16 through 2024/25).*

| Variable Name | Domain | Subset | Mean | Median | Std Dev | Min (Season) | Max (Season) | 10-Year Change | 10-Year % Change | Largest Single YoY Shift |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| `football_turnover` (£m) | Financial | Core | 436.81 | 391.45 | 122.24 | 327.60 (20/21) | 691.00 (24/25) | +340.40 | +97.09% | +151.40 (23/24 vs 22/23) |
| `staff_costs` (£m) | Financial | Core | 245.07 | 233.10 | 51.37 | 195.40 (15/16) | 347.00 (24/25) | +151.60 | +77.58% | +93.10 (23/24 vs 22/23) |
| `net_debt` (£m) | Financial | Core | 134.58 | 154.00 | 120.45 | -12.90 (17/18) | 283.00 (24/25) | +276.50 | N/A (Signed) | +91.20 (20/21 vs 19/20) |
| `operating_profit_loss` (£m) | Financial | Core | -36.55 | -52.00 | 55.40 | -130.40 (20/21) | 43.40 (16/17) | -81.50 | N/A (Signed) | -74.40 (18/19 vs 17/18) |
| `net_profit_loss` (£m) | Financial | Core | -21.55 | -27.65 | 47.03 | -107.30 (20/21) | 56.50 (17/18) | -2.65 | N/A (Signed) | -83.60 (18/19 vs 17/18) |
| `permanent_gross_transfer_spend` (£m) | Transfer | Core | 108.70 | 98.40 | 53.07 | 15.00 (15/16) | 199.30 (23/24) | +73.85 | +492.33% | -110.45 (24/25 vs 23/24) |
| `permanent_net_transfer_spend` (£m) | Transfer | Core | 71.61 | 73.86 | 52.18 | -8.50 (17/18) | 141.70 (22/23) | +5.63 | N/A (Signed) | -116.05 (24/25 vs 23/24) |
| `permanent_transfer_income` (£m) | Transfer | Core | 37.09 | 22.65 | 36.07 | 1.78 (15/16) | 112.80 (17/18) | +68.22 | +3832.58% | -107.90 (18/19 vs 17/18) |
| `primary_transfer_spend_to_revenue_pct` (%) | Transfer | Supp. | 25.88 | 25.12 | 11.82 | 4.28 (15/16) | 40.55 (19/20) | +10.65 | +248.83% | +23.51 (19/20 vs 18/19) |
| `points` (Championship Pts) | Sporting | Core | 71.20 | 70.50 | 10.06 | 56.00 (19/20) | 89.00 (23/24) | +3.00 | +4.23% | +15.00 (22/23 vs 21/22) |
| `ppg` (Points Per Match) | Sporting | Core | 1.87 | 1.85 | 0.26 | 1.47 (19/20) | 2.34 (23/24) | +0.08 | +4.28% | +0.39 (22/23 vs 21/22) |
| `league_position` (Rank) | Sporting | Core | 4.50 | 5.00 | 2.42 | 2.00 (15/16) | 8.00 (19/20) | +0.00 | N/A (Rank) | +3.00 (16/17 vs 15/16) |
| `goal_difference` (Goals) | Sporting | Core | 28.60 | 26.00 | 16.15 | 8.00 (19/20) | 62.00 (23/24) | +6.00 | N/A (Signed) | +32.00 (22/23 vs 21/22) |
| `xg` (Expected Goals) | Sporting | Core | 67.51 | 68.53 | 10.61 | 50.82 (19/20) | 84.39 (23/24) | +0.04 | +0.05% | -13.98 (19/20 vs 18/19) |
| `xga` (Expected Goals Against) | Sporting | Core | 45.28 | 46.11 | 8.55 | 31.78 (23/24) | 57.30 (18/19) | +6.12 | +18.07% | -14.02 (20/21 vs 19/20) |
| `xgd` (Expected Goal Diff) | Sporting | Core | 22.23 | 20.02 | 17.44 | -6.43 (19/20) | 52.61 (23/24) | -6.08 | N/A (Signed) | -23.16 (16/17 vs 15/16) |
| `xpts` (Expected Points) | Sporting | Core | 66.51 | 65.33 | 9.63 | 50.15 (19/20) | 81.94 (23/24) | -4.05 | -5.26% | -14.89 (16/17 vs 15/16) |
| `ppda` (Defensive Ratio) | Sporting | Core | 10.04 | 9.51 | 1.81 | 8.26 (16/17) | 13.64 (20/21) | +0.45 | +5.39% | -3.00 (22/23 vs 21/22) |

---

## 3. Observational Highlights

1. **Top-Line Growth & Payroll Scale:**
   - Football turnover expanded by +97.09% over the decade (£350.60m to £691.00m), heavily influenced by commercial expansion and UEFA Champions League return distributions in 2023/24 and 2024/25.
   - Aggregate staff costs rose by +77.58% (£195.40m to £347.00m). As noted in the data dictionary, `staff_costs` represents total statutory group employee expenditure and cannot be interpreted as player wages alone.
2. **Capital Debt & Operating Balances:**
   - Balance sheet net debt shifted from a net cash position of -£12.90m (2017/18) following major player disposal receipts to a net liability of £283.00m (2024/25) under shareholder debt financing.
   - Operating balances exhibited a structural transition: the club posted operating profits during the first three seasons (FY2016–FY2018), followed by operating deficits across seven consecutive seasons (FY2019–FY2025), troughing during the COVID-disrupted 2020/21 period (-£130.40m).
3. **Transfer Investment Cycles:**
   - Permanent gross transfer spend averaged £108.70m per season. The series opened at £15.00m (2015/16), peaked at £199.30m (2023/24), and settled at £88.85m (2024/25).
4. **Sporting Trajectory:**
   - On-pitch performance followed a distinct U-shaped curve over the decade: starting at 2nd place (71 points, 1.87 PPG in 2015/16), troughing at 8th place (56 points, 1.47 PPG in 2019/20; 61 points in 2020/21), and recovering to 2nd place finishes in 2022/23 (84 points), 2023/24 (89 points), and 2024/25 (74 points).
