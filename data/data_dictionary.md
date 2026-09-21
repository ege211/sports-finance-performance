# Master Panel Variable Dictionary & Classification Taxonomy

This dictionary provides formal definitions, accounting boundaries, mathematical formulas, and measurement limitations for all 108 variables in `arsenal_master_panel.csv`.

---

## 1. Core Semantic Rules & Accounting Boundaries

1. **`staff_costs` (Total Group Employee Compensation):**
   - Under statutory UK GAAP and IFRS disclosures, employee compensation is reported as `staff_costs`.
   - **`staff_costs` is NOT a player-only wage variable.** It comprises aggregate statutory remuneration across all club employees—playing squad, managerial and coaching staff, academy personnel, medical teams, administrative staff, commercial operations, and statutory employer pension and social security charges.
2. **`permanent_gross_transfer_spend` (Primary Investment Variable):**
   - Gross fixed and guaranteed consideration committed for permanent senior first-team player acquisitions, excluding loan fees, contingent performance add-ons, and sell-on clauses.
3. **Separation of Loan Fees & Contingent Add-Ons:**
   - Temporary loan fees (`loan_fee_spend`, `loan_income`) are accounted for separately from permanent transfer transactions.
   - Potential contractual performance add-ons are audited separately as sensitivity boundaries (`upper_bound_permanent_spend`, `spend_add_on_differential`).
4. **Market Fees vs. Accounting Additions:**
   - Cash/headline transfer market commitments are conceptually distinct from balance sheet player registration capital additions (`player_registration_additions`) and annual accounting amortisation (`player_amortisation`) under IAS 38.
5. **Net Debt Identity:**
   - $\text{net\_debt} = \text{gross\_debt} - \text{cash}$. Cash and cash equivalents are subtracted from total gross borrowings.
6. **Third-Party Analytical Estimates:**
   - Understat metrics ($xG$, $xGA$, $xGD$, $xPTS$, $PPDA$) are model-derived third-party analytical estimates, distinct from official Premier League competition records.
7. **No Composite Performance Indices:**
   - No subjective aggregate sporting performance index is constructed; pitch outcomes are tracked through individual official competition metrics (points, points per game, goal difference, league standing) and structural expected goals metrics.
8. **Strictly Non-Causal & Observational:**
   - All empirical specifications are observational and associational. Correlation coefficients describe statistical co-movement across seasons ($N=10$ contemporaneous; $N=9$ lagged $t \to t+1$) and do not denote causal or predictive mechanisms.

---

## 2. Epistemic Taxonomy & Cell Classification Summary

The master panel comprises exactly 10 annual rows (seasons 2015/16 through 2024/25) $\times$ 108 columns = 1,080 cell observations:
- **Observed Values (`OBSERVED_VALUE`):** 980 cells (90.74%) — Quantitative statutory metrics, competition records, or verified transactions.
- **True Zeros (`TRUE_ZERO`):** 91 cells (8.43%) — Verified historical absence of charges, transactions, or titles.
- **Structural Zeros (`NOT_APPLICABLE`):** 9 cells (0.83%) — Structural non-applicability due to non-qualification (2021/22 European metrics).
- **Missing / Unknown Cells:** Exactly 0 cells (0.00%).

---

## 3. Comprehensive Master Variable Catalog (108 Variables)

### 3.1 Identifiers (2 Variables)

| Variable Name | Statistical Type | Unit | Domain | Epistemic Status | Definition & Alignment |
| :--- | :---: | :---: | :---: | :---: | :--- |
| `season` | Categorical | Text | Identifier | Observed | Competitive football season (`YYYY/YY`, e.g., `2015/16` to `2024/25`). Primary key. |
| `financial_year` | Categorical | Text | Identifier | Observed | Statutory financial reporting year (`FY2016` to `FY2025`), ending 31 May. Aligned to the sporting season. |

---

### 3.2 Financial Module Variables (29 Variables)
*Source: Audited Annual Accounts of Arsenal Holdings Limited filed at Companies House (Deloitte LLP). Standard Unit: GBP Millions (£m).*

| Variable Name | Statistical Type | Unit | Alignment | Epistemic Status | Definition & Measurement Limitations |
| :--- | :---: | :---: | :---: | :---: | :--- |
| `football_turnover` | Direct | £m | FY / Season | Observed | Group football turnover excluding property development operations. Core revenue metric. |
| `total_turnover` | Direct | £m | FY / Season | Observed | Total group revenue, including property sales from legacy Highbury Square developments (FY2016–FY2018). |
| `broadcast_revenue` | Direct | £m | FY / Season | Observed | Statutory broadcast distributions from Premier League, UEFA competitions, and domestic cup rights. |
| `commercial_revenue` | Direct | £m | FY / Season | Observed | Commercial partnerships, stadium naming rights, kit sponsorships, and retail operations. |
| `matchday_revenue` | Direct | £m | FY / Season | Observed | Gate receipts, ticketing, and stadium hospitality across all domestic and European home fixtures. |
| `staff_costs` | Direct | £m | FY / Season | Observed | Total group employee remuneration across playing, technical, commercial, and administrative staff, including social security and pensions. *Limitation: Statutory accounts do not report a player-only wage bill.* |
| `operating_expenses` | Direct | £m | FY / Season | Observed | Group operating expenses excluding staff costs, player amortisation, and impairment charges. |
| `player_amortisation` | Direct | £m | FY / Season | Observed | Annual straight-line amortisation of player registration intangibles over contract duration (Note 10). |
| `player_impairment` | Direct | £m | FY / Season | Observed / Zero | Exceptional impairment charges recognized on player registration carrying values under IAS 36 (£0.0m in 7 seasons; non-zero in FY2020–FY2022). |
| `depreciation` | Direct | £m | FY / Season | Observed | Depreciation on tangible fixed assets (Emirates Stadium, London Colney training facilities). |
| `operating_profit_loss` | Direct | £m | FY / Season | Observed | Group operating profit or loss before player registrations trading and net finance costs. |
| `net_profit_loss` | Direct | £m | FY / Season | Observed | Final statutory profit or loss for the financial period after player trading, financing costs, and taxation. |
| `cash` | Direct | £m | Year-End (31 May) | Observed | Cash, cash equivalents, and short-term deposits held at bank at balance sheet date. |
| `gross_debt` | Direct | £m | Year-End (31 May) | Observed | Total borrowings, including fixed/floating stadium bonds (redeemed 2020) and parent company loan facilities. |
| `net_debt` | Derived | £m | Year-End (31 May) | Derived | Total gross debt minus cash balances: $\text{gross\_debt} - \text{cash}$. Negative value indicates net cash. |
| `net_finance_costs` | Direct | £m | FY / Season | Observed | Finance expense (debt interest payable) minus finance income (interest received). |
| `profit_on_player_disposals` | Direct | £m | FY / Season | Observed | Net accounting gain recognized on player sales: $\text{Gross Proceeds} - \text{Carrying Net Book Value}$. |
| `player_registration_additions` | Direct | £m | FY / Season | Observed | Capitalized additions to player registrations under IAS 38 during the financial period (Note 10). |
| `player_registration_nbv` | Direct | £m | Year-End (31 May) | Observed | Carrying Net Book Value (NBV) of player registrations at balance sheet date after amortisation and impairments. |
| `revenue_growth_pct` | Ratio | % | YoY | Derived | Year-on-year percentage growth rate of football turnover: $(\text{turnover}_t - \text{turnover}_{t-1}) / \text{turnover}_{t-1} \times 100$. |
| `commercial_share_pct` | Ratio | % | FY / Season | Derived | Commercial revenue as a percentage of football turnover. |
| `broadcast_share_pct` | Ratio | % | FY / Season | Derived | Broadcasting revenue as a percentage of football turnover. |
| `matchday_share_pct` | Ratio | % | FY / Season | Derived | Matchday revenue as a percentage of football turnover. Drops near zero in 2020/21 due to COVID-19 spectator shutdown. |
| `wage_to_revenue_pct` | Ratio | % | FY / Season | Derived | Total staff costs as a percentage of football turnover: $\text{staff\_costs} / \text{football\_turnover} \times 100$. |
| `operating_margin_pct` | Ratio | % | FY / Season | Derived | Operating profit/loss as a percentage of football turnover. |
| `net_margin_pct` | Ratio | % | FY / Season | Derived | Net profit/loss as a percentage of football turnover. |
| `net_debt_to_revenue_pct` | Ratio | % | FY / Season | Derived | Net debt as a percentage of football turnover: $\text{net\_debt} / \text{football\_turnover} \times 100$. |
| `net_finance_cost_to_revenue_pct` | Ratio | % | FY / Season | Derived | Net finance costs as a percentage of football turnover. |
| `amortisation_to_revenue_pct` | Ratio | % | FY / Season | Derived | Player amortisation as a percentage of football turnover: $\text{player\_amortisation} / \text{football\_turnover} \times 100$. |

---

### 3.3 Transfer Module Variables (33 Variables)
*Source: Verified Transaction Census (128 transactions) cross-referenced across club statements, Tier-1 journalistic consensus, and secondary market archives. Standard Unit: GBP Millions (£m).*

| Variable Name | Statistical Type | Unit | Epistemic Status | Definition & Measurement Limitations |
| :--- | :---: | :---: | :---: | :--- |
| `permanent_gross_transfer_spend` | Direct | £m | Observed | **[PRIMARY INVESTMENT METRIC]** Agreed gross fixed/guaranteed consideration for permanent senior first-team acquisitions. Excludes loan fees and unvested add-ons. *Limitation: 77.8% of consideration relies on secondary reporting consensus.* |
| `loan_fee_spend` | Direct | £m | Observed / Zero | Fixed fees paid for incoming temporary loan arrangements. Excludes player wage subsidies. |
| `total_transfer_consideration` | Derived | £m | Derived | Comprehensive gross investment: $\text{permanent\_gross\_transfer\_spend} + \text{loan\_fee\_spend}$. |
| `permanent_transfer_income` | Direct | £m | Observed | Fixed consideration received from permanent player departures. |
| `loan_income` | Direct | £m | Observed / Zero | Fees received from outgoing temporary loans. |
| `total_transfer_income` | Derived | £m | Derived | Total transfer receipts: $\text{permanent\_transfer\_income} + \text{loan\_income}$. |
| `permanent_net_transfer_spend` | Derived | £m | Derived | Net permanent outlay: $\text{permanent\_gross\_transfer\_spend} - \text{permanent\_transfer\_income}$. |
| `total_net_transfer_consideration` | Derived | £m | Derived | Net total cash outlay: $\text{total\_transfer\_consideration} - \text{total\_transfer\_income}$. |
| `primary_transfer_spend_to_revenue_pct` | Ratio | % | Derived | Permanent gross transfer spend as a percentage of football turnover. |
| `total_spend_to_revenue_pct` | Ratio | % | Derived | Total transfer consideration as a percentage of football turnover. |
| `permanent_net_spend_to_revenue_pct` | Ratio | % | Derived | Permanent net transfer spend as a percentage of football turnover. |
| `total_net_spend_to_revenue_pct` | Ratio | % | Derived | Total net transfer consideration as a percentage of football turnover. |
| `upper_bound_permanent_spend` | Derived | £m | Derived | Gross permanent spend plus theoretical maximum contingent performance add-ons. |
| `upper_bound_total_consideration` | Derived | £m | Derived | Total consideration plus theoretical maximum contingent performance add-ons. |
| `spend_add_on_differential` | Derived | £m | Derived | Contractual contingent ceiling: $\text{upper\_bound\_total\_consideration} - \text{total\_transfer\_consideration}$. |
| `spend_sensitivity_pct` | Ratio | % | Derived | Potential add-on upside as a percentage of base consideration: $\text{spend\_add\_on\_differential} / \text{total\_transfer\_consideration} \times 100$. |
| `transaction_count` | Count | Count | Observed | Total audited transactions (incoming and outgoing) executed in the season. |
| `incoming_count` | Count | Count | Observed | Total incoming acquisitions (permanent registrations and temporary loans). |
| `outgoing_count` | Count | Count | Observed | Total outgoing departures (permanent sales, contract terminations, loans). |
| `permanent_count` | Count | Count | Observed | Number of permanent transfer transactions (in and out). |
| `loan_count` | Count | Count | Observed / Zero | Number of temporary loan transactions (in and out). |
| `exact_fee_count` | Count | Count | Observed / Zero | Transactions with exact fee disclosures in primary regulatory stock exchange filings. |
| `estimated_fee_count` | Count | Count | Observed | Transactions where consideration is derived from verified multi-source journalistic consensus. |
| `undisclosed_fee_count` | Count | Count | Observed / Zero | Transactions officially announced without numerical consideration that remain undisclosed. |
| `zero_free_count` | Count | Count | Observed | Transactions executed on free transfers, expiry of contract, or mutual termination. |
| `loan_fee_count` | Count | Count | Observed / Zero | Incoming or outgoing loan arrangements involving explicit monetary loan fees. |
| `transaction_coverage_pct` | Ratio | % | Observed | Proportion of identified market activity captured in transaction ledger (100.0%). |
| `numerical_fee_coverage_pct` | Ratio | % | Observed | Proportion of monetary transactions with identified numerical values (100.0%). |
| `exact_fee_coverage_pct` | Ratio | % | Observed / Zero | Transactions verified via primary regulatory documentation as a % of total deals. |
| `primary_fee_coverage_pct` | Ratio | % | Observed / Zero | Transactions backed by official regulatory authority disclosures. |
| `estimated_value_share_pct` | Ratio | % | Observed | Monetary consideration share derived from secondary reporting consensus (77.8% across decade). |
| `classification` | Categorical | Text | Observed | Internal dataset audit classification status (`CORE`). |
| `notes` | Categorical | Text | Observed | Transaction ledger contextual footnotes and window audit commentary. |

---

### 3.4 Sporting Module Variables (43 Variables)
*Source: Official Competition Handbooks (Premier League, The FA, EFL, UEFA) & Third-Party Advanced Analytics (Understat).*

| Variable Name | Statistical Type | Unit | Epistemic Status | Source Authority | Definition & Limitations |
| :--- | :---: | :---: | :---: | :---: | :--- |
| `league_position` | Direct | Rank | Observed | Premier League | Final ranking in the Premier League table (1 to 20). |
| `points` | Direct | Points | Observed | Premier League | Official championship points accumulated over 38 matches. |
| `matches_played` | Count | Matches | Observed | Premier League | Total Premier League matches played (38 in all seasons). |
| `wins` | Count | Matches | Observed | Premier League | Total Premier League victories in the season. |
| `draws` | Count | Matches | Observed | Premier League | Total Premier League draws in the season. |
| `losses` | Count | Matches | Observed | Premier League | Total Premier League defeats in the season. |
| `goals_for` | Count | Goals | Observed | Premier League | Total goals scored in Premier League fixtures. |
| `goals_against` | Count | Goals | Observed | Premier League | Total goals conceded in Premier League fixtures. |
| `goal_difference` | Derived | Goals | Derived | Premier League | Net goal differential: $\text{goals\_for} - \text{goals\_against}$. |
| `ppg` | Ratio | Points/Match | Derived | Premier League | Points per game: $\text{points} / 38$. |
| `fa_cup_stage` | Categorical | Text | Observed | The FA | Furthest round reached in the FA Cup. |
| `fa_cup_matches` | Count | Matches | Observed | The FA | Total FA Cup fixtures contested (including replays). |
| `fa_cup_wins` | Count | Matches | Observed | The FA | FA Cup fixtures won in regulation/extra time. |
| `fa_cup_draws` | Count | Matches | Observed / Zero | The FA | FA Cup fixtures drawn requiring replay or penalties (0 in 9 seasons; 1 in 2015/16). |
| `fa_cup_losses` | Count | Matches | Observed | The FA | FA Cup fixtures lost. |
| `fa_cup_goals_for` | Count | Goals | Observed | The FA | Total FA Cup goals scored. |
| `fa_cup_goals_against` | Count | Goals | Observed | The FA | Total FA Cup goals conceded. |
| `fa_cup_trophy` | Categorical | Binary | Observed / Zero | The FA | Binary title indicator (1 in 2016/17 and 2019/20; 0 in other 8 seasons). |
| `league_cup_stage` | Categorical | Text | Observed | EFL | Furthest round reached in the EFL Cup. |
| `league_cup_matches` | Count | Matches | Observed | EFL | Total League Cup fixtures contested. |
| `league_cup_wins` | Count | Matches | Observed | EFL | League Cup fixtures won. |
| `league_cup_draws` | Count | Matches | Observed / Zero | EFL | League Cup fixtures drawn before penalty shootout. |
| `league_cup_losses` | Count | Matches | Observed | EFL | League Cup fixtures lost. |
| `league_cup_goals_for` | Count | Goals | Observed | EFL | Total League Cup goals scored. |
| `league_cup_goals_against` | Count | Goals | Observed | EFL | Total League Cup goals conceded. |
| `league_cup_trophy` | Categorical | Binary | True Zero | EFL | Binary title indicator (0 across all 10 seasons). |
| `europe_competition` | Categorical | Text | Observed / Struct | UEFA | Continental tournament entered: `Champions League`, `Europa League`, or `None` (2021/22). |
| `europe_stage` | Categorical | Text | Observed / Struct | UEFA | Furthest tournament stage reached (e.g., `Round of 16`, `Runners-up`, `Quarter-finals`, `None`). |
| `europe_matches` | Count | Matches | Observed / Struct | UEFA | Total UEFA fixtures contested (0 in 2021/22 due to non-qualification). |
| `europe_wins` | Count | Matches | Observed / Struct | UEFA | UEFA fixtures won. |
| `europe_draws` | Count | Matches | Observed / Struct | UEFA | UEFA fixtures drawn. |
| `europe_losses` | Count | Matches | Observed / Struct | UEFA | UEFA fixtures lost. |
| `europe_goals_for` | Count | Goals | Observed / Struct | UEFA | Goals scored in UEFA fixtures. |
| `europe_goals_against` | Count | Goals | Observed / Struct | UEFA | Goals conceded in UEFA fixtures. |
| `europe_trophy` | Categorical | Binary | True Zero / Struct | UEFA | Binary continental title indicator (0 in all seasons). |
| `xg` | Direct | Goals | Observed | Understat | Total Expected Goals accumulated over 38 league matches. *Third-party model estimate.* |
| `xga` | Direct | Goals | Observed | Understat | Total Expected Goals Against accumulated over 38 league matches. *Third-party model estimate.* |
| `xgd` | Derived | Goals | Derived | Understat | Net Expected Goal Difference: $\text{xg} - \text{xga}$. |
| `xpts` | Direct | Points | Observed | Understat | Model-derived Expected Points based on match shot-probability distributions. *Third-party estimate.* |
| `ppda` | Ratio | Ratio | Observed | Understat | Passes Allowed Per Defensive Action in opponent 3/5: $\sum \text{Attacking Passes Allowed} / \sum \text{Defensive Actions}$. |
| `possession_pct` | Ratio | % | Observed | Opta / PL | Average ball possession percentage across 38 league fixtures. |
| `shots` | Count | Shots | Observed | Opta / PL | Total goal attempts recorded in Premier League matches. |
| `shots_on_target` | Count | Shots | Observed | Opta / PL | Shots on target requiring goalkeeper save or resulting in a goal. |

---

### 3.5 Contextual Module (1 Variable)

| Variable Name | Statistical Type | Unit | Epistemic Status | Source Authority | Definition |
| :--- | :---: | :---: | :---: | :---: | :--- |
| `covid_disruption_flag` | Categorical | Binary | Observed | Premier League / FA | Binary shock indicator: `1` for the pandemic-disrupted seasons (2019/20 and 2020/21); `0` for all other seasons. Used for sensitivity sub-sample exclusions. |
