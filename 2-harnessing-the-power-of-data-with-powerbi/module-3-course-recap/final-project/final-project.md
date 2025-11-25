## 📋 Practical Labs & Exercises

This module concludes with a comprehensive final project that simulates the early stages of a major business initiative. It focuses on the strategic "pre-analysis" phase: identifying stakeholders, evaluating data sources, and performing initial cleaning to ensure data readiness.

---

### 🏆 Final Project: Product Launch Analysis
* **Objective:** Lay the groundwork for a high-stakes product launch analysis. The task involves identifying key stakeholders, evaluating the schema of a raw sales dataset, and designing a data cleaning strategy to ensure accuracy for strategic decision-making.
* **Files:**
    * [📂 View Project Files](./final-project/)
    * [📊 View Cleaned Dataset](./final-project/Sales%20Cleaned.xlsx)

#### Key Actions Performed:
* **Stakeholder Analysis:**
    * Identified core stakeholder groups (Marketing, Product Development, Sales) and defined their specific data needs (e.g., Customer Preferences for Product Dev, Sales Trends for Marketing).
    * Mapped data insights to business decisions, such as refining product features or targeting specific demographics.
* **Data Source Evaluation:**
    * Audited the raw `Sales.csv` file to determine available fields (`Product Category`, `Order Quantity`, `Customer ID`) and their relevance to the product launch strategy.
    * Identified data gaps and recommended integrating external sources (Marketing Data, Website Analytics, Customer Feedback) to create a holistic view of performance.
* **Data Import & Transformation:**
    * Used the **Text Import Wizard** in Excel to correctly parse the raw CSV file, identifying the **Semicolon (;)** delimiter to split merged data into distinct columns.
    * Standardized column data types to ensure accuracy (e.g., ensuring IDs are treated as Text to prevent calculation errors).
* **Cleaning Strategy Design:**
    * Defined a cleaning protocol for critical columns:
        * **Product Name/Category:** Recommended string manipulation functions (like `TRIM` or `PROPER`) to fix inconsistent formatting.
        * **Missing Data:** Developed a strategy for handling nulls in the `Product Description` field (e.g., excluding incomplete records or flagging them for review).
