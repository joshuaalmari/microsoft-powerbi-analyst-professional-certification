# 🏗️ Module 1: Data Modeling Fundamentals

This module initiates **Course 4: Data Modeling in Power BI**. It shifts focus from data preparation to **Data Modeling**—the process of defining relationships between tables to enable accurate reporting. It covers schema design, cardinality, normalization, and the specific configuration of table and column properties to optimize performance and usability.

---

## 📐 The Core Building Blocks: Views & Architecture

Power BI offers specific views to manage the data structure. Understanding the distinction between them is critical for efficiency.

### 1. The Model View (Architecture)
* **Purpose:** The structural blueprint of your data. This is where you define *how tables relate* to one another .
* **Key UI Elements:**
    * **Diagram View:** Visualizes tables as boxes and relationships as connection lines .
    * **Properties Pane:** The command center for configuration. Allows you to edit settings for multiple objects at once (e.g., select 5 columns and hide them all simultaneously) .

### 2. The Table View (Inspection)
* *Formerly "Data View".*
* **Purpose:** To inspect the actual raw data rows after loading. You cannot see relationships here, but you can see the data values to verify accuracy .
* **Key UI Elements:**
    * **Data Grid:** A spreadsheet-like view of the data .
    * **Contextual Ribbons:** The **Table Tools** and **Column Tools** tabs appear at the top only when you select data in this view .

---

## ⚙️ Configuration: Where to Do What?

Many tasks can be done in both views, but some are specific to one.

### 🔹 Unique to Model View (Properties Pane)
These advanced architectural settings are **only** available here:
* **Synonyms:** Defining alternate names for Q&A (e.g., letting users type "Revenue" to find "Sales Amount") .
* **Row Label:** Defining which column represents the "row" (e.g., telling Power BI that the "Name" column identifies the row, not the "ID") .
* **Key Column:** Designating a unique identifier for the table .
* **Display Folder:** Grouping measures and columns into folders for a cleaner Report View.

### 🔹 Unique to Table View (Data Grid)
* **Visual Inspection:** Sorting and filtering the *raw data* to check for errors (e.g., "Did my 'Remove Duplicates' step actually work?") .
* **Copying Data:** You can right-click a cell or table to copy raw values to the clipboard.

### 🔸 Shared Capabilities (Do in Both)
These actions can be performed in the **Column Tools** ribbon (Table View) OR the **Properties Pane** (Model View).

| Feature | Description |
| :--- | :--- |
| **Formatting** | Setting the format (Currency, Percentage), decimal places, and symbols ($ vs €) . |
| **Data Type** | defining if a column is Text, Whole Number, Decimal, or Date/Time . |
| **Sort By Column** | A critical feature. Allows you to sort one column by another (e.g., sorting "Month Name" by "Month Number" so April follows March, not August) . |
| **Data Category** | Tagging a column (e.g., "City", "Web URL", "Image URL") so Power BI knows how to render it . |
| **Summarization** | Defining the default math behavior (Sum, Average, or **"Don't Summarize"** for ID columns) . |
| **Visibility** | Hiding tables or columns (using the **Eye Icon** or "Is Hidden" toggle) to declutter the Report View . |

---

## 🗺️ Schema Design Architectures

Choosing the right schema is the most important architectural decision in Power BI.

### 1. Flat Schema
* **Structure:** All data is stored in a single, massive table.
* **Pros:** Simple to understand; easy for very small datasets .
* **Cons:** Massive data redundancy; slow performance at scale; difficult to maintain .

### 2. Star Schema (The Gold Standard)
* **Structure:** A central **Fact Table** surrounded by **Dimension Tables**.
    * **Fact Table:** Contains quantitative metrics (Sales Amount, Quantity) and foreign keys. Long and narrow.
    * **Dimension Table:** Contains descriptive attributes (Product Name, City, Date). Short and wide .
* **Pros:** Optimized for query performance; reduces redundancy; intuitive for report users .

### 3. Snowflake Schema
* **Structure:** An extension of the Star Schema where Dimension tables are normalized into multiple related tables (e.g., Product table linked to Subcategory, linked to Category) .
* **Pros:** Maximizes data integrity and eliminates all redundancy .
* **Cons:** Increases complexity; query performance can decrease due to the extra joins required to retrieve basic attributes .

---

## 🔗 Model Relationships & Logic

Relationships are the "wires" that allow filters to flow from one table to another.

### Cardinality Types
* **One-to-Many (1:*):** The standard relationship. A unique record in a Dimension (One) filters many records in a Fact Table (Many) .
* **One-to-One (1:1):** Rare. Usually indicates tables should be merged or are split for security reasons .
* **Many-to-Many (*:*):** Multiple records in Table A match multiple records in Table B. *Risk:* Introduces ambiguity; use with caution .

### Cross-Filter Direction
* **Single (Default):** Filters flow from the "One" side to the "Many" side. This ensures a predictable reporting path .
* **Both (Bi-Directional):** Filters flow in both directions. *Risk:* Can cause performance degradation and ambiguous filter paths .

---

## 🛠️ Data Engineering & Optimization

### Normalization vs. Denormalization
* **Normalization:** Splitting data into multiple related tables (Snowflake approach). Improves data integrity .
* **Denormalization:** Combining tables to simplify the model (Flat/Star approach). Improves read performance .

### Granularity
* **Definition:** The level of detail in the data (e.g., Transaction-level vs. Daily Summary) .
* **Impact:** High granularity allows deep analysis but increases file size. Relationships can only be built between tables with matching granularity .
