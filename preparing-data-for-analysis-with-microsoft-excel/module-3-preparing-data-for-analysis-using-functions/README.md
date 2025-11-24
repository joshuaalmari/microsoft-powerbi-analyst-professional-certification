# 🛠️ Module 3: Preparing Data for Analysis Using Functions

This module transitions from basic calculations to advanced data transformation. It focuses on **cleaning** messy data, **standardizing** text formats, manipulating **dates**, and applying **logic** to automate decision-making within the spreadsheet.

---

## 🧹 Data Quality and Cleaning

Before analysis can begin, data must be consistent. "Dirty" data (inconsistent formats, typos) leads to incorrect insights.

### Common Data Errors
* **Inconsistent Entry:** Typing "Chicago" vs. "Chicago " (with a space) causes Excel to treat them as two different cities.
* **Wrong Data Types:** Typing currency symbols manually (e.g., `$100`) instead of using number formatting turns the value into text, making it unusable for calculation.
* **Structural Issues:** Placing multiple data points (City, State, Zip) in one column makes filtering impossible.
* **Date Errors:** Entering dates as text (using incorrect separators) prevents time-based analysis.
* **Duplicate Data:** Rows entered multiple times (often via copy-paste errors) artificially inflate results and distort analysis.

### Cleaning Functions
* **TRIM:** Removes all extra spaces from a text string, leaving only single spaces between words. It is essential for fixing invisible "leading" or "trailing" spaces that break VLOOKUPs or matching.
    * *Syntax:* `=TRIM(text)`
* **Standardizing Case:** Functions used to fix unprofessional or inconsistent capitalization.
    * `=UPPER(text)`: Converts to ALL UPPERCASE.
    * `=LOWER(text)`: Converts to all lowercase.
    * `=PROPER(text)`: Capitalizes the First Letter Of Each Word (Title Case).

---

## 🔤 Text Manipulation Functions

These functions allow you to extract specific parts of a cell or combine multiple cells into one.

### Extraction (Splitting Text)
* **LEFT:** Extracts a specific number of characters from the *start* of a cell.
    * *Syntax:* `=LEFT(text, [num_chars])`
* **RIGHT:** Extracts characters from the *end* of a cell.
    * *Syntax:* `=RIGHT(text, [num_chars])`
* **MID:** Extracts characters from the *middle* of a cell, given a starting point and length.
    * *Syntax:* `=MID(text, start_num, num_chars)`
* *Alternative Tool:* **Text to Columns** (Data Ribbon) is a non-formula feature used to split data based on delimiters (like commas or spaces) efficiently without writing functions.

### Combination (Joining Text)
* **CONCAT:** Joins text from multiple ranges or strings. It replaces the legacy `CONCATENATE` function.
    * *Syntax:* `=CONCAT(text1, text2, ...)`
    * *Note:* You must manually add delimiters (like spaces) as arguments: `=CONCAT(A2, " ", B2)`.
* **TEXTJOIN:** A more advanced version of CONCAT that allows you to specify a delimiter *once* and ignore empty cells.
    * *Syntax:* `=TEXTJOIN(delimiter, ignore_empty, text1, ...)`
* **TEXTSPLIT:** Spills text across columns or rows based on delimiters.
    * *Syntax:* `=TEXTSPLIT(text, col_delimiter)`

---

## 📅 Date and Time Intelligence

Excel stores dates as **Serial Numbers** (starting from Jan 1, 1900) and time as decimal fractions. This allows for mathematical operations on dates.

### Dynamic Dates
* **TODAY():** Returns the current date. Updates every time the workbook recalculates.
* **NOW():** Returns the current date *and* time.
* **Applications:** Useful for calculating "Days Overdue" or "Days Until Launch" (e.g., `=Deadline_Date - TODAY()`).

### Project Management Calculations
* **NETWORKDAYS:** Calculates the number of working days between two dates, automatically excluding weekends (Saturday/Sunday).
    * *Syntax:* `=NETWORKDAYS(start_date, end_date, [holidays])`
    * *Holidays:* You can optionally exclude specific dates (like public holidays) by selecting a range containing those dates.
* **NETWORKDAYS.INTL:** Allows customization of which days are considered weekends (e.g., only Sunday).
* **DATEDIF:** A legacy function used to calculate the exact difference between dates in years ("Y"), months ("M"), or days ("D").

### Extraction and Compilation
* **DAY/MONTH/YEAR:** Extracts the specific component from a date serial number.
* **DATE:** Reassembles separate numbers into a valid Excel date.
    * *Syntax:* `=DATE(year, month, day)`

---

## 🧠 Logical Functions (Decision Making)

Logical functions allow Excel to ask Yes/No questions about data and perform different actions based on the answer.

### The IF Function
* **Concept:** Checks a condition. If TRUE, do X. If FALSE, do Y.
* **Syntax:** `=IF(logical_test, value_if_true, value_if_false)`
* **Operators:**
    * `=` (Equal to)
    * `>` (Greater than), `<` (Less than)
    * `>=` (Greater/Equal), `<=` (Less/Equal)
    * `<>` (Not equal to)

### Complex Logic (Nested IFs and IFS)
* **Nested IF:** Placing an IF function inside another IF function to test multiple conditions (e.g., Tier 1 Bonus, Tier 2 Bonus, No Bonus).
* **IFS Function:** A cleaner alternative to Nested IFs. It evaluates multiple conditions sequentially and returns the value corresponding to the *first* TRUE result.
    * *Syntax:* `=IFS(test1, value1, test2, value2, ...)`

### Expanding Logic (AND / OR)
These are usually nested *inside* the `logical_test` argument of an IF function.
* **AND:** Returns TRUE only if **all** arguments are true.
    * *Example:* `=IF(AND(Sales>1000, Attendance>90%), "Bonus", "No Bonus")`
* **OR:** Returns TRUE if **at least one** argument is true.

---

## 📊 Conditional Aggregation

These functions perform math (Sum, Count, Average) *only* on cells that meet specific criteria.

| Function | Purpose | Syntax |
| :--- | :--- | :--- |
| **SUMIF** | Adds values in a range that match criteria. | `=SUMIF(range, criteria, [sum_range])` |
| **COUNTIF** | Counts the number of cells that match criteria. | `=COUNTIF(range, criteria)` |
| **AVERAGEIF** | Averages values in a range that match criteria. | `=AVERAGEIF(range, criteria, [average_range])` |

* **Note on Criteria:** Text criteria must be enclosed in double quotes (e.g., "Seattle"). Logical criteria must also be in quotes (e.g., ">100").
