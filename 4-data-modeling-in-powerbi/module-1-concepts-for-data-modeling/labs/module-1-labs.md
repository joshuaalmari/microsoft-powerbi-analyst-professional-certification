
## 📋 Practical Labs & Exercises

The exercises in this module guide the learner through the evolution of data modeling. The projects start with basic Flat Schemas (single-source and multi-source), progress to the industry-standard Star Schema, and conclude with advanced Normalization techniques for Snowflake Schemas.

---

### 🧪 Lab 1: Configuring a Flat Schema
* **Objective:** Establish a baseline data model by importing a single, consolidated dataset into a simple Flat Schema. The goal was to perform initial property configuration to ensure the single-table model was ready for basic analysis.
* **Files:**
    * [📂 View Lab Files](./lab-1-configuring-a-flat-schema/)
    * [📊 View Flat Model](./lab-1-configuring-a-flat-schema/Configuring%20a%20Flat%20Schema.pbix)

#### Key Actions Performed:
* **Data Connection:** Connected Power BI Desktop to a single Excel worksheet containing consolidated product and order data.
* **Data Integrity:** Identified and removed duplicate records in the `OrderID` column to ensure unique transaction identifiers.
* **Property Configuration:**
    * Renamed the raw table to `Product` for clarity.
    * Added a description to the table metadata for documentation.
    * Formatted the `Product Price` column as **Currency** to ensure correct visualization.

---

### 🧪 Lab 2: Configure a Flat Schema with Multiple Sources
* **Objective:** Create a unified Flat Schema by manually integrating two separate data tables ("Sales" and "Salespersons"). The goal was to denormalize the data into a single table to simplify the model for a specific reporting need.
* **Files:**
    * [📂 View Lab Files](./labs/lab-2-multi-source-flat-schema/)
    * [📊 View Merged Model](./labs/lab-2-multi-source-flat-schema/Flat_Schema_Multi_Source.pbix)

#### Key Actions Performed:
* **Data Ingestion:** Loaded two distinct tables from the `AdventureWorksDataset` Excel workbook.
* **Cleaning:** Removed duplicate `SalesOrderNumber` entries to prepare the "Sales" table for merging.
* **Denormalization (Merging):**
    * Performed a **Left Outer Join** to merge the `Salesperson` details directly into the `Sales` table.
    * Expanded the merged columns to include `Employee ID`, `Salesperson Name`, and `Title`.
    * **Deleted** the original `Salesperson` table from the model, leaving only one flat, consolidated table.

---

### 🧪 Lab 3: Configuring a Star Schema
* **Objective:** Re-architect the data strategy by implementing a **Star Schema**. The task involved moving from a single table to a relational model with distinct Fact and Dimension tables to improve query performance.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-star-schema/)
    * [📊 View Star Model](./labs/lab-3-star-schema/Star_Schema_Configured.pbix)

#### Key Actions Performed:
* **Model Setup:** Disabled **"Auto-detect new relationships"** in Power BI Options to maintain full manual control over the schema design.
* **Table Classification:** Loaded four distinct tables (`Sales`, `Products`, `Region`, `Salesperson`) and identified `Sales` as the central **Fact Table**.
* **Relationship Building:**
    * Manually established relationships between the Fact table and Dimensions using common keys (e.g., `ProductKey`, `SalesTerritoryKey`).
    * Configured Cardinality as **Many-to-One (*:1)**.
    * Set Cross-filter direction to **Single** to ensure filters propagate correctly from Dimensions to Facts.

---

### 🧪 Lab 4: Changing your Star Schema into a Snowflake Schema
* **Objective:** Optimize the model for data integrity by **Normalizing** the Product dimension. The goal was to split a single wide dimension into a hierarchy of related tables.
* **Files:**
    * [📂 View Lab Files](./labs/lab-4-snowflake-schema/)
    * [📊 View Snowflake Model](./labs/lab-4-snowflake-schema/Snowflake_Schema_Configured.pbix)

#### Key Actions Performed:
* **Normalization via DAX:**
    * Used Data Analysis Expressions (DAX) `GROUPBY` functions to mathematically create new `Category` and `Subcategory` tables from the original `Product` data.
* **Hierarchy Construction:**
    * Established a chain of relationships: `Category` → `Subcategory` → `Product` → `Sales`.
    * Configured the relationship chain as **One-to-Many**, allowing filters on the "Category" table to flow all the way down to the "Sales" transactions.
* **Validation:** Verified that the new normalized structure reduced redundancy while maintaining accurate filtering capabilities.
