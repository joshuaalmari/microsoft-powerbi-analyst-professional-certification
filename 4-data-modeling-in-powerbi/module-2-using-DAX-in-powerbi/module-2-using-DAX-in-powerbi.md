# 🧮 Module 2: Using Data Analysis Expressions (DAX) in Power BI

This module builds a solid foundation in **Data Analysis Expressions (DAX)**, the calculation language used in **Power BI**, **Excel Power Pivot**, and **Analysis Services**. It explains how DAX works with the data model, how formulas are structured, and how to use calculated columns, calculated tables, and measures to answer real business questions.

---

## 📘 1. DAX Fundamentals

### 1.1 What DAX Is

**DAX (Data Analysis Expressions)** is a formula language that provides:

- Functions  
- Operators  
- Constants  
- Expressions  

You use DAX to:

- Create **calculated columns** and **calculated tables** in the model  
- Define **measures** that power visuals and KPIs  
- Implement logic that isn’t present in the original source data  

DAX operates **on top of a data model**, which means you must understand:

- Tables and relationships  
- Keys and cardinality  
- Granularity (level of detail)  

to use it effectively.

---

### 1.2 Basic DAX Formula Pattern

All DAX model calculations follow the same basic structure:

- Calculated table, column, or measure:

  `<Calculation Name> = <DAX Expression>`

Examples:

- Calculated table  
  `Ship Date = 'Date'`

- Calculated column  
  `Total Sales = Sales[Quantity] * Sales[Unit Price]`

- Measure  
  `Revenue = SUM(Sales[Sales Amount])`

The expression must return:

- A **table object** → for calculated tables  
- A **scalar value** → for calculated columns and measures  

---

### 1.3 DAX Syntax Essentials

Key syntax rules:

- Formulas always start with an **equals** sign `=`  
- You can use:
  - Scalar constants (numbers, text)  
  - References to tables, columns, or measures  
  - Functions with arguments  
  - Operators (+, -, *, /, &&, ||, etc.)  

Examples of valid formulas:

- `= 3`  
- `= "Sales"`  
- `= 'Sales'[Amount]`  
- `= 0.03 * [Amount]`  
- `= PI()`  

The meaning of a formula depends on **context**, which is covered later.

---

### 1.4 Data Types in DAX

DAX works with the following core data types:

- **Text** – string values, e.g., `"Hello"`  
- **Whole Number** – integers, e.g., `123`  
- **Decimal Number (Float)** – e.g., `1.23`  
- **Boolean** – `TRUE` or `FALSE`  
- **Date/Time** – date or datetime values  
- **Currency** – fixed decimal number suitable for financials  

DAX performs **implicit conversions** when needed, but you should still design calculations with the expected type in mind.

---

### 1.5 References to Tables, Columns, and Measures

DAX formulas refer only to:

- Tables  
- Columns  
- Measures  

**Table references**

- `'Table Name'`  
- Quotes are required if the table name has spaces, special characters, or is a reserved word.  
- Example:  
  `Ship Date = 'Date'`  

**Column references**

- `[Column Name]` → unqualified (same table)  
- `Table[Column Name]` → fully qualified  

Example:

- `Revenue = SUM(Sales[Sales Amount])`  

**Measure references**

- `[Measure Name]`  

Example:

- `Profit = [Revenue] - [Cost]`  

Best practice:

- Always fully qualify columns: `Sales[Sales Amount]`  
- Avoid prefixing measures with table names unless necessary to disambiguate.

---

### 1.6 Operators

DAX operators support arithmetic, comparisons, logical evaluation, and text concatenation.

**Arithmetic**

- `+` addition  
- `-` subtraction  
- `*` multiplication  
- `/` division  
- `^` exponentiation  

**Logical**

- `&&` logical AND  
- `||` logical OR  

**Comparison**

- `=` equal to  
- `<>` not equal to  
- `>` greater than  
- `>=` greater than or equal to  
- `<` less than  
- `<=` less than or equal to  

**Text concatenation**

- `&` joins text strings  

Example:

- `[Region] & ", " & [City]`

**Parentheses**

- `()` group expressions and control evaluation order.

---

## 🧮 2. DAX Functions and CALCULATE

### 2.1 Function Basics

A function in DAX is a named expression that:

- Accepts **arguments**  
- Returns either a **scalar** or a **table**  

General form:

`FUNCTION_NAME(argument1, argument2, ...)`

Conventions:

- Function names are typically written in uppercase, e.g., `SUM`, `CALCULATE`, `FILTER`.  
- Some functions have no arguments but still require parentheses, e.g., `PI()`.

Common function families:

- Aggregation: `SUM`, `AVERAGE`, `MIN`, `MAX`, `COUNT`, `DISTINCTCOUNT`  
- Logical: `IF`, `AND`, `OR`, `NOT`  
- Text: `LEFT`, `CONCATENATE`  
- Date/Time: `YEAR`, `MONTH`, `NOW`  
- Time Intelligence: `SAMEPERIODLASTYEAR`, `DATESYTD`, `DATESMTD`, `DATESQTD`, `EDATE`  
- Relational: `RELATED`, `RELATEDTABLE`  
- Statistical: `MEDIAN`, `STDEV.P`, `RANKX`  
- Table functions: `FILTER`, `SUMMARIZE`, `ADDCOLUMNS`, `DISTINCT`, `VALUES`, `UNION`, `CALENDAR`, `CALENDARAUTO`, `TOPN`, `FILTERS`  

---

### 2.2 CALCULATE: The Core DAX Function

`CALCULATE` is one of the most important functions in DAX. It:

- Evaluates an expression  
- In a context modified by one or more filter arguments  

Pattern:

```DAX
CALCULATE(
    <expression>,
    <filter1>,
    <filter2>,
    ...
)
```

Example: compute total sales for products of a specific color:

```DAX
Total Sales (Blue) =
CALCULATE(
    SUM(Sales[Sales Amount]),
    Product[Color] = "Blue"
)
```

Here:

- `SUM(Sales[Sales Amount])` is evaluated  
- Only for rows where `Product[Color] = "Blue"`  

`CALCULATE` is also central to:

- Time intelligence patterns  
- Semi-additive measure logic  
- Scenario analysis with multiple filters  

---

### 2.3 Variables (VAR / RETURN)

Variables simplify complex DAX expressions by:

- Storing intermediate results  
- Improving readability and performance  

Pattern:

```DAX
Measure Name =
VAR SomeValue =
    <expression 1>
VAR AnotherValue =
    <expression 2>
RETURN
    <final expression that uses the variables>
```

Example: year-over-year sales growth:

```DAX
Sales YoY % =
VAR SalesPriorYear =
    CALCULATE(
        [Sales],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
RETURN
DIVIDE(
    [Sales] - SalesPriorYear,
    SalesPriorYear
)
```

---

### 2.4 Whitespace and Formatting

Whitespace (spaces, tabs, line breaks) does not change logic, but it greatly improves readability.

Recommended practices:

- Add spaces around operators: `A + B`  
- Put each major function argument on a separate line  
- Indent nested functions  

Readable example:

```DAX
Total Revenue =
CALCULATE(
    SUM(Sales[Revenue]),
    FILTER(
        Sales,
        Sales[OrderYear] = 2018 &&
        Sales[Product Color] = "Blue"
    )
)
```

---

## 🧱 3. Context in DAX: Row Context and Filter Context

Correct use of **context** is fundamental to DAX.

### 3.1 Evaluation Context

The **evaluation context** is the environment in which a DAX expression is evaluated. It defines:

- Which rows are visible  
- Which filters are active  
- How relationships affect the current calculation  

Two key types of context:

- **Row context**  
- **Filter context**

They often work together.

---

### 3.2 Row Context

Row context refers to the **current row** being processed.

It is present when:

- You define a **calculated column**  
- You use **iterators** that evaluate row by row, such as `SUMX`, `AVERAGEX`, `FILTER`  

Example (calculated column):

```DAX
Total Sales =
Sales[Quantity] * Sales[Unit Price]
```

For each row:

- `Sales[Quantity]` is taken from that row  
- `Sales[Unit Price]` is taken from that row  
- The result is stored as the `Total Sales` value for that row  

Row context allows you to perform row-level calculations.

---

### 3.3 Filter Context

Filter context is the set of filters applied **before** an expression is evaluated.

It originates from:

- Report filters, slicers, and visual selections  
- Explicit filters in DAX, often through `CALCULATE` / `CALCULATETABLE`  
- Cross-filter propagation through relationships  

Example:

```DAX
Total Sales =
SUM(Sales[Sales Amount])
```

If a report filters:

- Year = 2024  
- Region = "North"  

then `Total Sales` is computed only over rows matching those filters.

---

### 3.4 Interaction Between Row and Filter Context

When DAX evaluates an expression:

1. **Filter context** determines which rows are visible.  
2. **Row context** (if present) iterates over those visible rows.  

Example:

- Filter context selects a given region and product category.  
- Within that subset, row context iterates each row to compute totals.

Multiple filters applied on different columns of the same table combine via a **logical AND**. Only rows that meet all filter conditions are included.

---

### 3.5 Relationships and Propagating Filters

Relationships influence how filters move between tables:

- Filters can propagate from one table to related tables.  
- The direction (single or bidirectional) affects how far filters flow.  

Key points:

- A filter on a dimension table typically reduces rows in a related fact table.  
- In large models with many relationships, filter propagation should be designed carefully to avoid ambiguity or performance issues.

Row context does not automatically cross relationships. To access related data in row context, use:

- `RELATED(column)` – access a value from a related table on the one-side  
- `RELATEDTABLE(table)` – access related rows on the many-side  

---

## 🗃️ 4. Calculated Tables and Table Functions

### 4.1 What Calculated Tables Are

A **calculated table** is:

- A table created with a DAX expression inside the model  
- Not directly imported from an external source  
- Evaluated and stored as part of the data model  

Use calculated tables to:

- Create summary tables  
- Normalize dimensions  
- Clone tables for scenario analysis  
- Create date tables  

---

### 4.2 Cloning Tables

Cloning creates a copy of a table so you can:

- Adjust or enrich the cloned version  
- Preserve the original data table, which might be refreshed from a source  

Pattern:

```DAX
Cloned Sales =
ALL(Sales)
```

This creates a new table with the same rows and columns as `Sales`. You can then extend `Cloned Sales` without affecting the original.

---

### 4.3 Combining Data into a Calculated Table

If data is split across different sources (for example, a customer table and a sales table), you can create calculated tables that combine and summarize them using functions like:

- `SUMMARIZE`  
- `ADDCOLUMNS`  
- `CALCULATE`  

Example: yearly sales summary by product category:

```DAX
Annual Sales Summary =
ADDCOLUMNS(
    SUMMARIZE(
        Sales,
        'Date'[Calendar Year],
        Product[Category]
    ),
    "Total Sales", CALCULATE(SUM(Sales[Sales Amount]))
)
```

---

### 4.4 Normalizing Dimension Tables

You can normalize a wide dimension table by creating smaller, related tables using calculated tables. For example, a product table can be split into:

- Product Category  
- Product Subcategory  
- Product  

This creates hierarchies that improve navigation and reporting.

---

### 4.5 Calendar Tables with CALENDAR and CALENDARAUTO

Time intelligence functions rely on a proper date table.

**Static date range:**

```DAX
Date =
CALENDAR(
    DATE(2015, 1, 1),
    DATE(2021, 12, 31)
)
```

**Automatic date range:**

```DAX
Date =
CALENDARAUTO()
```

`CALENDARAUTO` infers the minimum and maximum dates from the model and creates a contiguous date range.

Once created, mark the date table as a **Date table** in Power BI.

---

### 4.6 Core Table Functions

Some of the most frequently used table functions:

- `DISTINCT(column or table)`  
  Returns unique values. Useful for removing duplicates or building helper tables.

- `VALUES(column or table)`  
  Returns unique values including a possible blank row. Often used in dynamic measures.

- `UNION(table1, table2, ...)`  
  Appends rows from multiple tables with the same columns.

- `FILTER(table, condition)`  
  Returns only rows that satisfy the given condition. Common inside `CALCULATE` and iterators.

- `ADDCOLUMNS(table, "Name", expression, ...)`  
  Adds calculated columns to a table expression.

- `TOPN(N, table, orderByExpression, [Order])`  
  Returns the top N rows based on a sorting expression.

- `FILTERS(column)`  
  Returns the filter values applied directly to a column; used in more advanced scenarios.

These functions are building blocks for complex calculated tables and advanced measures.

---

## 🧱 5. Calculated Columns

### 5.1 What a Calculated Column Is

A **calculated column**:

- Is added to an existing table in the data model  
- Uses a DAX expression evaluated row by row  
- Stores its results as part of the model  
- Can be used in:
  - Rows/columns of visuals  
  - Slicers and filters  
  - Relationships  

Unlike measures, calculated columns do not change with filter context—they are evaluated when the column is computed.

---

### 5.2 Creating a Calculated Column (Example Workflow)

Assume a sales table includes:

- `Quantity`  
- `Unit Price`  
- `Cost`  

You want to derive:

- `Total Sales` per row  
- `Profit` per row  
- `Profit Margin` per row  

Steps in Power BI Desktop:

1. Open **Data view** and select the sales table.  
2. On the **Table Tools** tab, select **New column**.  
3. Create `Total Sales`:

   ```DAX
   Total Sales =
   Sales[Quantity] * Sales[Unit Price]
   ```

4. Create `Profit`:

   ```DAX
   Profit =
   Sales[Total Sales] - Sales[Cost]
   ```

5. Create `Profit Margin`:

   ```DAX
   Profit Margin =
   DIVIDE(Sales[Profit], Sales[Total Sales])
   ```

6. Format:
   - `Profit` as **Currency**  
   - `Profit Margin` as **Percentage**

These columns can now be used in visuals just like imported fields.

---

### 5.3 When to Use Calculated Columns vs Measures

Use a **calculated column** when:

- You need a **row-level attribute** (for example, category or label).  
- You need the value as a **key**, **grouping**, or **sort-by column**.  
- The logic does not depend on report filters.

Use a **measure** when:

- You want a **dynamic aggregation** that responds to filters/slicers.  
- The result should be recalculated for each visual and context.  

---

## 📏 6. Measures

### 6.1 What Measures Are

A **measure** is a DAX expression that:

- Returns a scalar value  
- Is evaluated in filter context  
- Recalculates dynamically based on slicers, filters, and interactions  

Measures are used in:

- Charts and tables  
- Cards and KPIs  
- Dashboards  

Examples:

```DAX
Total Sales =
SUM(Sales[Sales Amount])

Profit =
[Revenue] - [Cost]
```

---

### 6.2 Why Measures Are Important

Key benefits:

- **Dynamic** – react to the current filter context  
- **Reusable** – defined once, used in many visuals  
- **Consistent** – the same business logic everywhere  
- **Efficient** – evaluated at query time, not stored per row  

---

### 6.3 Creating Tables from Measures

You can create summary tables that use measures alongside groupings. For example:

```DAX
Product Sales Summary =
SUMMARIZE(
    Sales,
    Product[Product Name],
    "Total Sales", [Total Sales]
)
```

This yields a table with each product and its total sales, which can be further analyzed or referenced by other calculations.

---

## 📊 7. Types of Measures: Additive, Semi-Additive, Non-Additive

Understanding additivity is essential for correct reporting.

### 7.1 Additive Measures

**Additive measures** can be summed across all dimensions, including time.

Examples:

- Revenue  
- Quantity sold  
- Units produced  

If you sum revenue for January and February, the total is meaningful.

These measures typically use `SUM` over a numeric column.

---

### 7.2 Non-Additive Measures

**Non-additive measures** cannot be meaningfully summed across dimensions.

Examples:

- Averages (e.g., average sales per customer)  
- Ratios (e.g., profit margin, conversion rate)  

Incorrect:

- Adding the average for January and the average for February does not give a valid two-month average.

Correct pattern:

1. Compute totals for numerator and denominator across the period.  
2. Divide the totals:

```DAX
Average Sales per Customer =
DIVIDE(
    [Total Sales],
    DISTINCTCOUNT(Sales[Customer ID])
)
```

---

### 7.3 Semi-Additive Measures

**Semi-additive measures** can be aggregated across some dimensions, but not all (especially time).

Examples:

- Inventory balance  
- Account balance  

You can:

- Sum balances across products or locations **at a point in time**  

You should not:

- Sum balances across months to get a “total balance” for a period  

Instead, use time intelligence to pick the correct snapshot (for example, end of month).

---

## 📈 8. Statistical Functions

Statistical functions help analyze distributions, trends, and ranges.

### 8.1 AVERAGE

```DAX
Average Quantity Sold =
AVERAGE(Sales[Quantity])
```

Returns the arithmetic mean of numeric values in a column.

---

### 8.2 MEDIAN

```DAX
Median Response Time =
MEDIAN(Support[Response Time])
```

Returns the middle value in a sorted set of numbers. More robust to outliers than the average.

---

### 8.3 COUNT and DISTINCTCOUNT

```DAX
Number of Orders =
COUNT(Sales[Order ID])

Unique Customers =
DISTINCTCOUNT(Sales[Customer ID])
```

- `COUNT` – counts non-blank rows in a column  
- `DISTINCTCOUNT` – counts distinct, non-blank values  

---

### 8.4 MIN and MAX

```DAX
Minimum Inventory =
MIN(Inventory[Quantity])

Maximum Inventory =
MAX(Inventory[Quantity])
```

These functions provide the minimum and maximum values for a column, useful for range analysis and boundary checks.

---

## 🧭 9. Time Intelligence Overview

Time intelligence functions work with date tables to compute common time-based metrics.

Common functions:

- `SAMEPERIODLASTYEAR('Date'[Date])` – returns the same period one year earlier  
- `DATESYTD('Date'[Date])` – dates from the start of the year to the current date  
- `DATESMTD('Date'[Date])` – month-to-date  
- `DATESQTD('Date'[Date])` – quarter-to-date  
- `EDATE(start_date, months)` – shifts a date by a specified number of months  

Example pattern for year-over-year comparison:

```DAX
Sales YoY % =
VAR SalesPriorYear =
    CALCULATE(
        [Sales],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
RETURN
DIVIDE(
    [Sales] - SalesPriorYear,
    SalesPriorYear
)
```

rich reporting.

