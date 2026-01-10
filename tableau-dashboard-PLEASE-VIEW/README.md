# Tableau Dashboard Cheat Sheet

## Understanding the Metrics
- **Affordability Index** → Higher score means **housing is less affordable**.  
- **Median Household Income** → Average income in the county.  
- **Median Home Value** → Typical home price in the county.  
- **Percent Seasonal Housing** → Percentage of homes used seasonally (e.g., vacation homes).  
- **Total Housing Units** → Total number of homes in the county.  
- **Total Seasonal Units** → Number of homes that are seasonal.  

> **Note:** Affordability Index is inverse-friendly: higher is worse, lower is better.  

---

## How to Interact With the Dashboard

### 1. Map
- Hover over a county to see details.  
- The **color intensity** shows the value of the selected metric.  
- Use the **year filter** to display any single year.  

### 2. Line Chart (“Trend Over Time”)
- Shows **metric trends for the selected county**.  
- Select a **county on the map**, and the line chart updates automatically.  
- Use the **Metric dropdown** to see different metrics over time.  
- **Y-axis updates dynamically** to match the selected metric.  

### 3. Bar Chart (“Top N Counties”)
- Select **Top N or Bottom N** metric values using the parameters.  
- Use **Control (Windows) or Command (Mac) + click & drag** to select multiple counties.  
- The **map and line chart update** to show only the selected counties.  
- Click on the selection again to **reset** and view all counties.  

### 4. Year Filter
- Single-value dropdown lets you view one year at a time.  
- Affects all charts **simultaneously**.  

### 5. Metric Selection
- Change the **dropdown metric selector** to see different metrics across all visualizations.  
- All charts and maps update automatically.  

---

## Tips for Exploring
- Combine **Top N selection + metric change** to focus on the most or least affordable counties.  
- Hover over any chart element to **see exact values**.  
- Click on a county in the map to **highlight and compare trends** in the line chart.  

---

## Optional Enhancements
- **KPIs:** Numbers at the top reflect the selected metric for quick reference.  
- **Tooltips:** Hover over bars or map for details without needing extra clicks.  
- **Dynamic Titles:** All charts update titles automatically when you change the metric or year.  
