# Intermediate SQL - Sales Analysis

![sales_image](/images/sales_image.jpg)

## Dataset Link:
https://github.com/lukebarousse/Int_SQL_Data_Analytics_Course/releases/tag/v.0.0.0

## Overview
Analysis of customer behavior, retention, and lifetime value for an e-commerce company to improve customer retention and maximize revenue.

## Business Questions
1. Customer Segmentation: Who are our most valuable customers?
2. Cohort Analysis: How do different customer groups generate revenue?
3. Retention Analysis: Who hasn't purchased recently?

## Analysis Approach

### 1. Customer Segmentation
- Categories customers based on total lifetime value (LTV)
- Assigned customers to High, Mid, and Low Value segments
- Calculated key metrics: total revenue

Query: [1_customer_segmentation](/1_customer_segmentation.sql)

**Visualization:**

![1_customer_segmentation](/images/1_customer_segmentation.png)

**Key Findings:**
- High-value segment (25% of customers) drives 66% of revenue ($135.4M)
- Mid-value segment (50% of customers) generates 32% of revenue ($66.6M)
- Low-value segment (25% of customers) accounts for 2% of revenue ($4.3M)

**Business Insights:**
- High-Value (66% revenue):
    -  Offer premium membership program to 12,372 VIP customers
    - Provide early access to new products and dedicated support
    - Focus on retention as losing one customer impacts revenue significantly

- Mid-Value (32% revenue):
    - Create upgrade paths for 24,743 customers through personalized promotions
    - Target with "next best product" recommendations based on high-value patterns
    - Potential $66.6M $135.4M revenue opportunity if upgraded to high-value

- Low-Value (2% revenue):
    - Design re-engagement campaigns for 12,372 customers to increase purchase frequency
    - Test price-sensitive promotions to encourage more frequent purchases
    - Focus on converting $4.3M segment to mid-value through targeted offers

### 2. Cohort Analysis
- Tracked revenue and customer count per cohorts
- Cohorts were grouped by year of first purchase
- Analyzed customer retention at a cohort level

Query: [2_cohort_analysis](/2_cohort_analysis.sql)

**Visualization:**

![2_cohort_analysis](/images/2_cohort_analysis.png)

**Key Findings:**
- Revenue per customer shows an alarming decreasing trend over time 
    - 2022-2024 cohorts are consistently performing worse than earlier cohorts
    - Note: Although net revenue is increasing, this is likely due to a larger customer base, which is not reflective of customer value

**Business Insights:**
- Value extracted from customers is decreasing over time and needs further investigation.
- In 2023 we saw a drop in number of customers acquired, which is concerning.
- With both lowering LTV and decreasing customer acquisition, the company is facing a potential revenue decline.

### 3. Retention Analysis
- Identified customers at risk of churning
- Analyzed last purchase patterns
- Calculated customer-specific metrics

Query: [3_customer_retention](/3_retention_analysis.sql)

**Visualization:**

![3_percentage_status](/images/3_1_status_percentage.png)

![3_customer_retention](/images/3_2_cutomer_retention.png)

**Key Findings:**
- Cohort churn stabilizes at ~90% after 2-3 years, indicating a predictable long-term retention pattern.
- Retention rates are consistently low (8-10%) across all cohorts, suggesting retention issues are systemic rather than specific to certain years.
- Newer cohorts (2022-2023) show similar churn trajectories, signaling that without intervention, future cohorts will follow the same pattern.

**Business Insights:**
- Strengthen early engagement strategies to target the first 1-2 years with onboarding incentives, loyalty rewards, and personalized offers to improve long-term retention.
- Re-engage high-value churned customers by focusing on targeted win-back campaigns rather than broad retention efforts, as reactivating valuable users may yield higher ROI.
- Predict & preempt churn risk and use customer-specific warning indicators to proactively intervene with at-risk users before they lapse.

**Strategic Recommendations:**

1. **Customer Value Optimization (Customer Segmentation)**
    - Launch VIP program for 12,372 high-value customers (66% revenue)
    - Create personalized upgrade paths for mid-value segment ($66.6M → $135.4M opportunity)
    - Design price-sensitive promotions for low-value segment to increase purchase frequency

2. **Cohort Performance Strategy (Customer Revenue by Cohort)**
    - Target 2022-2024 cohorts with personalized re-engagement offers
    - Implement loyalty/subscription programs to stabilize revenue fluctuations
    - Apply successful strategies from high-spending 2016-2018 cohorts to newer customers

3.  **Retention & Churn Prevention(Customer Retention)**
    - Strengthen first 1-2 year engagement with onboarding incentives and loyalty rewards
    - Focus on targeted win-back campaigns for high-value churned customers
    - Implement proactive intervention system for at-risk customers before they lapse

## Technical Details

- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, Dbeaver
- **Visualization:** Excel
