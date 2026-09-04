# NovaTrust Bank — Banking Performance & Business Intelligence Dashboard

## Overview
A full end-to-end analytics project for a retail banking dataset, covering the
complete pipeline from raw data cleaning through relational database design
to an interactive Power BI dashboard. Built to answer five core business
questions on branch performance, customer segmentation, product usage,
revenue trends, and the profitability impact of fee waivers.

## Tools Used
- Google Sheets (Data Cleaning & Preparation)
- PostgreSQL (Database Design, SQL Analysis)
- Power BI (Data Modelling, DAX, Dashboard Design)

## Data Model
A star schema with **Transaction** as the fact table, linked to three
dimension tables through enforced foreign key relationships:

```
Branch (dim)  ──┐
Product (dim) ──┼── Transaction (fact)
Customer (dim)──┘
```

- **transaction** — every transaction record: amount, fees, waivers, interest
  income, revenue, profit, satisfaction score, channel
- **branch** — 20 branches: type, city, manager, staff count, size, ATM status
- **product** — 10 products: category, launch date, fees, interest rate, risk rating
- **customer** — 999 customers: demographics, segment, account type, occupation

## Key Findings
- 🏢 Branch revenue is highly concentrated — two branches lead all 20 by a clear margin
- 👥 Premium and Retail customer segments together drive ~59% of total revenue
- 📱 Mobile Money and POS transactions dominate transaction volume — a clear digital-first shift
- 💸 Fee waivers materially reduce profit per transaction
- 📈 Revenue growth is volatile rather than steady, with sharp recurring monthly spikes

## Business Questions Answered
1. Which branch generates the highest revenue, and how does performance compare across the bank?
2. Which customer segment contributes the most revenue, and which contribute the least?
3. Which banking product records the highest transaction volume?
4. Is monthly revenue growing, stable, or declining over time?
5. How do fee waivers affect profitability?

## SQL Analysis
Five queries answer the business questions directly, including a window
function (`LAG()`) query calculating month-over-month revenue growth to
determine trend direction.

## DAX Measures Built
- Total Revenue
- Total Profit
- Total Transaction Value
- Transaction Volume
- Total Customers
- Total Branches
- Total Products
- Fee Waived Amount
- Profit Margin

Plus a dedicated **Date table** built with `CALENDAR()`, with Year, Quarter,
Month, and Day of Week columns, enabling full drill-down on the revenue trend visual.

## Dashboard
A single-page interactive Power BI dashboard featuring:
- 7 KPI cards (Transaction Value, Revenue, Profit, Volume, Customers, Branches, Products)
- Revenue by Branch (bar chart)
- Revenue Trend over Time (line chart, Year → Quarter → Month → Day drill-down)
- Revenue by Customer Segment (donut chart)
- Profit by Fee Waived Status (column chart)
- Transaction Volume by Product (bar chart)
- 4 slicers: Branch, Product, Customer Segment, Year

## Files in This Repository
- `NovaTrust_Analysis_Report.docx` — Full written report: data model, analysis
  process, dashboard explanation, and management recommendations
- `NovaTrust_Data_Model.sql` — Table creation, constraints, and data cleaning queries
- `NovaTrust_Business_Questions.sql` — The five business-question SQL queries
- `NovaTrust_Dashboard_Screenshot.png` — Power BI dashboard preview
- `NovaTrust_Data_Model_Screenshot.png` — Relational model view

## Dataset
NovaTrust Bank operational dataset
- Branch Data: 20 branches
- Product Data: 10 products
- Customer Data: 999 customers
- Transaction Data: 2,940 transactions

## Recommendations
Full recommendations are detailed in the written report, covering branch
performance replication, fee waiver policy review, segment-focused customer
strategy, continued digital channel investment, and a recurring dashboard
review process for management.

## Author
**Ibirogba Abiodun Isaac** | Data Analyst
📍 Lagos, Nigeria
🔗 [LinkedIn](https://linkedin.com/in/abiodun-ibirogba)

