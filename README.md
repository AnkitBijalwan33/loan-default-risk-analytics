# 🏦 Loan Default Risk Analytics Dashboard

An end-to-end BFSI analytics project built to identify high-risk loan applicants for **Home Credit Group**, using SQL, Python, and Power BI — covering portfolio health, risk segmentation, demographic patterns, and a custom rule-based risk-scoring model.

---

## 📌 Short Description / Purpose

This project analyzes **307,511 loan applications** from Home Credit Group (a global consumer lending company) to uncover the key drivers of loan default. It combines SQL for data cleaning, Python for exploratory analysis and risk-score design, and Power BI for an interactive 4-page dashboard. The goal is to help credit risk teams flag high-risk applicants early — using a simple, explainable model rather than a black-box machine learning approach.

---

## 🛠️ Tech Stack

The project was built using the following tools and technologies:

- 🗄️ **MySQL Workbench** – Data cleaning, column selection, and derived-column logic (age, employment years, income-to-credit ratio)
- 🐍 **Python (Pandas, Seaborn, Matplotlib)** – Exploratory Data Analysis, correlation analysis, and rule-based Risk Score design
- 📊 **Power BI Desktop** – Main dashboard and visualization platform
- 🧠 **DAX (Data Analysis Expressions)** – Calculated measures, conditional formatting gradients, cumulative % (Pareto logic), and bookmark-driven view toggling
- 📝 **Data Modeling** – Single-table model (`Final_Loan_Data`) with calculated columns for age group, credit group, ratio group, and risk category
- 📁 **File Format** – `.sql` for queries, `.ipynb` for analysis, `.pbit` for the Power BI template, `.png` for dashboard previews

---

## 📂 Data Source

**Source:** [Home Credit Default Risk – Kaggle](https://www.kaggle.com/c/home-credit-default-risk)

The dataset (`application_train.csv`) contains 307,511 loan applications from Home Credit Group, a multinational lending company that serves customers with limited or no traditional credit history ("thin-file" borrowers). Of the original 122 columns, 21 relevant fields were selected — covering applicant demographics, income, loan details, region rating, and three external credit bureau scores (`EXT_SOURCE_1/2/3`).

---

## ✨ Features / Highlights

### 🎯 Business Problem

Home Credit Group faces two competing risks on every loan decision:
1. **Approving risky applicants** → loan defaults → direct financial loss
2. **Rejecting reliable applicants** → lost interest income → customers go to competitors

The company had applicant-level data (income, education, job type, region, credit bureau scores) but no clear, explainable way to answer:
- Which applicant segments are most likely to default?
- Is the company's own region-risk rating actually accurate?
- Can a simple, non-ML rule flag high-risk applicants early?

### 🎯 Goal of the Dashboard

To deliver a 4-page interactive Power BI report that:
- Breaks down default risk across loan type, income, education, family status, occupation, age, region, and gender
- Validates whether existing company assumptions (e.g., region ratings) hold up against the data
- Introduces a transparent, rule-based Risk Score that flags high-risk applicants without requiring ML infrastructure

### 🖥️ Walkthrough of Key Visuals

**Page 1 — Portfolio Health**
- KPI cards: Total Applicants (307,511), Default Rate (8.07%), Total Loan Amount, High Risk Count (1,504)
- Pareto chart: Default rate by occupation, with cumulative % — applicants with an "Unknown" occupation show the highest default rate (33.5%)
- Donut chart: Cash loans (90.5%) vs. Revolving loans (9.5%), with Cash loans showing a higher default rate (8.3% vs 5.5%)

**Page 2 — Risk Segmentation**
- Bar chart: Default rate by education level — ranges from 1.9% (Academic Degree) to 10.6% (Lower Secondary)
- Bookmark-toggled view: a summary bar chart of Family Status default rates, switchable to a full **Family Status × Education Level matrix** with conditional-formatting heatmap
- Donut chart: Income type distribution — 51.6% of applicants are salaried ("Working")

**Page 3 — Demographics & Regional Analysis**
- Line chart: Default rate declines steadily with age, from 11.4% (20–30) to 4.9% (60–70)
- Bar charts: Default rate by Region Rating (4.8% → 11.1%) and by Gender (Male 10.1% vs Female 7.0%)
- **Age Group × Region Rating matrix**: reveals that applicants aged 20–30 in Region Rating 3 default at **15.94%** — nearly double the portfolio average, and higher than either factor alone

**Page 4 — Financial Behavior & Risk Scoring**
- Bar charts: Default rate by Credit Amount group and Income-to-Credit Ratio group — both show a non-linear, U-shaped pattern where mid-range values carry more risk than the extremes
- Ribbon chart: Applicant distribution across credit-score bands, segmented by default status
- **Gauge chart**: the flagship visual — showing the Risk Score's flagged "High Risk" segment (23.8% default rate) against the portfolio average (8.07%), a **3x risk multiplier**

### 💡 Business Impact & Insights

- **Risk Score validation:** The custom rule (low credit score + young age + high-risk region) flags just 0.5% of applicants, but that group defaults at **3x** the portfolio average — proving a simple, explainable rule can meaningfully sharpen underwriting decisions without machine learning.
- **Compounded risk:** Individual risk factors understate real risk when combined — age and region together nearly double the expected default rate.
- **Rating system validation:** Home Credit's existing region-rating system is statistically accurate and should be retained, not replaced.
- **Non-linear financial risk:** Larger loans and higher income-to-credit ratios are not automatically safer — mid-range segments need the most scrutiny, challenging a common assumption in credit risk.

---

## 📸 Screenshots / Demos

| Page | Preview |
|---|---|
| Portfolio Health | `screenshots/page1_portfolio_health.png` |
| Risk Segmentation | `screenshots/page2_risk_segmentation.png` |
| Demographics & Regional Analysis | `screenshots/page3_demographics_regional.png` |
| Financial Behavior & Risk Scoring | `screenshots/page4_financial_behavior.png` |

🎥 **Watch the interactive dashboard demo (with live slicer filtering):** [LinkedIn Post Link]

*Note: The Power BI file (.pbit) is included in this repo but requires the source CSV to refresh data on load.*

---

## 📁 Repository Structure

```
loan-default-risk-analysis/
├── README.md
├── SQL_query_file.sql
├── BFSI_Risk.ipynb
├── Loan_Default_Risk_Dashboard.pbit
└── screenshots/
    ├── page1_portfolio_health.png
    ├── page2_risk_segmentation.png
    ├── page3_demographics_regional.png
    └── page4_financial_behavior.png
```

---

## 🔗 Connect

If you're working in BFSI / risk analytics and have feedback on this project, I'd love to hear it — feel free to reach out on [LinkedIn].
