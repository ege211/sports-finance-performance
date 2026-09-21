# Phase 1: Operational Data Collection Plan
## Project Arsenal FC (2015/16–2024/25)

---

### Purpose & Scope
This document outlines the strict operational protocol for data collection to be executed in subsequent phases. In adherence to the **Critical Restriction**, no scraping, panel synthesis, or database building has been executed during Phase 1. This plan defines how raw observations will be systematically harvested, verified, and mapped into the provenance ledger once data collection is formally initiated.

---

## 1. Domain-Specific Collection Protocols

### Protocol 1: Financial Data Extraction (Primary Audited)
* **Target Source:** Companies House PDF filings for **Arsenal Holdings Limited** (Company No. 04250459).
* **Target Periods:** FY2016 through FY2025 (10 filings).
* **Extraction Workflow:**
  1. Retrieve official PDF documents using the verified Document Reference IDs cataloged in `FINANCIAL_SOURCE_MAP.csv`.
  2. Extract data directly from the audited financial statement pages:
     - Consolidated Statement of Comprehensive Income (Profit & Loss Account).
     - Consolidated Balance Sheet (Statement of Financial Position).
     - Note 1: Segmental Turnover Analysis (Matchday, Broadcasting, Commercial).
     - Note 2 & 3: Operating Expenses & Staff Costs (Employee numbers and compensation).
     - Note 6: Finance Costs (Net interest payable).
     - Note 9: Tangible Fixed Assets (Depreciation, stadium assets).
     - Note 10: Intangible Fixed Assets (Player Registrations additions, amortisation, impairments, NBV).
     - Note 17: Borrowings (Stadium bonds, KSE loan facility).
  3. Every number must be recorded twice by independent transcription or automated regex double-checking against PDF text layers.
  4. Record the original value in `raw_value_as_reported` (typically in `£000`) before converting to standardized `£m`.

### Protocol 2: Transfer Transaction Ingestion (Bifurcated Model)
* **Target Sources:**
  - *Accounting Additions (Concept B):* Note 10 of Annual Accounts (Intangible Fixed Assets - Additions).
  - *Market Transactions (Concept A):* *Transfermarkt* transfer records, cross-referenced with *BBC Sport* and official *Arsenal.com* signing statements.
* **Extraction Workflow:**
  1. Construct transaction roster for all permanent transfers and loans across the 20 transfer windows (Summer 2015 through Winter 2025).
  2. Categorize each deal by Direction (`In` vs `Out`), Status (`Permanent`, `Loan`, `Free`, `Mutual Termination`), and Transfer Date.
  3. Capture reported headline market fee in original currency (€, £).
  4. Flag undisclosed transactions explicitly as `UNDISCLOSED`.
  5. Ensure accounting additions from financial accounts remain in a distinct macro-level variable and are **never** divided among players using speculative formulas (Rule 4 & Rule 5).

### Protocol 3: Official Sporting Records Harvesting
* **Target Sources:**
  - Premier League Official Handbooks & Statistics Archive (`premierleague.com`).
  - UEFA Technical Reports and Match Handbooks (`uefa.com`).
  - The Football Association & English Football League Official Archives.
* **Extraction Workflow:**
  1. Transcribe final league tables for seasons 2015/16 through 2024/25:
     - Matches, Wins, Draws, Losses, Goals For, Goals Against, Goal Difference, Points Total, Final League Rank.
  2. Verify all standings against published Premier League Handbooks.
  3. Transcribe domestic cup outcomes:
     - FA Cup: Stage reached, matches played, trophy won (binary).
     - League Cup: Stage reached, matches played, trophy won (binary).
  4. Transcribe UEFA European performance:
     - Competition entered (UCL, UEL, None).
     - Stage reached (Group, R32, R16, QF, SF, Final, Trophy).
     - UEFA Club Coefficient points allocated for the specific season.

### Protocol 4: Advanced Metrics Extraction
* **Target Sources:** Understat official public database (`understat.com/team/Arsenal`).
* **Extraction Workflow:**
  1. Harvest season aggregate metrics across the 38 Premier League fixtures:
     - Expected Goals ($xG$)
     - Expected Goals Against ($xGA$)
     - Expected Goal Difference ($xGD = xG - xGA$)
     - Expected Points ($xPTS$)
     - Passes Per Defensive Action ($PPDA$)
     - Opponent Passes Per Defensive Action (Press resistance)
     - Deep completions and box entries.
  2. Confirm model consistency across the 2015/16–2024/25 continuum.
  3. Do **not** harvest discontinued or broken tracking metrics (pressures, progressive carries) as established in the feasibility audit.

---

## 2. Provenance Ledger Population Sequence

For every extracted datum, an entry in `DATA_PROVENANCE_LEDGER.csv` must be generated concurrently:

```
[Extract Raw Value from Primary Document]
                  │
                  ▼
[Verify Document ID, Page, and Line Reference]
                  │
                  ▼
[Populate observation_id, season, raw_value, reported_unit]
                  │
                  ▼
[Apply Standardized Transformation (e.g., raw / 1000)]
                  │
                  ▼
[Populate final_standardized_value and standardized_unit]
                  │
                  ▼
[Record Verification Status and Auditor Caveats]
```

---

## 3. Automated Quality Control & Validation Pipeline

Before any dataset is finalized for subsequent exploratory analysis, a Python validation suite (`validate_arsenal_dataset.py`) will run the following assertions:

1. **Assertion 1 (Zero Missing Cells in Core Panel):** Every Core GREEN variable must have exactly 10 observations (one per completed season).
2. **Assertion 2 (Accounting Mathematical Identity):**
   $$\text{Operating Profit After Trading} = \text{Operating Profit Before Trading} - \text{Amortisation} - \text{Impairments} + \text{Disposal Profits}$$
   The extracted financial figures must reconcile to within statutory rounding tolerances ($\pm £0.1\text{m}$).
3. **Assertion 3 (Balance Sheet Debt Reconciliation):**
   $$\text{Net Debt} = \text{Gross Borrowings} - \text{Cash and Cash Equivalents}$$
   Verified across all 10 reporting periods.
4. **Assertion 4 (Sporting Record Verification):**
   $$\text{Points} = (3 \times \text{Wins}) + (1 \times \text{Draws})$$
   $$\text{Goal Difference} = \text{Goals For} - \text{Goals Against}$$
   Must hold exactly for all 10 seasons.
5. **Assertion 5 (Exclusion Verification):** Assert that no prohibited variables (player-specific salaries, synthetic tracking metrics, composite indices) appear in the core longitudinal file.

---

## 4. Execution Governance & Protocol Freezing

* **Phase Gate:** This collection plan remains inactive until Phase 1 deliverables are reviewed and authorized.
* **Audit Trail:** Any modification to variable mappings, source locators, or standardization formulas requires a formal version increment and explicit documentation in the research log.
