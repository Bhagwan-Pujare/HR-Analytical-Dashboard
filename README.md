# 📊 HR Attrition Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-0078D4?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Data_Modeling-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

An interactive, data-driven **Power BI Dashboard** designed to track, analyze, and predict employee attrition trends. This business intelligence solution transforms complex HR Information System (HRIS) data into actionable retention strategies for leadership and HR teams.

---

## 🎯 Project Overview & Objectives

High employee turnover is disruptive and financially taxing. This analytics dashboard provides a granular breakdown of workforce demographics, job performance metrics, and cultural parameters to uncover the core drivers behind employee attrition.

### Key Business Questions Answered:
* **What** is our current headcount versus attrition count, and what is the overall attrition rate?
* **Who** is leaving the organization? (Analysis by Age, Gender, Marital Status, and Education).
* **Where** is turnover most volatile? (Analysis by Department, Job Role, and Job Level).
* **Why** are employees resigning? (Correlation with Job Satisfaction, Environment Satisfaction, Work-Life Balance, and Income).

---

## 📊 Key Features & Analytical Views

* **Executive Summary KPIs:** Real-time metrics showing Total Employee Count, Active Employees, Attrition Count, and Attrition Rate.
* **Demographic Breakdown:** Interactive visuals analyzing attrition by demographic cohorts (e.g., Age Groups, Gender distribution, and Education fields).
* **Job & Department Patterns:** Matrices and charts contrasting attrition across key departments (R&D, Sales, HR) and specialized job roles.
* **Sentiment & Satisfaction Metrics:** Scatter plots and heat maps cross-referencing turnover against Employee/Environment Satisfaction scores and Work-Life Balance ratings.
* **Compensation & Tenure Analysis:** Correlation tracking between attrition rates and salary bands, years at the company, and stock options.

---

## 📸 Dashboard Preview

> 💡 *Tip: Replace the placeholder below with an actual screenshot or GIF of your report once it is pushed to your repository.*

![HR Attrition Dashboard Overview](https://raw.githubusercontent.com/placehold-it/private/master/assets/images/placeholder.png)

---

## 🛠️ Data Architecture & Modeling

The project employs a structured data pipeline within Power BI:
* **Extraction & Transformation (ETL):** Built via **Power Query** to handle conditional formatting, clean null spaces, classify age/income groups, and optimize data types.
* **Data Model:** Clean, relational schema structured for optimized analytical performance.
* **Calculations:** Advanced DAX (Data Analysis Expressions) utilized to generate dynamic metrics.

### Key DAX Measures Implemented:

```dax
// Total Employee Count
Total Employees = COUNT('HR Analytics'[EmployeeID])

// Total Resigned Employees 
Attrition Count = CALCULATE(COUNT('HR Analytics'[EmployeeID]), 'HR Analytics'[Attrition] = "Yes")

// Dynamic Attrition Rate (%)
Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)

// Currently Active Workforce
Active Employees = [Total Employees] - [Attrition Count]
