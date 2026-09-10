# 📊 HR Operations & Executive Payroll Intelligence System

An end-to-end HR Operations and Payroll Analytics solution built using **Advanced Excel** and **Power Query**. This project applies a documented, formula-based payroll simulation model on top of a real HR dataset, then transforms the result into automated payslips, an executive KPI dashboard, and a data quality audit pipeline.

---

## 📌 Project Overview
* **Base Dataset:** IBM HR Analytics Employee Attrition & Performance (1,470 real employee records: department, job role, hourly rate, overtime status, and other HR attributes).
* **Important note on payroll figures:** the source dataset does not include detailed payroll data (no base salary breakdown, allowances, tax, or social insurance columns). All payroll components in this project — Overtime Pay, Allowances, Gross Salary, Social Insurance, Income Tax, and Net Salary — are calculated using a **documented formula-based simulation model**, applied to each employee's real `HourlyRate` and `OverTime` status from the source data. These are illustrative calculated figures, not real historical payroll records.
* **Core Objective:** demonstrate an automated payroll calculation engine and executive HR reporting system — the same logic and structure used in real payroll systems — built entirely with Excel and Power Query.
* **Architecture Workflow:** Raw Data → Power Query Cleaning → Payroll Calculation Model (documented formulas) → Executive Dashboard & Automated Payslips.

---

## 🧮 Payroll Calculation Model (Simulation Logic)
Since the source dataset provides only `HourlyRate` and `OverTime` (Yes/No) as real payroll-relevant fields, the following simplified, consistent formulas were applied to every employee to simulate a realistic payroll structure:

| Component | Formula (applied uniformly to all employees) |
|---|---|
| Overtime Hours | 15 hours/month if `OverTime = Yes`, otherwise 0 |
| Overtime Pay | `Hourly_Rate × Overtime Hours` |
| Allowances | fixed percentage of base pay (illustrative) |
| Gross Salary | Base Pay + Allowances + Overtime Pay |
| Social Insurance | fixed percentage of Gross Salary (illustrative, not tied to any specific country's real statutory rate) |
| Income Tax | fixed percentage of Gross Salary (illustrative) |
| Net Salary | Gross Salary − Social Insurance − Income Tax |

This is a generic illustrative deduction model, not based on any specific country's actual tax or insurance law — it demonstrates the calculation logic and dashboard/payslip structure of a payroll system rather than a legally accurate one.

---

## 🛠️ Tech Stack & Key Capabilities
* **Power Query:** data cleaning, custom column transformations, and automated ETL workflows.
* **Advanced Excel Functions:** dynamic lookup and conditional logic (`XLOOKUP`, `IFERROR`, `COUNTIF`, `COUNTBLANK`, `ROUND`).
* **Interactive Visualization:** PivotTables, PivotCharts, Slicers, dynamic KPI cards.
* **Data Governance & QA:** automated audit log tab (`Data_Quality`) verifying zero duplicates, non-null values, and 100% payroll calculation reconciliation (Gross − Deductions = Net for every employee).

---

## 📂 Repository Structure
```text
├── HR_Executive_Payroll_System.xlsx        # Complete Excel system (dashboard, payslip, QA)
├── EXECUTIVE_PAYROLL_&_HR_OPERATIONS.pdf   # Exported executive report
└── README.md                               # Project documentation
```

---

## 🔑 Key Features
* **Executive Dashboard:** dynamic visualization of Gross Payroll, Net Salary distribution, and departmental cost breakdowns.
* **Automated Payslip Generator:** interactive employee lookup outputting earnings, itemized deductions, and net pay, calculated live from the model above.
* **Data Quality Governance (DQ/QA):** automated checks ensuring data type compliance, zero missing fields in the source HR data, and full payroll reconciliation across all 1,470 employees.

## 👤 Author
**Name:** Fathallah Saied Abou Eid
**Specialization:** Data Analytics | HR Operations & Payroll Systems
