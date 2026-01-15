Business Case
Medical Attendance Revenue Analytics Dashboard
Industry: Healthcare
Country: Switzerland
Currency: CHF (Swiss Franc)

1. Business Context
A healthcare provider operating in Switzerland delivers medical services across multiple care domains, including:
•	Emergency Care
•	Inpatient Hospitalization
•	Surgical Services
•	Laboratory Services
Each domain represents a critical contributor to both clinical outcomes and financial performance. Ensuring transparency and control over service volumes and revenue generation is essential for sustainable operations in a highly regulated healthcare environment.
Senior management requires a single, trusted analytical view to understand:
•	Service utilization levels
•	Revenue generated per care domain
•	Alignment between actual revenues and monthly financial forecasts

2. Current Challenges
Despite the availability of data, the organization faces several structural challenges:
•	Medical attendance and billing data is dispersed across multiple systems (clinical, administrative, laboratory).
•	Reporting processes are fragmented and lack standardization.
•	Monthly performance comparisons against financial forecasts are manual, time-consuming, and available only after month-end close.
As a result, management lacks timely answers to key strategic questions:
•	Which care domains are driving revenue growth?
•	Are financial targets being met consistently?
•	Are deviations driven by service volume, pricing, or case mix?
Impact:
Decision-making is predominantly reactive, relying on static reports rather than real-time, insight-driven analytics.

3. Objective of the Business Case
The objective is to design and implement a centralized analytics solution that enables:
•	Transparent analysis of medical attendance volumes and revenue (CHF) by care domain
•	Systematic comparison of actual versus forecasted revenues on a monthly basis
•	Immediate identification of overperformance and underperformance
The solution delivers reliable, decision-ready insights for:
•	Executive management
•	Finance and controlling
•	Medical leadership and operational planning

4. Key Performance Indicators (KPIs)
a) Service Utilization
•	Total number of medical attendances
•	Breakdown by care domain:
o	Emergency
o	Hospitalization
o	Surgery
o	Laboratory
b) Revenue Performance (CHF)
•	Actual revenue per domain and month
•	Forecasted revenue per domain and month
c) Performance vs Forecast
•	Absolute and percentage variance
•	Visual performance indicator:
o	Actual greater than or equal to forecast
o	Actual below forecast

5. Proposed Data Model
5.1 Logical Data Structure
Dimension: medical_services
Attribute	Description
service_id	Service identifier
service_name	Emergency, Hospitalization, Surgery, Laboratory
Fact Table: medical_attendances
Attribute	Description
attendance_id	Attendance identifier
service_id	Service type
attendance_date	Date of service
patient_id	Patient identifier
amount_chf	Billed amount (CHF)
Fact Table: monthly_estimates
Attribute	Description
year	Fiscal year
month	Fiscal month
service_id	Service type
estimated_amount_chf	Monthly revenue forecast

6. Source Systems
Clinical Information Systems (HIS / LIS)
•	Daily data extracts or direct SQL access
•	Includes medical attendances, service classification, service date, and billed amounts
Financial Planning Systems
•	Monthly forecast files (Excel / CSV)
•	Includes revenue projections by service and period

7. Analytical Logic (SQL Layer)
Monthly Actual Performance by Service
SELECT
    EXTRACT(YEAR FROM attendance_date) AS year,
    EXTRACT(MONTH FROM attendance_date) AS month,
    ms.service_name,
    COUNT(ma.attendance_id) AS total_attendances,
    SUM(ma.amount_chf) AS actual_revenue_chf
FROM medical_attendances ma
JOIN medical_services ms
    ON ma.service_id = ms.service_id
GROUP BY
    EXTRACT(YEAR FROM attendance_date),
    EXTRACT(MONTH FROM attendance_date),
    ms.service_name;

Actual vs Forecast Comparison
SELECT
    r.year,
    r.month,
    r.service_name,
    r.total_attendances,
    r.actual_revenue_chf,
    e.estimated_amount_chf,
    (r.actual_revenue_chf - e.estimated_amount_chf) AS variance_chf,
    CASE
        WHEN r.actual_revenue_chf >= e.estimated_amount_chf THEN 'Above Target'
        ELSE 'Below Target'
    END AS performance_status
FROM actuals r
JOIN monthly_estimates e
  ON r.year = e.year
 AND r.month = e.month
 AND r.service_id = e.service_id;

8. Executive Dashboard Design
The Power BI dashboard provides a concise executive view, including:
•	KPI tiles for actual revenue, forecasted revenue, variance, and total attendances
•	Comparative bar charts showing actual versus forecast by service
•	Performance matrix with conditional formatting
All visuals follow a red-and-white corporate design aligned with executive reporting standards.

9. Business Value Delivered
•	Immediate transparency into financial and operational performance
•	Early identification of adverse trends
•	Clear distinction between volume-driven and revenue-per-case deviations
The solution supports informed decisions on budget allocation, capacity planning, and resource optimization.

10. Executive Summary
This initiative enables the healthcare organization to transition from retrospective reporting to forward-looking performance management. By integrating clinical and financial data into a unified analytical model, leadership gains timely, actionable insights aligned with the governance, efficiency, and accountability standards of the Swiss healthcare system.
