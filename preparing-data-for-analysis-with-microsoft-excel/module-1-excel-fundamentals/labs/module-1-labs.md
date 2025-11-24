## 📋 Practical Labs & Exercises

The practical exercises in this module establish the foundation for efficient data management. The projects focus on **structuring raw data** for professional presentation and utilizing **sorting and filtering** tools to navigate and analyze large datasets effectively.

---

### 🧪 Lab 1: Adding Data to a Worksheet
* **Objective:** Transform a raw data source (PDF) into a structured, formatted Excel report for executive presentation. The task involved data cleaning, integration, and visual standardization.
* **Files:**
    * [📂 View Lab Files](./lab-1-adding-data-to-a-worksheet/)
    * [📊 View Completed Workbook](./lab-1-adding-data-to-a-worksheet/Sample_Completed.xlsx)

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

### 🧪 Lab 2: Sorting and Filtering Data
* **Objective:** Process a large product inventory file to support decision-making. The project required organizing the full dataset for management review and extracting precise record counts for analysis.
* **Files:**
    * [📂 View Lab Files](./lab-2-sorting-and-filtering-data/)
    * [📊 View Completed Workbook](./lab-2-sorting-and-filtering-data/Adventure%20Works%20Inventory%20Completed.xlsx)

#### 1. Data Reorganization (Sorting Focus)
* **Objective:** Establish grouping logic (e.g., by vendor and stock level) on the initial data sheet.
* **Actions Performed:**
    * **Preparation:** Added a **visual marker** (yellow fill) to a row to easily track how simple and complex sorting operations physically reorder the data.
    * **Alpha-Numeric Sorts:** Applied standard sorts to data columns (e.g., **Product Name**, **Supplier**) and performed a numeric sort on **Date Entered** (Oldest to Newest).
    * **Multi-Level Sort:** Performed a focused sort using the dialog box to group data by two criteria simultaneously: **Supplier** (Ascending) and **Units in Stock** (Descending).
    * **Process Note:** Demonstrated proficiency with keyboard shortcuts to access the Sort dialog and used **Undo (Ctrl+Z)** to reverse accidental sorts.

#### 2. Data Extraction and Analysis (Filtering Focus)
* **Objective:** Extract precise record counts required to answer complex inventory questions from the analyst.
* **Actions Performed:**
    * **Query Setup:** Turned on the **Filter** feature (Data tab) to enable on-the-fly analysis.
    * **Categorical Filtering:** Isolated records to find the total number of listings for **Gear Components**.
    * **Compound Date Filtering:** Filtered records first by **Supplier (Z123)** and then adjusted the date filter to find counts for orders placed in **2023** and **2022** separately.
    * **Advanced Text Filtering:** Used the **Text Filter** submenu on the "Product Name" column to find all versions of **Mountain Bike Frames**.
    * **Stock Level Analysis:** Applied a second filter on the already-filtered mountain bike data to determine how many orders had a **Stock Level > 500**.
    * **Validation:** Verified the total number of extracted records using the count displayed on the Excel status bar after each filter operation.
