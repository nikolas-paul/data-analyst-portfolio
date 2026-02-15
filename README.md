# Excel Online Retail Dashboard

  ## Profile
  Experienced operations officer turning to data analysis, focused on practical
  business insights, clean reporting, and decision-ready dashboards.

  ## Objective
  Build a sales performance dashboard in Excel (Web) to track:
  - Revenue trends over time
  - Top countries by revenue
  - Top products by revenue
  - Order volume patterns

  ## Dataset
  - Name: Online Retail
  - Source: UCI Machine Learning Repository
  - Link: https://archive.ics.uci.edu/dataset/352/online+retail
  - Format used: Excel workbook (`Online Retail.xlsx`)

  ## Data Access Note
  The full raw dataset is not stored in this repository because GitHub web upload
  has a file size limit.
  Use the source link above to download the original file and reproduce the
  analysis.

  ## Data Cleaning Steps
  The following rules were applied before analysis:
  1. Removed cancelled invoices (`InvoiceNo` starts with `C`)
  2. Removed rows with `Quantity <= 0`
  3. Removed rows with `UnitPrice <= 0`
  4. Removed rows with blank `CustomerID`
  5. Added calculated field:
     - `Revenue = Quantity * UnitPrice`
  6. Added monthly field:
     - `YearMonth = TEXT(InvoiceDate,"yyyy-mm")`
  7. Added validity flag:
     - `KeepRow = TRUE` only for rows meeting all quality checks

  ## Dashboard Components
  1. Monthly Revenue Trend
  2. Top 10 Countries by Revenue
  3. Top 10 Products by Revenue
  4. Orders per Month
  5. KPI cards:
     - Total Revenue
     - Total Orders
     - Average Order Value (AOV)

  ## KPI Formulas
  - Total Revenue: `=SUMIFS(Table1[Revenue],Table1[KeepRow],TRUE)`
  - Total Orders: `=COUNTIFS(Table1[KeepRow],TRUE)`
  - AOV: `=TotalRevenue/TotalOrders`

  ## Files in This Project
  - `images/dashboard.png` - Final dashboard screenshot
  - `docs/insights.md` - Business insights and recommendations

  ## Reproducibility
  To reproduce:
  1. Download the dataset from UCI (link above)
  2. Apply the cleaning logic listed here
  3. Build pivots/charts in Excel Web
  4. Recreate the dashboard layout and KPI formulas
