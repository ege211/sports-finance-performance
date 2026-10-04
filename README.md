# Sports Finance & Sporting Performance
### A Longitudinal Case Study of Arsenal Football Club (2015/16–2024/25)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Academic Level](https://img.shields.io/badge/Level-High%20School%20Student%20Research-blue.svg)](#)

> **Independent student research exploring how corporate financial resources, transfer market investments, and squad commitments relate to pitch performance in European professional football.**

---

## 1. Student Researcher's Note & Motivation

**Author:** Ege Umut Can  
**School:** FMV Özel Ispartakule Işık High School, Istanbul (Class of 2027)  
**Profile:** Student-Athlete (High School Football Team) & AP Economics Student  

### Why I Undertook This Research:
As a high-school student who actively plays football for my school team and studies AP Microeconomics and Macroeconomics, I have always been fascinated by the business side of the sport I love. In modern European football, fans and media often assume a simple linear equation: *spend more money on transfers $\rightarrow$ immediately win more games*. 

However, watching football and studying economic principles taught me that reality is rarely that simple. Clubs operate under financial constraints, debt obligations, and regulatory frameworks, while newly acquired players require time, tactical cohesion, and managerial stability to translate into pitch results. 

To explore this dynamic objectively, I conducted a 10-season longitudinal study focusing on **Arsenal Football Club** between **2015/16 and 2024/25**. Arsenal provides a unique case study because the club experienced the end of Arsène Wenger's 22-year tenure, an ownership buyout by Kroenke Sports & Entertainment (KSE), a transition from stadium bond repayment to squad reinvestment, the COVID-19 revenue shock, and a comprehensive squad rebuild under Mikel Arteta.

---

## 2. Research Question & Scope

### Core Research Question:
> *"To what extent are changes in Arsenal Football Club’s financial resources and investment decisions associated with changes in sporting performance between 2015/16 and 2024/25?"*

### Six Investigated Areas (SQ1–SQ6):
1. **Financial Evolution (SQ1):** How Arsenal's turnover (matchday, commercial, broadcasting), wage bill, debt profile, and cash reserves evolved over the decade.
2. **Revenue to Transfer Investment (SQ2):** How top-line turnover growth was associated with gross and net transfer market expenditure.
3. **Investment to Pitch Results (SQ3):** How transfer spending related to Premier League points, goal difference, and underlying expected goal differential (xGD).
4. **Staff Costs & Payroll (SQ4):** How total statutory employee remuneration related to subsequent league performance.
5. **Overall Financial Health & Results (SQ5):** How operating profit/loss and cash reserves co-moved with sporting outcomes.
6. **Lagged Effects & Squad Cohesion (SQ6):** Investigating whether transfer investments show stronger associations with pitch results after a one-season lag ($t \to t+1$) as new players adapt.

---

## 3. Four-Layer Conceptual Framework

To organize the study methodologically, I structured the analysis across four connected layers:

```text
┌─────────────────────────┐
│   Financial Resources   │  Turnover (Matchday, Commercial, Broadcast),
└────────────┬────────────┘  Cash Balances, Gross & Net Debt, Staff Costs
             │
             ▼
┌─────────────────────────┐
│  Investment Decisions   │  Permanent Gross & Net Transfer Spend,
└────────────┬────────────┘  Player Additions, Disposal Receipts
             │
             ▼
┌─────────────────────────┐
│   Squad / Team Inputs   │  Wage-to-Revenue Ratio, Registration Amortisation,
└────────────┬────────────┘  Net Book Value of Squad, Squad Rebuilding Velocity
             │
             ▼
┌─────────────────────────┐
│  Sporting Performance   │  Official: Points, League Finish, Goal Difference;
└─────────────────────────┘  Advanced Analytics: Expected Goals (xG, xGA, xGD), xPTS
```

---

## 4. Data Sources & Empirical Methodology

### Data Provenance (100% Publicly Verifiable):
- **Statutory Corporate Accounts:** Audited annual financial statements of Arsenal Holdings Limited and Arsenal Football Club plc filed with the UK Companies House registry.
- **Transfer Census:** Comprehensive census of 128 individual player transactions across the 10 seasons, cross-referenced against statutory registration additions.
- **Match & Advanced Analytics:** Official Premier League competition tables, cup progression, and advanced performance metrics (expected goals [$xG$], expected points [$xPTS$]) from Understat.

### Methodological Principles & Limitations:
- **Observational, Non-Causal Design:** As a high-school student working with a single-club time-series ($N=10$ seasons), this study strictly measures **statistical associations and co-movements**. It does not claim deterministic causality.
- **Correlation & Robustness:** Evaluated using Pearson correlation ($r$), Spearman rank correlation ($\rho$), and Leave-One-Season-Out (LOO) sensitivity checks to ensure individual outlier years (like the COVID-19 season) do not distort the broader decade trend.

---

## 5. Key Empirical Takeaways

1. **Top-Line Expansion (+97.1%):** Arsenal's football turnover expanded from £350.6m in 2015/16 to £691.0m in 2024/25, driven by commercial growth and Champions League return.
2. **Transfer Spending & the Lag Effect:** Contemporaneous transfer spend showed modest correlation with same-season points, but exhibited substantially stronger positive associations with pitch performance **in the subsequent season ($t \to t+1$, $r = +0.6189$ with xPTS)**. This quantitatively illustrates the time required for squad investments to mature.
3. **The Limits of Payroll Alone:** Statutory staff costs showed weak correlation with league points ($r = +0.0516$), proving that simply carrying a high wage bill does not guarantee sporting success without efficient recruitment and squad balance.

---

## 6. Repository Structure

```text
sports-finance-performance/
├── data/                  # 10-season panel dataset and variable dictionary
├── methodology/           # Research design notes, data collection plan, provenance map
├── paper/                 # Full research paper (PDF, Markdown, Word versions)
│   ├── FINAL_ARSENAL_PAPER.pdf
│   ├── FINAL_ARSENAL_PAPER.md
│   └── FINAL_ARSENAL_PAPER.docx
├── references/            # Academic literature on sports economics (Szymanski, Dobson & Goddard)
└── results/               # Empirical correlation tables and robustness checks
```

---

## 7. Citation & Contact

```bibtex
@misc{can2026arsenal,
  author       = {Ege Umut Can},
  title        = {Financial Resources, Investment Decisions, and Sporting Performance: A Longitudinal Investigation of Arsenal Football Club (2015/16--2024/25)},
  year         = {2026},
  school       = {FMV Işık High School},
  howpublished = {\url{https://github.com/ege211/sports-finance-performance}}
}
```

**Contact:** Ege Umut Can — [macroeconomic-data-lab](https://ege211.github.io/macroeconomic-data-lab/) | [GitHub Profile](https://github.com/ege211)

---

## 8. Research Methodology & Transparency Note

As an independent 12th-grade student researcher and high-school athlete, I formulated the core research questions, collected and verified the 10-season statutory financial accounts of Arsenal Holdings Limited from the UK Companies House registry, compiled the 128-transaction transfer census, and conducted the non-causal statistical correlation and Leave-One-Season-Out sensitivity analysis. I utilized AI tools for editorial review, Markdown formatting, and data structuring. All empirical analyses, interpretations, and conclusions are strictly my own.

---

## 9. License

This project is licensed under the [MIT License](LICENSE).
