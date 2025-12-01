
## 📋 Practical Labs & Exercises

This module's exercises focus on troubleshooting performance issues and implementing advanced storage strategies. The projects involve auditing slow reports, optimizing DirectQuery settings, and building aggregation tables to handle massive datasets efficiently.

---

### 🧪 Lab 1: Optimizing a DirectQuery model
* **Objective:** Optimize a sluggish report connected to a live SQL database. The goal was to reduce the "chattiness" of the report (too many queries) and improve table retrieval speeds.
* **Files:**
    * [📂 View Lab Files](./labs/lab-1-optimizing-a-directquery-model/)
    * [📊 View Optimized Report](./labs/lab-1-optimizing-a-directquery-model/Optimized_Sales_Report.pbix)

#### Key Actions Performed:
* **Connection Setup:** Established a **DirectQuery** connection to the SQL database, selecting Fact and Dimension tables without importing data.
* **Query Reduction:**
    * Accessed **Options** to disable default cross-highlighting, preventing unnecessary queries when users click visuals.
    * Added **"Apply" buttons** to the Filter Pane and Slicers, ensuring the database is only queried when the user finishes their selection.
* **Storage Optimization:** Converted the Fact table from **DirectQuery** to **Import Mode** to demonstrate the performance gains of caching data in memory.

---

### 🧪 Lab 2: Improving data model performance
* **Objective:** Diagnose and fix a sluggish report caused by an inefficient relationship structure. The goal was to identify the specific relationship bottleneck and adjust its properties.
* **Files:**
    * [📂 View Lab Files](./labs/lab-2-improving-data-model-performance/)
    * [📊 View Optimized Model](./labs/lab-2-improving-data-model-performance/AdventureWorksSales_Optimized.pbix)

#### Key Actions Performed:
* **Performance Diagnosis:** Used the **Data View** and **Model View** to inspect the schema and identify a relationship causing high latency.
* **Relationship Tuning:**
    * Modified the **Cross-filter direction** from "Both" (Bi-directional) to "Single" to reduce the processing load required to propagate filters.
    * Adjusted **Cardinality** settings to align with the data structure (enforcing One-to-Many).
* **Validation:** Verified that the report visuals loaded faster after simplifying the filter path.

---

### 🧪 Lab 3: Creating aggregations
* **Objective:** Optimize a model containing millions of rows by creating a pre-aggregated summary table. The task involved building a high-performance "Import" table to handle high-level queries while keeping the original detailed data available.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-creating-aggregations/)
    * [📊 View Aggregation Model](./labs/lab-3-creating-aggregations/Aggregations_Configured.pbix)

#### Key Actions Performed:
* **Aggregation Table Construction:**
    * Duplicated the raw Fact table in Power Query.
    * Used the **Group By** transformation to create a summary table (`SalesAgg`) grouped by `Order Date`, aggregating metrics like `TotalQuantityCount` and `SumTotalSales`.
* **Storage Configuration:** Set the new Aggregation table to **Import Mode** (for speed) while leaving the original Fact table in **DirectQuery Mode** (for detail).
* **Relationship Management:** Connected the new `SalesAgg` table to the `Date` dimension to ensure slicers worked across both the summary and detailed data.
