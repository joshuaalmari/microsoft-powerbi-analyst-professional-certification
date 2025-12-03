
## 📋 Practical Labs & Exercises

The exercises in this module focus on advanced analytical capabilities. The projects progress from statistical segmentation to AI-driven insights, forecasting, and root cause analysis.

---

### 🧪 Lab 1: Performing an analysis
* **Objective:** Enhance existing visualizations to provide clearer insights into product performance and demographics using statistical tools.
* **Files:**
    * [📂 View Lab Files](./lab-1-performing-an-analysis/)
    * [📊 View Enhanced Report](./lab-1-performing-an-analysis/Performing-an-analysis%20-%20Final.pbix)

#### Key Actions Performed:
* **Top N Analysis:** Applied a "Top 10" filter to the Funnel Chart to declutter the view, focusing stakeholder attention only on the highest-revenue products.
* **Binning:** Created "Age Bins" (e.g., 20-30, 30-40) to improve the clarity of a Histogram, transforming granular data into readable distribution patterns.
* **Clustering:** Automatically identified natural segments in the Scatter Chart by using the "Automatically find clusters" feature, grouping cities into distinct performance categories based on data similarity.

---

### 🧪 Lab 2: Using the Play Axis visualization
* **Objective:** Visualize how data trends evolve over time using animation. The goal was to track the relationship between advertising spend and sales revenue across different campaigns.
* **Files:**
    * [📂 View Lab Files](./lab-2-using-the-play-axis-visualization/)
    * [📊 View Animated Report](./lab-2-using-the-play-axis-visualization/Time-series-analysis%20-%20Final.pbix)

#### Key Actions Performed:
* **Scatter Plot Configuration:** Plotted *Sales Revenue* vs. *Profit Margin* to analyze the correlation between spend and return.
* **Animation:** Dragged the *Date* field into the **Play Axis** well to animate the data points.
* **Trend Observation:** Played the timeline to observe how specific marketing campaigns shifted quadrants over the fiscal year, identifying which strategies became more profitable over time.

---

### 🧪 Lab 3: Explaining the increase
* **Objective:** Use automated AI tools to diagnose sudden changes in data trends without manual investigation.
* **Files:**
    * [📂 View Lab Files](./labs/lab-3-explaining-the-increase/)
    * [📊 View Diagnostic Report](./labs/lab-3-explaining-the-increase/Sales_Fluctuation.pbix)

#### Key Actions Performed:
* **AI Analysis:** Right-clicked a sharp increase in the *Total Sales* line chart and selected **"Analyze > Explain the increase"**.
* **Insight Generation:** Reviewed the automatically generated "Waterfall Chart" provided by Power BI, which highlighted that the specific increase was driven primarily by the "Bicycles" product category.
* **Visual Integration:** Pinned the AI-generated explanation visual directly to the report to provide permanent context for the anomaly.

---

### 🧪 Lab 4: Forecasting sales
* **Objective:** Project future financial performance based on historical data patterns to aid in resource planning.
* **Files:**
    * [📂 View Lab Files](./labs/lab-4-forecasting-sales/)
    * [📊 View Forecast Model](./labs/lab-4-forecasting-sales/Sales_Forecast.pbix)

#### Key Actions Performed:
* **Forecasting Model:** Activated the **Forecast** feature in the Analytics pane of a Line Chart plotting *Sales* over *Time*.
* **Configuration:** Defined the forecast length (e.g., next 6 months) and set a **95% Confidence Interval** to visualize the probable range of outcomes (grey shaded area).
* **Seasonality:** Adjusted settings to account for seasonal trends, ensuring the prediction accurately reflected recurring sales cycles.

---

### 🧪 Lab 5: Root cause analysis
* **Objective:** Enable open-ended exploration of a complex environmental dataset to understand the drivers behind CO2 emissions.
* **Files:**
    * [📂 View Lab Files](./labs/lab-5-root-cause-analysis/)
    * [📊 View AI Analysis Report](./labs/lab-5-root-cause-analysis/Emission_Analysis.pbix)

#### Key Actions Performed:
* **Decomposition Tree:** Built an interactive tree visual to analyze *Average CO2 Emissions*, allowing users to drill down into any dimension (Powertrain, Engine Size) in any order.
* **AI Splits:** Utilized the **"Low Value"** AI split to automatically traverse the data hierarchy.
* **Insight Discovery:** Let the AI pinpoint the exact combination of attributes (e.g., Hybrid Electric Vehicle + Specific Engine Class) that resulted in the lowest emissions, effectively isolating the root cause of high efficiency.
