
## 📋 Practical Labs & Exercises

This final module features a comprehensive capstone project that consolidates all ETL skills learned throughout the course. The objective is to build a robust data pipeline by connecting to multiple sources, cleaning anomalies, and merging historical data into a unified analytical dataset.

---

### 🏆 Final Project: Transforming Multiple Data Sources
* **Objective:** Construct a clean, consolidated sales dataset for detailed store analysis. The project involves ingesting raw order data from multiple years, optimizing the schema by removing unnecessary fields, detecting and resolving data quality issues, and merging transactional details into a single master table.
* **Files:**
    * [📂 View Project Files](./final-project)
    * [📊 View Final Model](./final-project/Transforming%20Multiple%20Data%20Sources.pbix)

#### Key Actions Performed:
* **Data Optimization:**
    * **Column Reduction:** Identified and kept only critical analytical fields (`ProductID`, `OrderQty`, `UnitPrice`) from the `OrderDetails` table, removing noise to improve performance.
* **Advanced Profiling & Cleaning:**
    * **Anomaly Detection:** Used **Column Profile** statistics (Min/Max/Mean) on the `UnitPrice` column to statistically identify outlier values.
    * **Outlier Removal:** Filtered out specific rows containing erroneous pricing data (likely data entry errors) to prevent skewed financial reporting.
* **Data Integration:**
    * **Appending (Stacking):** Combined historical data files (`Order2022` and `Order2023`) into a single `Orders` master table to enable longitudinal analysis.
    * **Merging (Joining):** Performed an **Inner Join** between the `Order Details` and `Orders` tables using `SalesOrderID` as the key, ensuring only matched records were retained.
    * **Enrichment:** Expanded the merged table to pull in the `OrderDate`, enabling time-based analysis on the transactional details.
