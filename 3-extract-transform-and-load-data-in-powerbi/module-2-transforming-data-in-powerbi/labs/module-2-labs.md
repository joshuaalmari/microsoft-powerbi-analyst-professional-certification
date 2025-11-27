## 📋 Practical Labs & Exercises

This module focuses on the practical application of Power Query to clean, reshape, and combine data. The exercises simulate real-world data preparation tasks required before analysis can begin.

---

### 🧪 Lab 1: Preparing a Dataset
* **Objective:** Clean a raw sales dataset (`SalesFile.xlsx`) containing common data quality issues such as nulls, mixed data types, and duplicates to ensure accurate reporting.
* **Files:**
    * [📂 View Lab Files](./lab-1-preparing-a-dataset/)
    * [📊 View Cleaned Dataset](./lab-1-preparing-a-dataset/Preparing%20a%20Dataset.pbix)

#### Key Actions Performed:
* **Handling Nulls:** Replaced null values in numeric columns (`Units Sold`, `Sales`, `Profit`) with `0` to allow for aggregation, and filled missing dates with a default standard value.
* **Data Type Correction:** Converted `Manufacturing Price` and `Sale Price` to **Decimal Number** format and `Units Sold` to **Whole Number**, fixing errors where text (e.g., "six hundred") prevented calculation.
* **Error Removal:** Used the "Remove Errors" function to automatically drop rows with corrupt data in critical financial columns.
* **De-duplication:** Identified and removed duplicate rows based on the `Products` column to prevent double-counting sales.

---

### 🧪 Lab 2: Apply a Pivot
* **Objective:** Transform a flat list of product details (`Product-Color Model.xlsx`) into a summary table that displays the count of products per color in a matrix format.
* **Files:**
    * [📂 View Lab Files](./labs/lab-2-apply-a-pivot/)
    * [📊 View Pivoted Model](./labs/lab-2-apply-a-pivot/Product_Color_Pivot.pbix)

#### Key Actions Performed:
* **Column Management:** Removed unnecessary columns (`Product Name`) to focus the aggregation on Color and Model.
* **Pivoting:** Used the **Pivot Column** feature on the `Color` column, selecting `Model` as the values column.
* **Aggregation:** Applied the **Count (All)** aggregate function to generate a table where unique colors became column headers, showing the total count of models for each color.

---

### 🧪 Lab 3: Appending & Merging Data
* **Objective:** Consolidate data from multiple sources into a single analytical view. This involved stacking historical sales files (Append) and enriching sales data with product details (Merge).
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-combining-data/)
    * [📊 View Combined Report](./labs/lab-3-combining-data/Combined_Sales_Analysis.pbix)

#### Part A: Appending (Stacking)
* **Scenario:** Merging a legacy sales file with a new subsidiary's sales file.
* **Action:** Renamed columns in the subsidiary file (e.g., changing `Quantity` to `OrderQty`) to match the primary schema.
* **Result:** Used **"Append Queries as New"** to create a "Consolidated Sales" table containing all records from both sources.

#### Part B: Merging (Joining)
* **Scenario:** Enriching a transactional `Sales` table with product details from a separate `Product` lookup table.
* **Action:** Performed a **Left Outer Join** using `ProductKey` as the common identifier.
* **Result:** Expanded the new `Product` column to bring in the `Product Name`, allowing sales to be analyzed by name rather than just ID.
