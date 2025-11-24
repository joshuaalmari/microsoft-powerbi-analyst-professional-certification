## 📋 Practical Labs & Exercises

This final module features a comprehensive capstone project that integrates all skills learned throughout the course. The objective is to transform raw, multi-year sales data into a polished **Executive Data Summary** for management review.

---

### 🏆 Final Capstone Project: Executive Data Summary
* **Objective:** Prepare a high-level Q1 Sales Report for a management meeting. The task involves cleaning raw product data, calculating quarterly sales performance across two years (2022 vs. 2023), and identifying year-over-year percentage growth.
* **Files:**
    * [📂 View Project Files](./final-project/)
    * [📊 View Completed Report](./final-project/Quarter%20One%20Report%20Completed.xlsx)

#### Key Actions Performed:
* **Data Preparation & Formatting:**
    * **Visual Design:** Created a professional dashboard layout with merged, bolded, and colored headers to clearly distinguish "Total Sales" from "Monthly Breakdowns".
    * **Data Standardization:** Used the `PROPER` function to fix inconsistent capitalization in product names, then converted the formulas to static text using **Paste Values** to permanently clean the dataset.
    * **View Management:** Applied **Freeze Panes** to keep header rows visible and **Hid** unnecessary intermediate columns to declutter the executive view.
* **Advanced Sorting:**
    * Performed a targeted sort on specific data columns (Order Date: Oldest to Newest) while carefully excluding the summary tables to maintain report structure.
* **Time Intelligence:**
    * Extracted **Month** and **Year** from order dates using `MONTH()` and `YEAR()` functions to facilitate period-based aggregation.
* **Financial Calculations:**
    * **Revenue Calculation:** Computed total order values by multiplying Retail Price by Order Quantity.
    * **Conditional Logic (`IF`):** Implemented automated tax calculations: *IF* order value > $2,000, apply 5% tax; otherwise, $0.
* **Executive Reporting Metrics:**
    * **Yearly Aggregation (`SUMIFS`):** Calculated total Q1 sales for 2022 and 2023 separately by summing revenue *only* where the "Year" column matched the target year.
    * **Monthly Breakdown:** Created granular monthly totals (Jan, Feb, Mar) using `SUMIFS` with multiple criteria (Year AND Month).
    * **Performance Analysis:** Calculated **Year-Over-Year Growth** using the percentage difference formula: `(New Value - Old Value) / Old Value`.
