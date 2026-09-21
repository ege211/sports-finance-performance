# Phase 5C: Robustness & Sensitivity Analysis Results

This document presents the systematic robustness and influence analysis evaluating whether the 17 pre-specified primary bivariate associations identified in Phase 5B are sensitive to individual season pairs, macroeconomic COVID-19 pandemic shocks, or the choice of correlation metric.

In strict adherence to the non-causal research design, all findings are reported as observational sensitivity checks.

---

## 1. Analytical Procedures & Decision Rules

1. **Leave-One-Season-Out (LOO) Analysis:**
   - Contemporaneous specifications ($N=10$): Sequentially omitted each single season to evaluate sensitivity across $N=9$ iterations.
   - Lagged specifications ($N=9$): Sequentially omitted each single $(t \to t+1)$ transition pair to evaluate sensitivity across $N=8$ iterations.
   - Identified minimum and maximum correlation coefficients, calculated LOO ranges, and tested for directional sign changes.
2. **COVID-Excluded Sensitivity:**
   - Evaluated the impact of the exogenous pandemic shock by removing pandemic-disrupted seasons (`covid_disruption_flag == 1`).
   - Contemporaneous: $N=8$ (omitting 2019/20 and 2020/21).
   - Lagged: $N=6$ (omitting the three transitions involving pandemic shock seasons: `2018/19 -> 2019/20`, `2019/20 -> 2020/21`, and `2020/21 -> 2021/22`).
3. **Cross-Method Agreement:**
   - Evaluated directional consistency across parametric linear correlation (Pearson $r$) and non-parametric rank metrics (Spearman $\rho$, Kendall $\tau$).
   - Classified into `ALL_AGREE` (identical directional sign across all three metrics) or `SIGN_REVERSAL` (divergent signs between parametric and non-parametric metrics).

---

## 2. Robustness & Influence Results Table (17 Primary Specifications)

*Lagged specifications evaluate predictor at $t$ against outcome at $t+1$.*

| Specification ID | Predictor ($t$) | Outcome ($t$ or $t+1$) | Baseline Pearson $r$ | Baseline Spearman $\rho$ | Method Agreement | LOO Pearson Min (Omitted) | LOO Pearson Max (Omitted) | LOO Range | LOO Sign Change | COVID-Excluded Pearson $r$ ($N=6/8$) | COVID $\Delta r$ |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| `PRIMARY-SQ2-01` | `football_turnover` | `permanent_gross_transfer_spend` | +0.3659 | +0.3455 | `ALL_AGREE` | +0.0830 (23/24) | +0.6824 (24/25) | 0.5994 | No | +0.4064 ($N=8$) | +0.0405 |
| `PRIMARY-SQ2-02` | `staff_costs` | `permanent_gross_transfer_spend` | +0.3894 | +0.3091 | `ALL_AGREE` | +0.0751 (23/24) | +0.6768 (24/25) | 0.6017 | No | +0.4179 ($N=8$) | +0.0286 |
| `PRIMARY-SQ2-03` | `net_debt` | `permanent_gross_transfer_spend` | +0.5906 | +0.4182 | `ALL_AGREE` | +0.4643 (23/24) | +0.7246 (24/25) | 0.2603 | No | +0.6791 ($N=8$) | +0.0885 |
| `PRIMARY-SQ3-04` | `permanent_gross_transfer_spend` | `ppg` ($t+1$) | +0.3911 | +0.4500 | `ALL_AGREE` | +0.2411 (22/23->23/24) | +0.6244 (15/16->16/17) | 0.3833 | No | +0.3818 ($N=6$) | -0.0093 |
| `PRIMARY-SQ3-05` | `permanent_gross_transfer_spend` | `xgd` ($t+1$) | +0.5982 | +0.6500 | `ALL_AGREE` | +0.5334 (22/23->23/24) | +0.7157 (15/16->16/17) | 0.1822 | No | +0.6392 ($N=6$) | +0.0409 |
| `PRIMARY-SQ3-06` | `permanent_gross_transfer_spend` | `xpts` ($t+1$) | +0.6189 | +0.6667 | `ALL_AGREE` | +0.5560 (22/23->23/24) | +0.7073 (15/16->16/17) | 0.1513 | No | +0.7061 ($N=6$) | +0.0872 |
| `PRIMARY-SQ4-07` | `staff_costs` | `ppg` ($t+1$) | +0.0516 | -0.0333 | `SIGN_REVERSAL` | -0.0936 (23/24->24/25) | +0.1648 (21/22->22/23) | 0.2585 | **Yes** | +0.0924 ($N=6$) | +0.0408 |
| `PRIMARY-SQ4-08` | `staff_costs` | `xgd` ($t+1$) | +0.2229 | +0.1833 | `ALL_AGREE` | -0.0909 (23/24->24/25) | +0.3020 (22/23->23/24) | 0.3929 | **Yes** | +0.3348 ($N=6$) | +0.1120 |
| `PRIMARY-SQ4-09` | `staff_costs` | `xpts` ($t+1$) | +0.2618 | +0.2667 | `ALL_AGREE` | -0.0298 (23/24->24/25) | +0.3420 (21/22->22/23) | 0.3718 | **Yes** | +0.3810 ($N=6$) | +0.1192 |
| `PRIMARY-SQ5-10` | `football_turnover` | `ppg` ($t+1$) | +0.2412 | +0.2333 | `ALL_AGREE` | +0.1228 (22/23->23/24) | +0.3591 (21/22->22/23) | 0.2363 | No | +0.0112 ($N=6$) | -0.2300 |
| `PRIMARY-SQ5-11` | `football_turnover` | `xgd` ($t+1$) | +0.5046 | +0.5000 | `ALL_AGREE` | +0.4692 (19/20->20/21) | +0.5780 (18/19->19/20) | 0.1088 | No | +0.4607 ($N=6$) | -0.0439 |
| `PRIMARY-SQ5-12` | `football_turnover` | `xpts` ($t+1$) | +0.4851 | +0.5167 | `ALL_AGREE` | +0.4449 (19/20->20/21) | +0.5651 (18/19->19/20) | 0.1203 | No | +0.4776 ($N=6$) | -0.0075 |
| `PRIMARY-SQ5-13` | `net_debt` | `ppg` ($t+1$) | +0.5663 | +0.4333 | `ALL_AGREE` | +0.4841 (21/22->22/23) | +0.6632 (15/16->16/17) | 0.1791 | No | +0.6839 ($N=6$) | +0.1176 |
| `PRIMARY-SQ5-14` | `net_debt` | `xgd` ($t+1$) | +0.6320 | +0.6333 | `ALL_AGREE` | +0.5902 (23/24->24/25) | +0.7214 (16/17->17/18) | 0.1312 | No | +0.7734 ($N=6$) | +0.1413 |
| `PRIMARY-SQ5-15` | `net_debt` | `xpts` ($t+1$) | +0.6937 | +0.6167 | `ALL_AGREE` | +0.6593 (23/24->24/25) | +0.7664 (16/17->17/18) | 0.1071 | No | +0.8335 ($N=6$) | +0.1398 |
| `PRIMARY-SQ6-16` | `permanent_gross_transfer_spend` | `xgd` ($t+1$) | +0.5982 | +0.6500 | `ALL_AGREE` | +0.5334 (22/23->23/24) | +0.7157 (15/16->16/17) | 0.1822 | No | +0.6392 ($N=6$) | +0.0409 |
| `PRIMARY-SQ6-17` | `permanent_gross_transfer_spend` | `xpts` ($t+1$) | +0.6189 | +0.6667 | `ALL_AGREE` | +0.5560 (22/23->23/24) | +0.7073 (15/16->16/17) | 0.1513 | No | +0.7061 ($N=6$) | +0.0872 |

---

## 3. Key Robustness Findings

1. **Directional Stability in Transfer Investment (SQ3 / SQ6):**
   - Gross transfer spend associations with subsequent sporting performance maintained strictly positive signs across all LOO iterations:
     - $PPG_{t+1}$: Pearson $r \in [+0.2411, +0.6244]$
     - $xGD_{t+1}$: Pearson $r \in [+0.5334, +0.7157]$
     - $xPTS_{t+1}$: Pearson $r \in [+0.5560, +0.7073]$
   - Under COVID exclusion ($N=6$), coefficients remained stable and positive ($r = +0.3818$, $+0.6392$, $+0.7061$).
2. **Directional Sensitivity in Staff Costs (SQ4):**
   - Statutory staff costs exhibited marked sensitivity to individual observations:
     - `PRIMARY-SQ4-07` (Staff Costs $\to$ Subsequent PPG) crossed zero in LOO iterations (range: $-0.0936$ when omitting `2023/24 -> 2024/25` to $+0.1648$ when omitting `2021/22 -> 2022/23`).
     - It was the **only specification exhibiting directional sign reversal across correlation methods** (Pearson $r = +0.0516$ vs Spearman $\rho = -0.0333$).
     - Associations with subsequent process metrics (`PRIMARY-SQ4-08` and `PRIMARY-SQ4-09`) also crossed zero into negative territory when the final season transition was omitted.
3. **Turnover & Debt Sensitivity (SQ5):**
   - Net debt maintained invariant positive signs across all LOO iterations and COVID exclusion, reflecting the synchronous capital restructuring and sporting ascent in the second half of the decade.
   - Turnover vs subsequent points per game (`PRIMARY-SQ5-10`) experienced a sharp drop in coefficient magnitude under COVID exclusion ($r = +0.2412$ at baseline to $r = +0.0112$ on $N=6$, $\Delta = -0.2300$), though preserving positive sign.
