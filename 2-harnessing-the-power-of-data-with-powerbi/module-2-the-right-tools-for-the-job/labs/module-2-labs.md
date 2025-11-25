## 📋 Practical Labs & Exercises

The exercises in this module focus on the critical "pre-analysis" phase: evaluating whether a dataset is fit for purpose and performing initial cleaning operations in Excel to ensure data quality before it ever reaches Power BI.

---

### 🧪 Lab 1: Dataset
* **Objective:** Assess a raw product inventory file (`Adventure Works Inventory.xlsx`) to determine if it contains the necessary data points to track supplier price increases over time.
* **Files:**
    * [📂 View Lab Files](./lab-1-dataset/)

#### Key Actions Performed:
* **Field Identification:** Reviewed schema to locate critical fields (`DateEntered`, `ProductName`, `Supplier`, `UnitPrice`) required for longitudinal price tracking.
* **Data Validation:** Sorted data by `Product Name` and `Date Entered` to visually verify historical pricing trends and identify potential anomalies.
* **Gap Analysis:** Identified "noise" columns (e.g., `Reorder Level`, `Discontinued`) that, while present, were irrelevant to the specific pricing analysis objective.

---

### 🧪 Lab 2: Evaluating Data for Transformation
* **Objective:** Perform a comprehensive data quality audit and cleanup on three distinct datasets (Sales, Inventory, Customer Feedback) using Excel to prepare them for ingestion into Power BI.
* **Files:**
    * [📂 View Lab Files](./lab-2-evaluating-data-for-transformation/raw-files)
    * [📊 View Cleaned Datasets](./lab-2-evaluating-data-for-transformation/completed-files)

#### Key Actions Performed:
* **Sales Data Cleaning:**
    * **Sanitization:** Filtered out rows with missing `TransactionID` to ensure data integrity.
    * **Type Correction:** Manually corrected text entries in number columns (e.g., replacing "four-hundred" with `400`) and replaced nulls with `0` to prevent calculation errors.
* **Inventory Standardization:**
    * **Standardization:** Used "Find and Replace" to normalize frequency terms (converting "30 d" to "30 days").
    * **Gap Filling:** Identified missing `Category` entries and populated them with a default "No Category Provided" tag to maintain grouping capabilities.
* **Customer Feedback Repair:**
    * **Date Fixing:** Converted text-based dates (e.g., "five May 2023") into valid Excel Date formats to enable time-series analysis.
    * **Score Correction:** Cleaned the `FeedbackScore` column by removing non-numeric characters to allow for average score calculations.
