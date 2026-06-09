# Olist — Revenue & Customer Analysis

## Executive Summary

This project analyzes e-commerce performance for Olist, a Brazilian marketplace, using SQL and Power BI. The analysis covers $15.4M in delivered orders across all Brazilian states, with a focus on identifying revenue drivers, concentration risk, and customer retention patterns.

Three material findings emerged:

- Revenue is geographically concentrated, with São Paulo accounting for 37.4% of total revenue — representing meaningful regional dependency risk.
- Repeat customers are a small but disproportionately valuable segment, representing ~3% of customers but generating ~5.6% of total revenue.
- Revenue growth is driven primarily by order volume, not by increases in average order value — suggesting acquisition is outpacing monetization efficiency.

---

## Business Questions

1. What is the total revenue and order volume across the analysis period?
2. Which states generate the most revenue, and how concentrated is geographic distribution?
3. What share of customers are repeat buyers, and how does their revenue contribution compare to one-time buyers?
4. Is revenue growth driven by more orders or by higher spend per order?
5. Where are the greatest opportunities to improve retention and reduce concentration risk?

---

## Data Sources

| Dataset | Description |
|---|---|
| orders | Order status, timestamps, and customer IDs |
| order_items | Product-level line items and pricing |
| payments | Payment values aggregated at the order level |
| customers | Customer location and unique identifiers |

Data was filtered to delivered orders only to ensure accurate revenue reporting. Payment data was aggregated at the order level to prevent duplication from multi-payment orders.

---

## Tools & Skills Used

- **SQL (PostgreSQL / DBeaver):** Multi-table joins, aggregation, revenue segmentation, retention analysis
- **Power BI:** Data modeling, DAX measures, KPI cards, geographic visualization, interactive filtering
- **DAX:** Calculated measures for KPIs and dynamic dashboard interactivity

---

## Key Findings

**Geographic Concentration**
São Paulo (SP) accounts for 37.4% of total revenue ($5.77M of $15.42M). The top 3 states — SP, RJ, and MG — together represent over 55% of total revenue, indicating significant regional dependency.

**Customer Retention**
Repeat customers account for approximately 3% of the customer base but generate ~5.6% of total revenue. Their average order value is meaningfully higher than one-time buyers, suggesting strong lifetime value potential if retention improves.

**Revenue Growth Drivers**
Revenue growth over the analysis period is driven primarily by increased order volume rather than higher average order value. Average revenue per order remained relatively stable, indicating that growth is coming from customer acquisition rather than increased spend per customer.

---

## Key Business Recommendations

| Priority | Recommendation |
|---|---|
| 🌎 Reduce geographic risk | Invest in marketing and logistics expansion in underperforming states to reduce dependence on São Paulo |
| 🔁 Improve retention | Implement loyalty programs or targeted re-engagement campaigns for one-time buyers — even modest improvement in repeat rate has outsized revenue impact |
| 📈 Increase order value | Explore bundling, upsell, and cross-sell strategies to raise average order value alongside volume growth |

---

## Data Cleaning, Assumptions & Limitations

- Analysis is restricted to orders with status = 'delivered' to exclude canceled, unavailable, and in-transit orders from revenue figures.
- Payment values were aggregated at the order level before joining to prevent row duplication from installment or multi-method payments.
- Customer identity is based on unique customer IDs; the dataset does not support cross-order customer matching beyond the provided identifier.
- Analysis does not include margin, cost-of-goods, or seller fee data — all revenue figures reflect gross payment values.

---

## Project Structure

```
olist-revenue-customer-analytics/
├── sql/
│   ├── customer_revenue.sql       # Customer segmentation and repeat buyer analysis
│   ├── monthly_revenue.sql        # Revenue and order volume trends over time
│   └── revenue_by_state.sql       # Geographic revenue concentration analysis
├── powerbi/                       # Power BI dashboard (.pbix)
├── images/                        # Dashboard screenshots
└── README.md
```

### Dashboard Preview

**Customer Behavior**

![Customer Behavior](images/customer_behavior.png)

**Geographic Revenue**

![Geographic Revenue](images/geographic_revenue.png)

**Revenue Trends**

![Revenue Trends](images/revenue_trends.png)
