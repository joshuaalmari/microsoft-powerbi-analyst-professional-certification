
### 📋 Practical Labs & Exercises

This final module features a comprehensive capstone project that consolidates all data modeling skills learned throughout the course. The objective is to build a robust, high-performance data model from scratch to solve specific business challenges regarding sales stagnation and inventory management.

---

### 🏆 Final Project: Building and optimizing a data model
* **Objective:** Revolutionize the organization's reporting capabilities by constructing an efficient data model. The task involved transforming raw sales and manufacturing data into a structured relational model to align products, markets, and strategies.
* **Files:**
    * [📂 View Project Files](./final-project/)
    * [📊 View Final Model](./final-project/AdventureWorksSales%20-%20Final.pbix)

#### Key Actions Performed:
* **Model Architecture:**
    * Imported raw `Customers` and `Orders` datasets to establish the foundation of the model.
    * Used **Data View** to audit the initial state of the tables before modeling.
* **Optimization Strategies:**
    * **Data Typing:** Manually configured column data types (e.g., setting `Order Quantity` to **Whole Number**, `Discounts` to **Decimal Number**, and `Order Date` to **Date**) to minimize memory usage and ensure calculation accuracy.
    * **Performance Tuning:** Disabled the **Auto Date/Time** feature in global options to prevent the automatic generation of hidden date tables, significantly reducing the model's file size.
* **Relationship Management:**
    * Established a **One-to-Many** relationship between `Customers` and `Orders` using `Customer ID` as the key.
    * Enforced a **Single** cross-filter direction to ensure filters propagate logically from the dimension table to the fact table without creating ambiguous paths.
