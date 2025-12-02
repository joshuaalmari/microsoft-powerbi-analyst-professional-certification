## 📋 Practical Labs & Exercises

The exercises in this module focus on enhancing User Experience (UX) through accessibility features, data governance via sorting and filtering, and advanced interactivity using app-like navigation elements.

---

### 🧪 Lab 1: Creating an accessible report
* **Objective:** Retrofit an existing sales report to meet accessibility standards (WCAG), ensuring it is usable by stakeholders with visual or motor impairments.
* **Files:**
    * [📂 View Lab Files](./lab-1-creating-an-accessible-report/)
    * [📊 View Accessible Report](./lab-1-creating-an-accessible-report/Creating-an-accessible-report%20-%20Final.pbix)

#### Key Actions Performed:
* **Screen Reader Support:** Added descriptive **Alt Text** to charts (e.g., "Sales trends by month") to ensure context is conveyed to non-visual users.
* **Keyboard Navigation:** Manually configured the **Tab Order** in the Selection Pane to ensure users can navigate through visuals in a logical sequence without a mouse.
* **Visual Clarity:** Enabled **Markers** on line charts to distinguish data series by shape rather than just color, and applied a high-contrast **Theme** to improve readability.

---

### 🧪 Lab 2: Improving accessibility with tooltips
* **Objective:** Provide granular data details on demand without cluttering the main dashboard. The goal was to make complex charts accessible and understandable for users who need additional context.
* **Files:**
    * [📂 View Lab Files](./lab-2-improving-accessibility-with-tooltips/)
    * [📊 View Enhanced Report](./lab-2-improving-accessibility-with-tooltips/Tooltip_Configured.pbix)

#### Key Actions Performed:
* **Contextual Data:** Customized the standard **Tooltip** by dragging additional fields (e.g., *Order Quantity* and *Product Stock*) into the Tooltips field well.
* **Aggregation Logic:** Configured the tooltip aggregations (Sum, Average) to ensure the pop-up data provided meaningful context when hovering over specific data points.
* **User Guidance:** Used tooltips to define metrics and explain data anomalies, aiding users who need additional support to interpret the visualizations.

---

### 🧪 Lab 3: Sorting and filtering a report
* **Objective:** Optimize a sales report for clarity by strictly controlling how data is ordered and what data is visible to the end-user.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-sorting-and-filtering-a-report/)
    * [📊 View Optimized Report](./labs/lab-3-sorting-and-filtering-a-report/Sorting_Filtering_Configured.pbix)

#### Key Actions Performed:
* **Sort Logic:** Corrected the sort order on time-series visuals to display data **Chronologically** (Jan, Feb, Mar) rather than by magnitude (highest sales first), ensuring linear trends were readable.
* **Data Governance (Filtering):** Applied a **Page-Level Filter** to exclude "Cancelled" orders from all visuals, ensuring the report reflected only valid revenue.
* **Interaction Management:** Configured **Edit Interactions** to switch visuals from "Cross-Highlighting" (dimming) to "Cross-Filtering" (removing) for cleaner data views.

---

### 🧪 Lab 4: Creating an interactive report
* **Objective:** Transform a static multi-page report into a dynamic, app-like experience for executive stakeholders. The goal was to simplify navigation and allow users to reset or customize their view instantly.
* **Files:**
    * [📂 View Lab Files](./labs/lab-4-creating-an-interactive-report/)
    * [📊 View Interactive Dashboard](./labs/lab-4-creating-an-interactive-report/AdventureWorks_Interactive.pbix)

#### Key Actions Performed:
* **Dynamic Navigation:** Inserted and configured **Buttons** (Right Arrow, Left Arrow) to create a guided navigation path between the "Sales Summary" and "Sales Details" pages.
* **Bookmark Logic:** Created a "Reset" bookmark that captures the default state of the report (all filters cleared). Linked this to a **"Clear All Slicers"** button to allow users to restart their analysis with one click.
* **Slicer Management:** Added and synchronized **Slicers** across pages to ensure filter consistency.
* **Drill-Through:** Configured a detailed "Product" page to accept drill-through actions from the summary chart, enabling deep-dive analysis.
