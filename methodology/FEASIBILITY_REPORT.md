# Phase 1: Comprehensive Feasibility Report & Audit Standard
## Project Arsenal FC: Financial Resources, Investment Decisions, and Sporting Performance (2015/16–2024/25)

---

### Document Overview
This document delivers the final **Feasibility Scorecard** across all 10 core research components and formally answers the **10 Mandatory Audit Standard Questions** required before Phase 1 completion. 

In strict adherence to the **Critical Restriction**, this report does not contain econometrics, master panel scraping, data imputation, regressions, correlations, machine learning models, or empirical conclusions. It establishes whether and under what exact constraints the research project can proceed.

---

## 1. Feasibility Scorecard (10 Research Components)

| Component # | Research Component | Feasibility Status | Core Methodological Justification |
| :---: | :--- | :---: | :--- |
| **1** | **Financial Data** | **FEASIBLE** | Complete, unbroken primary-source coverage across all 10 reporting periods (FY2016–FY2025) via audited Group Accounts of Arsenal Holdings Limited filed at Companies House. Audited by Deloitte LLP without qualification. |
| **2** | **Transfer Data** | **CONDITIONALLY FEASIBLE** | FEASIBLE for aggregate accounting measures (IAS 38 Player Additions, Amortisation, NBV). CONDITIONALLY FEASIBLE for transaction-level market data: club statements routinely cite "undisclosed fees," necessitating secondary market proxies (Transfermarkt) that must remain strictly separate from balance sheet additions under Rule 7. |
| **3** | **Sporting Data (League)** | **FEASIBLE** | 100% complete, verified coverage from official Premier League archives across all 10 seasons (Points, Standings, W/D/L, Goals, PPG, Home/Away splits). |
| **4** | **European Competition Data** | **FEASIBLE** | 100% complete, verified coverage from UEFA official competition records across all seasons. Captures Champions League, Europa League, and the single season of non-participation (2021/22). |
| **5** | **Domestic Cup Data** | **FEASIBLE** | 100% complete coverage from FA and EFL official archives (FA Cup and League Cup). Cup progress provides discrete categorical indicators rather than continuous panel variables. |
| **6** | **Advanced Tactical Metrics** | **CONDITIONALLY FEASIBLE** | FEASIBLE for Understat metrics ($xG$, $xGA$, $xGD$, $xPTS$, $PPDA$) which maintain a single unbroken model from 2014/15 to 2024/25. NOT FEASIBLE for event-level tracking metrics (pressures, progressive passes/carries, SCA) which have missing data for 2015/16 and 2016/17 and are excluded under Rule 3. |
| **7** | **Financial $\to$ Investment Analysis** | **CONDITIONALLY FEASIBLE** | Feasible for directional descriptive evaluation and non-parametric rank association. Small sample size ($N=10$, reducing to $N=9$ with 1-year lag) precludes multivariable OLS regression due to low degrees of freedom ($df \le 6$) and secular revenue trend collinearity. |
| **8** | **Investment $\to$ Performance Analysis** | **CONDITIONALLY FEASIBLE** | Feasible using lagged non-parametric tests (e.g., Spearman's $\rho$ between additions/amortisation at $t$ and points at $t+1$). Requires explicit recognition that transfer additions do not immediately translate into pitch minutes due to squad integration and injury variance. |
| **9** | **Financial $\to$ Performance Analysis** | **CONDITIONALLY FEASIBLE** | Feasible for bivariate rank association (Staff Costs vs Points). High collinearity between wage growth and revenue inflation across the Premier League prevents multi-parameter econometric identification in an $N=10$ single-club sample. |
| **10** | **Structural Mechanism Analysis** | **CONDITIONALLY FEASIBLE** | Feasible strictly as a descriptive conceptual framework tracing: $\text{Financial Capacity} \to \text{Wage/Additions Spend} \to \text{Squad Inputs} \to \text{Understat xGD} \to \text{League Points}$. Cannot be statistically proven via formal causal mediation modeling due to lack of a counterfactual control group and small sample size. |

---

## 2. Explicit Audit Standard: The 10 Critical Questions

### Question 1: Which variables have reliable primary-source coverage across the full decade?
* **Financial Variables (Audited Primary Source: Companies House — Arsenal Holdings Limited):**
  - Total Turnover, Football Turnover, Broadcast Revenue, Commercial Revenue, Matchday Revenue.
  - Total Staff Costs (Wages, Salaries, Social Security, Pensions).
  - Operating Expenses, Player Registration Amortisation, Player Impairment Charges, Depreciation.
  - Operating Profit/Loss before player trading, Operating Profit/Loss after player trading, Net Profit/Loss after tax.
  - Cash and Cash Equivalents, Gross Debt / Borrowings, Net Debt, Net Finance Costs.
  - Profit on Disposal of Player Registrations, Capitalized Player Registration Additions (IAS 38), Net Book Value of Registrations.
* **Sporting Variables (Official Primary Source: Premier League, UEFA, The FA, EFL):**
  - Premier League: Final Position, Points, Wins, Draws, Losses, Goals For, Goals Against, Goal Difference, Points Per Game.
  - European: Competition Tier (UCL/UEL/None), Stage Reached, Matches Played, Match Record, UEFA Club Coefficient Points.
  - Domestic Cups: FA Cup Stage Reached, FA Cup Trophy Won, EFL Cup Stage Reached, Domestic Cup Matches Played.
* **Contextual Variables (Official Primary Source: Club Announcements & Regulatory Filings):**
  - Manager / Head Coach Identity, In-season managerial dismissals, Corporate ownership structure (NEX Exchange public listing vs KSE private ownership), Stadium debt refinancing status.

### Question 2: Which variables have only partial coverage?
* **Event-Level Tactical Tracking Metrics:**
  - FBref / StatsBomb tracking metrics: Pressures, Pressure Regains, Progressive Passes, Progressive Carries, Shot-Creating Actions ($SCA$), and Goal-Creating Actions ($GCA$). Standardized public coverage only begins in **2017/18**. Coverage across the 10-season panel is only **80%** (8 out of 10 seasons).
* **Territorial Spatial Metrics:**
  - Field Tilt %: Proprietary Opta metric with irregular public availability prior to 2019/20 (~60% coverage).
* **Squad-Specific Player Wage Breakdown:**
  - Disaggregated individual player wage figures are absent from statutory accounts (0% audited coverage).

### Question 3: Which variables are definitionally inconsistent?
* **Debt / Borrowings Structure:**
  - Prior to July 2020, Arsenal's borrowings consisted of publicly listed, amortising fixed-rate and floating-rate stadium bonds with mandatory debt service reserve accounts. In July 2020, these bonds were fully redeemed and replaced by an internal floating-rate loan facility from parent company KSE UK INC. While the accounting definition of gross debt remains valid, the economic nature of the liability shifted from public bondholder obligations to parent shareholder financing.
* **Property Development Turnover:**
  - In FY2016–FY2018, Total Turnover included revenue from residential property developments (Highbury Square / Queensland Road). In FY2019–FY2025, property revenue became zero. To ensure definitional consistency, **Football Turnover** must be utilized rather than unadjusted Total Turnover.
* **UEFA Competition Format (2024/25):**
  - The transition from the 32-team group stage (6 matches) to the 36-team single league phase (8 matches) in 2024/25 altered the denominator for match counting and coefficient point distribution.

### Question 4: Which variables require secondary sources?
* **Market Transfer Fees:** Contractual transfer transaction fees (headline purchase/sale prices) require established secondary databases (*Transfermarkt*, verified by *BBC Sport* reports). Official club announcements almost universally withhold fee amounts under "undisclosed fee" provisions.
* **Advanced Tactical Metrics:** Expected Goals ($xG$), Expected Goals Against ($xGA$), and Passes Per Defensive Action ($PPDA$) are not published by statutory football authorities and require established third-party analytics sources (*Understat*).

### Question 5: Which variables should be excluded?
Under **Rule 2** and **Rule 3**, the following variables are **strictly excluded** from the core longitudinal analysis:
1. **Specific Player Wages:** Excluded because individual salaries are not disclosed in audited accounts. Using unverified secondary salary websites (e.g., Capology, Spotrac) violates Rule 1 and Rule 2.
2. **Pressures, Progressive Passes, Progressive Carries, SCA, GCA:** Excluded because they lack coverage for 2015/16 and 2016/17, violating Rule 3 (*"NO COMPARABLE HISTORICAL COVERAGE = EXCLUDE THE VARIABLE"*).
3. **Field Tilt %:** Excluded due to proprietary definition shifts and discontinuous historical records.
4. **Composite "Success Indices":** Excluded under Phase 1 guidelines prohibiting the arbitrary blending of domestic and European cup competitions into synthetic numerical scores.

### Question 6: What financial/football season alignment problems exist?
* **The May 31 Cutoff vs May Season Completion:**
  - In standard years (8 out of 10 seasons), the football season concludes in mid-to-late May, preceding the 31 May accounting year-end. Alignment is **EXACT**.
* **The COVID-19 Disruption Shock (FY2020 & FY21):**
  - In the **2019/20 season**, the pandemic caused the suspension of fixtures from 13 March 2020 to 17 June 2020. The Premier League season finished on **26 July 2020**, and the FA Cup Final was played on **1 August 2020**. 
  - Consequently, **10 competitive matches** of the 2019/20 season fell outside the FY2020 financial year (ended 31 May 2020).
  - Under IFRS 15 revenue recognition principles, **£34 million of broadcasting revenue** attributable to the 2019/20 season was deferred into the FY2021 financial accounts.
  - In FY2021, matches were played behind closed doors, causing matchday revenue to collapse to £3.8m. Meanwhile, broadcast revenue appeared artificially elevated (£184.4m) because it contained the deferred £34m from 2019/20.
  - *Analytical Consequence:* Naively pairing FY20 financial figures with 2019/20 sporting performance underestimates revenue generated by that sporting campaign, while pairing FY21 figures overstates television distributions relative to in-season performance.

### Question 7: What transfer-data limitations exist?
1. **The Disclosure Barrier:** British football clubs are under no statutory obligation to disclose individual transfer consideration. Arsenal's official statements designate almost all incoming and outgoing transfer fees as *"undisclosed."*
2. **Transfermarkt Discrepancies:** Secondary transfer databases aggregate media rumors, rely on unverified foreign currency conversions, and frequently blend guaranteed base fees with contingent performance-related add-ons (e.g., appearances, Champions League qualification, international caps).
3. **Inability to Reconcile to Player Additions:** Balance-sheet player additions under IAS 38 include agent intermediary commissions, signing bonuses, and statutory legal acquisition fees, while excluding VAT and factoring in payment discounting. Reconciling a single player's market fee to the audited financial accounts is methodologically impossible at an individual player level. Both concepts must remain in separate analytical silos (Rule 7).

### Question 8: Which advanced metrics are genuinely comparable?
* **Understat Metrics ($xG$, $xGA$, $xGD$, $xPTS$, $PPDA$):**
  - **Genuinely Comparable.** Understat has maintained a consistent proprietary machine-learning model applied retrospectively and prospectively across all Premier League matches from 2014/15 through 2024/25. The mathematical definitions and data collection protocols have remained stable across all 10 seasons of the research window.
* **Basic Match Events (Possession %, Shots, Shots on Target):**
  - **Genuinely Comparable.** Opta's baseline match-event definitions for shots, shots on target, and pass-completion ratios have remained consistent across the entire 10-year period.

### Question 9: Can the proposed lagged analyses actually be constructed?
* **Yes, but under severe sample-size restrictions:**
  - A 1-year lag ($\text{Variable}_t \to \text{Variable}_{t+1}$) reduces the sample from $N=10$ to **$N=9$**.
  - A 2-year lag ($\text{Variable}_t \to \text{Variable}_{t+2}$) reduces the sample to **$N=8$**.
  - With $N=9$, multivariable regression is econometrically illegitimate. However, **bivariate rank-order correlations (Spearman’s $\rho$, Kendall’s $\tau$)** and **directional co-movement analyses** are empirically viable.
  - Feasible Lag Specifications:
    1. $\text{Football Turnover}_t \longrightarrow \text{Player Additions}_{t+1}$ ($N=9$)
    2. $\text{Player Additions}_t \longrightarrow \text{Points}_{t+1}$ and $xGD_{t+1}$ ($N=9$)
    3. $\text{Staff Costs}_t \longrightarrow \text{Points}_{t+1}$ ($N=9$)

### Question 10: What would make the research invalid or misleading?
The following practices would fundamentally invalidate the research and are strictly barred:
1. **Asserting Causal Directionality:** Claiming that higher transfer spending *"caused"* higher point totals, ignoring manager quality, opponent strength, injury shocks, tactical innovations, and match randomness.
2. **Conflating Accounting Additions with Market Transfer Fees:** Treating Transfermarkt gross spend as identical to audited IAS 38 player additions.
3. **Running Multivariable OLS Regressions on $N=10$:** Reporting $p$-values and $R^2$ statistics from regression models with 3+ parameters, which produces severe overfitting and false precision.
4. **Ignoring COVID-19 Revenue Timing Deferrals:** Failing to account for the £34m broadcast revenue shift between FY20 and FY21.
5. **Backfilling Broken Advanced Metrics:** Interpolating or synthesizing pressures or progressive carries for 2015/16 and 2016/17.
6. **Constructing Arbitrary Composite Indices:** Creating subjective weighted formulas (e.g., combining FA Cup runs and league points into a single "success score") without empirical justification.

---

## 3. Methodological Boundary Mandate for Subsequent Phases
To preserve scientific validity under the zero-trust standard:
* Any subsequent empirical work must use **association/relationship language**.
* Primary quantitative analysis must center on **non-parametric correlation (Spearman/Kendall)**, **directional elasticity**, and **inter-temporal structural narrative tracking**.
* All final observations must carry full **atomic provenance** back to Companies House filings or official competition records.
