## 📋 Practical Labs & Exercises

This module includes hands-on scenarios using data from **AdventureWorks**, a fictional multinational manufacturing company. Below are the key projects completed to demonstrate proficiency.

---

### 🧪 Lab 1: Standardizing Text Based Data
* **Scenario:** A colleague (Lucas) provided a "Reseller Details" dataset downloaded from an external system. The data was "dirty"—containing inconsistent capitalization, extra spaces, and merged text fields—making it impossible to analyze without significant cleaning.
* **Files:**
    * [📂 View Lab Files](./lab-1-standardizing-text-based-data/)
    * [📊 View Completed Workbook](./lab-1-standardizing-text-based-data/Reseller%20Information%20Completed.xlsx)

#### Key Actions Performed:
* **Space Removal:** Used the `TRIM` function to strip invisible leading and trailing spaces that would otherwise break matching algorithms.
* **Case Standardization:** Applied `PROPER` to convert City names into Title Case (e.g., "new york" to "New York") and `UPPER` to standardize country codes (e.g., "usa" to "USA").
* **Extraction & Splitting:**
    * Used `LEFT` and `RIGHT` to extract specific geographical regions ("States", "New York") from a merged location column.
    * Used `MID` to surgically extract text from the middle of a string based on position.
* **Recombination:** Used `CONCAT` to join cleaned columns back together with correct spacing.
* **Finalization:** Converted all formulas to static text using **Paste Values** and deleted the original messy columns to leave a polished, analysis-ready dataset.

---

### 🧪 Lab 2: Calculating Working Days
* **Scenario:** An analyst needed to track the "USA Advertising Campaign" rollout. The goal was to calculate dynamic milestones, including the number of working days available before deadlines and the precise launch timing.
* **Files:**
    * [📂 View Lab Files](./lab-2-calculating-working-days/)
    * [📊 View Completed Workbook](./lab-2-calculating-working-days/Advertising%20Campaign%20USA%20Dates%20Completed.xlsx)

#### Key Actions Performed:
* **Calendar Analysis:** Calculated the raw number of calendar days between the project start and deadline using simple subtraction.
* **Resource Planning (Working Days):**
    * Used `NETWORKDAYS` to calculate the actual days available for work, automatically excluding weekends.
    * Integrated a **Holiday Table** (Federal Holidays) as an argument to exclude specific non-working public holidays from the count.
    * Applied **Absolute References (`$`)** to the holiday range to ensure accuracy when copying the formula across multiple projects.
* **Milestone Extraction:** Used `MONTH` and `YEAR` functions to isolate launch windows for reporting purposes.
* **Dynamic Dating:** Utilized `TODAY()` to generate the current date for real-time "days remaining" tracking.

---

### 🧪 Lab 3: Adding Data Using IFS
* **Scenario:** A customized sales quotation was required for a major client ("Contoso Bikes"). The worksheet needed to automatically apply discounts based on order volume and calculate shipping costs based on specific regions.
* **Files:**
    * [📂 View Lab Files](./lab-3-adding-data-using-ifs/)
    * [📊 View Completed Workbook](./lab-3-adding-data-using-ifs/Contoso%20Bikes%20Completed.xlsx)

#### Key Actions Performed:
* **Automated Discounts (`IF`):** Created a logic test to check if the Subtotal exceeded $10,000.
    * *Logic:* If `>10000`, apply **10%**; otherwise, apply **0%**.
* **Complex Shipping Logic (`IFS`):**
    * Replaced complex Nested IFs with the cleaner `IFS` function to evaluate the Delivery Region.
    * *Logic:* If Region A = Charge $50; If Region B = Charge $75; If Region C = Charge $100.
* **Regional Aggregation (`SUMIF`):**
    * Created a summary table that calculated total sales **per region**.
    * *Logic:* Sum the "Total" column *only if* the "Region" column matches "Region A", "Region B", etc.
* **Formula Management:** Heavily utilized **Absolute References** for pricing tables to ensure formulas remained accurate when copied down hundreds of rows.
