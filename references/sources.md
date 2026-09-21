# Data Sources & Provenance Architecture

This document details the primary, official, and secondary data sources utilized in the longitudinal case study of **Arsenal Football Club (2015/16–2024/25)**, alongside the cell-level provenance framework governing the research.

In accordance with academic fair-use standards and data hygiene protocols, this repository does not redistribute copyrighted statutory filings, proprietary commercial data dumps, or raw third-party databases. Instead, complete bibliographic identifiers, statutory filing references, and transformation definitions are provided to enable independent replication against original public records.

---

## 1. Source Categories & Coverage

The longitudinal panel links four distinct empirical source domains across the ten completed football seasons from 2015/16 through 2024/25:

### 1.1 Statutory Corporate Financial Reporting (Primary Audited)
- **Publishing Entity:** Companies House (UK Executive Agency).
- **Reporting Corporate Entities:**
  - *Arsenal Holdings Limited* (Company No. 04250459; formerly *Arsenal Holdings plc*).
  - *Arsenal Football Club plc* (Company No. 00109244; operating football subsidiary).
- **Independent Auditor:** Deloitte LLP (Unqualified audit opinions issued across all reporting periods).
- **Temporal Coverage:** Financial reporting years ending 31 May (FY2016 through FY2025; 10 consecutive annual statutory filings).
- **Statutory Document Components:**
  - Consolidated Statement of Comprehensive Income (Profit and Loss Account)
  - Consolidated Statement of Financial Position (Balance Sheet)
  - Note 1: Segmental Turnover Analysis (Matchday, Broadcasting, and Commercial turnover)
  - Notes 2 & 3: Operating Expenses and Staff Costs (aggregate employee numbers and remuneration)
  - Note 6: Finance Costs (Net interest payable and debt service costs)
  - Note 9: Tangible Fixed Assets (Depreciation, stadium assets, capital expenditure)
  - Note 10: Intangible Fixed Assets (Player registrations additions, amortisation, impairments, and net book value under IAS 38)
  - Note 17: Borrowings and Financial Liabilities (Fixed/floating-rate stadium bonds, KSE shareholder loan facilities)
- **Variable Boundary Clarification:** Under UK GAAP and IFRS disclosures, employee compensation is reported as `staff_costs`. **`staff_costs` is an aggregate club-wide employee remuneration metric**, not a player-only wage variable. It encompasses playing squad, management, coaching, academy, medical, administrative, and commercial staff, as well as statutory employer pension and social security contributions.

### 1.2 Official Sporting Competition Records (Official Primary)
- **Publishing Authorities:**
  - *The Football Association* (The FA)
  - *English Football League* (EFL)
  - *The Premier League* (`premierleague.com`)
  - *Union of European Football Associations* (UEFA; `uefa.com`)
- **Temporal Coverage:** 2015/16 through 2024/25 (10 completed seasons).
- **Core Tracked Indicators:**
  - Domestic League: Points, points per match (PPG), final league finish rank, matches played, wins, draws, losses, goals for, goals against, goal difference.
  - Domestic Cups: FA Cup (stage reached, matches, win/draw/loss record, goals for/against, trophy won) and EFL Cup (stage reached, matches, win/draw/loss record, goals for/against, trophy won).
  - European Competitions: UEFA competition tier (Champions League, Europa League, or non-qualification), stage reached, matches played, win/draw/loss record, goals for/against, and trophy won.

### 1.3 Transfer Transaction Census (Primary Announcements & Secondary Consensus)
- **Census Scope:** 128 player transfer transactions (acquisitions and departures) completed between June 2015 and May 2025 across 20 transfer windows.
- **Reporting Authorities:**
  - *Primary Regulatory Disclosures:* Official club announcements via `arsenal.com` and FA/Premier League transaction registers.
  - *Secondary Journalistic Consensus:* Cross-referenced reporting from established sports journalism institutions (BBC Sport, The Athletic, Sky Sports) and structured market archives (*Transfermarkt*).
- **Measurement Uncertainty Protocol:** In European professional football, transfer fees are routinely designated as "undisclosed" in club announcements and are never itemized on an individual player basis in statutory accounts. Across Arsenal's 128 transactions, only 9 transactions possessed primary regulatory fee disclosures. Consequently, 77.8% of total gross consideration (£845.50m of £1,087.03m across the decade) relies on verified secondary consensus reporting. All transfer figures are treated with explicit estimation boundaries and subjected to add-on sensitivity audits.

### 1.4 Advanced Tactical Analytics (Third-Party Analytical Estimates)
- **Publishing Platform:** Understat (`understat.com/team/Arsenal`).
- **Metric Scope:** Season-level expected goals ($xG$), expected goals against ($xGA$), expected goal difference ($xGD$), expected points ($xPTS$), Passes Per Defensive Action ($PPDA$), and possession percentage.
- **Methodological Boundary:** Understat metrics are acknowledged strictly as third-party proprietary analytical estimates rather than official governing-body competition data.

---

## 2. Provenance Architecture & Data Ledger Specification

To eliminate data contamination, transcription drift, and irreproducible reporting, the research adheres to a cell-level provenance framework defined in [`methodology/PROVENANCE_SCHEMA.md`](../methodology/PROVENANCE_SCHEMA.md).

### 2.1 Deterministic Traceability
Every data point in the longitudinal panel resolves to an explicit provenance record cataloging:
1. `observation_id`: Unique immutable identifier (`OBS-YYYY-VAR-NNN`).
2. `season` & `financial_period`: Football season (`2015/16`–`2024/25`) and corporate accounting year (`FY2016`–`FY2025`).
3. `domain`: Variable classification (`Financial`, `Transfer`, `Sporting`, `Advanced`, `Context`).
4. `source_organization`: Regulatory or publishing body (e.g., Companies House, Premier League, Understat).
5. `document_title` & `document_reference_id`: Formal statutory document title and permanent filing locator.
6. `source_locator`: Page number, financial note number, or table identifier.
7. `raw_value_as_reported` & `reported_unit`: Verbatim figure extracted prior to mathematical transformation.
8. `transformation_applied` & `final_standardized_value`: Explicit arithmetic transformation (e.g., unit conversion from `£000` to `£m`) and standardized unit.
9. `verification_status`: Formal verification tier (`Primary Audited`, `Official Primary`, `Verified Secondary`).

### 2.2 Verification Tiers
- **`Primary Audited`:** Sourced exclusively from audited statutory accounts filed with Companies House. Required for all balance sheet, profit and loss, and cash flow items.
- **`Official Primary`:** Sourced directly from governing body competition handbooks, official league tables, and UEFA match registers.
- **`Verified Secondary`:** Multi-source journalistic consensus required for transaction-level transfer consideration where statutory itemization is unavailable.

### 2.3 Zero-Imputation Standard
- No data points are estimated via algorithmic imputation, synthetic generation, or industry-average interpolation.
- Missing statutory variables are recorded as unavailable rather than substituted with estimated figures.
- Currency conversions (e.g., transactions in EUR or USD) are normalized strictly using historical Bank of England spot exchange rates for the exact transaction date.

---

## 3. Public Repository Compliance & IP Safety

- **No Proprietary File Distribution:** Raw Companies House filing PDFs, scraped Understat database dumps, and commercial transfer market files are not distributed in this repository.
- **Audit Reproduction:** Independent researchers may reproduce every data point by referencing the audited statutory filings and official competition records cited herein using the specified page and note locators.
- **Zero Credentials:** This repository contains no API tokens, proprietary database connections, private credentials, or internal file paths.
