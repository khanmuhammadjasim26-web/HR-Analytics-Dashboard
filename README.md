# 👥 End-to-End HR Analytics Dashboard (Power BI)

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-2563EB?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Power Query](https://img.shields.io/badge/Power_Query-ETL_Transformation-10B981?style=for-the-badge)](https://powerbi.microsoft.com/)
[![Dataset](https://img.shields.io/badge/Dataset-1%2C470_Employees-8B5CF6?style=for-the-badge)](https://github.com/khanmuhammadjasim26-web/HR-Analytics-Dashboard)
[![Live Site](https://img.shields.io/badge/Live_Site-GitHub_Pages-000000?style=for-the-badge&logo=github)](https://khanmuhammadjasim26-web.github.io/HR-Analytics-Dashboard/)

> **Project by Muhammad Jasim**  
> 🌐 **Live Web Showcase:** [https://khanmuhammadjasim26-web.github.io/HR-Analytics-Dashboard/](https://khanmuhammadjasim26-web.github.io/HR-Analytics-Dashboard/)

---

## 📌 Project Overview & Purpose

Human Resources departments often struggle with fragmented employee data spread across disparate spreadsheets, making it difficult to detect attrition drivers, track promotion eligibility, and plan organizational restructuring.

This project delivers an **end-to-end HR Analytics & Workforce Intelligence Dashboard** built in **Microsoft Power BI**. It extracts, cleans, models, and transforms complex, multi-source HR data into actionable business intelligence to empower HR leaders, executives, and department managers to make data-driven workforce decisions.

---

## 🎯 Key Business Objectives

1. **Workforce Demographics & Structure:** Track total headcount (1,470 employees), gender diversity, department allocations, and role hierarchy.
2. **Attrition & Turnover Root-Cause Analysis:** Diagnose key retention risks linked to **OverTime workload**, **business travel frequency**, **distance from home**, and **workplace satisfaction scores**.
3. **Promotion Pipeline Management:** Proactively identify and surface the **72 employees due for promotion** to optimize talent development and reward top performers.
4. **Retrenchment & Layoff Risk Mitigation:** Monitor **117 employees flagged for retrenchment risk** across business units with operational decision tables.
5. **Performance & Satisfaction Diagnostics:** Benchmark high-rated vs. low-rated employee ratios, job involvement levels, and work-life balance indices.

---

## 📊 Dashboard Architecture & Report Pages

The Power BI workbook (**`Power Bi Practice Dashboard.pbix`**) is structured into 3 interactive reporting pages:

```
Power Bi Practice Dashboard.pbix
├── 🏠 Page 1: Home (Executive Overview & Demographics)
├── ⚡ Page 2: Action (Promotion Pipeline & Retrenchment Watchlist)
└── 📋 Page 3: Details (Deep-Dive Workforce & Performance Analytics)
```

### 🏠 Page 1: Home (Executive Overview)
* **High-Level KPIs:** Total Headcount (`1,470`), Male vs. Female distribution, Promotion readiness (`Due for Promotion` vs `Not Due`).
* **Visuals & Breakdowns:**
  * Department Headcount share (Research & Development, Sales, Human Resources).
  * Workforce volume by Job Role.
  * Job Satisfaction rating distribution.
  * OverTime contribution split.

### ⚡ Page 2: Action (Talent Management Hub)
* **Operational Rosters:**
  * **Promotion Candidates Table:** Actionable list of 72 eligible employees sorted by service tenure and years since last promotion.
  * **Retrenchment Watchlist Table:** Risk roster displaying compensation, role level, and performance metrics.
* **Interactive Slicers:** Dynamic filtering by Gender, Department, and Service Years.

### 📋 Page 3: Details (Granular Diagnostics)
* **Performance Analysis:** Ratio cards for `% of High Rated Employees` vs. `% of Low Rated Employees`.
* **Workload & Tenures:** OverTime impact distributions, service year brackets, and role-by-role compensation matrices.

---

## 📐 Data Architecture & Modeling

### 📁 Datasets Used
| Dataset | Rows | Columns | Primary / Join Key | Purpose |
| :--- | :---: | :---: | :--- | :--- |
| **`HR Analytics Data.csv`** | 1,470 | 35 | `EmployeeNumber` | Primary fact table (Demographics, Satisfaction, Compensation, Attrition, Tenure) |
| **`HR employee data.csv`** | 1,470 | 2 | `EmployeeNumber` $\rightarrow$ `Emplyee name` | Employee dimension mapping IDs to names |
| **`data.csv Retrenchment.csv`** | 1,470 | 2 | `Emplyee name` | Retrenchment risk indicator (117 flagged records) |
| **`data.csv promomtion.csv`** | 72 | 2 | `Emplyee name` | Promotion pipeline roster (72 eligible candidates) |

---

## 🧮 DAX Measures (`All Measures` Table)

A dedicated measure table was constructed with 15 custom DAX calculations:

| # | Measure Name | Purpose |
| :-: | :--- | :--- |
| 1 | `Total Emp` | Total headcount of employees in context |
| 2 | `Male` | Total male employee count |
| 3 | `% Male` | Percentage share of male workforce |
| 4 | `Female` | Total female employee count |
| 5 | `% Female` | Percentage share of female workforce |
| 6 | `Due for Promotions` | Count of employees eligible for promotion |
| 7 | `% Due for Promotion` | Percentage of workforce due for promotion |
| 8 | `Not Due` | Employees not currently eligible for promotion |
| 9 | `% Not Due` | Percentage of workforce not due for promotion |
| 10 | `Will be Retrenched` | Count of employees at risk of retrenchment |
| 11 | `% will be Retreanched` | Percentage share of retrenchment risk |
| 12 | `On Service` | Count of active personnel currently on service |
| 13 | `% On Service` | Percentage share of active service personnel |
| 14 | `% of High Rated Employees` | Proportion of top performance rating staff |
| 15 | `% of Low Rated Employee` | Proportion of low performance rating staff |

---

## 💡 Key Business Insights Discovered

* **Workforce Scale:** Total analyzed workforce of **1,470 employees** across 3 core departments (Research & Development: 65.4%, Sales: 30.3%, Human Resources: 4.3%).
* **Attrition Risk Drivers:** Employees working **OverTime** and employees with frequent **Business Travel** exhibit significantly higher turnover rates compared to standard staff.
* **Promotion Pipeline:** **72 employees (4.9%)** are due for promotion, representing key talent retention opportunities.
* **Organizational Risk:** **117 employees (7.9%)** are identified on the retrenchment watchlist, enabling structured workforce optimization.

---

## 🛠️ How to Open and Refresh the Project

1. **Download the Project:**
   * Clone this repo or download **`Power Bi Practice Dashboard.pbix`** and the CSV files.
2. **Open in Power BI Desktop:**
   * Launch **Power BI Desktop** (Free download from Microsoft).
   * Open `Power Bi Practice Dashboard.pbix`.
3. **Refresh Local Data Source Paths:**
   * In Power BI Desktop, click **Home** &rarr; **Transform Data** &rarr; **Data source settings**.
   * Select the data source and click **Change Source**.
   * Browse to the folder where you saved the CSV files on your machine.
   * Click **Close & Apply** to refresh all visuals with local data.

---

## 👨‍💻 Author & Contributions

* **Created by:** [Muhammad Jasim](https://github.com/khanmuhammadjasim26-web)
* **Repository:** [https://github.com/khanmuhammadjasim26-web/HR-Analytics-Dashboard](https://github.com/khanmuhammadjasim26-web/HR-Analytics-Dashboard)
* **Live Showcase:** [https://khanmuhammadjasim26-web.github.io/HR-Analytics-Dashboard/](https://khanmuhammadjasim26-web.github.io/HR-Analytics-Dashboard/)

---
*Feel free to star ⭐ this repository if you find this HR Analytics Dashboard useful!*
