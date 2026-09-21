# Phase 1: Source Provenance Architecture & Data Ledger Specification
## Project Arsenal FC (2015/16–2024/25)

---

### Standard Overview
Under **Rule 1** (*"NO VERIFIABLE SOURCE = NO OBSERVATION"*) and **Rule 6** (*"Every observation in the final dataset must have provenance"*), no data point may enter the final dataset without an explicit, audit-grade provenance record. This document establishes the architectural schema and validation rules for tracking every single historical observation.

---

## 1. Provenance Architecture Principles

1. **Deterministic Traceability:** Every numeric or categorical cell in any downstream dataset must resolve to an immutable primary or verified secondary document.
2. **Atomic Granularity:** Provenance is maintained at the individual cell / observation level, not at the file or dataset level.
3. **Audit Immutability:** Raw scraped or transcribed numbers must be recorded exactly as published, prior to any unit scaling, currency conversion, or deflation.
4. **Transparent Transformation:** Any mathematical transformation (e.g., converting thousands to millions, applying exchange rates, computing per-game rates) must be codified as an explicit formula in the provenance ledger.

---

## 2. Provenance CSV Schema (`DATA_PROVENANCE_LEDGER.csv`)

Every collected observation will be recorded in a centralized ledger with the following mandatory 17-column specification:

| Field Index | Column Name | Data Type | Requirement | Description / Valid Values | Example |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **1** | `observation_id` | String (UUID) | Mandatory | Unique immutable identifier (`OBS-YYYY-VAR-NNN`) | `OBS-2016-REV-001` |
| **2** | `season` | String | Mandatory | Football season (`2015/16` to `2024/25`) | `2015/16` |
| **3** | `financial_period` | String | Conditional | Accounting period if financial (`FY2016` to `FY2025`) | `FY2016` |
| **4** | `domain` | String (Enum) | Mandatory | `Financial`, `Transfer`, `Sporting`, `Advanced`, `Context` | `Financial` |
| **5** | `variable_name` | String | Mandatory | Standardized variable identifier matching matrix | `total_turnover` |
| **6** | `source_organization` | String | Mandatory | Publishing authority (`Companies House`, `Premier League`, etc.) | `Companies House / Arsenal Holdings PLC` |
| **7** | `document_title` | String | Mandatory | Full formal title of the source filing or publication | `Group of companies' accounts made up to 31 May 2016` |
| **8** | `document_reference_id`| String | Mandatory | Filing ID, ISBN, DOI, or permanent archive reference | `MzE2Njc3MDIwNGFkaXF6a2N4` |
| **9** | `publication_date` | Date (ISO) | Mandatory | Formal publication or filing date (`YYYY-MM-DD`) | `2017-01-17` |
| **10** | `source_locator` | String | Mandatory | Page number, Note number, Table identifier, or URL path | `p. 23, Consolidated Profit and Loss Account` |
| **11** | `raw_value_as_reported`| String | Mandatory | Exact verbatim value extracted from the primary document | `353,546` |
| **12** | `reported_unit` | String | Mandatory | Original unit (`£000`, `£m`, `€`, `Points`, `Ratio`) | `£000` |
| **13** | `transformation_applied`| String | Mandatory | Exact mathematical operation applied (`None`, `/ 1000`, etc.) | `raw_value / 1000` |
| **14** | `final_standardized_value`| Numeric/String| Mandatory | Value aligned to project standard unit | `353.55` |
| **15** | `standardized_unit` | String | Mandatory | Target unit (`£m`, `Integer`, `Float`, `Ratio`) | `£m` |
| **16** | `verification_status` | String (Enum) | Mandatory | `Primary Audited`, `Official Primary`, `Verified Secondary`, `Flagged` | `Primary Audited` |
| **17** | `auditor_notes` | String | Optional | Contextual caveats, accounting notes, or known distortions | `Includes £5.1m property development turnover` |

---

## 3. Data Integrity & Validation Constraints

### Validation Rule A: Primary Match Verification
If `domain == 'Financial'`, `source_organization` MUST be `Companies House` or `Arsenal Holdings Limited / PLC`, and `verification_status` MUST be `Primary Audited`. Any secondary citation for core balance-sheet or P&L items will be rejected by the validation pipeline.

### Validation Rule B: No Arbitrary Substitution
If `raw_value_as_reported` is missing or labeled `"undisclosed"` in primary documents:
- `raw_value_as_reported` must be recorded as `NULL` or `UNDISCLOSED`.
- `final_standardized_value` must be recorded as `NaN` / empty string.
- Under **Rule 4** and **Rule 5**, imputing a number or applying an industry average formula is strictly prohibited.

### Validation Rule C: Currency Normalization Protocol
For transactions denominated in Euros (€) or US Dollars ($):
- `raw_value_as_reported` must record the exact foreign currency figure (e.g., `€53,000,000`).
- `transformation_applied` must cite the specific historical Bank of England spot rate for the transaction date (e.g., `value_eur * 0.8812 [BOE spot 2017-07-05]`).
- The source of the exchange rate must be explicitly documented in `auditor_notes`.

---

## 4. Source Document Archival Structure

All primary PDF filings, statutory regulatory disclosures, and archived HTML snapshots will be preserved locally in the project tree to ensure permanent auditability:

```
project_arsenal/
├── data/
│   ├── raw_sources/
│   │   ├── financial_filings_companies_house/
│   │   │   ├── 04250459_AA_20160531_FY16.pdf
│   │   │   ├── 04250459_AA_20170531_FY17.pdf
│   │   │   ├── 04250459_AA_20180531_FY18.pdf
│   │   │   ├── 04250459_AA_20190531_FY19.pdf
│   │   │   ├── 04250459_AA_20200531_FY20.pdf
│   │   │   ├── 04250459_AA_20210531_FY21.pdf
│   │   │   ├── 04250459_AA_20220531_FY22.pdf
│   │   │   ├── 04250459_AA_20230531_FY23.pdf
│   │   │   ├── 04250459_AA_20240531_FY24.pdf
│   │   │   └── 04250459_AA_20250531_FY25.pdf
│   │   ├── official_competition_handbooks/
│   │   │   ├── premier_league_handbook_archives/
│   │   │   └── uefa_statistics_handbooks/
│   │   └── secondary_transfer_snapshots/
│   │       └── transfermarkt_arsenal_transfers_2015_2025.csv
│   └── ledgers/
│       └── DATA_PROVENANCE_LEDGER.csv
```

---

## 5. Automated Verification Script Specification

Before any dataset ingestion script runs in Phase 2, an automated checksum verification script (`verify_provenance.py`) will execute:
1. **Uniqueness Check:** Ensure all `observation_id` keys are non-null and unique.
2. **Schema Conformity:** Validate that all 17 columns exist and match expected types.
3. **Null Check:** Assert that no `final_standardized_value` is populated without a valid `document_reference_id` and `source_locator`.
4. **Integrity Rule Enforcement:** Scan for blacklisted terms (`estimated`, `assumed`, `interpolated`, `synthetic`) in `raw_value_as_reported` for all Core GREEN variables. Any match triggers a fatal build failure.
