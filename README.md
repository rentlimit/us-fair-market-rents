---
license: cc-by-4.0
language: [en]
pretty_name: US Fair Market Rents FY2027 and Income Limits by County (verified)
tags: [housing, rent, fair-market-rent, hud, section-8, income-limits, census, acs, affordability, united-states]
size_categories: [1K<n<10K]
---

# US Fair Market Rents FY2027, Income Limits FY2026 and Renter Affordability by County

One row per U.S. county (and New England town group) with HUD's **FY2027 Fair Market Rents** (effective 2026-10-01), the FY2026 values for comparison, HUD **FY2026 Section 8 income limits**, and Census **ACS 5-Year 2020–2024** median gross rent, median renter income and rent burden with margins of error.

- Rows: 3,268 (3,229 counties; 39 extra New England town groups)
- File: `us-fair-market-rents-fy2027-by-county.csv` (UTF-8, comma-separated)
- Maintainer: RentLimit, https://rentlimit.com (same figures as the website)
- Built: 2026-11-07

## Why this dataset

HUD's own files are split across several spreadsheets with different keys, and huduser.gov blocks most scripted downloads. This file joins them on the county FIPS code, adds the previous year and the Census affordability measures, and was **checked against the official lookup tools**:

- 2026-11-05: 6 counties against HUD's FMR and income limits documentation system on huduser.gov – all values match.
- 2026-11-05: 3 counties against data.census.gov – all values match.

## Sources

| Data | Source | Effective |
|---|---|---|
| Fair Market Rents FY2027 | https://www.huduser.gov/portal/datasets/fmr/fmr2027/FY27_FMRs.xlsx | 2026-10-01 |
| Fair Market Rents FY2026 (revised) | https://www.huduser.gov/portal/datasets/fmr/fmr2026/FY26_FMRs_revised.xlsx | 2025-10-01 |
| Income limits FY2026 | https://www.huduser.gov/portal/datasets/il/il26/Section8-FY26.xlsx | 2026-05-01 |
| ACS 5-Year 2020–2024: B25064, B25119, B25070 (B19013 fallback) | https://www.census.gov/programs-surveys/acs/data/summary-file.html | released Dec. 2025 |

The underlying government data is public domain. This compilation is licensed **CC BY 4.0**: please credit "RentLimit (rentlimit.com), from HUD and U.S. Census Bureau data".

## Notes

- FMRs are gross rents (rent + tenant-paid utilities except phone, cable, internet), set at the 40th percentile of recent-mover rents for standard units. They are not a legal rent cap.
- Housing authorities set voucher payment standards at 90–110% of the FMR (or of ZIP-level Small Area FMRs where required).
- ACS figures are survey estimates; use the margin-of-error columns. Rent burden shares are empty for counties with fewer than 100 renter households.
- Connecticut uses planning regions instead of counties since 2022 (no ACS 2015–2019 comparison).

## Columns

| Column | Description |
|---|---|
| `state` | State or territory name |
| `state_code` | USPS state code |
| `county` | County or county-equivalent name (Connecticut: planning region) |
| `county_fips` | 5-digit county FIPS code |
| `fmr_area_code` | HUD FMR area code |
| `fmr_area_name` | HUD FMR area name |
| `is_primary_area` | 1 = most populous FMR area of the county (shown on rentlimit.com); 0 = further New England town group |
| `metro` | 1 = metropolitan FMR area |
| `fmr2027_0br` | HUD FY2027 Fair Market Rent, studio (USD/month, gross rent incl. utilities) |
| `fmr2027_1br` | HUD FY2027 Fair Market Rent, 1 bedroom (USD/month, gross rent incl. utilities) |
| `fmr2027_2br` | HUD FY2027 Fair Market Rent, 2 bedroom (USD/month, gross rent incl. utilities) |
| `fmr2027_3br` | HUD FY2027 Fair Market Rent, 3 bedroom (USD/month, gross rent incl. utilities) |
| `fmr2027_4br` | HUD FY2027 Fair Market Rent, 4 bedroom (USD/month, gross rent incl. utilities) |
| `fmr2026_0br` | HUD FY2026 Fair Market Rent (revised file), studio |
| `fmr2026_1br` | HUD FY2026 Fair Market Rent (revised file), 1 bedroom |
| `fmr2026_2br` | HUD FY2026 Fair Market Rent (revised file), 2 bedroom |
| `fmr2026_3br` | HUD FY2026 Fair Market Rent (revised file), 3 bedroom |
| `fmr2026_4br` | HUD FY2026 Fair Market Rent (revised file), 4 bedroom |
| `il2026_median_family_income` | HUD FY2026 area median family income (USD/year) |
| `il2026_low_80pct_1p` | HUD FY2026 low-income limit (80%), household of 1 |
| `il2026_low_80pct_2p` | HUD FY2026 low-income limit (80%), household of 2 |
| `il2026_low_80pct_3p` | HUD FY2026 low-income limit (80%), household of 3 |
| `il2026_low_80pct_4p` | HUD FY2026 low-income limit (80%), household of 4 |
| `il2026_low_80pct_5p` | HUD FY2026 low-income limit (80%), household of 5 |
| `il2026_low_80pct_6p` | HUD FY2026 low-income limit (80%), household of 6 |
| `il2026_low_80pct_7p` | HUD FY2026 low-income limit (80%), household of 7 |
| `il2026_low_80pct_8p` | HUD FY2026 low-income limit (80%), household of 8 |
| `il2026_very_low_50pct_4p` | HUD FY2026 very-low-income limit (50%), household of 4 |
| `il2026_extremely_low_30pct_4p` | HUD FY2026 extremely-low-income limit (30%), household of 4 |
| `acs_median_gross_rent` | Census ACS 5-Year 2020–2024, B25064 median gross rent (USD/month), county |
| `acs_median_gross_rent_moe` | Margin of error (90%) |
| `acs_median_renter_income` | Census ACS 5-Year 2020–2024, B25119 median household income of renter households (USD/year); B19013 all households where flagged |
| `acs_median_renter_income_moe` | Margin of error (90%) |
| `acs_income_is_renter` | 1 = renter household income (B25119), 0 = all households fallback (B19013) |
| `acs_renter_households` | Renter households for which rent as % of income is computed (B25070 line 1 minus line 11) |
| `acs_rent_burden_30pct` | Share of those renter households paying 30%+ of income on gross rent (%), empty if < 100 households |
| `acs_rent_burden_30pct_moe` | Margin of error (percentage points, Census formula for derived proportions) |
| `acs_rent_burden_50pct` | Share paying 50%+ (%) |
| `acs_rent_burden_50pct_moe` | Margin of error (percentage points) |
| `rentlimit_url` | County page on rentlimit.com with sources and context |

## Updates

FMRs: each October (HUD publishes in August/September). Income limits: each spring. ACS: each December. Changelog: https://rentlimit.com/changes/
