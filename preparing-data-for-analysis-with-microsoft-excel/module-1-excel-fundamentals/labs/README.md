# 📋 Practical Labs & Exercises

This module includes hands-on scenarios using data from **AdventureWorks**, a fictional multinational manufacturing company. Below are the key projects completed to demonstrate proficiency.

---

### 🧪 Lab 1: Data Entry, Formatting, and Worksheet Management
* **Scenario:** An executive based in the USA, required a financial report integrating external data from a PDF (`Exchange Rates.pdf`) into an existing Excel workbook (`Sample.xlsx`). The dataset required cleaning, international currency formatting, and structural reorganization for a presentation.
* **Files:**
    * [📂 View Lab Files](./labs/lab-1-adding-data-to-a-worksheet/)
    * [📊 View Completed Workbook](./labs/lab-1-adding-data-to-a-worksheet/Sample_Completed.xlsx)

#### Key Actions Performed:
* **Data Cleaning & Structure:**
    * **Column Management:** Deleted the redundant "State Abbreviation" column to declutter the international dataset.
    * **Data Correction:** Identified and fixed numeric errors where Excel treated numbers as text due to special characters (removed `~` from cell G18).
    * **Data Entry:** Inserted a new "Country" column and utilized **Autofill** to efficiently populate "USA", "Japan", and "Germany".
    * **Segmentation:** Inserted new rows to visually separate data blocks for Japan and Germany.
* **Advanced Formatting:**
    * **Visual Styling:** Standardized headers using **Font Size 14**, background colors, and **Center Alignment**. Used the **Format Painter** to copy these styles to the new Country sub-headers.
    * **Layout:** Applied **Wrap Text** to fix header visibility issues without creating excessive whitespace.
    * **Multi-Currency Formatting:** Applied specific formats to different data ranges:
        * **USA:** Standard Dollar ($).
        * **Germany:** Euro (€).
        * **Japan:** Yen (¥) — *Note: This required accessing the "More Accounting Formats" menu as Yen is not in the default dropdown*.
* **Worksheet Management:**
    * **External Data Integration:** Created a new sheet named "Exchange Rates" and manually entered data derived from an external PDF.
    * **Organization:** Renamed generic tabs to "Sample Figures" and "Exchange Rates" for clarity.
    * **Presentation:** Reordered the tabs for logical flow and **Hid** the irrelevant "Contacts" sheet to focus the stakeholder presentation.

---

### 🧪 Lab 2: Data Organization (Standard and Multi-level Sorting)
* **Scenario:** The Analytics Team needed to reorganize a large product inventory file (151 rows) to view data grouped by vendor and stock level, making it ready for management review.
* **Files:**
    * [📂 View Lab Files](./labs/lab-2-sorting-data/)
    * [📊 View Completed Workbook](./labs/lab-2-sorting-data/Inventory_Completed_Sort.xlsx)

#### Key Actions Performed:
* **Preparation:** Added a **visual marker** (yellow fill) to a row to easily track how simple and complex sorting operations physically reorder the data.
* **Alpha-Numeric Sorts:** Applied standard sorts to data columns (e.g., **Product Name**, **Supplier**) and performed a numeric sort on **Date Entered** (Oldest to Newest).
* **Multi-Level Sort:** Performed a focused sort using the dialog box to group data by two criteria simultaneously: **Supplier** (Ascending) and **Units in Stock** (Descending).
* **Process Note:** Demonstrated proficiency with keyboard shortcuts to access the Sort dialog and used **Undo (Ctrl+Z)** to reverse accidental sorts.

---

### 🧪 Lab 3: Data Extraction (Filtering for Analysis)
* **Scenario:** An Inventory Analyst submitted a list of complex questions requiring precise extraction of numerical counts (record quantities) from the inventory file for analysis.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-filtering-data/)
    * [📊 View Completed Workbook](./labs/lab-3-filtering-data/Inventory_Completed_Filter.xlsx)

#### Key Actions Performed:
* **Query Setup:** Turned on the **Filter** feature (Data tab) to enable on-the-fly analysis.
* **Categorical Filtering:** Isolated records to find the total number of listings for **Gear Components**.
* **Compound Date Filtering:** Filtered records first by **Supplier (Z123)** and then adjusted the date filter to find counts for orders placed in **2023** and **2022** separately.
* **Advanced Text Filtering:** Used the **Text Filter** submenu on the "Product Name" column to find all versions of **Mountain Bike Frames**.
* **Stock Level Analysis:** Applied a second filter on the already-filtered mountain bike data to determine how many orders had a **Stock Level > 500**.
* **Validation:** Verified the total number of extracted records using the count displayed on the Excel status bar after each filter operation.
