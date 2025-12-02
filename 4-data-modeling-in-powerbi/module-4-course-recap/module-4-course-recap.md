
# 🎓 Module 4: Course Recap

This final module consolidates the advanced skills acquired throughout the **Data Modeling** course. It reviews the end-to-end modeling journey—from architecting efficient schemas and defining relationships to writing complex DAX measures and tuning performance for enterprise-scale datasets.

---

## 🏗️ Phase 1: Data Modeling Foundations

The foundation of any report is a well-structured data model.

### Key Concepts
* **Schema Design:**
    * **Flat Schema:** Single-table models (simple but redundant).
    * **Star Schema:** The industry standard. Central Fact tables surrounded by Dimension tables.
    * **Snowflake Schema:** Normalized dimensions (e.g., Product -> Subcategory -> Category) for data integrity.
* **Relationships:**
    * **Cardinality:** Defining how records match (One-to-Many, Many-to-Many).
    * **Cross-Filter Direction:** Controlling how filters propagate (Single vs. Both).
    * **Active vs. Inactive:** Managing multiple relationship paths between tables.

---

## 📈 Phase 2: Data Analysis Expressions (DAX)

DAX is the formula language used to create dynamic insights that go beyond standard aggregations.

### Core Logic
* **Calculation Types:**
    * **Calculated Columns:** Static data stored in the model (Row Context).
    * **Measures:** Dynamic calculations computed on demand (Filter Context).
    * **Calculated Tables:** Generating new tables using DAX functions (e.g., `SUMMARIZE`, `CALENDAR`).
* **Context:** Understanding the difference between **Row Context** (current row) and **Filter Context** (active slicers/visuals) is crucial for accurate formulas.
* **Time Intelligence:** Using functions like `TOTALYTD` and `SAMEPERIODLASTYEAR` to compare performance over time.
* **Date Tables:** The importance of setting up a dedicated, contiguous Date Dimension for accurate time-based reporting.

---

## 🚀 Phase 3: Performance & Optimization

Ensuring reports run efficiently even as data volume grows.

### Optimization Strategies
* **Diagnostics:** Identifying performance bottlenecks using tools like Performance Analyzer.
* **Model Tuning:**
    * Reducing **Cardinality** to save memory.
    * Removing unnecessary columns and optimizing data types.
    * Using **Aggregations** to speed up queries on large datasets.
* **DirectQuery vs. Import:** Balancing the speed of Import mode with the real-time capabilities of DirectQuery.
