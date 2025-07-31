# ⚡ Energy Consumption Analysis (Power BI)

## 📌 Project Overview
This Power BI dashboard presents an in-depth analysis of energy consumption and associated costs across **Water**, **Electricity**, and **Gas** sectors. The analysis spans four years (2016–2019) and compares usage and cost across key U.S. cities. The dashboard helps stakeholders monitor cost efficiency, resource utilization, and seasonal trends in consumption.

---

## 🧹 Data Cleaning and Preparation
Performed in Power Query:
- Removed **blank**, **error**, and **empty** rows.
- **Unpivoted** energy-type columns (Water, Gas, Electricity) for normalization.
- **Split** attribute column to extract energy type and unit/cost.
- Extracted **Year** from the date column.
- Created a composite **ID column** (`Year + Energy Type`) to build relationships between:
  - `Energy Consumption Table` & `Rates Table`.

---

## 🛠️ Tools & Skills Used
- Power BI (Data Modeling, Power Query, DAX)
- DAX Measures (SUMX, CALCULATE, RELATED)
- Data Cleaning & Transformation
- Relationship Building (One-to-Many Model)
- Tooltip and Visual Enhancements

---

## 🌟 Key Features
- Three dashboards: **Water**, **Electricity**, and **Gas**
- Year and category filtering
- Dynamic KPIs (Total Cost, Units Consumed, % Consumed)
- City-wise & month-wise breakdown
- Custom tooltips for more context

---

## 📊 Key Visuals

| Visual Type    | Description |
|----------------|-------------|
| KPI Cards      | Total Cost, Unit Consumed, % Consumed |
| Bar Charts     | Cost and Units by City |
| Line Charts    | Monthly Cost and Units Trend |
| Tooltips       | Hover info on City-level graphs |

---

## 📈 Key DAX Measures

### Common Measures:
Dax
-Total Cost = SUMX('Energy Consumptions', 'Energy Consumptions'[Units] * RELATED(Rates[Price Per Unit]))
-Unit Consumed = SUM('Energy Consumptions'[Units])

-Water Cost = CALCULATE([Total Cost], Rates[Energy Type]="Water")
-Water Cost Left = [Total Cost] - [Water Cost]
-Water Unit Consumed = CALCULATE([Unit Consumed], Rates[Energy Type]="Water")
-% of Water Consumed = [Water Unit Consumed] / [Unit Consumed]
-Water Unit Consumed Left = [Unit Consumed] - [Water Unit Consumed]

Electricity and Gas:
Similar DAX formulas used by replacing the energy type.

## 🔍 Key Insights
- Water had the **highest cost and usage**, indicating potential overuse.
- Electricity cost was the **lowest**, but usage was consistent across cities.
- Gas showed **seasonal consumption**, peaking during colder months.
- New York and Chicago were the **top consumers** across all energy categories.

---

## 🧠 Data Story
This dashboard illustrates how energy resources are consumed differently by city and by type over time. It highlights inefficiencies and peak usage periods to drive action toward better resource management.

---

## 🚀 Top Insights
- **April** recorded the highest **water consumption** (16.4M units).
- **Electricity cost** peaked between **August and October** across most cities.
- **Gas usage** was significantly lower in **summer months**.
- **Phoenix and Houston** displayed **efficient electricity usage** compared to other cities.

---

## ✅ Recommendations
- Implement **awareness campaigns** to reduce gas usage in cold-weather cities.
- Deploy **smart water meters** to better monitor and control water usage.
- Encourage **energy efficiency programs** in high-cost cities like New York and Chicago.
- Use the dashboard for **monthly monitoring**, budgeting, and future consumption forecasting.





