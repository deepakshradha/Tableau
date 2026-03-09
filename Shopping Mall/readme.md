##  🛍️ Shopping Mall Sales Dashboard

This workbook providing an interactive sales performance dashboard for shopping mall retail data, with year-over-year KPI tracking, subcategory analysis, and weekly trend visualization.

---

## ⚙️ Requirements

- **Tableau Desktop** or **Tableau Public** (version 2025.2 or compatible)
- No external database connection required — data is embedded via a `.hyper` extract
  
---

##  🗄️ Data Sources

The workbook is built on four CSV files, joined into a single `Sales DataSource`:

| Table | Key Fields |
|-------|-----------|
| `Orders.csv` | Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Segment, Postal Code, Product ID, Sales, Quantity, Discount, Profit |
| `Customers.csv` | Customer ID, Customer Name |
| `Location.csv` | Postal Code, City, State, Region, Country/Region |
| `Products.csv` | Product ID, Category, Sub-Category, Product Name |

> 📌 **Note:** The original source files were located at a local Windows path. The packaged workbook includes an embedded `.hyper` extract, so no reconnection to the original CSVs is needed.

---

## 🎛️  Parameters

| Parameter | Type | Options | Default |
|-----------|------|---------|---------|
| 📅  Select Year | Integer | 2020, 2021, 2022, 2023 | 2021 |

Use the **Select Year** parameter to switch the dashboard between fiscal years. All KPIs automatically compare the selected year against the previous year.

---


###  🏪 Sales Dashboard

The main dashboard view, composed of the following sheets:

| Sheet | Purpose |
|-------|---------|
| **kpi sales** | KPI tile showing current year vs. previous year Sales, with % difference indicator |
| **KPI Profit** | KPI tile showing current year vs. previous year Profit, with % difference indicator |
| **KPI Quantity** | KPI tile showing current year vs. previous year Quantity sold, with % difference indicator |
| **legend KPI** | Color legend for KPI indicators (positive/negative trend) |
| **Sales and Profit by subcategory** | Bar chart comparing Sales and Profit across product sub-categories; acts as an interactive filter on the dashboard |
| **Weekly Trends** | Line chart showing weekly sales/profit trends across the selected year vs. prior year; acts as an interactive filter on the dashboard |
| **Ledgend Subcategory** | Legend for sub-category chart coloring |

A **Customer Dashboard** navigation icon is also present, suggesting this workbook is part of a larger multi-dashboard project.

---

##  🏪 Key Calculated Fields

| Field | Description |
|-------|-------------|
| Current Year Sales / Profit / Quantity | Aggregated values for the selected year |
| Previous Year Sales / Profit / Quantity | Aggregated values for the year prior to the selected year |
| % Difference Sales / Profit / Quantity | Year-over-year percentage change |
| Min / Max Sales / Profit / Quantity | Sparkline reference bands showing highest and lowest periods |
| KPI Sales Avg / KPI Color Avg Profit | Color-coded KPI indicators (positive = green, negative = red) |
| KPI CY Less PY | Directional indicator comparing current year to previous year |

---

## 🖱️ Interactivity

-  **Year selector** — Use the `Select Year` parameter control to switch between 2020–2023.
-  **Sub-category filter** — Clicking a bar in the *Sales and Profit by subcategory* chart filters the entire dashboard.
-  **Weekly trend filter** — Clicking a point in the *Weekly Trends* chart filters the entire dashboard.
-  **Filter panel toggle** — Icons in the navigation bar allow showing or hiding the filter panel.
-  **Dashboard navigation** — Icons at the top link to the Sales Dashboard and Customer Dashboard views.

---
