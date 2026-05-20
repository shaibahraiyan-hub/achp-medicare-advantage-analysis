# 🏥 ACHP Medicare Advantage Market Exit Analysis

> Full-cycle consulting analysis of 607 Medicare Advantage plan exits across 43 states — identifying market opportunities, quantifying share shifts, and delivering an actionable Expand vs Defend triage framework to ACHP leadership.

---

## 📌 Overview

In 2025–2026, 607 Medicare Advantage plans exited the market across 43 states and 1,268 counties, displacing thousands of beneficiaries. ACHP — a national health plan association — needed to understand: **which markets did they win, which did they lose, and where should they expand next?**

This project delivers a complete analytical framework: from raw CMS data ingestion to hypothesis-tested findings to a county-level triage system presented directly to ACHP leadership.

---

## 🧠 Research Questions

- Do ACHP member plans gain market share in counties where competitors exit?
- Does exit volume drive pickup — or is it the product vacuum left behind?
- Which counties should ACHP prioritize for expansion vs defense?
- Can we build an early-warning system for future carrier exits?

---

## 🗂️ Data Sources

| Source | Description |
|---|---|
| CMS MA Landscape Files CY2025 & CY2026 | Plan-level data: carrier, county, premium, benefits |
| CMS Monthly Enrollment Files (2025-01 to 2026-03) | Beneficiary enrollment by plan and county |
| USDA Rural-Urban Codes | County-level urban/rural classification |
| ACS Census Demographics | County demographics: age, income, population |
| 2024 Baseline Enrollment | Pre-exit market share benchmarks |

**Scale:** 607 exited plans · 45 parent organizations · 43 states · 1,268 affected counties

---

## 🔬 Methodology

### Data Pipeline
- Merged CMS Landscape and enrollment files on plan ID and county FIPS codes
- Standardized carrier names across years to track parent organization exits
- Engineered features: market share delta, HHI change, exit severity score, rural/urban flag

### Hypothesis Testing
| Hypothesis | Test | Result |
|---|---|---|
| H1a: ACHP gains share in exit counties | Two-sample t-test | ✅ Significant (p < 0.0001) |
| H1b: Share gain scales with exit volume | Correlation analysis | ❌ Weak relationship |
| H1c: Product vacuum drives pickup | Regression on plan count delta | ✅ Significant (p < 0.0001) |
| H2: HHI concentration predicts ACHP gain | OLS regression | ✅ Moderate effect |
| H3: Rural counties show different patterns | Subgroup analysis | ✅ Significant difference |

### Market Concentration (HHI)
- Calculated Herfindahl-Hirschman Index (HHI) for each county pre and post exit
- Classified counties by ΔHHI threshold into competitive opportunity tiers

### Triage Framework
Counties classified into 4 quadrants based on ACHP share gain potential and competitive risk:
- **Expand (185 counties):** High opportunity, low defense risk
- **Defend (73 counties):** ACHP incumbent, competitor pressure
- **Monitor (412 counties):** Moderate signals, watch list
- **Hold (598 counties):** Low priority

---

## 📊 Key Results

| Metric | Value |
|---|---|
| ACHP share gain in exit counties | **+0.82 percentage points** |
| ACHP share gain in non-exit counties | +0.28 percentage points |
| Difference (exit premium) | **+0.54pp (p < 0.0001)** |
| Exit volume correlation with ACHP gain | **Weak (r = 0.18)** |
| Product vacuum correlation with ACHP gain | **Strong (r = 0.61)** |
| Expand counties identified | **185** |
| Defend counties flagged | **73** |

**Key finding:** It's not *how many* plans exit — it's *what products* disappear. Counties where exiting plans held unique benefit structures (dental, vision, $0 premium) showed 2.3x higher ACHP pickup rates than high-volume but product-redundant exits.

---

## 💡 Recommendations to ACHP

1. **Build an early-warning carrier exit system** — monitor CMS quarterly filings for exit signals 6–9 months ahead of open enrollment
2. **Prioritize the 185 Expand counties** — focus member outreach and broker relationships in Q3 2026
3. **Defend the 73 high-risk counties** — proactive retention campaigns for existing ACHP enrollees
4. **Target product vacuum counties** — deploy benefit-matched plans where dental/vision coverage is disappearing
5. **Rural expansion** — rural exit counties show 1.8x pickup rates; underserved opportunity

---

## 🛠️ Tools & Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue?style=flat)

- **Python / Pandas** — data pipeline, cleaning, merging, feature engineering
- **NumPy / SciPy** — statistical hypothesis testing
- **Matplotlib / Seaborn** — visualizations
- **OLS Regression** — HHI and product vacuum modeling
- **PowerPoint** — executive presentation to ACHP leadership

---

## 📁 Files

| File | Description |
|---|---|
| `data_prep_eda.ipynb` | Data cleaning, merging, EDA — CMS Landscape + enrollment files |
| `hypothesis_testing.ipynb` | Statistical tests: H1a/b/c, H2, H3 |
| `triage_framework.ipynb` | Expand vs Defend county classification model |
| `ACHP_Analytics_Project.pptx` | Full consulting deck presented to ACHP leadership |
| `Team3_Final_Status_report.pptx` | Project status and methodology report |

---

## 🎓 Context

**Client:** ACHP (Alliance of Community Health Plans) — national association of nonprofit health plans  
**Course:** Advanced Business Analytics Consulting Project  
**School:** Johns Hopkins Carey Business School  
**Type:** Real-world client consulting engagement  
**Presented to:** ACHP leadership team  

This project demonstrates: real-world consulting workflow, CMS government data analysis, market concentration modeling (HHI), hypothesis testing with statistical significance, and executive communication of analytical findings.

---

## 🔗 Related Analysis Links

- [Data Preparation & EDA](https://colab.research.google.com/drive/11Yg0rKcoB4LcRZDr5ftqAp1s_vBCTJ1W?usp=sharing)
- [EDA Notebook](https://colab.research.google.com/drive/1eOOoszz1NnOLV8tOj4cvHdBFVuy0t6t5?usp=sharing)
