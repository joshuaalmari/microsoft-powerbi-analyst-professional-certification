## 📋 Practical Labs & Exercises

The labs in this module focus on establishing the fundamental data pipeline. The projects involve connecting Power BI Desktop to static data sources and configuring the Power BI Service to automate data ingestion via cloud-based triggers.

---

### 🧪 Lab 1: Setting Up an Excel Data Source
* **Objective:** Consolidate disparate sales reports from multiple regional managers into a single analytical dataset. The task involves identifying a flat file, preparing the data structure, and establishing a stable connection in Power BI Desktop.
* **Files:**
    * [📂 View Lab Files](./lab-1-setting-up-excel-data-source/)
    * [📊 View Completed Report](./lab-1-setting-up-excel-data-source/Importing_Excel_Data_Source.pbix)

#### Key Actions Performed:
* **Data Preparation:**
    * Validated the source Excel file to ensure it met "Flat File" standards (no pivot tables, no total rows, consistent column data types).
    * Renamed tables to space-free formats (e.g., `SalesData`) to ensure compatibility with best practices.
* **Connection Configuration:**
    * Used the **"Get Data" > "Excel Workbook"** connector to establish a link to the local file.
    * Navigated the **Navigator Window** to select specific worksheets vs. named tables.
* **Data Inspection:**
    * Verified the import using the **Table View** to ensure all rows loaded correctly without truncation or formatting errors.

---

### 🧪 Lab 2: Implementing Triggers
* **Objective:** Eliminate the manual workload of daily reporting by creating an automated data pipeline. The task involves moving a local dataset to the cloud and configuring a time-based trigger to refresh the data automatically every night.
* **Files:**
    * [📂 View Lab Files](./lab-2-implementing-triggers/)
    * [📊 View Automation Config](./lab-2-implementing-triggers/Automation_Setup_Guide.pdf)

#### Key Actions Performed:
* **Cloud Ingestion:**
    * Uploaded the source Excel file to **OneDrive for Business** to enable cloud-to-cloud connectivity.
    * Used the **"Get Data"** feature within the **Power BI Service** (web browser) to connect directly to the OneDrive file, bypassing the local desktop.
* **Trigger Configuration:**
    * Accessed the **Dataset Settings** in the Power BI Service to locate the "Scheduled Refresh" options.
    * Configured a **Time-Based Trigger** to execute a data refresh daily at a specific time.
    * Defined the refresh frequency to ensure the management team always accesses the latest numbers without manual intervention.
