## 📋 Practical Labs & Exercises

The exercises in this module focus on the final stages of the reporting lifecycle: dashboard creation, distribution, and performance optimization. The projects involve consolidating visuals for executive monitoring, preparing reports for stakeholder consumption, and fine-tuning report performance.

---

### 🧪 Lab 1: Building a dashboard
* **Objective:** Construct a high-level executive summary dashboard by consolidating key insights from multiple separate reports (Sales, Customer, and Order reports).
* **Files:**
    * [📂 View Lab Files](./lab-1-building-a-dashboard/raw-files)
    * [📄 View Documentation](./lab-1-building-a-dashboard/Building-a-dashboard-documentation.pdf)

#### Key Actions Performed:
* **Visual Aggregation:** Pinned critical visuals (e.g., *Total Sales*, *Order Trends*) from three different source reports onto a single **Dashboard** canvas.
* **Layout Design:** Reorganized tiles to prioritize high-impact KPIs at the top left, ensuring immediate visibility of business health.
* **Mobile Optimization:** Used the **Mobile Layout** view to create a phone-friendly version of the dashboard, ensuring executives could access key metrics on the go.

---

### 🧪 Lab 2: Sharing a report
* **Objective:** Prepare a comprehensive financial performance report for executive review. The goal was to structure the report for easy readability, publish it to a secure workspace, and generate static exports for offline meetings.
* **Files:**
    * [📂 View Lab Files](./lab-2-sharing-a-report/)
    * [📊 View Final Report](./lab-2-sharing-a-report/Adventure-Works-Product-Sales-Report%20-%20Final.pbix)

#### Key Actions Performed:
* **Pagination:** Organized the report into distinct pages (e.g., "Summary" vs. "Details") to improve navigation and reduce visual clutter.
* **Publishing:** Uploaded the local `.pbix` file to the **Power BI Service** to make it accessible to the "Financial Team" workspace.
* **Exporting:** Generated a **PDF** version of the report to provide a static snapshot for stakeholders who require offline access.

---

### 🧪 Lab 3: Improving DAX performance
* **Objective:** Optimize a sluggish sales report to improve load times and interactivity. The task involved diagnosing specific performance bottlenecks and refactoring inefficient DAX code.
* **Files:**
    * [📂 View Lab Files](./lab-3-improving-DAX-performance/)
    * [📊 View Optimized Model](./lab-3-improving-DAX-performance/Improving-DAX-performance%20-%20Final.pbix)

#### Key Actions Performed:
* **Diagnosis:** Used the **Performance Analyzer** to record visual load times and identified the "Total Sales by Year" area chart as the primary bottleneck.
* **Code Analysis:** Examined the underlying DAX query and identified an inefficient use of nested `CROSSJOIN` and `GENERATESERIES` functions.
* **Refactoring:** Rewrote the measure using `SUMX` and a simplified `CROSSJOIN` logic to reduce the computational load on the engine.
* **Validation:** Re-ran the Performance Analyzer to verify that the DAX query duration was significantly reduced.
