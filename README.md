# Power-BI-Road-Accident-Analysis
It provides interactive insights into accident trends, casualties, and year-on-year comparisons. It helps identify high-risk areas and supports data-driven road safety decisions.

---

## Table of Contents
- [Introduction](#introduction)
- [Dashboard Requirements](#dashboard-requirements)
- [Installation / Usage](#installation--usage)
- [DAX (Formulas Used in Measures)](#dax-formulas-used-in-measures)
- [Bug / Feature Request](#bug--feature-request)
- [Authors](#authors)

---

## Introduction

This Power BI report provides a detailed analysis of road accident data in the United Kingdom. It presents key insights related to total casualties, accident types, vehicle involvement, and location-based trends.  
🔗 **Dataset Link**: [Google Drive - Road Accident Data]https://docs.google.com/spreadsheets/d/1tdsA0IuAA_pTvupbG5sFtOZEm7qk0kpX/edit?gid=324101254#gid=324101254
The dashboard supports quick identification of critical risk factors and high-impact areas for road safety improvements.

---

## Dashboard Requirements

- **Primary KPIs:**
  - Total Casualties and Total Accidents for Current Year and YoY Growth
  - Casualties by Accident Severity for Current Year and YoY Growth
- **Secondary KPIs:**
  - Casualties by Vehicle Type for Current Year
  - Monthly Trend Comparison (Current Year vs Previous Year)
  - Casualties by Road Type
  - Casualties by Area/Location and Day/Night
  - Total Casualties and Accidents by Location

---

## Installation / Usage

1. Open the `.pbix` file using **Power BI Desktop**.
2. Refresh the data if connected to an external source.
3. Use filters to slice data by:
   - Road Surface
   - Weather Conditions
4. Interact with visualizations to explore detailed insights.

---

## DAX (Formulas Used in Measures)

### 1. Total Casualties – Current Year and YoY Growth

**(a) CY Casualties Measure**
```DAX
CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])
```

**(b) PY Casualties Measure**
```DAX
PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))
```

**(c) YoY Casualties Measure**
```DAX
YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]
```

### 2. Total Accidents – Current Year and YoY Growth

**(a) CY Accidents Count Measure**
```DAX
CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])
```

**(b) PY Accidents Count Measure** 
```DAX
PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))
```

**(c) YoY Accidents Count Measure** 
```DAX
YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]
```

---

## Bug / Feature Request

If you encounter issues or would like to suggest improvements:
- Email: sagar007ak@gmail.com
- Or raise an issue on the project repository (if applicable)

---

## Authors

- **Your Name:** Sagar
- **Role:** Data Analyst / Tableau Developer
- Linkedin: www.linkedin.com/in/sagar1505
- Email: sagar007ak@gmail.com
