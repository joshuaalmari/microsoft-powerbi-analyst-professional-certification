## 📋 Practical Labs & Exercises

The exercises in this module focus on applying design theory to create cohesive, professional reports. The projects involve managing the design lifecycle—from data ingestion to the application of color theory, positioning, and conditional formatting.

---

### 🧪 Lab 1: Improving report cohesiveness
* **Objective:** Create a unified marketing budget report by consolidating data from multiple quarters. The goal was to transform raw data into a cohesive visual narrative by applying consistent themes and logical positioning.
* **Files:**
    * [📂 View Lab Files](./labs/lab-1-improving-report-cohesiveness/)
    * [📊 View Final Report](./labs/lab-1-improving-report-cohesiveness/Sales_Target_Report.pbix)

#### Key Actions Performed:
* **Data Consolidation (ETL):**
    * Connected to multiple Excel files representing different quarters (`Q1` and `Q2`).
    * Used Power Query to **Append** the datasets into a single master table, ensuring headers were promoted and data types were consistent.
* **Visual Composition:**
    * Created a **Table Visual** to display detailed budget vs. actuals and a **Pie Chart** to visualize budget distribution by category.
    * Aligned visuals to create a logical flow and consistent scale across the report page.
* **Design & Theming:**
    * Applied the **"Accessible City Park"** report theme to instantly standardize the color palette and fonts.
    * Used **Conditional Formatting** to dynamically highlight top sales figures with specific font colors.
    * Manually customized specific data points with a unique color to draw attention to key performance drivers.

---

### 🧪 Lab 2: Highlighting key information
* **Objective:** Format a sales-versus-target report to emphasize critical data points for executive review. The task focused on using color and conditional logic to make key insights stand out immediately.
* **Files:**
    * [📂 View Lab Files](./labs/lab-2-highlighting-key-information/)
    * [📊 View Highlighted Report](./labs/lab-2-highlighting-key-information/Sales_Target_Formatted.pbix)

#### Key Actions Performed:
* **Layout Optimization:** Arranged a detailed **Table** and a **Column Chart** vertically to allow for easy comparison between granular data and high-level trends.
* **Visual Hierarchy:** Inserted the company logo in the top-left corner and increased title font sizes to **20pt** (Bold) to establish a clear reading order.
* **Conditional Formatting:**
    * Applied logic to the *Sales* column to turn text **Pink** (#f1c4cc) for minimum values and **Dark Red** (#6f3640) for maximum values.
    * Used the **"Show All"** data colors feature to manually override the color of the *2022 Sales* bar to **Gold** (#AD8F21), instantly differentiating the current year's performance from historical data.
