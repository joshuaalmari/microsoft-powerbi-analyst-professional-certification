# 🚀 Module 1: Data Sources in Power BI

This module initiates **Course 3: Extract, Transform and Load Data**. It focuses on the "Extract" phase of the ETL pipeline, detailing data structures, connection protocols, storage architectures, and automation strategies within Power BI.

---

## 🏗️ Data Classification and Storage Strategy

Before ingesting data, an analyst must understand its structure to choose the correct storage solution.

### Data Types
* **Structured Data:** Highly organized quantitative data stored in rows and columns (Relational). Easily searchable.
    * *Storage:* Relational Databases (SQL Server, Azure SQL), Excel.
* **Unstructured Data:** Data without a predefined model, often qualitative.
    * *Examples:* Images, video files, social media posts, text documents.
    * *Storage:* **Azure Blob Storage** (optimized for binary large objects).
* **Semi-Structured Data:** Data that uses tags or markers to separate elements but lacks a rigid schema.
    * *Examples:* JSON, XML, HTML.
    * *Process:* Often requires **Serialization**—converting the data into a specific format for transmission and storage.

---

## 🔌 Data Connectors and Sources

Power BI uses "Connectors" to bridge the gap between the application and the raw data source.

### Dataset vs. Data Source
* **Data Source:** The origin of the data (e.g., an SQL Server, a CSV file on a hard drive).
* **Dataset:** The container within Power BI that holds the data, connection info, and credentials.

### Connection Protocols
* **Authentication Methods:** When connecting to a database, you must choose the correct credential type:
    * **Windows:** Uses your current OS login.
    * **Database:** Uses specific SQL username/password credentials managed by a DBA.
    * **Microsoft Account:** Uses Azure Active Directory (OAuth) credentials.
* **Limitations:**
    * **Column Limit:** A single dataset is restricted to **16,000 columns**.
    * **Source Limit:** A user can have up to **1,000 data sources** per account.

---

## 📂 Dataset Architecture: Local vs. Shared

Power BI allows datasets to be reused across the organization to prevent data silos.

### Local Datasets
* **Definition:** Data exists only within a specific report or user's desktop file.
* **Pros:** Full control, high security (locked to one user).
* **Cons:** Difficult to collaborate; creates version control issues.

### Shared Datasets
* **Definition:** A centralized dataset published to the Power BI Service.
* **Governance:**
    * **Build Permissions:** Controls who can create new reports from this data.
    * **Endorsement:** Datasets can be marked as **Promoted** (ready for broad use) or **Certified** (verified by IT/Admin).
* **Benefit:** Ensures a "Single Source of Truth" across departments (e.g., Sales and Warehouse using the same numbers).

---

## 💾 Storage Modes

A critical architectural decision affecting performance and data freshness.

### 1. Import Mode (The Default)
* **How it works:** Copies data from the source into Power BI's internal memory.
* **Pros:** Fastest query performance; supports all DAX functions.
* **Cons:** Data is static until refreshed.
* **Critical Warning:** Switching a table from DirectQuery to Import is **irreversible**.

### 2. DirectQuery
* **How it works:** Stores **no data**. Sends queries to the source system in real-time.
* **Pros:** Handles massive datasets (Petabytes); data is always current.
* **Cons:** Slower performance; dependent on source system speed.

### 3. Dual Mode (Hybrid)
* **How it works:** Tables act as *either* Import or DirectQuery depending on the query context.
* **Use Case:** Optimizing "Dimension" tables (like *Date* or *Product*) that interact with both massive fact tables and smaller lookup tables.

### 4. Composite Models
* Allows mixing multiple DirectQuery sources and Import data in a single report, enabling cross-database analysis.

---

## 🤖 Automation: Refresh Scheduling

To keep "Import Mode" data current without manual intervention, automation is required.

### The Refresh Workflow
1.  **Configuration:** Performed in the **Power BI Service** (Data Hub > Settings).
2.  **Frequency:** Can be scheduled Daily or Weekly.
3.  **Capacity Limits:**
    * **Shared Capacity (Pro):** Maximum **8 refreshes per day**.
    * **Premium Capacity:** Up to 48 refreshes per day.
4.  **Maintenance:** If the source file moves or passwords change, the refresh will fail. Connection strings must be updated in "Data Source Settings".
