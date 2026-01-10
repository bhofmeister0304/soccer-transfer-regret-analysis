# Wisconsin County Housing Affordability Project (2013-2023)

This project analyzes county-level housing affordability in Wisconsin and predicts trends up to 2028. It combines historical data, machine learning predictions, and interactive visualizations in Tableau.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
- [Machine Learning Models](#machine-learning-models)
- [2028 Predictions](#2028-predictions)
- [Tableau Dashboard](#tableau-dashboard)
- [How to Use the Dashboard](#how-to-use-the-dashboard)
- [Key Insights](#key-insights)

---

## Project Overview
The goal of this project was to understand **county-level housing affordability trends** and predict the **2028 affordability index**.  

**Original Hypothesis:**  
Housing pressure was expected to be increasing in counties with high seasonal housing — that is, counties with more vacation or second homes would have faster-rising home prices and worsening affordability.

**What the Data Showed:**  
Contrary to the hypothesis, high-seasonal counties did not always see worsening affordability. Instead, other factors such as **income growth** and **home value growth** were stronger predictors of affordability changes.

---

## Data Sources

| Dataset | Description |
|---------|-------------|
| `final_df` | County-level data including median household income, total housing units, total seasonal units, median home value, FIPS, and total population for 2013, 2018, 2023. |
| `growth_df` | Derived growth metrics between years including income growth %, home value growth %, housing units growth %, seasonal units growth %, pct seasonal, and affordability index. |
| `final_affordability_predictions` | Predicted affordability index for 2028 at the county level. |

---

## Methodology

1. **Data Cleaning:** Combined historical datasets and ensured consistent FIPS codes.
2. **Feature Engineering:** Calculated growth percentages, percent seasonal homes, and other derived metrics.
3. **Modeling:** Used **Random Forest Regressors** to predict affordability index growth.
   - Model 1: 2013 → 2018
   - Model 2: 2013 + 2018 → 2023
4. **Evaluation Metrics:**
   - MAE (Mean Absolute Error)
   - RMSE (Root Mean Squared Error)
   - R² (Coefficient of Determination)

---

## Machine Learning Models

### Random Forest: 2013 → 2018
- **MAE:** 1.870  
- **RMSE:** 2.250  
- **R²:** 0.693  

**Top Features**
| Feature | Importance |
|---------|------------|
| Total Seasonal Units (2013) | 0.258 |
| Median Home Value (2013) | 0.223 |
| Percent Seasonal (2013) | 0.195 |
| Median Household Income (2013) | 0.185 |
| Total Housing Units (2013) | 0.129 |
| Seasonal Indicator | 0.010 |

### Random Forest: 2013 + 2018 → 2023
- **MAE:** 1.962  
- **RMSE:** 2.591  
- **R²:** 0.900  

**Top Features**
| Feature | Importance |
|---------|------------|
| Income Growth % | 0.329 |
| Home Value Growth % | 0.273 |
| Median Household Income (2018) | 0.090 |
| Housing Units Growth % | 0.070 |
| Percent Seasonal (2013) | 0.045 |

> Interpretation: Although seasonal units were important in earlier years, **income growth and home value growth dominate in predicting affordability changes**, which contradicts the original hypothesis about seasonal housing pressure.

---

## 2028 Predictions

- The **2028 Affordability Index** was predicted for each county using the trained Random Forest model.
- The 2028 dataset contains:
  - County Name
  - FIPS
  - Year = 2028
  - Total Population (from 2023)
  - Predicted Affordability Index
  - Other variables set as `NA` for alignment

**Sample:**

| FIPS | County | Year | Total Population | Affordability Index |
|------|--------|------|-----------------|------------------|
| 1    | Adams  | 2028 | 20,928          | 3.313 |
| 3    | Ashland| 2028 | 16,050          | 3.032 |
| 5    | Barron | 2028 | 46,741          | 3.069 |

---

## Tableau Dashboard

The dashboard visualizes county-level housing data with the following features:

1. **Choropleth Map**
   - Counties colored by selected metric
   - Hover for details
   - FIPS codes used for accurate mapping
   - Filled borders to show county boundaries

2. **Line Chart (Trend Over Time)**
   - Metric trends for a selected county
   - Dynamic Y-axis and title based on selected metric
   - Filterable by county

3. **Top N Bar Chart**
   - Shows top or bottom N counties for the selected metric
   - Adjustable using parameters for N and Top/Bottom
   - Dynamically filters map and line chart

4. **Filters**
   - Metric (dropdown)
   - Year (single value dropdown)
   - County (multi-select)

> Tip: Use **Ctrl (Windows) / Cmd (Mac) + click** in the bar chart to filter multiple counties across all sheets.

---

## How to Use the Dashboard

1. Select a **metric** from the dropdown to update all visualizations.
2. Choose a **year** to view data for that year.
3. Use the **Top N** bar chart to highlight top/bottom counties; the map and line chart automatically update.
4. Hover over counties on the map or points on the line chart for more details.
5. Higher Affordability Index scores indicate **less affordable housing**.

---

## Key Insights

- **Original Hypothesis:** Seasonal housing pressure drives worsening affordability.  
- **Data-Driven Insight:** Seasonal housing was **not the dominant factor**. Instead:
  - Income growth
  - Home value growth
  - Changes in housing stock  
  are stronger predictors of affordability trends.
- Some high-seasonal counties became more affordable relative to income due to income growth keeping pace with home values.
- Affordability is projected to worsen in some counties by 2028, but not necessarily those with the highest seasonal housing.

---

## Repository Structure


