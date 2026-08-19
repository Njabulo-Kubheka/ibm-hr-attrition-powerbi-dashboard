# IBM HR Analytics — Employee Attrition Power BI Dashboard

An interactive Power BI dashboard analysing IBM's HR employee attrition dataset — identifying the key drivers of employee attrition and presenting findings through professional business intelligence visualisations. Built as the third instalment of a multi-tool analytics portfolio covering the same dataset across Python, Excel, and Power BI.

📊 **Live Dashboard:** [View on Power BI Service](#) *(replace with your published link)*

---

## Overview

Employee attrition costs businesses significantly — recruiting and onboarding a replacement can cost up to twice an employee's annual salary. This dashboard answers one core business question:

**Why are employees leaving, and what can the business do about it?**

---

## Dataset

| Property | Detail |
|---|---|
| Source | IBM HR Analytics Employee Attrition & Performance (Kaggle) |
| Records | 1,470 employees |
| Features | 35 columns |
| Missing values | 0 |

---

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard development and data visualisation |
| DAX | Custom measures — Attrition Rate, Age Group calculated column |
| Power Query | Data loading and transformation |

---

## Dashboard Features

**4 KPI Cards**
- Total Employees — 1,470
- Attrition Rate — 16.1%
- Average Monthly Income — R6,500
- Average Years at Company — 7.01

**4 Interactive Charts**
- Attrition by Department — horizontal bar chart
- Attrition by Age Group — horizontal bar chart with DAX-calculated age bands
- Average Monthly Income vs Attrition — comparison bar chart
- Attrition by Overtime Status — clustered bar chart

**3 Interactive Slicers**
- Department
- Gender
- Job Role

All slicers filter every visual on the dashboard simultaneously — allowing stakeholders to explore attrition patterns for any combination of department, gender, and role.

---

## DAX Measures and Calculated Columns

**Attrition Rate measure:**
```
Attrition Rate = 
DIVIDE(
    COUNTROWS(FILTER('Table', 'Table'[Attrition] = "Yes")),
    COUNTROWS('Table')
)
```

**Age Group calculated column:**
```
Age Group = 
SWITCH(
    TRUE(),
    'Table'[Age] >= 18 && 'Table'[Age] <= 27, "18-27",
    'Table'[Age] >= 28 && 'Table'[Age] <= 37, "28-37",
    'Table'[Age] >= 38 && 'Table'[Age] <= 47, "38-47",
    'Table'[Age] >= 48 && 'Table'[Age] <= 57, "48-57",
    "58+"
)
```

---

## Key Findings

1. **16.1% overall attrition rate** — 237 out of 1,470 employees left
2. **Research & Development** has the highest attrition by department
3. **Employees aged 28-37** leave the most — early career retention is the biggest challenge
4. **Income gap** — employees who left earned R4,787/month vs R6,833 for those who stayed — a R2,046 difference
5. **Overtime doubles attrition risk** — 30.5% of overtime workers left vs 10.4% who don't work overtime

---

## Business Recommendations

- Review compensation for Laboratory Technicians and Sales Executives
- Reduce overtime demands especially in Research & Development
- Improve onboarding and early engagement for employees in their first year
- Monitor job satisfaction scores regularly as an early warning system

---

## Multi-Tool Portfolio

This dashboard is part of a three-tool analysis of the same dataset:

| Tool | Project | Link |
|---|---|---|
| Python / Pandas | Exploratory Data Analysis | [Kaggle Notebook](https://www.kaggle.com/code/njabulokubheka/ibm-hr-attrition-analysis-njabulo-kubheka) |
| Microsoft Excel | Interactive PivotTable Dashboard | [GitHub](https://github.com/Njabulo-Kubheka/hr-attrition-excel-dashboard) |
| Power BI | This dashboard | This repo |

Building the same analysis across three tools demonstrates tool versatility — the ability to deliver the same business insight using whichever BI tool a stakeholder or employer uses.

---

## Author

**Njabulo Kubheka**
BCom Information Systems — University of the Western Cape
[LinkedIn](https://www.linkedin.com/in/njabulo-kubheka) | [GitHub](https://github.com/Njabulo-Kubheka) | [Kaggle](https://www.kaggle.com/njabulokubheka)
