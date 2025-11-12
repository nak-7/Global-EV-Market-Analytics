# ⚡ Global EV Market Analytics Dashboard (Power BI – PL-300 Level)

## 🚀 Project Overview
The **Global EV Market Analytics Dashboard** is an advanced Power BI project that provides comprehensive insights into the growth and trends of the electric vehicle (EV) industry across the world.  
This project was designed to **showcase mastery of PL-300 Data Analyst skills**, including data modeling, DAX measures, data cleaning, and advanced visualization design principles.

It delivers executive-level analytics with interactive features that allow users to explore EV sales, stock, charging infrastructure, and energy impact trends by year, country, and powertrain type.

---

## 🧩 Objectives
- Analyze **EV sales, stock, charging points, and energy demand** globally.
- Track **year-over-year (YoY)** growth in EV adoption and infrastructure.
- Compare **powertrain (mode)** performance across different markets.
- Identify **top-performing countries** and emerging regions.
- Build a **professional, interactive, and navigable dashboard** following PL-300 best practices.

---

## 🗂️ Dataset Details
**Source:** Kaggle — *Global EV Data (by IEA)*  
**Rows:** 9,174  
**Key Fields:**
- `region`, `country`, `year`
- `powertrain` (BEV, PHEV, FCEV)
- `EV sales`, `EV stock`, `EV charging points`
- `Electricity demand`, `Oil displacement (Mbd)`, `Oil displacement (million lge)`

---

## 🧱 Data Model & Transformations (Power Query)

### 1. **Data Cleaning (EV_Historical)**
- Removed null and redundant fields.  
- Renamed columns for clarity:
  - “EV sales” → “EV Sales”
  - “EV stock” → “EV Stock”
  - “EV charging points” → “Charging Points”
- Cleaned text fields (Trim, Clean, Capitalize).
- Converted numeric columns to proper data types.
- Replaced missing values (`Unknown`, `Not Specified`).

### 2. **Fact & Dimension Tables**
- **Fact Table:** `Fact_EV_Sales` (formerly EV_Historical)
- **Dimension Tables:**
  - `Dim_Year` – distinct list of years  
  - `Dim_Country` – distinct country names  
  - `Dim_Region` – distinct regional classification  

**Relationships:**
- `Dim_Year[Year]` → `Fact_EV_Sales[year]`
- `Dim_Country[Country]` → `Fact_EV_Sales[country]`
- `Dim_Region[Region]` → `Fact_EV_Sales[region]`

All relationships: *Many-to-One*, cross-filter *Single*.

---

## 🧮 Key DAX Measures

| Measure | Formula (Simplified) | Description |
|----------|----------------------|--------------|
| **Total EV Sales** | `SUM(Fact_EV_Sales[EV Sales])` | Total electric vehicle sales globally. |
| **Total EV Stock** | `SUM(Fact_EV_Sales[EV Stock])` | Total electric vehicles in stock. |
| **Total Charging Points** | `SUM(Fact_EV_Sales[Charging Points])` | Total charging stations worldwide. |
| **YoY EV Sales Growth %** | `( [Total EV Sales] - CALCULATE([Total EV Sales], PREVIOUSYEAR(Dim_Year[Year])) ) / CALCULATE([Total EV Sales], PREVIOUSYEAR(Dim_Year[Year]))` | Measures yearly sales growth. |
| **EVs per Charging Point** | `DIVIDE([Total EV Stock], [Total Charging Points])` | Infrastructure efficiency metric. |

---

## 🎨 Report Design

The report consists of **three interactive pages**, each serving a distinct analytical purpose.

---

### 🖥️ **Page 1 – Global Overview**

**Purpose:** Executive summary of global EV trends.

**Visuals:**
- **4 KPI Cards:**  
  - Total EV Sales  
  - Total EV Stock  
  - YoY EV Sales Growth %  
  - EVs per Charging Point  
- **Line & Clustered Column Chart:**  
  - Columns → EV Sales  
  - Line → YoY EV Sales Growth %  
  - X-Axis → Year  
- **Clustered Bar Chart – Total EV Sales by Mode (Powertrain):**  
  - X-Axis → Total EV Sales  
  - Y-Axis → Powertrain  
  - Title → *Total EV Sales by Mode (Powertrain)*  
- **Year Slicer:**  
  - List-style with styled selection boxes.  
- **Navigation Header:**  
  - Global Overview | Regional Trends | Country Insights

---

### 🌍 **Page 2 – Regional Trends**

**Purpose:** Compare EV adoption across regions and countries.

**Visuals:**
- **Filled Map:**  
  - Country = Location  
  - Color saturation = Total EV Sales  
  - Title → *EV Sales by Country*  
- **Bar Chart (Top N):**  
  - Top 10 Countries by Total EV Sales  
  - Sorted descending  
- **Line Chart:**  
  - EV Sales Trend by Powertrain  
  - X-Axis = Year, Legend = Powertrain  
- **Scatter Chart:**  
  - X = Total Charging Points  
  - Y = Total EV Sales  
  - Size = Total EV Stock  
  - Legend = Powertrain  
  - Title → *Sales vs Charging Infrastructure*  
- **Year Slicer** controlling all visuals.

---

### 📈 **Page 3 – Country Insights (Drillthrough)**

**Purpose:** Deep-dive into metrics for a selected country.

**Visuals:**
- **4 KPI Cards:** Country-specific totals.  
- **Clustered Column Chart:** EV Sales by Year.  
- **Bar/Donut Chart:** EV Stock by Powertrain.  
- **Scatter Chart:** Sales vs Charging Points (filtered to country).  
- **Back Navigation Button** (returns to previous page).

---

## 🎯 PL-300 Concepts Demonstrated
✔️ Power Query Transformations  
✔️ Data Modeling & Relationships  
✔️ Star Schema Design  
✔️ DAX Measures & Time Intelligence  
✔️ Hierarchies & Aggregations  
✔️ Page Navigation & Drillthrough  
✔️ Slicers, Interactions, and Filters  
✔️ Visual Formatting & UX Design  
✔️ Performance Optimization (fields, relationships)  

---

## 🧠 Insights Derived
- Global EV sales show exponential growth post-2017, led by China and Europe.  
- BEVs dominate over PHEVs in cumulative stock.  
- Charging infrastructure growth trails EV stock increase, indicating infrastructure lag.  
- Countries with higher EV stock density correlate with higher electricity demand displacement.  

---

## 💼 Portfolio Value
This project exemplifies **real-world, enterprise-grade Power BI reporting** aligned with **Microsoft PL-300 skills**.  
It demonstrates:
- Advanced DAX proficiency  
- Clean, intuitive report design  
- Data storytelling ability through KPIs and visual hierarchy  

---

## 🛠️ Tools Used
- **Power BI Desktop**
- **Microsoft Excel / CSV Data Source**
- **DAX (Data Analysis Expressions)**
- **Power Query (M Language)**

---

## 📎 How to Use
1. Open `Global_EV_Analytics.pbix` in Power BI Desktop.  
2. Explore via navigation header:
   - Global Overview → Regional Trends → Country Insights.  
3. Use the Year slicer and visual interactions to drill deeper.

---

## 🏁 Author
**👤 Nakshatra Devkar**  
🎓 B.E. Artificial Intelligence & Data Science  
💡 Power BI | Data Analytics | Python | SQL  

📫 *Connect:* [LinkedIn](#) | [GitHub](#)

---

## 🏷️ Keywords
`Power BI`, `PL-300`, `Data Modeling`, `DAX`, `Dashboard`, `Electric Vehicles`, `Data Visualization`, `Analytics`, `Microsoft Data Analyst`

---

