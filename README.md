\# E-Commerce Executive Dashboard (Power BI)



End-to-end BI solution. Expanding stack from Tableau to Power BI.



\## Features

\- Executive Summary: 4 KPIs via DAX (Revenue, Profit, AOV, Margin)

\- Bar chart: Sales by Sub-Category

\- Line chart: Revenue trend by Year-Quarter

\- Drill-through: Product details by Sub-Category

\- Top 5 products visualization

\- Category slicer



\## DAX Measures

```dax

AOV = DIVIDE(SUM('df'\[sales]), DISTINCTCOUNT('df'\[order\_id]), 0)

Profit Margin = DIVIDE(SUM('df'\[profit]), SUM('df'\[sales]), 0)

