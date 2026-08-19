# E-Commerce Executive Dashboard (Power BI)

> End-to-end BI solution built on the [Superstore Sales Dataset](https://www.kaggle.com/datasets/vivek468/superstore-sales-dataset).  
> First independent project transitioning from Tableau to Power BI stack.

---

## 📊 Project Overview

This dashboard provides a comprehensive analysis of e-commerce sales performance across categories, sub-categories, products, and time periods. It is designed for executive stakeholders who need quick access to key metrics with the ability to drill down into product-level details.

**Key objectives:**
- Track revenue, profit, average order value (AOV), and profit margin at a glance
- Identify top and bottom performing sub-categories
- Analyze quarterly revenue trends and seasonality
- Enable drill-through from high-level summary to individual product performance

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Data modeling, DAX calculations, visualization |
| **DAX** | Custom measures (KPIs, margins, rankings) |
| **Excel / CSV** | Source data (Superstore dataset) |

---

## 📁 Dashboard Structure

The report consists of **2 pages**:

### Page 1 — Executive Summary (`Сторінка 1`)
High-level overview for C-level and management.

| Visual | Description |
|--------|-------------|
| **4 KPI Cards** | Total Sales (8M), Total Profit (1.47M), AOV (313.15), Profit Margin (19%) |
| **Bar Chart** | Sales by Sub-Category — identifies leaders (Phones, Chairs, Binders) and laggards (Labels, Fasteners) |
| **Line Chart** | Revenue Trend by Year-Quarter — reveals seasonality, growth trajectory, and anomalies (e.g., Q1 2012 dip) |
| **Slicers** | Category filter for interactive exploration |

### Page 2 — Drill-Through: Product Analysis (`Сторінка 2`)
Detailed product-level view activated via drill-through from Page 1.

| Visual | Description |
|--------|-------------|
| **Multi-Row KPI Card** | Product Count, Total Sales, Total Profit, Profit Margin for the selected sub-category |
| **Product Table** | Full product list with Sales, Profit, and Margin — sorted by performance |
| **Bar Chart** | Top 5 products by Sales within the selected sub-category |

**Drill-through flow:** Click any sub-category bar on Page 1 → automatically navigate to Page 2 with pre-filtered data.

---

## 📐 DAX Measures

```dax
// Average Order Value
AOV = 
DIVIDE(
    SUM('df'[sales]), 
    DISTINCTCOUNT('df'[order_id]), 
    0
)

// Profit Margin
Profit Margin = 
DIVIDE(
    SUM('df'[profit]), 
    SUM('df'[sales]), 
    0
)

// Product Count (for drill-through page)
Product Count = 
DISTINCTCOUNT('df'[product_name])
```

---

## 🔍 Key Insights

1. **Phones** is the top sub-category by profit (~0.93M), but profit margin varies significantly across individual products (from -4% to +26%).
2. **Revenue trend** shows consistent growth from 2011 to 2014, with notable dips in Q1 of each year — likely post-holiday seasonality.
3. **Bottom performers** (Labels, Fasteners, Envelopes) generate minimal profit and may be candidates for portfolio review or bundling strategies.
4. **Drill-through reveals** that high-sales products are not always the most profitable — e.g., some Motorola and Samsung audio docks lead in revenue but have moderate margins.

---

## 🚀 How to Use

1. Clone this repository
2. Open `bi_dashboard.pbix` in **Power BI Desktop**
3. Interact with the report:
   - Use slicers to filter by category
   - Click on any sub-category bar to drill through to product details
   - Hover over charts for tooltips with exact values

---

## 📸 Screenshots

| Executive Summary (Page 1) | Drill-Through Product Analysis (Page 2) |
|:--:|:--:|
| ![Page 1](screenshots/page1_executive_summary.png) | ![Page 2](screenshots/page2_drillthrough.png) |

---

## 🎯 Learning Outcomes

This project was built as part of a transition from Tableau to Power BI. Key skills practiced:

- Data modeling and relationships in Power BI
- DAX measure writing (aggregation, division, distinct counts)
- Drill-through page configuration and filter context
- Conditional formatting (data bars, color scales for profit/loss)
- Dashboard layout, alignment, and UI grouping
- KPI design and executive-ready visual storytelling

---

## 📄 License

Dataset: [Superstore Sales Dataset](https://www.kaggle.com/datasets/vivek468/superstore-sales-dataset)  
Project: Personal portfolio use.

---

> Built with Power BI Desktop | Interface language: Ukrainian
