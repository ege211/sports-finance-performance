# Sports Finance & Sporting Performance Research

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Research Status](https://img.shields.io/badge/Research-Active-success.svg)](#)

> **Longitudinal research on the relationship between financial resources, investment decisions, and sporting performance in professional football.**

---

## Executive Overview

`sports-finance-performance` is an independent empirical research repository focused on the economics and corporate finance of professional association football. The project investigates how financial resource endowments, capital expenditure strategies (transfer investments, amortisation commitments), and operating cost structures (wage bills, turnover allocation) relate to on-pitch sporting outcomes over multi-decade horizons.

While the inaugural longitudinal study utilizes **Arsenal Football Club** (1992–2024) as a detailed single-club case study across the Premier League era, the repository architecture and econometric pipeline are constructed as a generalized framework applicable to multi-club, multi-league, and cross-era sports finance inquiries.

---

## Core Research Questions & Theoretical Themes

The research framework explores several foundational questions in sports economics:

1. **Resource Scale vs. Allocation Efficiency**
   - How strongly does wage expenditure constrain sporting league performance relative to transfer expenditure?
   - What are the diminishing returns to wage scale, and how do wage-to-turnover ratios reflect structural efficiency versus financial distress?

2. **Capital Investment & Amortisation Dynamics**
   - How do multi-year player registration amortisation schedules and net transfer expenditures correlate with structural performance measures (e.g., goal differential, expected points) versus raw points accumulation?
   - Under what conditions does squad reinvestment exhibit lag effects across distinct managerial regimes?

3. **Exogenous Shocks & Robustness**
   - How do systemic macroeconomic disruptions (e.g., stadium financing debt periods, the COVID-19 spectator shutdown) alter the relationship between operating cash flow and sporting competitiveness?
   - Evaluating empirical robustness through non-parametric rank tests (Spearman $\rho$, Kendall $\tau$), leave-one-out (LOO) sensitivity analyses, and outlier diagnostics.

---

## Inaugural Case Study: Arsenal FC (1992–2024)

The inaugural research paper hosted within this repository explores a complete 32-season longitudinal panel of Arsenal Football Club:

- **Panel Scope:** 32 seasons (1992–93 through 2023–24), capturing pre-stadium, Emirates construction debt, late-Wenger austerity, ownership transition, and post-2019 squad restructuring phases.
- **Empirical Findings:** Demonstrates that wage bill scale exhibits the strongest and most resilient rank correlation with sporting performance, while transfer expenditure exhibits higher variance, regime-dependent sensitivity, and greater vulnerability to single-season allocation shocks.
- **Methodological Standards:** Zero causal overclaiming; strict non-parametric rank association reporting; complete leave-one-out sensitivity testing.

---

## Repository Architecture

```text
sports-finance-performance/
├── .gitignore             # Comprehensive Python, environment, and data cache exclusions
├── LICENSE                # MIT License
├── README.md              # Project motivation, framework, and documentation index
├── docs/                  # Working papers, research designs, and variable dictionaries
├── src/                   # Econometric, data hygiene, and panel construction modules
└── tests/                 # Data validation and empirical consistency test suites
```

---

## Data Governance & Reproducibility Standards

To maintain academic and commercial integrity:

- **No Proprietary Raw Data:** Raw statutory filings, licensed commercial match event feeds, and copyrighted financial schedules are not hosted directly in this repository.
- **Auditable Provenance:** Every empirical metric is documented with explicit derivation formulas, variable definitions, and statutory filing line-item mappings (e.g., Companies House statutory accounts, official league records).
- **Zero Synthetic Data:** All empirical findings are derived strictly from documented, verified historical records without synthetic interpolation or simulated outcomes.

---

## Getting Started

### Prerequisites

- Python 3.10 or higher
- Standard scientific stack (`numpy`, `pandas`, `scipy`, `statsmodels`)

### Environment Setup

```bash
# Clone the repository
git clone https://github.com/ege211/sports-finance-performance.git
cd sports-finance-performance

# Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install development dependencies
pip install --upgrade pip
```

---

## Citation & Academic Use

If you utilize this framework, methodology, or the longitudinal research in your academic or professional work, please cite:

```bibtex
@misc{cavusoglu2026sportsfinance,
  author       = {Ege Cavusoglu},
  title        = {Longitudinal Research on the Relationship Between Financial Resources, Investment Decisions, and Sporting Performance in Professional Football},
  year         = {2026},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/ege211/sports-finance-performance}}
}
```

---

## License

This project is licensed under the terms of the [MIT License](LICENSE).
