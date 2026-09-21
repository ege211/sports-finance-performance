# Phase 5B: Pre-Specified Bivariate Association Results

This document reports the empirical bivariate association results across Arsenal Football Club's financial resources, transfer investments, and sporting performance over the 10 completed seasons from **2015/16 through 2024/25**.

In strict adherence to the non-causal research design, all results are presented as observed statistical co-movements. **Correlations do NOT establish causality, predictive relationships, or structural mechanisms.**

---

## 1. Methodological Parameters & Decision Rules

1. **Sample Sizes & Temporal Horizons:**
   - **Contemporaneous Specifications ($t$ vs $t$):** $N = 10$ annual seasonal observations ($df = 8$).
   - **Lagged Specifications ($t \to t+1$):** $N = 9$ season transitions ($df = 7$), pairing financial/investment metrics in year $t$ with pitch performance in year $t+1$.
2. **Correlation Metrics Reported:**
   - **Pearson Correlation ($r$):** Parametric measure of linear co-movement.
   - **Spearman Rank Correlation ($\rho$):** Non-parametric measure of monotonic co-movement resistant to outlier leverage.
   - **Kendall’s Tau-b ($\tau$):** Conservative rank metric assessing pairwise concordance.
   - **Descriptive Reference P-Values:** Two-sided p-values are reported strictly as descriptive markers of sample variability relative to a zero-correlation null hypothesis under small-$N$ bivariate assumptions. **They do not constitute proof of structural economic significance or causal relationships.**
3. **No Subjective Verbal Magnitude Labels:**
   - Qualitative verbal labels (e.g., "weak", "moderate", "strong") were not pre-specified in the research design and are omitted to avoid post-hoc threshold construction. The exact numerical coefficients and signs are reported directly.
4. **Explicit SQ3 / SQ6 Empirical Overlap:**
   - Specifications `PRIMARY-SQ6-16` and `PRIMARY-SQ6-17` evaluate `permanent_gross_transfer_spend_t` against `xgd_t+1` and `xpts_t+1`.
   - These are **mathematically identical calculations** to `PRIMARY-SQ3-05` and `PRIMARY-SQ3-06`.
   - They appear in both questions because SQ3 addresses overall sporting performance while SQ6 focuses specifically on underlying process metrics versus surface outcomes. **They must NOT be counted as separate, independent confirmatory findings.**
5. **`staff_costs` Variable Scope:**
   - `staff_costs` represents total statutory group employee expenditure across all club departments (playing, technical, coaching, medical, administrative, and commercial personnel). It is **not** a player-only wage variable.

---

## 2. Pre-Specified Primary Association Specifications (17 Specifications)

*All 17 specifications evaluate the locked Core Analytical Subset. Lagged specifications evaluate year $t$ predictors against year $t+1$ outcomes.*

| ID | Research Question | Predictor ($t$) | Outcome ($t$ or $t+1$) | $N$ | Pearson $r$ ($p$) | Spearman $\rho$ ($p$) | Kendall $\tau$ ($p$) | Empirical Direction |
| :--- | :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| `PRIMARY-SQ2-01` | SQ2 — Finance $\to$ Investment | `football_turnover` | `permanent_gross_transfer_spend` ($t$) | 10 | +0.3659 (0.2984) | +0.3455 (0.3282) | +0.2444 (0.3711) | Positive |
| `PRIMARY-SQ2-02` | SQ2 — Finance $\to$ Investment | `staff_costs` | `permanent_gross_transfer_spend` ($t$) | 10 | +0.3894 (0.2661) | +0.3091 (0.3848) | +0.2889 (0.2831) | Positive |
| `PRIMARY-SQ2-03` | SQ2 — Finance $\to$ Investment | `net_debt` | `permanent_gross_transfer_spend` ($t$) | 10 | +0.5906 (0.0722) | +0.4182 (0.2291) | +0.3333 (0.2105) | Positive |
| `PRIMARY-SQ3-04` | SQ3 — Investment $\to$ Subsequent Performance | `permanent_gross_transfer_spend` | `ppg` ($t+1$) | 9 | +0.3911 (0.2980) | +0.4500 (0.2242) | +0.3333 (0.2515) | Positive |
| `PRIMARY-SQ3-05` | SQ3 — Investment $\to$ Subsequent Performance | `permanent_gross_transfer_spend` | `xgd` ($t+1$) | 9 | +0.5982 (0.0888) | +0.6500 (0.0581) | +0.5000 (0.0763) | Positive |
| `PRIMARY-SQ3-06` | SQ3 — Investment $\to$ Subsequent Performance | `permanent_gross_transfer_spend` | `xpts` ($t+1$) | 9 | +0.6189 (0.0756) | +0.6667 (0.0499) | +0.5000 (0.0763) | Positive |
| `PRIMARY-SQ4-07` | SQ4 — Staff Costs $\to$ Subsequent Performance | `staff_costs` | `ppg` ($t+1$) | 9 | +0.0516 (0.8951) | -0.0333 (0.9322) | 0.0000 (1.0000) | Divergent Sign |
| `PRIMARY-SQ4-08` | SQ4 — Staff Costs $\to$ Subsequent Performance | `staff_costs` | `xgd` ($t+1$) | 9 | +0.2229 (0.5643) | +0.1833 (0.6368) | +0.1667 (0.6022) | Positive |
| `PRIMARY-SQ4-09` | SQ4 — Staff Costs $\to$ Subsequent Performance | `staff_costs` | `xpts` ($t+1$) | 9 | +0.2618 (0.4962) | +0.2667 (0.4879) | +0.1667 (0.6022) | Positive |
| `PRIMARY-SQ5-10` | SQ5 — Finance $\to$ Subsequent Performance | `football_turnover` | `ppg` ($t+1$) | 9 | +0.2412 (0.5318) | +0.2333 (0.5457) | +0.1667 (0.6022) | Positive |
| `PRIMARY-SQ5-11` | SQ5 — Finance $\to$ Subsequent Performance | `football_turnover` | `xgd` ($t+1$) | 9 | +0.5046 (0.1659) | +0.5000 (0.1705) | +0.3333 (0.2515) | Positive |
| `PRIMARY-SQ5-12` | SQ5 — Finance $\to$ Subsequent Performance | `football_turnover` | `xpts` ($t+1$) | 9 | +0.4851 (0.1856) | +0.5167 (0.1544) | +0.3333 (0.2515) | Positive |
| `PRIMARY-SQ5-13` | SQ5 — Finance $\to$ Subsequent Performance | `net_debt` | `ppg` ($t+1$) | 9 | +0.5663 (0.1119) | +0.4333 (0.2440) | +0.2778 (0.3481) | Positive |
| `PRIMARY-SQ5-14` | SQ5 — Finance $\to$ Subsequent Performance | `net_debt` | `xgd` ($t+1$) | 9 | +0.6320 (0.0678) | +0.6333 (0.0671) | +0.4444 (0.1179) | Positive |
| `PRIMARY-SQ5-15` | SQ5 — Finance $\to$ Subsequent Performance | `net_debt` | `xpts` ($t+1$) | 9 | +0.6937 (0.0382) | +0.6167 (0.0769) | +0.4444 (0.1179) | Positive |
| `PRIMARY-SQ6-16` | SQ6 — Investment Quality / Process | `permanent_gross_transfer_spend` | `xgd` ($t+1$) | 9 | +0.5982 (0.0888) | +0.6500 (0.0581) | +0.5000 (0.0763) | Positive |
| `PRIMARY-SQ6-17` | SQ6 — Investment Quality / Process | `permanent_gross_transfer_spend` | `xpts` ($t+1$) | 9 | +0.6189 (0.0756) | +0.6667 (0.0499) | +0.5000 (0.0763) | Positive |

---

## 3. Pre-Specified Sensitivity Specifications (12 Specifications)

*Testing alternative investment definitions (`permanent_net_transfer_spend`, `primary_transfer_spend_to_revenue_pct`) and league rank outcome (`league_position_t+1`). Note: Lower league rank numbers represent better sporting standing, naturally producing negative correlation signs with positive investment.*

| ID | Specification Focus | Predictor ($t$) | Outcome ($t+1$) | $N$ | Pearson $r$ ($p$) | Spearman $\rho$ ($p$) | Kendall $\tau$ ($p$) | Empirical Direction |
| :--- | :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| `SENSITIVITY-SQ3-01` | Net Spend vs Subsequent PPG | `permanent_net_transfer_spend` | `ppg` | 9 | +0.4050 (0.2796) | +0.3667 (0.3317) | +0.2222 (0.4655) | Positive |
| `SENSITIVITY-SQ3-02` | Net Spend vs Subsequent xGD | `permanent_net_transfer_spend` | `xgd` | 9 | +0.7013 (0.0353) | +0.7500 (0.0199) | +0.6111 (0.0286) | Positive |
| `SENSITIVITY-SQ3-03` | Net Spend vs Subsequent xPTS | `permanent_net_transfer_spend` | `xpts` | 9 | +0.6968 (0.0370) | +0.6833 (0.0424) | +0.6111 (0.0286) | Positive |
| `SENSITIVITY-SQ3-04` | Reinvestment % vs Subsequent PPG | `primary_transfer_spend_to_revenue_pct` | `ppg` | 9 | +0.2978 (0.4364) | +0.2000 (0.6059) | +0.2222 (0.4655) | Positive |
| `SENSITIVITY-SQ3-05` | Reinvestment % vs Subsequent xGD | `primary_transfer_spend_to_revenue_pct` | `xgd` | 9 | +0.4324 (0.2451) | +0.3167 (0.4064) | +0.1667 (0.6022) | Positive |
| `SENSITIVITY-SQ3-06` | Reinvestment % vs Subsequent xPTS | `primary_transfer_spend_to_revenue_pct` | `xpts` | 9 | +0.4699 (0.2018) | +0.3000 (0.4328) | +0.1667 (0.6022) | Positive |
| `SENSITIVITY-RANK-01` | Gross Spend vs Subsequent Rank | `permanent_gross_transfer_spend` | `league_position` | 9 | -0.5495 (0.1254) | -0.6239 (0.0726) | -0.4642 (0.1444) | Inverted (Better Rank) |
| `SENSITIVITY-RANK-02` | Net Spend vs Subsequent Rank | `permanent_net_transfer_spend` | `league_position` | 9 | -0.4945 (0.1760) | -0.4679 (0.2040) | -0.2785 (0.4042) | Inverted (Better Rank) |
| `SENSITIVITY-RANK-03` | Reinvestment % vs Subsequent Rank | `primary_transfer_spend_to_revenue_pct` | `league_position` | 9 | -0.3568 (0.3460) | -0.3206 (0.4003) | -0.3404 (0.2971) | Inverted (Better Rank) |
| `SENSITIVITY-RANK-04` | Staff Costs vs Subsequent Rank | `staff_costs` | `league_position` | 9 | -0.3481 (0.3587) | -0.2513 (0.5143) | -0.1547 (0.6767) | Inverted (Better Rank) |
| `SENSITIVITY-RANK-05` | Turnover vs Subsequent Rank | `football_turnover` | `league_position` | 9 | -0.5294 (0.1427) | -0.3639 (0.3357) | -0.2785 (0.4042) | Inverted (Better Rank) |
| `SENSITIVITY-RANK-06` | Net Debt vs Subsequent Rank | `net_debt` | `league_position` | 9 | -0.6855 (0.0415) | -0.6325 (0.0675) | -0.4642 (0.1444) | Inverted (Better Rank) |

---

## 4. Key Empirical Observations

1. **Finance $\to$ Investment (SQ2):**
   - Football turnover, staff costs, and balance sheet net debt exhibited positive contemporaneous correlations with permanent gross transfer spend ($r \in [+0.3659, +0.5906]$).
2. **Transfer Spend $\to$ Subsequent Performance (SQ3 & SQ6):**
   - Permanent gross transfer spend at year $t$ exhibited a positive association with subsequent points per game at $t+1$ ($r = +0.3911$, $\rho = +0.4500$).
   - Higher correlation coefficients were observed between gross transfer spend and subsequent structural process metrics ($xGD_{t+1}$: $r = +0.5982$; $xPTS_{t+1}$: $r = +0.6189$) than for realized league points per game.
3. **Staff Costs $\to$ Subsequent Performance (SQ4):**
   - Statutory staff costs exhibited a near-zero correlation with subsequent league points per game (`PRIMARY-SQ4-07`: $r = +0.0516$, $\rho = -0.0333$, $\tau = 0.0000$).
   - Associations with subsequent process metrics were positive but lower than for transfer outlays ($r = +0.2229$ for $xGD_{t+1}$; $r = +0.2618$ for $xPTS_{t+1}$).
4. **Turnover & Debt $\to$ Subsequent Performance (SQ5):**
   - Football turnover and net debt both exhibited positive correlations with subsequent pitch metrics, reflecting the co-movement between shareholder-funded squad restructuring, rising revenues from European qualification, and sporting recovery in the latter half of the decade.
