## 📋 Practical Labs & Exercises

The exercises in this module focus on advanced visualization techniques, including mobile optimization, geospatial analysis, and extending Power BI capabilities with custom visuals and Python scripting.

---

### 🧪 Lab 1: Optimizing a report for mobile
* **Objective:** Adapt an existing desktop sales report for executive consumption on mobile devices. The goal was to create a vertical, touch-friendly view for stakeholders traveling between meetings.
* **Files:**
    * [📂 View Lab Files](./lab-1-optimizing-a-report-for-mobile/)
    * [📊 View Mobile Layout](./lab-1-optimizing-a-report-for-mobile/Optimizing-a-report-for-mobile%20-%20Final.pbix)

#### Key Actions Performed:
* **Layout Configuration:** Accessed the **Mobile Layout** view to redesign the report flow without affecting the desktop version.
* **Visual Selection:** Pinned specific high-impact visuals (KPI Chart, Bubble Chart, Pie Chart) to the mobile canvas.
* **Mobile Formatting:** Adjusted the size and position of the visuals to fit the narrow phone form factor, ensuring text and data points were legible on small screens.

---

### 🧪 Lab 2: Visualizing data by geographical location
* **Objective:** Create a focused summary report for regional managers to predict sales trends. The task involved using a specialized map visual to display data for specific US states.
* **Files:**
    * [📂 View Lab Files](./lab-2-visualizing-data-by-geographical-location/)
    * [📊 View Map Report](./lab-2-visualizing-data-by-geographical-location/Visualizing-data-by-geographical-location%20-%20Final.pbix)

#### Key Actions Performed:
* **Data Preparation:** Reviewed and adjusted data types in the *Column Tools* tab to ensure the location fields were correctly recognized as geospatial data.
* **Shape Map Creation:** Implemented a **Shape Map** visual to display sales density across US states.
* **Configuration:** Applied the **"Accessible City Park"** theme and configured the color saturation to visually represent sales trends (e.g., darker shades for higher sales).
* **Zoom Controls:** Enabled and validated zoom controls to allow users to manually drill down into specific regions.

---

### 🧪 Lab 3: Activity: Installing custom visualizations from AppSource
* **Objective:** Expand the native visualization options to better display regional sales data. The goal was to import and configure a certified custom visual from the Microsoft marketplace.
* **Files:**
    * [📂 View Lab Files](./lab-3-installing-custom-visualizations/)
    * [📊 View Custom Visual Report](./lab-3-installing-custom-visualizations/Adventure-Works-Regional-Sales%20-%20Final.pbix)

#### Key Actions Performed:
* **AppSource Integration:** Accessed the "Get more visuals" menu and searched for the **Aster Plot** visual.
* **Visual Implementation:** Converted a standard Donut Chart into an Aster Plot to represent values by both slice width and depth.
* **Formatting:** Configured the Legend (Left position, Blue color) and enabled **Center Labels** with specific formatting (Blue, 10pt) to match the report's cohesive theme.

---

### 🧪 Lab 4: Activity: Adding a chart using Python
* **Objective:** Leverage Python scripting to create a highly customized bar chart that goes beyond standard Power BI capabilities.
* **Files:**
    * [📂 View Lab Files](./labs/lab-4-adding-a-chart-using-python/)
    * [📊 View Python Visual](./labs/lab-4-adding-a-chart-using-python/Python_Sales_Chart.pbix)

#### Key Actions Performed:
* **Environment Setup:** Configured Power BI Options to detect the local **Python home directory**.
* **Scripting:** Wrote a Python script using the `matplotlib` library to generate a bar chart plotting *Total Sales* by *Month*.
* **Code Customization:** Modified the script code directly to change the bar colors to **Red**.
* **Interactivity Test:** Added a standard Power BI **Slicer** (Product Category) to the page and verified that the Python visual automatically filtered and updated when different categories were selected.
