# 👥 Employee Attrition Risk & Retention Cost Dashboard

An end-to-end people-analytics project built to identify which employees carry the highest attrition risk and what that risk actually costs, using Python, Excel, and Power BI — covering workforce attrition patterns, a validated Risk Score, and a rupee-denominated retention cost estimate.

---

## 📌 Short Description / Purpose

This project analyzes **4,410 employees** across three linked HR datasets to move retention planning beyond department-level guesswork. It combines Python for cleaning, exploratory analysis, and a statistically-verified Risk Score, Excel for independent validation and a ready-to-use priority list, and Power BI for an interactive executive dashboard. The goal is to show HR leadership not just who is leaving, but which employees are most likely to leave next — and what that exposure costs in rupees.

---

## 🛠️ Tech Stack

- 🐍 **Python (Pandas, Seaborn, Matplotlib)** – Data cleaning, exploratory data analysis, correlation-based feature selection, and Attrition Risk Score design
- 📗 **Microsoft Excel** – Independent validation of the Python output, a separately-built Risk Score (nested `IF`), and a High Risk Employee priority list
- 📊 **Power BI Desktop** – Power Query (ETL), data modeling, and the main executive dashboard
- 🧠 **DAX (Data Analysis Expressions)** – Attrition Rate, Average Salary, Job Satisfaction Score, and department/role ranking measures
- 📁 **File Format** – `.ipynb` for the analysis notebook, `.xlsx` for the Excel workbook, `.png` for the dashboard preview

---

## 📂 Data Source

An internal-style HR dataset split across three linked files — general employee records, an employee self-reported satisfaction survey, and a manager-rated performance survey — covering 4,410 employees, joined on `EmployeeID`.

---

## ✨ Features / Highlights

### 🎯 Business Problem

HR has attrition data but no way to prioritize retention effort. Leadership can't easily answer:

- Which employees are actually at risk of leaving, not just which departments look bad on paper?
- Are commonly-assumed attrition drivers (department size, age bracket) actually correct, or just a count effect?
- What does losing these employees cost the business, in rupees?

### 🎯 Goal of the Dashboard

To deliver an interactive Power BI report that:

- Tracks core workforce KPIs (headcount, attrition rate, salary, satisfaction) with live filtering
- Surfaces attrition patterns by department, job role, and age group
- Is backed by a Risk Score that was statistically validated against real attrition outcomes, not assumed

### 🖥️ Walkthrough of Key Visuals

**HR Analytics Dashboard**
- KPI cards: Total Employees (4,410), Active Employees, Attrition Count (711), Attrition Rate (16.1%), Average Salary (₹65K), Job Satisfaction Score (2.7)
- Bar chart: Employee Attrition by Department — Research & Development has the highest raw count (453), though the rate-based view tells a different story
- Bar chart: Employee Attrition by Job Role — Sales Executive is the most affected role (165 exits)
- Donut chart: Employee Attrition by Age Group
- Gauge: Overall attrition rate against a 25% reference band
- Insights and Recommendation panel, updating with the applied filters

### 💡 Business Impact & Insights

- **Count vs. rate — the department story flips:** Research & Development shows the highest *number* of employees leaving (453), which is the standard read on this data. But by *rate*, Human Resources has the highest attrition at 30.2% — more than double R&D's 15.7%. HR is a small department (189 people), so it doesn't show up in a raw-count chart, but proportionally it is the most at-risk group in the company.
- **Age risk is concentrated younger than assumed:** The 18–25 age band has a 35.8% attrition rate — nearly double the 26–35 band (19.1%), which is often cited as the highest-risk group. Retention effort aimed at the wrong age bracket would miss the real problem.
- **A validated Risk Score, not a guess:** Five factors were kept in the score only after checking their actual correlation with attrition (Age, Total Working Years, Years With Current Manager, Job Satisfaction, Environment Satisfaction — all in the -0.10 to -0.17 range); weaker factors like Work-Life Balance and Job Involvement were dropped. The resulting High Risk tier shows a **53.4% real attrition rate**, against 11.4% for the Low Risk tier — a 4.7x gap that confirms the score is actually predictive, not just a plausible-looking formula.
- **₹9.15 crore in quantified exposure:** Applying a standard 6-months-salary replacement-cost assumption to the 219 employees (5% of the workforce) flagged as High Risk puts potential retention cost at approximately ₹9.15 crore — turning an abstract risk score into a number finance can act on.
- **A cross-tool bug caught in validation:** Rebuilding the Risk Score independently in Excel initially produced a different High Risk count than Python. The cause was Excel treating blank survey responses as zero, which silently inflated risk scores for employees with missing data. Adding an `ISNUMBER` guard fixed it — a reminder that even a working formula can be quietly wrong until it's checked against a second source.

---

## 📸 Screenshots / Demos

**HR Analytics Dashboard**
![HR Analytics Dashboard](page1_hr_analytics_dashboard.png)

🎥 **Watch the interactive dashboard demo (with live slicer filtering):** [LinkedIn Post Link]

*Note: The Power BI file (.pbix) is not included in this repository, to protect the dashboard design and DAX logic. A screenshot and video walkthrough are provided instead — feel free to reach out if you'd like to discuss the implementation.*

---

## 📁 Repository Structure

```
employee-attrition-risk-dashboard/
├── README.md
├── HR_Attrition_EDA_RiskScoring.ipynb
├── HR_Attrition_Analysis.xlsx
└── page1_hr_analytics_dashboard.png
```

---

## 🔗 Connect

**Ankit Bijalwan**
If you're working in people analytics or HR technology and have feedback on this project, I'd love to hear it — feel free to reach out on [LinkedIn](https://www.linkedin.com/in/bijalwanankit).
