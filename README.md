# **Credit-Card-Customer-Revenue-Analysis-Dashboard**

## **Project Overview**

This project presents an interactive **Business Intelligence Dashboard** developed using **Power BI** to analyze customer behavior, transaction performance, portfolio performance, and key operational KPIs for a credit card business.

The dashboard transforms raw customer and transaction data into meaningful business insights through customer segmentation, trend analysis, KPI reporting, and interactive visualizations, enabling stakeholders to monitor business performance and support data-driven decision-making.

---

# **Business Problem**

Credit card businesses generate large volumes of customer and transaction data every day. Monitoring revenue performance, customer behavior, portfolio health, and operational KPIs through traditional reporting methods can be time-consuming and inefficient.

This project addresses these challenges by developing an interactive dashboard that provides a centralized view of business performance and supports strategic decision-making.

---

# **Project Objectives**

- Monitor key financial and operational KPIs
- Analyze customer demographics and spending behavior
- Evaluate credit card portfolio performance
- Perform customer segmentation
- Track weekly and quarterly revenue trends
- Monitor activation and delinquency metrics
- Generate actionable business insights and recommendations

---

# **Tech Stack**

- Power BI
- SQL (Database Connectivity)
- DAX

---

# **Dataset**

The project utilizes two datasets:

- Customer Details
- Credit Card Transaction Details

The datasets were imported into a SQL database and connected to Power BI for dashboard development and business analysis.

---

# **Project Workflow**

1. Collected customer and transaction datasets.
2. Imported the datasets into a SQL database.
3. Connected the SQL database to Power BI.
4. Built the data model and relationships.
5. Created calculated columns and DAX measures.
6. Designed interactive dashboards.
7. Performed business analysis and generated actionable recommendations.

---

# **Dashboard Overview**

The solution consists of two interactive dashboards.

## Customer Dashboard

The customer dashboard provides insights into:

- Revenue by Age Group
- Revenue by Gender
- Revenue by Income Group
- Revenue by Education
- Revenue by Card Category
- Revenue by State
- Customer Segmentation<img width="1317" height="727" alt="Screenshot 2026-07-09 215336" src="https://github.com/user-attachments/assets/8841713f-8d11-4cc7-9212-9ba2394456ef" />


---

## Transaction Dashboard

The transaction dashboard monitors:

- Total Revenue
- Total Transaction Amount
- Interest Earned
- Transaction Count
- Weekly Revenue Trend
- Quarterly Performance
- Customer Acquisition
- Activation Rate
- Delinquency Rate
<img width="1302" height="720" alt="Screenshot 2026-07-09 220110" src="https://github.com/user-attachments/assets/2e6ff380-8197-488a-8806-93dc73962258" />

---

# **DAX Implementation**

The following calculated columns and measures were developed to support dynamic reporting.

### Calculated Columns

- Age Group-
  AgeGroup = SWITCH(
TRUE(),
'public cust_detail'[customer_age] < 30, "20-30",
'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
'public cust_detail'[customer_age] >= 60, "60+",
"unknown")

- Income Group
  IncomeGroup = SWITCH(
TRUE(),
'public cust_detail'[income] < 35000, "Low",
'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
'public cust_detail'[income] >= 70000, "High",
"unknown")

- Week Number
  week_num2 = WEEKNUM('public cc_detail'[week_start_date])

### **Measures**

- Revenue
  Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]

- Current Week Revenue
  Current_week_Reveneue = CALCULATE(
SUM('public cc_detail'[Revenue]),
FILTER(
ALL('public cc_detail'),
'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))

- Previous Week Revenue
  Previous_week_Reveneue = CALCULATE(
SUM('public cc_detail'[Revenue]),
FILTER(
ALL('public cc_detail'),
'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1))

These DAX measures enable KPI tracking, customer segmentation, and week-over-week business performance analysis.

---

# **Key Business Insights**

### Customer Analysis

- Blue Card customers contribute the largest share of overall revenue.
- Customers aged **40–50 years** represent the highest revenue-generating age segment.
- High-income customers contribute significantly more revenue than medium and low-income segments.

---

### Transaction Analysis

- Swipe transactions account for the highest transaction volume.
- Quarter 3 generated the strongest business performance compared to other quarters.
- Weekly revenue trends indicate periodic fluctuations in customer spending patterns.

---

### Geographic Analysis

- Texas, New York, and California collectively contribute approximately **68%** of total business revenue.

---

### Portfolio & Risk Monitoring

- Overall Customer Activation Rate: **57.47%**
- Overall Delinquency Rate: **6.07%**
- Self-employed customers exhibit comparatively higher delinquency levels, indicating a customer segment that may require closer portfolio monitoring.

---

# **Business Recommendations**

Based on the dashboard analysis, the following recommendations were identified:

- Target high-spending Blue Card customers with premium card upgrade campaigns.
- Increase digital payment adoption through cashback and promotional offers.
- Strengthen customer acquisition strategies in high-performing markets while expanding opportunities in underperforming regions.
- Launch personalized campaigns for high-income customer segments.
- Continuously monitor activation and delinquency metrics to support portfolio performance and risk monitoring.
- Review weekly business KPIs to identify emerging trends and support proactive decision-making.

---

#** Skills Demonstrated**

- Business Intelligence
- Business Analysis
- Data Analysis
- Dashboard Development
- Data Visualization
- KPI Reporting
- Customer Segmentation
- Trend Analysis
- Portfolio Performance Analysis
- Delinquency Analysis
- Risk Monitoring
- Data Modeling
- SQL Database Connectivity
- DAX
- Business Insight Generation
- Analytical Thinking

---
# Author

**Ayushi Singh**

Aspiring Business Analyst | Risk Analyst | Data Analyst

Thank you for exploring this project. Feedback and suggestions are always welcome.
