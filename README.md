# ⚡ Energy Consumption Dashboard (Power BI)

## 📌 Project Overview
This project shows how much **Water**, **Electricity**, and **Gas** were used in different U.S. cities from 2016 to 2019. It also shows how much money was spent on each type. The goal is to help understand energy usage, compare city trends, and manage costs better using interactive dashboards.

---

## 🧹 Data Cleaning and Preparation
I used Power Query in Power BI to clean and prepare the data:
- Removed blank, error, and empty rows.
- Combined Water, Gas, and Electricity columns into one column using **Unpivot**.
- Split that column to get energy type and unit values separately.
- Extracted **Year** from the Date column.
- Created an **ID column** using Year and Energy Type to connect tables.
- Merged and built relationships between:
  - Energy Consumption Table
  - Rates Table

---

## 🛠️ Tools and Skills Used
- **Power BI** – for dashboard, KPIs, and visuals
- **Power Query** – for cleaning and reshaping data
- **DAX** – for writing custom formulas
- **Data Modeling** – for linking tables
- **Tooltips** – for showing building info when hovering on charts

---

## 🌟 Key Features
- Three dashboards for Water, Gas, and Electricity
- Interactive KPIs: Total Cost, Units Used, and % of Total Usage
- Filters for Year and Energy Type
- Charts to show trends by City and by Month
- Tooltips showing building-level data for each city

---

## 📊 Key Visuals

 KPI Cards    -  Total Cost, Units Consumed, % of Use 
 Bar Charts   - Cost and Units by City 
 Line Charts  - Monthly Trend of Usage and Cost 
 Tooltips     - Extra details when hovering over charts 

---

## 📈 DAX Measures

### Total Cost and Units:
Dax
- Total Cost = SUMX('Energy Consumptions', 'Energy Consumptions'[Units] * RELATED(Rates[Price Per Unit]))
- Unit Consumed = SUM('Energy Consumptions'[Units])\
### Water:
- Water Cost = CALCULATE([Total Cost], Rates[Energy Type] = "Water")
- Water Cost Left = [Total Cost] - [Water Cost]
- Water Unit Consumed = CALCULATE([Unit Consumed], Rates[Energy Type] = "Water")
- % of Water Consumed = [Water Unit Consumed] / [Unit Consumed]
- Water Unit Consumed Left = [Unit Consumed] - [Water Unit Consumed]
#### Similar formulas were created for Electricity and Gas

## 🔍 Key Insights
- Water was used the most and had the highest cost. It might be overused.
- Electricity had the lowest cost, but its usage was steady across all cities.
- Gas was mostly used in winter and less in summer.
- New York and Chicago used the most energy across all types.

---

## 🧠 Data Story
This dashboard tells the story of how different cities use Water, Gas, and Electricity over time. It helps find patterns in energy use, spot months with high or low consumption, and identify areas where energy may be wasted.

---

## 🚀 Top Insights
- April had the highest water consumption (16.4 million units).
- Electricity cost peaked between August and October.
- Gas usage was very low in summer months.
- Phoenix and Houston used electricity more efficiently than other cities.

---

## ✅ Recommendations
- Run awareness programs in colder cities to reduce gas use during winter.
- Install smart water meters to track and reduce water waste.
- Start energy-saving programs in cities with high usage like New York and Chicago.
- Use this dashboard every month to help manage energy use and control costs.


