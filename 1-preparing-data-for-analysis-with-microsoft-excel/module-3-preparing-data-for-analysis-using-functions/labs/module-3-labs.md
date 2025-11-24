## 📋 Practical Labs & Exercises

The practical exercises in this module concentrate on the critical "pre-analysis" phase of data management. The projects involve hands-on **data cleansing** of legacy files, the creation of **dynamic project timelines**, and the construction of **logic-based pricing models** using advanced Excel functions.

---

### 🧪 Lab 1: Standardizing Text Based Data
* **Objective:** Prepare a raw "Reseller Details" dataset for database import by resolving inconsistent formatting, merged fields, and dirty data entry errors.
* **Files:**
    * [📂 View Lab Files](./lab-1-standardizing-text-based-data/)
    * [📊 View Completed Workbook](./lab-1-standardizing-text-based-data/Reseller%20Information%20Completed.xlsx)

#### Key Actions Performed:
* **Sanitization:** Applied `TRIM` to remove non-printing characters and invisible spaces that corrupt data matching.
* **Standardization:** Enforced consistent naming conventions using `PROPER` (Title Case for cities) and `UPPER` (uppercase for country codes).
* **Parsing:** Used `LEFT`, `RIGHT`, and `MID` to deconstruct merged text strings (e.g., extracting "State" and "Region" from a single cell).
* **Reconstruction:** Rebuilt clean, separate columns into a unified format using `CONCAT`.
* **Data Finalization:** Converted dynamic formulas into static values to permanently fix the dataset and removed redundant source columns.

---

### 🧪 Lab 2: Calculating the Number of Working Days Remaining in the Year
* **Objective:** Build a dynamic project schedule for a national advertising campaign to track milestones, launch windows, and resource availability.
* **Files:**
    * [📂 View Lab Files](./lab-2-calculating-the-number-of-working-days-remaining-in-the-year/)
    * [📊 View Completed Workbook](./lab-2-calculating-the-number-of-working-days-remaining-in-the-year/Advertising%20Campaign%20USA%20Dates%20Completed.xlsx)

#### Key Actions Performed:
* **Workforce Planning:** Calculated accurate resource availability using `NETWORKDAYS`, which automatically excludes weekends and a custom list of **Federal Holidays** from the timeline.
* **Dynamic Tracking:** Implemented `TODAY()` to provide a real-time countdown of "days remaining" until project deadlines.
* **Reporting Metrics:** Extracted specific time components (`MONTH`, `YEAR`) from launch dates to group campaigns for quarterly reporting.
* **Scalability:** Used **Absolute References** for holiday tables to ensure the logic remained accurate when applied to multiple project rows.

---

### 🧪 Lab 3: Adding a data column using the IFS function
* **Objective:** Create an automated pricing tool that calculates discounts and shipping logistics based on variable order criteria.
* **Files:**
    * [📂 View Lab Files](./lab-3-adding-a-data-column-using-the-IFS-function/)
    * [📊 View Completed Workbook](./lab-3-adding-a-data-column-using-the-IFS-function/Contoso%20Bikes%20Completed.xlsx)

#### Key Actions Performed:
* **Conditional Logic (`IF`):** Built a threshold rule to automatically apply a **10% discount** only if the order subtotal exceeds $10,000.
* **Multi-Condition Logic (`IFS`):** Replaced complex nested IF statements with a streamlined `IFS` function to assign shipping rates based on distinct delivery regions (Region A, B, or C).
* **Conditional Aggregation (`SUMIF`):** Generated a summary dashboard calculating total sales volume per region, ignoring non-matching records.
* **Formula Integrity:** Applied **Absolute References** to pricing lookup tables to prevent errors when scaling the quote tool across hundreds of line items.
