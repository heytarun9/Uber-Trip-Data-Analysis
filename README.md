
# 🚖 Uber Rides Analysis (Jan-Feb 2015)

## 📌 Project Overview
This project analyzes Uber rides data from January and February 2015, cleans and processes the dataset, 
and visualizes key metrics using **Power BI**.  
The cleaned dataset is optimized for analytics and can be used for further business insights.

---

## 🗂 Dataset Information
**File:** `uber_cleaned.csv` (Cleaned)  
**Rows:** 354  
**Columns:** 11

### Columns in Cleaned Dataset:
- **dispatching_base_number**: The unique base number of the Uber dispatch base.
- **date**: The ride date (YYYY-MM-DD).
- **active_vehicles**: Number of active vehicles for that date.
- **trips**: Total number of trips on that date.
- **pickup_datetime**: Date and time of trip pickup.
- **year**: Year of the trip.
- **month**: Month of the trip.
- **day**: Day of the month.
- **hour**: Hour of the day (0–23).
- **weekday**: Day of the week.
- **is_weekend**: Whether the trip occurred on a weekend.

---

## 🧹 Data Cleaning Process
1. **Removed Duplicates** – Ensured no repeated records.
2. **Handled Missing Values** – Filled or removed null entries.
3. **Standardized Date Formats** – Converted `date` and `pickup_datetime` to proper datetime objects.
4. **Extracted Date Components** – Added `year`, `month`, `day`, `hour`, and `weekday` columns.
5. **Created Weekend Indicator** – Added `is_weekend` boolean column.

---

## 📊 Exploratory Data Analysis (EDA)
- **Daily Trips Trend** – Observed peaks and drops in ride demand.
- **Hourly Distribution** – Identified busy hours.
- **Weekday vs Weekend** – Compared ride counts for weekdays and weekends.
- **Base Code Performance** – Compared trips for different Uber bases.

---

## 📈 Power BI Dashboard
The Power BI dashboard provides interactive visual insights.

### Visuals Included:
1. **KPI Cards** – Total Trips, Total Active Vehicles, MoM % Change.
2. **Line Chart** – Trips over time.
3. **Bar Chart** – Base-wise trips.
4. **Donut Chart** – Trips share by base.
5. **Table** – Date, Base, Active Vehicles, Trips.

### Key DAX Measures:
```DAX
Total Trips = SUM('Table'[trips])
Total Vehicles = SUM('Table'[active_vehicles])
Trips MoM% = DIVIDE(
    [Total Trips] - CALCULATE([Total Trips], DATEADD('Table'[date], -1, MONTH)),
    CALCULATE([Total Trips], DATEADD('Table'[date], -1, MONTH)),
    0
)
```

---

## 📂 Files in Repository
- `uber_cleaned.csv` → Cleaned dataset for analytics.
- `README.md` → Documentation.

---

## 🚀 Usage
- Use this dataset for any BI or analytics project.
- Load into **Power BI** or **Tableau** for interactive dashboards.

---

**Author:** Tarun 
**Email:** devtarun05@gmail.com 
