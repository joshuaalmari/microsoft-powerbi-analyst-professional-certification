# 🏗️ Module 1: Data Modeling Fundamentals

This module initiates **Course 4: Data Modeling in Power BI**. It shifts focus from data preparation to **Data Modeling**—the process of defining relationships between tables to enable accurate reporting. It covers schema design, cardinality, normalization, and the specific configuration of table and column properties to optimize performance and usability.

---

## 📐 The Core Building Blocks: Tables & Views

Power BI offers specific views to manage the data structure. Understanding the difference between them is critical for modeling.

### The Model View (Architecture)
The workspace for architecting relationships.
* **Diagram View:** Visualizes tables as boxes and relationships as lines.
* **Properties Pane:** Allows configuration of technical settings (synonyms, row labels, hiding tables) without changing the data itself.
* **Relationship Management:** Where cardinality and filter directions are defined.

### The Data View (Inspection)
Unlike the Report view, this allows analysts to inspect the raw data rows after they have been loaded.
* **Data Grid:** Displays the actual records. Useful for sorting and verifying data quality before modeling.
* **Column Tools:** A contextual ribbon for managing data types, formatting (Currency/Percentage), and sorting logic (e.g., "Sort By Column").

---

## 🗺️ Schema Design Architectures

Choosing the right schema is the most important architectural decision in Power BI.

### 1. Flat Schema
* **Structure:** All data is stored in a single, massive table (similar to a wide Excel spreadsheet).
* **Pros:** Simple to understand; easy for very small datasets.
* **Cons:** Massive data redundancy; slow performance at scale; difficult to maintain or update.

### 2. Star Schema (The Gold Standard)
* **Structure:** A central **Fact Table** surrounded by **Dimension Tables**.
    * **Fact Table:** Contains quantitative metrics (Sales Amount, Quantity) and foreign keys. Long and narrow.
    * **Dimension Table:** Contains descriptive attributes (Product Name, City, Date). Short and wide.
* **Pros:** Optimized for query performance; reduces redundancy; intuitive for report users.

### 3. Snowflake Schema
* **Structure:** An extension of the Star Schema where Dimension tables are normalized into multiple related tables (e.g., Product table linked to Subcategory, linked to Category).
* **Pros:** Maximizes data integrity and eliminates all redundancy.
* **Cons:** Increases complexity; query performance can decrease due to the extra joins required to retrieve basic attributes.

---

## 🔗 Model Relationships & Logic

Relationships are the "wires" that allow filters to flow from one table to another.

### Cardinality Types
* **One-to-Many (1:*):** The standard relationship. A unique record in a Dimension (One) filters many records in a Fact Table (Many).
* **One-to-One (1:1):** Rare. Usually indicates tables should be merged, unless splitting data for security or domain grouping.
* **Many-to-Many (*:*):** Multiple records in Table A match multiple records in Table B. Often requires a "Bridge Table" to resolve ambiguity.

### Cross-Filter Direction
* **Single (Default):** Filters flow from the "One" side to the "Many" side. This ensures predictable reporting path.
* **Both (Bi-Directional):** Filters flow in both directions. *Risk:* Can cause performance degradation and ambiguous filter paths.

### Granularity
* **Definition:** The level of detail in the data (e.g., Transaction-level vs. Daily Summary).
* **Impact:** High granularity allows deep analysis but increases file size. Low granularity (summary) is faster but limits drill-down.
* **Alignment:** Relationships can only be built between tables with matching granularity.

---

## 🛠️ Data Engineering & Optimization

### Normalization vs. Denormalization
* **Normalization:** The process of splitting data into multiple related tables to minimize redundancy (Snowflake approach). Improves data integrity.
* **Denormalization:** The process of combining tables to simplify the model (Star/Flat approach). Improves read performance.

### Resolving Common Challenges
* **Inferior Performance:** Often caused by complex calculations on flat schemas. *Solution:* Normalize columns into dimension tables.
* **Inconsistent Data:** caused by duplicate entries. *Solution:* Enforce unique keys in dimension tables.
* **Limited Scalability:** Flat files cannot grow with the business. *Solution:* Transition to a Star Schema.

---

## ⚙️ Object Configuration (Properties Pane)

The **Model View** allows for deep configuration of how tables and columns behave in the report.

### Table Properties
* **Name & Description:** Critical for documentation in shared models.
* **Row Label:** Defines which column represents the row when the table is used in Q&A.
* **Is Hidden:** The **Eye Icon** hides technical tables (like calculation tables) from the Report View to reduce clutter for end-users.

### Column Properties
* **Data Category:** Tags a column so Power BI knows how to treat it (e.g., tagging a text column as "City" or "Web URL").
* **Summarization:** Defines the default math (Sum, Average, Don't Summarize). *Tip: Set ID columns to "Don't Summarize" so Power BI doesn't accidentally add them up.*
* **Sort By Column:** A critical feature. Allows you to sort one column by another (e.g., Sorting the text "Month Name" by a hidden "Month Number" column so April comes after March, not August).
* **Formatting:** Controlling decimal places, currency symbols, and date formats globally for the model.

---
