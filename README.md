**Joycelyn Hughes-Moulden** - 
**Spring 2026 - DATA 801 Capstone Project** - 
**Applied Data Science and Analytics Master's Program**

# Exploratory Data Analysis & Pre-ML Diagnostics

---
## Overview

This repository contains the statistical foundation of my capstone project as a student of Howard University's Applied Data Science and Analytics Master's Program. This study advances a central argument: _Historically Black Colleges and Universities (HBCUs) are currently underserved by commercially dominant student success platforms designed around the demographic and institutional profiles of Predominantly White Institutions (PWIs). A purpose-built HBCU student success platform is not merely preferable; it is **structurally necessary**._
---

## Research Questions

1. Do student success platforms that are designed for PWIs help HBCUs close gaps in retention and graduation rates? If not, what type of student success platform 
would be more effective for HBCUs?

**_## Deeper Inquiry_**

3. Which institution-level academic and student support indicators correlate most strongly with **first-year retention** and **six-year graduation rates** at HBCUs?
4. Do HBCUs and PWIs differ significantly on key student success outcomes — and if so, does the pattern suggest that platform adoption alone cannot close the gap?
5. What structural data quality issues (multicollinearity, imbalance, missing data) must be diagnosed and remediated before building predictive ML models?

---

## Repository Structure

```
2026-Capstone-Project---JHM/
├── Spring_2026_-_Capstone.ipynb         ← Main analysis notebook (EDA + Pre-ML)
├── Data_for_Revised_Capstone_Enhanced.csv  ← 51-institution comparative dataset
└── README.md                            ← This file
```

---

## Dataset

A curated 51-institution comparative dataset (**26 HBCUs + 25 PWIs**) compiled from the following sources:

| Source | Variables |
|---|---|
| IPEDS / College Scorecard 2022-23 | Graduation rates, retention rates, enrollment, cost |
| NACUBO 2022 | Endowment figures |
| EAB & Institutional Websites | Platform adoption (Navigate, Starfish, Workday Student) |
| Hope Center HBCU Basic Needs Survey 2020 | % Financial shock, % housing insecurity |
| IPEDS Fall Enrollment 2016–2024 | Longitudinal retention trends (8 AY windows) |
| IPEDS Age Distribution 2022-23 | Traditional-age students, average undergraduate age |

**Key variable groups:**
- **Outcome variables** — 6-year graduation rate, first-year retention rate
- **Structural variables** — enrollment, endowment per student, sector (public/private)
- **Student-need indicators** — % Pell recipients, % first-generation students, % financial shock, % housing insecurity
- **Platform adoption** — Navigate (EAB), Starfish (Civitas Learning), Workday Student
- **Advising infrastructure** — proactive advising model, degree audit tool
- **Longitudinal retention trends** — AY 2016-17 through 2023-24

---

## Notebook Contents

The main notebook (`Spring_2026_-_Capstone.ipynb`) is organized into four sections:

### Section 0 — Data Loading & Cleaning
Raw IPEDS-formatted strings (e.g., `"78%"`, `"$14,100"`, `"Yes/No"`) are parsed into proper numeric and binary types. A `Has_Platform` binary indicator and `HBCU_Flag` are engineered for use in modeling.

### Section 1 — Exploratory Data Analysis (EDA)
- Descriptive statistics (mean, median, SD, IQR) for the full sample and stratified by institution type
- **8 figures**: histograms, HBCU/PWI boxplots, KDE density plots, and a longitudinal retention trend chart (AY 2016–2024)
- Pearson correlation heatmap with top-r rankings against the primary outcome variable

### Section 2 — Formal Hypothesis Testing

| Test | H₀ | H₁ | Result |
|---|---|---|---|
| Welch's T-Test | No difference in 6-yr graduation rates (HBCU vs. PWI) | HBCUs have significantly lower rates | **Rejected** — t = -7.15, p < 0.001, Cohen's d = -2.00, gap = 23.82 pp |
| Pearson Correlation | No association between endowment per student and graduation rate | Significant positive association | **Rejected** — r = 0.49, p < 0.001 (one-tailed) |

### Section 3 — Pre-ML Diagnosis & Remediation

| Diagnostic | Finding | Action Taken |
|---|---|---|
| Missing values | Platform Adoption Year missing for 16 non-adopters | Created binary `Has_Platform` indicator |
| Outliers | Right-skewed endowment and enrollment distributions | Log transformation applied; observations retained |
| Multicollinearity | `Pct_Pell_Recipients` ↔ `Pct_Pell_Eligible` (r = 1.00) | Dropped `Pct_Pell_Eligible` from feature set |
| Multicollinearity | Financial shock ↔ Housing insecurity (r = 0.99, VIF > 100) | Created `Basic_Needs_Burden` composite |
| Multicollinearity | `Pct_FirstGen` (VIF = 53.7), `HBCU_Flag` (VIF = 14.8) | Regularization (Ridge/Lasso) planned for Phase 4 |
| Class imbalance | 30 low-retention / 21 high-retention institutions (1.43:1) | Proposed `class_weight='balanced'` + `StratifiedKFold` |
| Zero-variance feature | `Early Alert System` returns NaN correlation | Excluded from ML feature set |

### Section 4 — Summary & Capstone Implications

The evidence reinforces the central thesis:

> *The graduation and retention gaps between HBCUs and PWIs are statistically robust, structurally rooted in resource inequity, and cannot be closed through platform adoption alone. A purpose-built HBCU student success platform must account for the full structural profile of HBCU students — including basic needs burden, first-generation status, and Pell dependency — in ways that commercially dominant PWI platforms do not.*

---

## Key Findings at a Glance

| Finding | Value |
|---|---|
| Mean 6-year graduation rate gap (HBCU vs. PWI) | **23.82 percentage points** |
| Mean first-year retention gap (HBCU vs. PWI) | **10.6 percentage points** |
| Mean % Pell Recipients — HBCUs vs. PWIs | **74% vs. 35%** |
| Mean % First-Generation Students — HBCUs vs. PWIs | **54% vs. 29%** |
| Median endowment per student — HBCUs vs. PWIs | **~$5K vs. ~$14K** |
| Navigate adoption among HBCUs in sample | **~87%** — yet graduation gaps persist |
| Navigate correlation with 6-year graduation rate | **r = -0.526** (selection bias effect) |

---

## How to Run

**Requirements:** Python 3.9 or higher

**1. Get the repository files**

   **Option A — Using Git:**
   ```bash
   git clone https://github.com/DrJHM/2026-Capstone-Project---JHM.git
   cd 2026-Capstone-Project---JHM
   ```
   **Option B — No Git required:**
   Click the green **Code** button on the repository page → **Download ZIP** → unzip the folder on your computer, then continue to Step 2.

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels jupyter
```
**3. Open the notebook**
```bash
jupyter notebook Spring_2026_-_Capstone.ipynb
```

> **Note:** The notebook expects `Data_for_Revised_Capstone_Enhanced.csv` to be in the same directory. The `DATA_PATH` variable at the top of the notebook can be updated if your file is stored elsewhere.

---

## Next Steps — Phase 4 (ML Modeling)

- Train regression models (Ridge, Lasso, Random Forest, Gradient Boosting) to predict 6-year graduation rate and first-year retention
- Apply `StratifiedKFold` cross-validation with `class_weight='balanced'`
- Feature importance analysis to identify the most actionable predictors within the HBCU subsample
- Subgroup analysis comparing Navigate adopters vs. non-adopters within the HBCU cohort

---

## Author
**Joycelyn Hughes-Moulden**
DATA 801 Capstone Project | Howard University | Spring 2026

---

*This is a data science capstone project examining student success platform equity at HBCUs. All data is drawn from publicly available institutional sources.*
