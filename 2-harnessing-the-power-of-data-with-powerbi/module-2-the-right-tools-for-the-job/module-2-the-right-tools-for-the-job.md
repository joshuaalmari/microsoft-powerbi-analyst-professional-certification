# 🛠️ Module 2: The Right Tools for the Job (Data Acquisition & Transformation)

This module focuses on the critical backend processes of data analysis: identifying the right data, bringing it into the system (Ingestion), and cleaning it for analysis (Transformation). It introduces the **ETL** framework and **Microsoft Power Query** as the primary tool for shaping data.

---

## 🎯 Data Identification and Evaluation

Before analysis begins, an analyst must define the business goal to determine what data is required.

### Types of Data
* **Structured Data:** Highly organized and formatted, typically found in relational databases (SQL) or ERP systems (Enterprise Resource Planning). Examples include sales tables, inventory lists, and customer records.
* **Semi-Structured Data:** Contains tags or markers to separate elements but lacks a rigid schema. Examples include sensor data (logs), JSON files, or email metadata.
* **Unstructured Data:** Lacks a predefined data model, making it the most difficult to analyze. Examples include social media posts, videos, images, and free-text customer reviews.

### Evaluation Criteria
When selecting data sources, analysts must ask:
* **Relevance:** Does this data directly answer the business question?
* **Granularity:** Is the data detailed enough (e.g., daily vs. monthly sales)?
* **Connectivity:** Can we connect this external data (e.g., foot traffic sensors) with internal data (sales figures) to find correlations?

---

## 🔄 The Power BI Workflow

To work effectively, components must be used in the correct sequence.

1.  **Create (Power BI Desktop):** The development phase. Analysts connect to data sources, clean/transform data, build models, and design reports.
2.  **Publish (Power BI Service):** The deployment phase. Reports are uploaded to the cloud to create dashboards and assign security permissions.
3.  **Share (Service & Mobile):** The consumption phase. Stakeholders access dashboards via web browsers or mobile apps to make decisions.

---

## 🏗️ The ETL Process

**ETL** (Extract, Transform, Load) is the industry-standard framework for moving data from source to destination.

### 1. Extract (Gathering & Ingestion)
Retrieving raw data from various sources.
* **Methods:**
    * **Manual Entry:** High risk of error, slow.
    * **File-Based:** Importing Excel/CSV files.
    * **Database Connections:** Direct SQL queries to live systems (efficient).
    * **Web Scraping:** Automated extraction from websites.
    * **Streaming:** Real-time data flow (e.g., IoT sensors).

### 2. Transform (Cleaning & Shaping)
The most time-consuming phase. Raw data is rarely ready for analysis.
* **Tasks:** Removing duplicates, handling missing values (nulls), splitting columns, changing data types (e.g., text to date), and standardizing units of measure (e.g., currency conversion).

### 3. Load (Storage)
Writing the cleaned data into the destination (Data Warehouse or Power BI Data Model).
* **Storage Planning:** Organizations must plan for capacity, scalability, and security (encryption, access controls) to ensure data is safe and retrievable.

---

## ⚡ Microsoft Power Query

Power Query is the dedicated **Data Transformation Engine** within Power BI (and Excel). It automates the ETL process.

### Core Features
* **Connectivity:** Connects to hundreds of sources (SQL, Web, Excel, Salesforce).
* **No-Code Transformation:** Provides a graphical interface to clean data without writing code (though it uses the **M Language** in the background).
* **Repeatable Workflows:** Power Query records every step (e.g., "Removed Top 3 Rows", "Changed Type"). When data is refreshed, these steps run automatically, saving hours of manual work.

---

## 🧹 Data Cleaning Strategies

Data cleaning can happen at two stages. Choosing the right location is critical for efficiency.

| Strategy | Description | Pros & Cons |
| :--- | :--- | :--- |
| **Cleaning at Source** | Fixing errors in the original system (e.g., the SQL Database or Excel file). | **Pros:** Fixes it for everyone forever. Best for data integrity.<br>**Cons:** Requires permission/access to the source system. |
| **Cleaning in Power BI** | Using Power Query to filter and fix errors during import. | **Pros:** Does not alter original data; Analyst has full control.<br>**Cons:** Processing repeats every refresh; fixes apply *only* to that report. |

### Common Data Quality Issues
* **Duplicates:** Artificially inflate sales numbers and skew averages.
* **Null Values:** Gaps in data that can break calculations.
* **Inconsistent Formatting:** Mixed date formats (MM/DD vs DD/MM) or mixed casing (e.g., "New York" vs "new york") prevents proper grouping.
