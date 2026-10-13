# PowerBI-Sales-Analytics-TMDL-DAX
# 📊 Sales & Operations Analytics Dashboard 

## 📌 Executive Summary
A comprehensive, end-to-end Power BI analytics project designed to deliver dynamic, actionable business insights for sales performance, operational efficiency, dynamic segmentations, and year-over-year (YoY) metrics. Built using standard data modeling best practices, clean ETL procedures in **Power Query**, advanced **DAX Time-Intelligence**, and code-driven model creation via **TMDL (Tabular Model Definition Language)**.

---


### 🖥️ Executive Dashboard View
![Executive Sales Analytics Dashboard](https://github.com/HagerSalahRamadan/PowerBI-Sales-Analytics-TMDL-DAX/blob/main/Dashboard.png)

---

### 🧬 Data Model Architecture (Star Schema)
![Data Model Architecture](https://github.com/HagerSalahRamadan/PowerBI-Sales-Analytics-TMDL-DAX/blob/main/model.png)

---

## 🔑 Key Features & Technical Highlights

### 1️⃣ Advanced Data Transformation (Power Query ETL)
* **Revenue Validation:** Computed line-item revenues (`Units * UnitPrice`) to validate and reconcile against provided raw revenue figures.
* **Margin Classification:** Applied conditional M logic to build a granular `Profit_Margin_Class` (`High Margin`, `Medium Margin`, `Low Margin`, `Loss/Breakeven`).
* **Unstructured Data Normalization:** Standardized raw operational statuses (`RawStatus`), correctly handling blank cells, null values, and trailing spaces into a structured `NormalizedStatus` field.
* **Dynamic Customer & Rating Bands:** Segmented order volumes into condition-based `Order_Value_Band` and `Rating_Band` dimensions for deep-dive customer satisfaction analysis.

---

### 2️⃣ Dimensional Modeling & Date Intelligence
* **Star Schema Architecture:** Established a clean Star Schema centered around `FactOrders`, connected to `Calendar` and `DimEmployee` via 1-to-Many ($1:*$) single-direction relationships.
* **Holiday Integration:** Linked `HolidaySeed` directly to `Calendar` via a 1-to-1 bi-directional relationship to easily cross-filter official holidays.
* **Continuous Date Table:** Built a continuous, dedicated **Calendar Table** covering the full range of `FactOrders`, configured formal **Marked as Date Table** behavior, and applied custom column sorting (`Month Name` by `Month Num`) to fix chronological rendering errors.

---

### 3️⃣ Model-Driven DAX Measures using TMDL View
All core calculations and KPIs were defined using **TMDL (Tabular Model Definition Language)** for structured, code-driven model maintenance:
* **Core Business KPIs:** `Total Revenue` ($152M), `Total Profit` ($46M), `Profit Margin %` (30%), `Total Orders` (30K), `Avg Order Value` ($5K), and `Return Rate %`.
* **Time Intelligence DAX:** Integrated `TOTALYTD` and `SAMEPERIODLASTYEAR` functions to calculate real-time `YoY Growth %` (49.7%) and historical year-over-year performance trends.


#### 📐 TMDL Code Snippets
![TMDL Measures Overview Part 1](https://github.com/HagerSalahRamadan/PowerBI-Sales-Analytics-TMDL-DAX/blob/main/tmdl_1.png)
![TMDL Measures Overview Part 2](https://github.com/HagerSalahRamadan/PowerBI-Sales-Analytics-TMDL-DAX/blob/main/tmdl_2.png)

```tmdl
// Sample TMDL Definition for YoY Growth
measure 'YoY Growth %' = DIVIDE([Total Revenue] - [Revenue PY], [Revenue PY], 0)
    formatString: +0.0%;-0.0%;0.0%
```

---

## 🛠️ Tech Stack & Tools

* **Business Intelligence:** Power BI Desktop
* **Data Processing & Transformation:** Power Query (M Language)
* **Semantic Modeling:** TMDL View, DAX (Data Analysis Expressions)
* **UI/UX Design:** Soft Card Theme ( Custom KPI Cards, Dynamic Visual Hierarchy)
* **Data Source:** `Task_2_Power_Query_TMDL_Calendar_Data.xlsx`

---

## 👤 Author
**Hager Salah**  
*Data Analyst & BI Developer*

---

## 📧 Contact

For any questions or feedback, feel free to reach out via email: **hagersalah.r39@gmail.com**
