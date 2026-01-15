# Healthcare Revenue & Medical Attendance Analytics Dashboard

**Power BI | SQL | Data Modeling | Healthcare Analytics**

---

## Project Overview

This project presents an end-to-end analytics solution designed for a healthcare organization in Switzerland. The objective is to provide executive-level visibility into medical attendances and revenue performance across key healthcare service segments, enabling data-driven financial and operational decision-making.

The solution integrates clinical and financial data, compares actual versus estimated revenue, and highlights performance deviations through clear visual indicators.

> **Note:** All data used in this project is fictional and intended solely for demonstration purposes, due to confidentiality requirements.

---

## Business Context

Healthcare organizations operate across multiple medical service lines, each generating significant operational volume and financial impact. In this scenario, the organization provides services through the following segments:

- **Emergency**  
- **Hospitalization**  
- **Surgery**  
- **Laboratory**  

Senior management requires a consolidated, reliable, and timely view to understand:

- How many medical attendances are performed  
- How much revenue is generated per segment  
- Whether actual revenue aligns with monthly estimates or projections  

---

## Business Problem

The organization faces challenges due to:

- Fragmented data sources (clinical systems, administrative systems, laboratory systems)  
- Manual and delayed comparison of actual versus projected revenue  
- Lack of a single, interactive view to identify financial deviations early  

As a result, financial decision-making is reactive rather than proactive.

---

## Project Objectives

The main goals of this project are to:

- Centralize medical attendance and revenue data  
- Analyze attendances and revenue (CHF) by medical service segment  
- Compare actual versus estimated revenue on a monthly basis  
- Clearly identify overperformance and underperformance  
- Provide reliable insights for finance, medical management, and planning teams  

---

## Key Metrics & KPIs

- **Total medical attendances**  
- **Actual revenue (CHF)**  
- **Estimated revenue (CHF)**  
- **Revenue variance (absolute and percentage)**  
- **Performance status (above or below estimate)**  

---

## Data Model

The solution is built using a **star schema**, optimized for analytical performance and Power BI reporting.

### Fact Tables
- **Medical Attendances** (volume and actual revenue)  
- **Monthly Revenue Estimates**  

### Dimension Tables
- **Medical Service**  
- **Date**  

This structure ensures scalability, clarity, and efficient filtering across time and service segments.

---

## Data Sources

- Clinical system extracts (simulated)  
- Financial planning projections (Excel/CSV format)  
- SQL transformations for aggregation and comparison logic  

---

## Dashboard Features

The Power BI dashboard includes:

- Executive KPI cards for high-level monitoring  
- Revenue comparison by medical service segment  
- Monthly trend analysis  
- Matrix table with conditional formatting to highlight performance  
- Consistent red and white corporate color palette  

The dashboard is designed to be **intuitive, clean, and suitable for executive consumption**.

---

## Business Value

This solution enables:

- Immediate visibility into financial performance  
- Early detection of negative deviations  
- Clear distinction between volume-driven and value-driven issues  
- Improved budget control and resource optimization  
- Data-driven strategic decision-making  

---

## Tools & Technologies

- Power BI  
- SQL  
- Star Schema Data Modeling  
- Excel / CSV (simulated sources)  

---

## Disclaimer

All data presented in this project is **fictional** and used exclusively for demonstration purposes, in compliance with confidentiality requirements.

---

## Author

**Anna E. Parra R.**  
_Data Analytics | Business Intelligence | Process Optimization_
Transforming clinical and financial data into actionable insights for healthcare decision-makers.

