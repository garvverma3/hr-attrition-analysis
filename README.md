# HR Attrition Analysis

A comprehensive end-to-end data analytics project analyzing employee turnover across 1,470 individuals using Google Sheets, Python, and Tableau — built as part of my Data Visualization & Analytics (DVA) course.

**[Live Project Site](https://hr-attrition-analysis.vercel.app) · [Tableau Dashboard](https://public.tableau.com/app/profile/garv.verma4431/viz/HRAttritionAnalysis-GarvVerma/Story1?publish=yes)**

---

## Overview

Using the IBM HR Analytics dataset, this project identifies the primary drivers of employee attrition through a three-phase analytical pipeline — data cleaning in Google Sheets, exploratory data analysis in Python, and interactive dashboard storytelling in Tableau.

**Dataset:** IBM HR Analytics Employee Attrition & Performance (Kaggle)
**Records:** 1,470 employees · 35 columns · 0 missing values

---

## Key Findings

| Finding | Insight |
|---|---|
| Overall attrition rate | **16.1%** (237 of 1,470 employees) |
| Highest attrition department | **Sales at 20.6%** |
| Overtime risk | Overtime employees are **3x more likely** to leave (30% vs 10%) |
| Tenure risk | Year 0 employees have a **36% attrition rate** |
| High earner retention | Salary outliers have only **4.4% attrition** |
| Top drivers | OverTime · Low Tenure · Low Job Level · Low Monthly Income |

---

## Tools & Methods

### Google Sheets
- Data import, cleaning, and null value validation (`COUNTBLANK`, `IFERROR`)
- Attrition rate by department using `COUNTIFS`
- Salary band lookup with `VLOOKUP`, `XLOOKUP`, `INDEX-MATCH`
- Pivot table: attrition by JobRole × Gender × OverTime
- Conditional formatting (RAG risk scoring)
- What-if analysis: Goal Seek on target attrition rate
- Interactive dashboard with slicers

### Python (Pandas, NumPy, Matplotlib, Seaborn)
- Full EDA pipeline: load → clean → analyze → visualize
- Dropped zero-variance columns (`EmployeeCount`, `StandardHours`, `Over18`)
- Encoded `Attrition` as binary target variable
- Correlation heatmap — top attrition drivers identified
- Outlier detection using IQR method on `MonthlyIncome`
- Distribution analysis — right-skewed income & tenure confirmed
- Rolling attrition rate by tenure (window function)
- Univariate, bivariate, and multivariate visualizations

### Tableau
- Calculated field: `Attrition Rate = SUM([Attrition Num]) / COUNT([Employee Number])`
- LOD expressions: `FIXED`, `INCLUDE`, `EXCLUDE`
- Parameter: salary threshold slider
- Sets: High Risk Employees, Overtime Workers
- Bins (YearsAtCompany), Hierarchy (Department → JobRole), Table calculations
- Interactive dashboard with cross-sheet filters
- 3-point storyboard: Overview → Root Causes → Recommendations
- Published on Tableau Public

---

## Project Structure

```
hr-attrition-analysis/
├── data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv   # Original dataset
├── notebooks/
│   └── hr_eda.ipynb                              # Python EDA notebook
├── screenshots/
│   ├── sheets_dashboard.png                      # Google Sheets dashboard
│   └── tableau_dashboard.png                     # Tableau dashboard
└── README.md
```

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/garvverma3/hr-attrition-analysis

# Open the notebook in Jupyter or Google Colab
# Upload WA_Fn-UseC_-HR-Employee-Attrition.csv and run all cells
```

---

## Links

- **Live Site:** https://hr-attrition-analysis.vercel.app
- **Tableau Public:** https://public.tableau.com/app/profile/garv.verma4431/viz/HRAttritionAnalysis-GarvVerma/Story1
- **Dataset:** https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

---

## Author

**Garv Verma** · 3rd Year B.Tech CS (AI) · Newton School of Technology, Rishihood University

[GitHub](https://github.com/garvverma3)
