# Retail POS & Category Market Share Tracker

**[Link to Live Interactive Dashboard](https://app.powerbi.com/groups/me/reports/9c844ca2-5937-4478-bd99-a9297b66621c/1b5a6363eacff52daf52?experience=power-bi)**

## Overview
This project is an end-to-end data analytics pipeline that transforms raw retail transaction logs into an interactive executive dashboard. Built using the Dunnhumby "The Complete Journey" dataset, this project demonstrates full-stack data analyst capabilities: data engineering with Python, relational database architecture with MySQL, and business intelligence visualization with Power BI.

![Dashboard Preview](file:///C:/Users/swami/AppData/Local/Temp/Power%20BI%20Desktop/print-job-9f875b40-6f65-4f0d-9186-f2131d36e90c/Retail%20POS%20&%20Category%20Market%20Share%20Tracker.pdf)
## Tech Stack
* **Data Extraction & Transformation:** Python (Pandas, NumPy, SQLAlchemy)
* **Database & Storage:** MySQL 
* **Data Modeling & BI:** Power BI Desktop, DAX

## Architecture & Data Pipeline
1. **ETL Process:** Python scripts were developed to ingest, clean, and dynamically generate missing geospatial and chronological data from the raw Dunnhumby dataset. 
2. **Database Design:** Architected a strict Star Schema in MySQL optimized for analytical querying.
   * **Fact Table:** `Fact_POS_Transactions` (Revenue, quantities, transaction timestamps)
   * **Dimension Tables:** `Dim_Products`, `Dim_Date` (dynamically generated continuous calendar), `Dim_Stores`
3. **Data Modeling:** Established 1-to-many relationships in Power BI, strictly typing date columns to enable Time Intelligence engine capabilities.

## Dashboard Features & Business Logic
* **F-Pattern Executive Layout:** Designed with a clear visual hierarchy, placing high-level KPIs (Total Revenue, YoY Growth) at the top left.
* **Continuous Time-Series Analysis:** Engineered a mathematically accurate, chronologically sorted revenue trend line spanning 24 months to monitor macro performance.
* **Hierarchical Drill-Down Matrix:** Implemented a performance matrix with conditional data bars, allowing stakeholders to investigate market share from the macro-category level down to specific brands.
* **Dynamic Time Intelligence:** Utilized DAX (`SAMEPERIODLASTYEAR`, `DIVIDE`) to calculate dynamic Year-over-Year (YoY) growth metrics that respond instantly to user slicer selections.
* **UX Controls:** Configured bookmark-driven "Reset Filters" functionality for a seamless user experience.

## Repository Contents
* `Data cleaning.ipynb`: Python scripts for data cleaning and SQL database insertion.
* `schema.sql`: MySQL DDL statements for creating the star schema.
* `retail_dashboard.pbix`: The final Power BI project file.
* `images/`: Folder containing high-resolution dashboard screenshots.

## How to Run
1. Execute the Python notebook to process the raw `.csv` files and populate your local MySQL instance.
2. Open the `.pbix` file in Power BI Desktop.
3. Update the Data Source settings to point to your local MySQL server credentials to refresh the data model.
