# Google-Data-Analythic-big-query-

eCommerce & Web Analytics Dashboard (BigQuery + Looker Studio)
This project demonstrates an end-to-end data analysis pipeline, from processing raw nested data in BigQuery to building interactive business dashboards in Looker Studio. The analysis covers two major public datasets: Google Analytics (Web Behavior) and TheLook eCommerce (Sales Transactions).



🚀 Live Dashboards
Dashboard 1: Web Traffic & Conversion (GA) - https://lookerstudio.google.com/reporting/23a6e6a4-eb68-4183-9a3b-2b13b6f8e60e

Dashboard 2: Sales & Customer Insights (TheLook) - https://lookerstudio.google.com/reporting/ced93441-5795-4fb9-a400-f897fb90c553

🛠️ Tech Stack & Skills
Google BigQuery: SQL (Window Functions, UNNEST, CTEs, Joins).

Data Modeling: Star Schema design and Denormalization.

Looker Studio: Data Visualization, Calculated Fields, and Funnel Analysis.

Business Intelligence: KPI definition (LTV, AOV, Conversion Rate).

 Project Structure
1. Data Modeling
I implemented a Star Schema to optimize query performance. The primary fact table is at the Order Item level to ensure granular analysis of product categories.

Code snippet
erDiagram
    FACT_ORDER_ITEMS ||--|| FINAL_SALES_FACTABLE : "1:1 Mapping"
    DIM_USERS ||--o{ FINAL_SALES_FACTABLE : "joins"
    DIM_PRODUCTS ||--o{ FINAL_SALES_FACTABLE : "joins"
2. SQL Transformations
GA Dataset: Flattened nested JSON-like structures using UNNEST for hits and products.

TheLook Dataset: Created a centralized final_sales_factable using Window Functions to categorize customers into "New" vs. "Repeat" segments.

Data Cleaning: Filtered out canceled/returned orders and handled currency conversion.

 Key Insights
High-Value Segment: Customers aged 50+ are the top revenue drivers, particularly in the Outerwear and Jeans categories.

Retention: Repeat customers have a Lifetime Value (LTV) approximately 3x higher than new customers, emphasizing the importance of CRM.

Device Gap: Desktop users show a significantly higher conversion rate than Mobile users, suggesting a need for mobile checkout optimization.

Channel Intent: Direct traffic leads in both AOV and conversion intent, showing strong brand loyalty.

 How to Use
Check the SQL_Queries/ folder for the BigQuery scripts used in this project.

Review the Insights_Report.pdf for a detailed business breakdown.

Interact with the Looker Studio links above to see the final visualizations.
