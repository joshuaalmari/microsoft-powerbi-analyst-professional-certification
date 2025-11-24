## 📂 Practical Labs & Exercises

This module includes hands-on scenarios using data from **AdventureWorks**, a fictional multinational manufacturing company. Below are the key projects completed to demonstrate proficiency.

---

### 🧪 Lab 1: Calculating Profit and Margin
* **Scenario:** Aimee, an executive at AdventureWorks, required a detailed financial model to present at a management review. The goal was to calculate wholesale costs, shipping fees, retail pricing with markup, and final profit margins for a specific division's sales data.
* **Files:**
    * [📂 View Lab Files](./lab-1-calculating-profit-and-margin/)
    * [📊 View Completed Workbook](./lab-1-calculating-profit-and-margin/Revenue%20Figures%20Completed.xlsx)

#### Key Formulas Constructed:
* **Cost Analysis:**
    * **Purchase Cost:** Calculated by multiplying *Items Purchased* by *Wholesale Cost*.
    * **Shipping Costs:** Calculated total shipping fees using a fixed rate stored in cell **P1**. Used **Absolute References (`$P$1`)** to ensure this rate remained constant when the formula was copied down thousands of rows.
    * **Total Cost:** Summed the Purchase Cost and Shipping Costs.
* **Pricing Strategy (Markup):**
    * **Retail Price:** Engineered a complex formula to set a price that covered the wholesale cost, individual shipping cost, plus a **50% markup**.
    * **Syntax Control:** Utilized **Parentheses `()`** to group the cost additions before applying the percentage multiplier, ensuring the Order of Precedence calculated the markup on the *total* cost, not just one part.
* **Revenue & Profit:**
    * **Revenue:** Calculated total earnings based on *Items Sold* multiplied by the calculated *Retail Price*.
    * **Profit:** Derived by subtracting *Total Costs* from *Revenue*.
    * **Profit Margin:** Calculated the overall division margin using the formula `=(Total Revenue - Total Costs) / Total Revenue`. This metric demonstrates what percentage of sales actually turned into profit.
* **Efficiency:**
    * Used the **Autofill double-click shortcut** to instantly apply these complex formulas to the entire dataset (over 200 rows), verifying that Excel correctly identified the data range.

---

### 🧪 Lab 2: Preparing a Monthly Sales Report
* **Scenario:** Lucas needed to present a monthly performance review for the "A2Mountain Bike Frame" product line. The task involved generating aggregate metrics (Total Revenue, Units Sold) and identifying performance extremes (Best/Worst sales days) from raw daily data.
* **Files:**
    * [📂 View Lab Files](./lab-2-preparing-a-monthly-sales-report/)
    * [📊 View Completed Workbook](./lab-2-preparing-a-monthly-sales-report/Monthly%20Sales%20Report%20Completed.xlsx)

#### Key Functions Applied:
* **Aggregations (`SUM`):**
    * Calculated **Total Revenue** and **Total Units Sold** for the month.
    * *Process Note:* Manually adjusted the cell range selection when AutoSum incorrectly guessed the data block.
* **Performance Extremes (`MIN` / `MAX`):**
    * Used `MIN` to identify the lowest daily sales volume.
    * Used `MAX` to identify the highest daily sales volume.
    * Correlated these figures with specific dates to provide context for the sales review meeting.
* **Operational Metrics (`COUNT` / `AVERAGE`):**
    * **Days in Month:** Used `COUNT` on the Date column. *Key Insight:* Excel stores dates as serial numbers, allowing mathematical functions to count them effectively.
    * **Daily Averages:** Used `AVERAGE` to calculate the mean daily revenue, providing a baseline for performance comparison.
* **Formatting:**
    * Verified that Excel automatically applied **Accounting Number Format** to the calculated results based on the source data's formatting.
