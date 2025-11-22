# 📊 Module 1: Excel Fundamentals

This module covers the essential building blocks of Microsoft Excel, establishing the skills necessary to navigate the interface, manage large datasets, and perform foundational data organization tasks like sorting and filtering.

---

## 🖥️ The Excel Interface and File Management

Understanding the layout and file constraints is the first step to efficient data management.

### Key UI Elements
* **Title Bar:** Located at the very top of the window, this bar displays the current filename, the Autosave toggle switch, and the central Search box used for finding specific tools or content.
* **The Ribbon:** The main control panel located immediately below the title bar. It contains specific **Command tabs** (like *Home*, *Insert*, *Data*) that organize hundreds of commands into logical groups.
    * *Contextual Tabs:* These are hidden tabs (e.g., *Chart Design*) that automatically appear on the ribbon only when you select a specific object, like a chart or table.
* **Formula Bar:** A long bar located above the grid letters (A, B, C...). It displays the *actual* underlying content of a selected cell (such as a formula or raw data), even if the cell itself displays a formatted result.
* **Worksheet Grid:** The primary area for data entry, composed of a grid where vertical columns (identified by letters) and horizontal rows (identified by numbers) intersect to form cells.

### File Naming Conventions
* Filenames can contain spaces and capital letters, but you must avoid special punctuation characters (like slashes or colons) as they are not permitted by the file system.
* **Character Limit:** While filenames can technically support up to 255 characters, it is best practice to keep them under 31 characters for readability and compatibility.

---

## 📝 Data Entry and Formatting

Correctly entering and formatting data ensures readability and prevents calculation errors.

### Data Types and Alignment
* **Default Alignment:** When you type data, Excel automatically aligns **text to the left** and **numbers to the right**. This provides a quick visual cue to check if your numbers are being recognized correctly.
* **Mixed Data:** If a cell contains a mix of letters and numbers (e.g., "ID-123"), Excel treats the entire entry as **text**.
* **Visual Error Indicators:**
    * **Scientific Notation:** If a number is too wide for the column, Excel displays it in a compressed format like `1E+09`. This is not an error, but a display setting indicating you need to widen the column.
    * **Hash Symbols (####):** If a column is too narrow to display the formatted content (often dates or currency), Excel fills the cell with pound signs (`####`). Widen the column to reveal the data.

### Entry Shortcuts
* **Autocomplete:** As you type text, Excel looks at the column above and suggests matching words to speed up entry.
* **Autofill Handle:** Hover over the bottom-right corner of a selected cell until the cursor changes to a **narrow black cross**. Dragging this handle copies data or extends a series into adjacent cells.
* **Format Painter:** Represented by a **paintbrush icon** on the Home ribbon, this tool copies the style (font, color, border) from a selected cell so you can "paint" that style onto other cells.

### Visualization Tools
* **Wrap Text:** Keeps the column width fixed but increases the row height, stacking long text vertically within the cell so the full heading is visible.
* **Number Formatting:** Tools in the *Home* tab allow you to format numbers as Currency, Percentages (note: this mathematically multiplies the cell content by 100), or adjust Decimal places.

---

## 🌍 Regional Variations and Settings

Excel adapts formats based on your computer's geographic settings, which is critical for global data compatibility.

* **Date/Time Systems:** The order of days and months (e.g., `MM/DD/YYYY` vs. `DD/MM/YYYY`) is determined by Windows settings. You can manually override this using the "More Number Formats" menu.
* **Decimal Separators:** Some regions use a **period (.)** for decimals, while others use a **comma (,)**.
    * *Formula Impact:* If your region uses commas for decimals, you must use **semicolons (;)** instead of commas to separate arguments inside formulas.
* **Date Systems:** Windows Excel defaults to the **1900 date system**, whereas some Mac versions use the **1904 date system**. Be cautious when copying dates between operating systems.
* **Customization:** You can override system defaults without changing your computer's settings by going to `File > Options > Advanced` and unchecking "Use system separators".

---

## 🗂️ Structuring Workbooks: Rows, Columns, and Sheets

Efficiently managing the structure of a workbook allows for better organization of large datasets.

### Managing Rows and Columns
* **Resizing:** Hover your mouse over the dividing line between two column headers (e.g., between A and B) until the cursor becomes a **double-headed arrow**. Click and drag to resize, or **double-click** to auto-fit the width to the content.
* **Hiding/Unhiding:** Used to simplify views without deleting data. To reveal a hidden column (e.g., Column B), you must select the visible columns on *both sides* of it (Columns A and C) before clicking "Unhide".
* **Inserting:** When you insert a new column, it always appears to the **left** of your selection. New rows always appear **above** your selection.

### Managing Worksheets (Tabs)
* **Organization:** The tabs at the bottom of the screen represent individual sheets. **Double-click** a tab to rename it, or **right-click** to change the tab color for visual categorization.
* **Duplication:** To create an exact clone of a sheet (useful for preserving raw data), right-click the tab, select "Move or Copy," and ensure the **"Create a copy"** box is checked.
* **Deletion Warning:** Unlike deleting text or cells, deleting a worksheet is **permanent** and cannot be reversed using the Undo button.

---

## 🔍 Navigating Large Data Blocks

Techniques to view and edit massive spreadsheets without losing context.

### View Features
* **Freeze Panes:** Found in the *View* tab, this keeps specific rows (like headers) or columns static on the screen while you scroll through the rest of the data. A distinct line appears to indicate the frozen boundary.
* **New Window:** Also in the *View* tab, this opens a second instance of the *same* file. This allows you to look at the top of a sheet in one window and the bottom in another, working on both simultaneously.

### The Name Box
* **Location:** The small input box located to the immediate left of the Formula Bar.
* **Function:** Typing a cell reference (like "Z100") here and pressing Enter jumps the cursor immediately to that location.
* **Naming Cells:** You can use this box to assign a descriptive name (e.g., `Tax_Rate`) to a specific cell. Note that these names must be unique and use **underscores** instead of spaces.

### Keyboard Shortcuts
* **Ctrl + Home:** Instantly jumps the cursor to cell **A1** (or the first active cell if panes are frozen).
* **Ctrl + End:** Instantly jumps to the very last cell in the worksheet that contains data.
* **Shift + Ctrl + Home/End:** Selects the entire block of data from your current position all the way to the start or end of the sheet.

---

## 🔽 Sorting vs. Filtering

It is crucial to understand the difference between these two data management tools found in the Data ribbon.

| Feature | Action | Impact on Data |
| :--- | :--- | :--- |
| **Sorting** | Reorders rows physically (e.g., A to Z, Oldest to Newest). | Changes the actual **position** of data in the file. |
| **Filtering** | Hides rows that don't match criteria. | Changes **visibility**, but the data remains in its original position. |

### Sorting Details
* **Multilevel Sort:** Used when a single condition isn't enough (e.g., Sort by Supplier, *then* by Date). This is accessed via the **Sort dialog box** rather than the quick-sort buttons.
* **Headers:** Always ensure the "My data has headers" checkbox is selected to prevent your top row from being sorted alphabetically into the data below.
* **Risk:** Once a file is saved after sorting, the original order cannot be restored via Undo.

### Filtering Details
* **Indicators:** A small **funnel icon** appears on the column header to show a filter is active. Additionally, the row numbers on the left will turn **blue** and become non-sequential (e.g., jumping from 10 to 112), indicating hidden rows.
* **Context Sensitive:** Excel intelligently offers different filter options based on the data type (e.g., it offers "Begins with" for text columns, but "Greater than" for number columns).
