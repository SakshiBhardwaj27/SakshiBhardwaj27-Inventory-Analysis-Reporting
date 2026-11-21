# 📦 Supply Chain Operations & Procurement Intelligence Dashboard

<p align="center">
  <strong>Turning raw supply chain data into actionable business insights using Microsoft Excel.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white" alt="Microsoft Excel">
  <img src="https://img.shields.io/badge/Data%20Transformation-Power%20Query-217346?style=for-the-badge" alt="Power Query">
  <img src="https://img.shields.io/badge/Analysis-PivotTables%20%26%20Formulas-4472C4?style=for-the-badge" alt="PivotTables and formulas">
  <img src="https://img.shields.io/badge/Visualization-Interactive%20Dashboard-4472C4?style=for-the-badge" alt="Interactive dashboard">
</p>

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Objectives](#-business-objectives)
- [Dataset Overview](#-dataset-overview)
- [Tools and Technologies](#-tools-and-technologies)
- [Data Preparation and Data Model](#-data-preparation-and-data-model)
- [Dashboard and Analysis](#-dashboard-and-analysis)
- [Key Performance Indicators](#-key-performance-indicators)
- [Key Findings](#-key-findings)
- [Data Quality Checks](#-data-quality-checks)
- [Project Structure](#-project-structure)
- [How to Use](#-how-to-use)
- [Business Value](#-business-value)

---

## 📊 Project Overview

Supply chain operations involve multiple interconnected processes, from inventory management and procurement to sales fulfilment and product returns.

This project focuses on analyzing these operations through seven related datasets to understand inventory availability, supplier performance, purchasing efficiency, sales trends, and return patterns.

Using **Microsoft Excel and Power Query**, I developed an end-to-end analytics solution that transforms raw operational data into structured fact and dimension tables, performs KPI calculations, and presents key findings through an interactive Executive Dashboard.

The dashboard enables users to explore operational performance, identify potential inventory risks, monitor procurement efficiency, and understand sales and return trends.

## 🎯 Business Objectives

The analysis addresses the following business questions:

1. **Inventory Management:** How is inventory distributed across warehouses and product categories? Which inventory records are at or below their reorder points?
2. **Procurement Performance:** What is the purchase order status distribution? How do ordered and received quantities compare across suppliers?
3. **Sales Performance:** How do sales order volumes change over time? Which product categories and warehouses contribute to order activity?
4. **Returns Analysis:** What are the most common return reasons? Which products have the highest return activity?
5. **Operational Monitoring:** What do inventory, delivery, fulfilment, and return KPIs reveal about overall supply chain performance?

## 🗂️ Dataset Overview

The project uses seven source datasets covering different areas of supply chain operations.

| Dataset | Description |
|---|---|
| Products | Product details, categories, pricing and supplier references |
| Suppliers | Supplier information and reliability-related attributes |
| Warehouses | Warehouse details and identifiers |
| Inventory | Stock on hand, reorder points and safety stock |
| Purchase Orders | Purchase order dates, ordered quantities, received quantities and delivery status |
| Sales Orders | Sales order dates, quantities, warehouse references and order status |
| Returns | Return dates, reasons, product references and returned quantities |

### Dataset scale

The following are the post-deduplication table sizes used in the analysis:

| Dataset / Table | Records |
|---|---:|
| Products | 80 |
| Suppliers | 12 |
| Warehouses | 5 |
| Inventory | 10,600 |
| Purchase Orders | 1,800 |
| Sales Orders | 6,000 |
| Returns | 295 |

*The source data is provided in the `data/raw/` folder.*

## 🛠️ Tools and Technologies

| Tool | Application |
|---|---|
| Microsoft Excel | Data analysis, calculations and dashboard development |
| Power Query | Data cleaning, transformation, merging and table preparation |
| PivotTables | Aggregation and multidimensional analysis |
| PivotCharts | Visual representation of operational metrics |
| Excel Formulas | KPI calculations and performance metrics |
| Slicers and Timeline | Interactive dashboard filtering |

## 🔄 Data Preparation and Data Model

The project follows a structured data preparation and analysis workflow.

### 1. Data ingestion

- Imported seven CSV datasets into Power Query.
- Created separate staging queries for the original datasets.
- Used reference queries to prepare the analytical tables.

### 2. Data cleaning and transformation

Performed data preparation tasks including:

- Removal of exact duplicate records.
- Review of missing and invalid values.
- Data type standardization.
- Column selection and renaming.
- Transformation of date and numerical fields.
- Merging related datasets to enrich operational records.

### 3. Data modelling

Organized the transformed data into **four fact tables and three dimension tables**.

| Table Type | Tables |
|---|---|
| Dimension | `dim_Products` |
| Dimension | `dim_Suppliers` |
| Dimension | `dim_Warehouses` |
| Fact | `fact_Inventory_Complete` |
| Fact | `fact_PurchaseOrders_Enriched` |
| Fact | `fact_SalesOrders_Enriched` |
| Fact | `fact_Returns_Enriched` |

The enriched tables bring relevant product, supplier and warehouse attributes into the operational datasets, supporting more meaningful analysis.

## 📈 Dashboard and Analysis

The Executive Dashboard brings together six analytical visualizations across inventory, procurement, sales and returns.

### 1. Inventory Analysis

**Inventory by Warehouse**

![Inventory by Warehouse and Category](screenshots/CHART_1_2.png)

Examines how stock is distributed across the five warehouses, helping compare inventory concentration and identify differences in stock levels.

**Inventory by Category**

Compares the distribution of inventory across product categories to understand the composition of available stock.

### 2. Procurement and Sales Analysis

**Purchase Order Status Distribution**

![Purchase Order Status and Monthly Sales Trend](screenshots/CHART__3_4.png)

Shows the proportion of purchase orders across In Transit, Partially Received and Received statuses.

**Monthly Sales Order Trend**

Tracks monthly sales order volumes across the available reporting period, helping identify fluctuations and changes in order activity.

### 3. Returns and Supplier Analysis

**Returns by Reason**

![Returns by Reason and Supplier Procurement Performance](screenshots/CHART_5_6.png)

Analyzes return reasons such as Damaged, Late Delivery, No Longer Needed, Quality Issue and Wrong Item.

**Supplier Procurement Performance**

Compares total quantities ordered and received for each supplier, helping identify differences in procurement fulfilment.

### Supporting Analysis

<details>
<summary><strong>📦 View Procurement Analysis</strong></summary>

![Procurement Analysis](screenshots/Procurement_Analysis.png)

The procurement analysis includes:

- Purchase orders by status.
- Ordered versus received quantities by supplier.
- Purchase order distribution by year.
- Average supplier lead time.

</details>

<details>
<summary><strong>↩️ View Returns Analysis</strong></summary>

![Returns Analysis](screenshots/Return_Analysis.png)

The returns analysis includes:

- Return records by reason.
- Return activity by product.
- Returned quantities by product.
- Monthly return trends.

</details>

## 📌 Key Performance Indicators

Six headline KPIs are presented on the Executive Dashboard.

| KPI | Business Definition | Observed Value |
|---|---|---:|
| Total Stock on Hand | Total available stock quantity | 5,432,101 |
| Inventory Records At/Below Reorder Point | Inventory records where stock is at or below the reorder point | 695 |
| Estimated Inventory Value | Estimated stock value using stock quantity and unit cost | 39,06,92,02,645.34 |
| Total Purchase Orders | Number of purchase orders | 1,800 |
| On-Time Delivery | Percentage of eligible purchase orders delivered on or before the expected date | 46.61% |
| Quantity Fulfilment | Total received quantity as a percentage of total ordered quantity | 86.46% |

### Additional supporting metrics

| Metric | Observed Value |
|---|---:|
| Total Sales Orders | 6,000 |
| Total Quantity Sold | 73,821 |
| Total Return Records | 295 |
| Order-Level Return Rate | 4.92% |

*Values represent the workbook snapshot at the time of analysis and may change after refreshing the data.*

<details>
<summary><strong>🧮 KPI calculation methodology</strong></summary>

**Total Stock on Hand**

Sum of stock quantities across inventory records.

**Inventory Records At/Below Reorder Point**

Count of inventory records where stock on hand is less than or equal to the reorder point, considering records with both values available.

**Estimated Inventory Value**

Calculated using stock quantity multiplied by unit cost. The estimate excludes records with negative stock or negative unit cost. It should be interpreted in the dataset's currency and with the data-quality limitations described below.

**On-Time Delivery**

Purchase orders with both actual and expected delivery dates, where the actual delivery date is on or before the expected date, divided by all purchase orders with both dates available.

**Quantity Fulfilment**

\[
\frac{\text{Total Quantity Received}}{\text{Total Quantity Ordered}}\times100
\]

**Order-Level Return Rate**

\[
\frac{\text{Distinct Sales Orders with at least one return}}{\text{Distinct Sales Orders}}\times100
\]

An order is counted only once in the return-rate numerator, even if it contains multiple return records.

</details>

## 💡 Key Findings

The analysis revealed several patterns in the available data:

- **Inventory distribution:** WH01 holds the largest stock quantity among the five warehouses, while WH02 has the lowest.
- **Category mix:** Grocery and Electronics each account for approximately 23% of the inventory distribution.
- **Procurement status:** Approximately 60% of purchase orders are partially received, 32% are received and 8% are in transit.
- **Supplier fulfilment:** Total received quantity is lower than total ordered quantity, with an overall quantity fulfilment rate of 86.46%.
- **Delivery performance:** The calculated on-time delivery rate is 46.61% among purchase orders with valid delivery-date pairs.
- **Sales trend:** Monthly sales order volumes fluctuate across the reporting period, rather than following a consistent upward or downward pattern.
- **Return patterns:** Return reasons are distributed relatively evenly across the five recorded reason categories.

These findings help identify areas that may require further operational investigation, particularly purchase order fulfilment, delivery performance and inventory replenishment.

## 🔍 Data Quality Checks

Data-quality validation is important when working with operational datasets because incomplete or invalid values can affect business metrics.

The workbook includes checks for missing and negative values in relevant fields.

| Data Quality Check | Observed Records |
|---|---:|
| Missing unit cost in enriched inventory | 0 |
| Negative unit cost in enriched inventory | 371 |
| Negative stock quantity | 110 |
| Missing received quantities | 79 |
| Negative received quantities | 44 |

Additional observations:

- The returns dataset contains 295 records, while 283 records have a populated return reason.
- Supplier lead-time values include negative and zero values, which require validation before interpreting supplier lead-time performance.

**Interpretation note:** These checks identify records requiring investigation; they do not establish that every flagged value is an error. Negative values and missing fields should be validated against the original business context rather than automatically replaced with zero. KPI results should therefore be interpreted with these limitations in mind.

## 📁 Project Structure

```text
Supply-Chain-Operations-Analytics/
│
├── data/
│   └── raw/
│       ├── products_raw.csv
│       ├── suppliers_raw.csv
│       ├── warehouses_raw.csv
│       ├── inventory_raw.csv
│       ├── purchase_orders_raw.csv
│       ├── sales_orders_raw.csv
│       └── returns_raw.csv
│
├── dashboard/
│   └── Supply_Chain_Operations_Dashboard.xlsx
│
├── screenshots/
│   ├── CHART_1_2.png
│   ├── CHART__3_4.png
│   ├── CHART_5_6.png
│   ├── KPI DASHBOARD.png
│   ├── Procurement_Analysis.png
│   └── Return_Analysis.png
│
└── README.md
```

## 🚀 How to Use

1. Clone or download this repository.
2. Open the Excel workbook in Microsoft Excel.
3. Explore the Executive Dashboard and supporting analysis sheets.
4. Use the slicers and timeline to filter the connected PivotTables and charts.
5. Review the KPI calculations and supporting analysis sheets for additional details.

**Note:** The workbook contains the transformed tables and analysis. If you want to refresh Power Query after downloading it to another computer, you may need to update the source-file paths in the query settings to point to the downloaded CSV files.

## 🎯 Business Value

This project demonstrates how Excel can be used to build a structured supply chain analytics solution from raw operational data.

It brings together data preparation, relational data modelling, KPI development and interactive reporting in one workbook.

The resulting dashboard provides a consolidated view of inventory, procurement, sales and returns, helping users monitor performance, identify potential operational issues and support data-informed decisions.

---

<p align="center">
  <strong>Built with Microsoft Excel | Power Query | PivotTables | PivotCharts</strong>
</p>

<p align="center">
  <em>End-to-end Supply Chain Analytics Portfolio Project</em>
</p>
