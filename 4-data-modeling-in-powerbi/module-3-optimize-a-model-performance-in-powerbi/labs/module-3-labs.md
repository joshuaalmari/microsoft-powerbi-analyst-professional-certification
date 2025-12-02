## 📋 Practical Labs & Exercises

This module's exercises focus on performance tuning and optimization. The projects involves auditing report speed, reducing model bloat, optimizing live connections, and implementing advanced aggregation strategies to handle massive datasets.

---

### 🧪 Lab 1: Improving data model performance
* **Objective:** Diagnose and fix a sluggish report caused by an inefficient relationship structure. The goal was to identify the specific relationship bottleneck and adjust its properties to improve query speed.
* **Files:**
    * [📂 View Lab Files](./lab-1-improving-data-model-performance/)
    * [📊 View Optimized Model](./lab-1-improving-data-model-performance/AdventureWorksSales%20-%20Final.pbix)

#### Key Actions Performed:
* **Performance Diagnosis:** Used the **Model View** to inspect the schema and identify a **Many-to-Many** relationship between the `Customers` and `Orders` tables causing ambiguity and slowness.
* **Relationship Tuning:**
    * Modified the **Cardinality** from "Many-to-Many" to **"One-to-Many"** to accurately reflect the data structure.
    * Changed the **Cross-filter direction** from "Both" to **"Single"** to reduce the processing load required to propagate filters.

---

### 🧪 Lab 2: Optimizing the columns and Auto date/time
* **Objective:** Optimize a data model by reducing its memory footprint. The task involved identifying redundant metadata and disabling resource-heavy background features.
* **Files:**
    * [📂 View Lab Files](./lab-2-optimizing-the-columns-and-auto-date-and-time/)
    * [📊 View Lean Model](./lab-2-optimizing-the-columns-and-auto-date-and-time/AdventureWorksSales%20-%20Final.pbix)

#### Key Actions Performed:
* **Column Pruning:** Identified and **Deleted** the `Payment Method` column as it was unnecessary for the reporting requirements, freeing up memory.
* **Metadata Optimization:**
    * **Categorization:** Tagged the `Location` column as **City** to ensure correct map rendering.
    * **Data Types:** Changed `Order Quantity` from Text to **Whole Number** to allow for aggregation and reduce storage size.
* **Time Intelligence:** Accessed **Options > Current File > Data Load** and disabled **"Auto Date/Time"**, preventing Power BI from generating hidden date tables for every date column.

---

### 🧪 Lab 3: Optimizing a DirectQuery model
* **Objective:** Optimize a sluggish report connected to a live SQL database. The goal was to reduce the "chattiness" of the report (too many queries) and improve table retrieval speeds.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-optimizing-directquery/)
    * [📊 View Optimized Report](./labs/lab-3-optimizing-directquery/Optimized_Sales_Report.pbix)

#### Key Actions Performed:
* **Connection Setup:** Established a **DirectQuery** connection to the SQL database, selecting Fact and Dimension tables without importing data.
* **Query Reduction:**
    * Accessed **Options** to disable default cross-highlighting, preventing unnecessary queries when users click visuals.
    * Added **"Apply" buttons** to the Filter Pane and Slicers, ensuring the database is only queried when the user finishes their selection.
* **Storage Optimization:** Converted the Fact table from **DirectQuery** to **Import Mode** to demonstrate the performance gains of caching data in memory.

---

### 🧪 Lab 4: Adding an aggregation
* **Objective:** Optimize a model containing millions of rows by creating a pre-aggregated summary table. The task involved building a high-performance "Import" table to handle high-level queries while keeping the original detailed data available.
* **Files:**
    * [📂 View Lab Files](./labs/lab-4-adding-an-aggregation/)
    * [📊 View Aggregation Model](./labs/lab-4-adding-an-aggregation/Aggregations_Configured.pbix)

#### Key Actions Performed:
* **Aggregation Construction:** Created a `SalesAgg` table in Power Query by grouping data by `Order Date` and `Customer Key` to summarize Sales and Unit Price.
* **Storage Management:**
    * Set the `SalesAgg` table to **Import Mode** for maximum speed.
    * Set the related Dimension tables (`Customer`, `Date`) to **Dual Mode** so they could work with both the aggregated data and the original DirectQuery fact table.
* **Mapping:** Used the **Manage Aggregations** interface to map the summary columns (e.g., `SumSalesAmount`) to the detailed source columns, enabling Power BI to automatically switch tables based on the user's query.
