## 📋 Practical Labs & Exercises

The exercises in this module focus on replacing manual Excel calculations with dynamic DAX measures and advanced data architecture. These labs simulate the creation of financial and time-intelligence reporting tools using Power BI's formula language.

---

### 🧪 Lab 1: Adding a calculated table and column
* **Objective:** Enhance the data model by creating a calculated table (a clone of existing data with new columns) and calculated columns (new fields) to enrich the dataset without altering the original source.
* **Files:**
    * [📂 View Lab Files](./lab-1-adding-a-calculated-table-and-column/)
    * [📊 View Model](./lab-1-adding-a-calculated-table-and-column/Adding%20a%20Calculated%20Table%20and%20Column.pbix)

#### Key Actions Performed:
* **Data Integrity:** Removed duplicate `SalesOrderNumber` values from the Fact table to ensure clean relationships.
* **Calculated Table:** Used `ADDCOLUMNS` and `RELATED` to generate a new "Yearly Sales by Color" table, physically combining columns from Sales, Product, and Date tables into the model.
* **Calculated Columns:** Added `Qtr` (Quarter) and abbreviated `Month` name columns to the Date table using DAX, enabling specific time-based filtering.

---

### 🧪 Lab 2: Adding a measure
* **Objective:** Create dynamic aggregation measures using both the "Quick Measure" feature (for speed) and custom DAX syntax (for precision).
* **Files:**
    * [📂 View Lab Files](./lab-2-adding-a-measure/)
    * [📊 View Model](./lab-2-adding-a-measure/Adding%20a%20Measure%20-%20Final.pbix)

#### Key Actions Performed:
* **Quick Measure:** Utilized the built-in tool to generate a **"Running Total in Year"** calculation without manually writing complex code.
* **Custom Measure:** Wrote an explicit `Total Revenue` measure using the `SUMX` iterator function to multiply `Quantity` by `Unit Price` row-by-row for accuracy.
* **Formatting:** Applied Currency formatting (2 decimal places) to ensure financial data satisfied reporting standards.

---

### 🧪 Lab 3: Using the CALCULATE function
* **Objective:** Perform granular analysis by creating measures that override the default filter context. The goal was to isolate specific sales segments (Non-US regions, specific product types, and employee roles).
* **Files:**
    * [📂 View Lab Files](./using-the-CALCULATE-function/)
    * [📊 View Model](./using-the-CALCULATE-function/Using%20th%20CALCULATE%20Function%20-%20Final.pbix)

#### Key Actions Performed:
* **Filter Context Modification:** Used the `CALCULATE` function to modify the `Total Revenue` measure.
* **Exclusion Logic:** Created a "Non-US Sales" measure using `FILTER` and the `<>` (not equal) operator to exclude United States data.
* **Multiple Filters:** Built a specific "Black Road Bikes" measure by applying two simultaneous filters (`Subcategory="Road Bikes"` AND `Color="Black"`).
* **Text Searching:** Used `CONTAINSSTRING` inside a filter to calculate sales specifically for employees with "Manager" in their job title.

---

### 🧪 Lab 4: Adding a role-playing dimension
* **Objective:** Configure the data model to analyze sales based on **Shipping Date** (inactive relationship) rather than the default Order Date, without creating a redundant date table.
* **Files:**
    * [📂 View Lab Files](./labs/exercise-adding-a-role-playing-dimension/)
    * [📊 View Model](./labs/exercise-adding-a-role-playing-dimension/Role_Playing_Model.pbix)

#### Key Actions Performed:
* **Relationship Configuration:** Established two relationships between the `Sales` table and `Date` dimension: one **Active** (Order Date) and one **Inactive** (Shipping Date).
* **Context Switching:** Created a custom measure (`August Sales by Shipping date`) using `CALCULATE` and `USERELATIONSHIP`. This forced the model to use the inactive shipping relationship specifically for that calculation.

---

### 🧪 Lab 5: Using time intelligence to compare to previous year
* **Objective:** Analyze sales growth by creating explicit year-over-year (YoY) comparison measures. The goal was to identify monthly and annual sales trends for strategic planning.
* **Files:**
    * [📂 View Lab Files](./labs/exercise-using-time-intelligence-to-compare-to-previous-year/)
    * [📊 View Model](./labs/exercise-using-time-intelligence-to-compare-to-previous-year/YoY_Analysis.pbix)

#### Key Formulas Constructed:
* **Prior Year Sales:** Created a measure (`RevenuePY`) using `CALCULATE` combined with `SAMEPERIODLASTYEAR` to shift the filter context back 12 months.
* **YoY Growth:** Created a measure (`Revenue YoY`) using the `DIVIDE` function to calculate the percentage change: `(Current Revenue - Previous Year Revenue) / Previous Year Revenue`.
* **Visualization:** Displayed these metrics in a Matrix visual to show monthly growth trends side-by-side.

---

### 🧪 Lab 6: Set up a common date table
* **Objective:** Create and configure a mandatory **Date Dimension Table** using DAX to ensure all time intelligence functions operate correctly.
* **Files:**
    * [📂 View Lab Files](./labs/activity-set-up-a-common-date-table/)
    * [📊 View Model](./labs/activity-set-up-a-common-date-table/Date_Table_Setup.pbix)

#### Key Actions Performed:
* **Table Creation:** Used the `CALENDAR` function to generate a dynamic single-column table with a contiguous set of dates covering the required sales history.
* **Attribute Enrichment:** Added helper columns for `YEAR`, `MONTH`, `WEEKNUM`, and `WEEKDAY` to allow for specific calendar filtering.
* **Model Configuration:** Officially marked the new table as a **Date Table** in the model settings, overriding Power BI's auto-date/time feature for better performance.
