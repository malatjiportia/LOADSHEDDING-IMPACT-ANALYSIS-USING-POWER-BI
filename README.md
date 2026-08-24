# LOADSHEDDING-IMPACT-ANALYSIS-USING-POWER-BI

# Loadshedding Impact Analysis — Power BI Portfolio Project

## Overview

This project analyses how South African loadshedding (rolling electricity
outages) affects daily sales performance at four small businesses in
Limpopo and Gauteng. It demonstrates an end-to-end data analytics
workflow: raw data auditing, cleaning in Power Query (M), DAX measure
design, and a three-page interactive Power BI report, backed by a written
findings/insights/recommendations report.

**Analysis period:** 3 January 2023 – 16 February 2023
**Businesses covered:** Thabo's Spaza Shop, Mama Grace Kitchen, Pick n Pay
Express Mokopane, Lebo's Hair Salon

## Project Files

| File | Description |
|---|---|
| `Power_BI_Project_Loadshedding.pbix` | The interactive Power BI report — 3 pages (Executive Overview, Business Deep Dive, Loadshedding Impact Analysis), 12 DAX measures, custom Box-and-Whisker visual |
| `Loadshedding_PowerBI_StarterPack.xlsx` | Source workbook: raw data, cleaned data, Data Quality Log, Removed Rows Log, Analysis Tables, DAX Measures reference, and the full Power Query (M) script |
| `Loadshedding_Impact_Analysis_Report.PDF` | Written report: findings, insights, recommendations, and full data cleaning methodology |
| `README.md` | This file |

## Data Pipeline Summary

- **Raw rows:** 133
- **Data quality issues identified:** 14 (inconsistent formats, spelling/case
  variants, an outlier, a duplicate row, a negative-sales row, missing
  values, and more — full detail in the Data Quality Log tab of the
  starter pack and in Section 1 of the written report)
- **Rows excluded:** 3 (a R999,999 outlier, an exact duplicate, and a
  negative-sales "refund day" row) — each preserved in a separate audit
  log rather than silently dropped
- **Clean rows analysed:** 130 (97.7% data retention)
- **Cleaning tool:** Power Query (M) — full script included in the starter
  pack, ready to paste into Power BI's Advanced Editor
- **Derived columns added:** `Day_of_Week`, `Week_Number`, `Month`,
  `LS_Severity` (None / Low 1-2 / High 3-4 / Severe 5-6)

## Key DAX Measures

| Measure | Purpose |
|---|---|
| `Total Sales` / `Avg Daily Sales` | Core revenue metrics |
| `Revenue Impact %` | Sales at a given loadshedding stage vs. the Stage-0 baseline |
| `Generator Uplift` | Sales difference between generator vs. non-generator businesses at Stage 3+ |
| `Zero Sales Days` | Count of days with R0 recorded sales |
| `Sales per Staff` | Total sales divided by staff on duty, to check staffing efficiency |
| `Days Stage 4+` | Count of high-severity loadshedding days in the period |

Full DAX expressions are documented in the starter pack's "DAX Measures" tab.

## Headline Findings

- Average daily sales fall from **R10,808** (no loadshedding) to **R3,668**
  (severe loadshedding) — a **66% decline**, and the drop compounds with
  severity rather than being a flat hit.
- Businesses with a generator averaged **13x** higher sales than those
  without, specifically during Stage 3+ outages.
- Small, informal, and service-based businesses (e.g. a hair salon with no
  non-electric fallback) are the most exposed, with lost trading days
  clustering at the most severe stages.

See `Loadshedding_Impact_Analysis_Report.PDF` for the full write-up,
including caveats and recommendations.

## Tools Used

Power BI Desktop · Power Query (M) · DAX · Excel (source data staging and
audit logs)

## Limitations

Small sample (4 businesses, ~33 days each) — this project is built to
demonstrate analytical technique and a clean, auditable methodology,
not to produce population-level claims about South African small
businesses generally. See the written report for the full limitations
section.
