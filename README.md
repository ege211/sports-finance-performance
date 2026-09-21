# sports-finance-performance

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Research Status](https://img.shields.io/badge/Research-Active-success.svg)](#)

> **Longitudinal research on the relationship between financial resources, investment decisions, and sporting performance in professional football.**

---

## 1. Overview & Research Scope

`sports-finance-performance` is an independent sports economics and sports finance research repository designed to investigate how corporate financial capabilities, capital allocation strategies, and squad input structures relate to sporting performance in professional association football.

The repository establishes a structured analytical framework connecting four sequential domain layers:

```text
Financial Resources  ──▶  Investment Decisions  ──▶  Squad / Team Inputs  ──▶  Sporting Performance
```

While the repository provides a general conceptual foundation for sports finance and sporting performance inquiries, all currently completed empirical work is strictly confined to a single-club longitudinal case study.

---

## 2. Current Empirical Case Study: Arsenal FC (2015/16–2024/25)

The inaugural empirical study within this repository is a longitudinal case study examining **Arsenal Football Club** across:

$$\textbf{2015/16–2024/25 (10 completed football seasons)}$$

The study is restricted to the pre-specified period 2015/16–2024/25; 2025/26 is outside the locked research design.

### Core Empirical Focus
The case study analyzes how changes in Arsenal's corporate revenue generation, cash balances, gross and net debt, operating and net profit/loss, and statutory staff costs relate to transfer market expenditures, player registration amortisation, derived financial commitment ratios, and on-pitch sporting outcomes.

### Associational Research Design & Non-Causality
- **Observational Design:** The current project is an **associational longitudinal case study and does not establish causality**. 
- **Methodological Standards:** Due to the observational nature of single-club longitudinal panels, small sample size ($N=10$ annual seasonal observations; $N=9$ for lagged specifications), statutory accounting aggregation (e.g., aggregate staff costs encompassing playing, coaching, and administrative personnel), and unobserved managerial and tactical confounders, all relationships are evaluated strictly through non-causal bivariate and rank associations (Pearson $r$, Spearman $\rho$, Kendall $\tau$).
- **Sensitivity & Robustness:** Findings are subjected to systematic Leave-One-Season-Out (LOO) sensitivity protocols to identify outlier sensitivity and directional stability across external shocks (including the COVID-19 spectator shutdown).

---

## 3. Four-Layer Analytical Framing

The research structure investigates the following empirical dimensions using only variables measured and documented in the frozen master panel:

```text
┌─────────────────────────┐
│   Financial Resources   │  Football Turnover (Matchday, Broadcasting, Commercial),
└────────────┬────────────┘  Cash Balances, Gross & Net Debt, Total Staff Costs,
             │              Operating Profit/Loss, Net Profit/Loss, Net Finance Costs
             ▼
┌─────────────────────────┐
│  Investment Decisions   │  Permanent Gross Transfer Spend, Loan Fees, Total Consideration,
└────────────┬────────────┘  Transfer Income, Net Transfer Spend, Player Registration Additions
             ▼
┌─────────────────────────┐
│   Squad / Team Inputs   │  Wage-to-Revenue Ratio, Player Registration Amortisation,
└────────────┬────────────┘  Player Registration Net Book Value (NBV), Transfer-to-Revenue Ratios,
             │              Transaction Counts (Incoming/Outgoing, Permanent/Loan)
             ▼
┌─────────────────────────┐
│  Sporting Performance   │  Official Results: Points, Points Per Game (PPG), League Position,
└─────────────────────────┘  Goal Difference, Domestic & European Cup Progression;
                             Analytical Metrics: Expected Goals (xG, xGA, xGD), xPTS, PPDA
```

1. **Financial Resources:** Audited statutory financial metrics from Companies House filings capturing football turnover (disaggregated into matchday, broadcasting, and commercial streams), cash balances, gross debt, net debt, net finance costs, operating profit/loss, net profit/loss, and aggregate employee remuneration (`staff_costs`).
2. **Investment Decisions:** Committed capital allocation in the transfer market, covering permanent gross transfer spend, loan fees, total transfer consideration, player disposal income, permanent net transfer spend, and capital additions to player registrations.
3. **Squad / Team Inputs:** Financial allocation intensity and balance sheet squad asset commitments, measured via wage-to-revenue percentage, statutory player registration amortisation, amortisation-to-revenue ratio, player registration net book value (NBV), primary transfer spend-to-revenue percentage, net spend-to-revenue percentage, and transaction activity counts. *(Note: Unmeasured constructs such as subjective squad market valuations, individual player performance contributions, squad rejuvenation indices, or directly measured tactical quality are not part of the dataset).*
4. **Sporting Performance:** Official competition outcomes (Premier League championship points, points per game [PPG], final league finishing position, goal difference, goals for/against, match win/draw/loss counts, FA Cup, League Cup, and European competition progression) alongside third-party advanced analytical metrics from Understat (expected goals [$xG$], expected goals against [$xGA$], expected goal difference [$xGD$], expected points [$xPTS$], passes per defensive action [$PPDA$], and possession percentage).

---

## 4. Data Governance & Provenance Standards

To ensure academic rigor, forensic reproducibility, and intellectual property compliance:

- **No Proprietary Raw Source Documents:** Raw statutory corporate filings, commercial match event feeds, and third-party database dumps are not distributed in this repository.
- **Verifiable Provenance:** Every metric is mapped to verifiable public records, including audited annual financial statements of Arsenal Holdings Limited filed with Companies House (UK), official Premier League competition records, and peer-reviewed sports data conventions.
- **Zero Synthetic Data:** All empirical analyses are conducted strictly on documented historical observations without synthetic interpolation, data simulation, or proxy imputation.

---

## 5. Future Research Directions

A clear distinction is maintained between current completed empirical work and prospective extensions:

- **Current Completed Empirical Work:** Confined strictly to the 10-season single-club associational longitudinal case study of Arsenal FC (2015/16–2024/25) across the locked 108-variable master panel.
- **Future Research Directions:** Prospective extensions for the repository may explore:
  - Applying the four-layer framework to comparative longitudinal case studies of additional European clubs across differing ownership models and financial environments.
  - Cross-sectional panel studies evaluating wage-elasticity versus transfer-elasticity across UEFA Financial Fair Play (FFP) and Financial Sustainability Regulations (FSR) benchmarks.
  - Methodological extensions examining multi-club panels or higher-frequency financial reporting where statutory data availability permits.

*(Note: Multi-club, cross-league, and multi-decade empirical studies have **not** been conducted; they represent prospective future research avenues).*

---

## 6. Repository Architecture

```text
sports-finance-performance/
├── .gitignore             # Comprehensive Python, environment, and data cache exclusions
├── LICENSE                # MIT License
├── README.md              # Research scope, case study framing, and methodology index
├── docs/                  # Methodological documentation, research designs, and preprints
├── src/                   # Econometric analysis and longitudinal panel construction modules
└── tests/                 # Data validation and empirical consistency test suites
```

---

## 7. Citation & Academic Reference

If you reference this framework, methodology, or the longitudinal case study in academic work, please cite:

```bibtex
@misc{cavusoglu2026sportsfinance,
  author       = {Ege Cavusoglu},
  title        = {Sports Finance and Sporting Performance: A Longitudinal Investigation of Arsenal Football Club (2015/16--2024/25)},
  year         = {2026},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/ege211/sports-finance-performance}}
}
```

---

## 8. License

This project is licensed under the terms of the [MIT License](LICENSE).
