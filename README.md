# Operations Analytics

##Table of content

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Insights](#insights)
- [Recommendations](#recommendations)


### Project Overview

This project aims to categorize customers based on their potential long-term value to a the company, so that the company can design personalized offers and bundled packages that resonate with each segment.


### Data Sources

NexaSat_data: The primary dataset used for this analysis is the "NexaSat_data.csv", containing detailed information about each customer's purchase from the company.

### Tools

- Microsoft Excel- Data Cleaning  [Download here](https://microsoft.com)

- MySQL Server - Data Analysis

- Microsoft Power Bi - Data visualization and reporting

### Data Cleaning/Preparation

In the initial data preparation phase, the following task was performed:
1. Data Loading  and inspection
2. Handling duplicates and missing values
3. Data cleaning and formatting.

##Exploratory Data Analysis

EDA involved exploring the company's sales data to answer key questions, such as:
- Who are our top customers
- Which customers are most likely to continue doing business with us in 
  high value and frequency
- Which customers should we focus on and give tailored preferences.

### Data Analysis

```MySQL
use nexasat;

select*, (Tenure_months*Monthly_Bill_Amount) as Total_revenue
from nexasat_data;

SELECT *,
       (Tenure_months * Monthly_Bill_Amount) AS Total_revenue,
       CASE
           WHEN (Tenure_months * Monthly_Bill_Amount) <= 4000 THEN 'Low value'
           WHEN (Tenure_months * Monthly_Bill_Amount) BETWEEN 4001 AND 15000 THEN 'Medium value'
           WHEN (Tenure_months * Monthly_Bill_Amount) >= 15001 THEN 'High value'
       END AS Value_Category;

```
### Insights

Customer Insights:

- Total Customers: 7043
- Total Revenue: $27.63M
- Customer Segmentation: Based on purchase amount and duration with the company

High-Value Customers:
- Count: 166 (2.3% of total customers)
- Revenue Contribution: $2.84M (10.3% of total revenue)
- Tech Support: 78.3% receive tech support
- Dependents: 69% are not dependents
- Plan Type: 100% use the postpaid plan
- Plan Level: 78% use the premium plan
- Gender Distribution: 53% male, with a fairly even gender distribution

Medium-Value Customers:
- Count: 2608 (37% of total customers)
- Revenue Contribution: $18.13M (65% of total revenue)
- Tech Support: 84.5% receive tech support
- Dependents: 70% are dependents
- Plan Type: 63% use the postpaid plan, 39% use the prepaid plan
- Gender Distribution: Evenly distributed
- Plan Level: 79% use the premium plan

Low-Value Customers:
- Count: 4268 (60.6% of total customers)
- Revenue Contribution:*$6.64M (24% of total revenue)
- Tech Support: 52% receive tech support
- Dependents: 69% are not dependents
- Plan Type: 53% use the postpaid plan, 47% use the prepaid plan
- Gender Distribution: Evenly distributed
- Plan Level: 68% use the basic plan, 32% use the premium plan

### Recommendations


- For low value customers, Improve the tech support offered to low-value customers. Since only 52% use tech support, enhancing this service could increase loyalty and satisfaction. Consider offering more accessible support options or incentives for usage.

- Also, Introduce value-added services or incentives for these customers to upgrade their plans or increase their usage. Explore targeted promotions or features that could entice them to move to higher-value plans.

- For Medium value customers, Maintain their engagement and potentially upsell them to higher plans.
 Leverage the 84.5% who receive tech support by offering advanced services or upgrades. Promote the benefits of the premium plan to those on basic  

- For high value customers, develop exclusive offers or loyalty programs for high-value customers. Enhance the tech support and consider personalized communication and offers to retain them.

- Overall, review and possibly expand the range of plan types and features. Introduce flexible plans that can cater to different customer segments' needs, potentially increasing the conversion rate to higher-value plans.
