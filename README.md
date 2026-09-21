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

While the repository provides a broader conceptual foundation for sports finance and performance research, the current empirical project focuses on a single club over an intensive decade.

---

## 2. Current Empirical Case Study: Arsenal FC (2015/16–2024/25)

The inaugural empirical study within this repository is a longitudinal case study examining **Arsenal Football Club** across:

$$\textbf{2015/16–2024/25 (10 completed football seasons)}$$

The ongoing 2025/26 season is strictly excluded to prevent partial-year survivorship distortions and incomplete financial reporting.

### Core Empirical Focus
The case study analyzes how changes in Arsenal's corporate revenue generation, operating cash flows, debt facilities, and staff payroll commitments relate to transfer market activity, player registration amortisation, squad market valuation, and on-pitch sporting outcomes.

### Associational Research Design & Non-Causality
- **Observational Design:** The current project is an **associational longitudinal case study and does not establish causality**. 
- **Methodological Standards:** Due to the observational nature of single-club longitudinal panels, small sample size ($N=10$ annual seasonal observations; $N=9$ for lagged specifications), statutory accounting aggregation (e.g., aggregate staff costs encompassing playing, coaching, and administrative personnel), and unobserved managerial and tactical confounders, all relationships are evaluated strictly through non-causal bivariate and rank associations (Pearson $r$, Spearman $\rho$, Kendall $\tau$).
- **Sensitivity & Robustness:** Findings are subjected to systematic Leave-One-Season-Out (LOO) sensitivity protocols to identify outlier sensitivity and directional stability across external shocks (including the COVID-19 spectator shutdown).

---

## 3. Four-Layer Analytical Framing

The research structure investigates the following empirical dimensions:

```text
┌─────────────────────────┐
│   Financial Resources   │  Turnover (Matchday, Broadcasting, Commercial), Operating Cash Flow,
└────────────┬────────────┘  Net Debt, Shareholder Financing, Total Staff Costs
             ▼
┌─────────────────────────┐
│  Investment Decisions   │  Gross Transfer Expenditure, Net Transfer Spend, Player Registration
└────────────┬────────────┘  Amortisation, Disposal Profits, Capital Investment Timing
             ▼
┌─────────────────────────┐
│   Squad / Team Inputs   │  Squad Market Valuation, Wage-to-Turnover Ratio, Squad Depth,
└────────────┬────────────┘  Squad Age Profiles, Retention vs. Renewal Cycles
             ▼
┌─────────────────────────┐
│  Sporting Performance   │  Realized Outcomes: Points Per Game (PPG), Points %, League Rank;
└─────────────────────────┘  Structural Metrics: Goal Difference, Expected Goals (xG, xGD, xPTS)
```

1. **Financial Resources:** Audited statutory financial metrics capturing top-line revenue scale, liquidity, operating profitability, capital debt obligations, and overall wage commitments.
2. **Investment Decisions:** Capital allocation choices regarding player acquisitions, net expenditure, and accounting amortisation commitments across successive transfer windows.
3. **Squad / Team Inputs:** Structural team capabilities, squad valuation dynamics, age profile transitions, and allocation efficiency ratios.
4. **Sporting Performance:** Realized competition results (league points, table finish, domestic/European cup progression) as well as underlying structural performance metrics (expected goals, expected points).

---

## 4. Data Governance & Provenance Standards

To ensure academic rigor, forensic reproducibility, and intellectual property compliance:

- **No Proprietary Raw Source Documents:** Raw statutory corporate filings, commercial match event feeds, and third-party database dumps are not distributed in this repository.
- **Verifiable Provenance:** Every metric is mapped to verifiable public records, including audited annual financial statements of Arsenal Holdings Limited filed with Companies House (UK), official Premier League competition records, and peer-reviewed sports data conventions.
- **Zero Synthetic Data:** All empirical analyses are conducted strictly on documented historical observations without synthetic interpolation, data simulation, or proxy imputation.

---

## 5. Future Research Directions

Future research extensions planned for this repository may include:

- Applying the four-layer framework to comparative longitudinal case studies of additional European clubs across differing ownership and governance structures.
- Investigating cross-sectional panels across multiple leagues to assess how differing regulatory environments (e.g., UEFA Financial Sustainability Regulations, domestic profitability rules) condition financial allocation.
- Developing modular analytical code to test the interaction between structural process metrics (e.g., advanced expected goals models) and long-term balance sheet stability.

*(Note: Multi-club, cross-league, and multi-decade empirical studies have **not** yet been conducted in this repository; they represent prospective future research avenues).*

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
