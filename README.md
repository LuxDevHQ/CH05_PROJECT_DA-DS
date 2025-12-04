# Online Retail Data Project - Project Brief

Hi Team,

I hope you’re doing well. We are beginning the next phase of our Online Retail data project, and I need you to carry out a structured workflow that prepares the dataset for high-quality analysis. The main goal is to ensure that the data is reliable, properly validated, and transformed in a way that supports deeper insights for leadership.

You will be working exclusively with the Online Retail dataset. Before any analysis can begin, the data must be thoroughly cleaned. Once this is done, I would like you to move through the remaining phases of the pipeline—data ingestion, storage, preparation, and analysis. These steps will help us uncover customer behavior patterns, revenue trends, and geographic demand using only this dataset.

Please review the detailed expectations below and let me know if you need clarification before you begin.

## WHAT YOU ARE EXPECTED TO DO

### PHASE 1 — DATA INGESTION
You will begin by bringing the dataset into Python for inspection:
- Load the Online Retail Excel file using pandas.
- Review the raw structure using `.head()`, `.shape()`, `.describe()`, and `.info()`.
- Convert the InvoiceDate column into a proper datetime format.
- Ensure all text fields (e.g., Country, Description) are correctly typed as string/object.

---

### PHASE 2 — DATA STORAGE (SQL Layer)
After the initial load:
- Create a PostgreSQL table to store the raw Online Retail dataset.
- Establish a schema that includes fields like:
  - InvoiceNo
  - StockCode
  - Description
  - Quantity
  - InvoiceDate
  - UnitPrice
  - CustomerID
  - Country
- Load the raw data into the SQL database using SQLAlchemy.
- Confirm table creation, data types, and row counts.

---

### PHASE 3 — DATA PREPARATION (CLEANING & TRANSFORMATION)
This is the most critical part. You must clean the data as follows:

#### 1. Quantity Validation
- Any quantity below 1 is invalid (returns, errors).
- Exclude or filter out all transactions with negative or zero quantity.

#### 2. Unit Price Validation
- Unit prices cannot be negative.
- Remove or correct all rows with UnitPrice < 0.

#### 3. Additional Cleaning
- Remove invoice cancellations (InvoiceNo beginning with "C").
- Drop rows where CustomerID is missing.
- Remove duplicate records.
- Create new fields:
  - Revenue = Quantity × UnitPrice
  - Month, Year, Day extracted from InvoiceDate

#### 4. Store a "cleaned" version
- Load the cleaned dataset into a new SQL table, e.g., `online_retail_clean`.

---

### PHASE 4 — DATA ANALYSIS (IN PYTHON ONLY)
Perform analytical steps to prepare insights for leadership:

#### 1. Time Series (2011 Revenue by Month)
- Filter data for Year = 2011
- Group by month and calculate revenue totals
- Identify seasonal patterns or month-to-month changes

#### 2. Country Performance (Excluding United Kingdom)
- Rank countries by total revenue
- Identify the top 10 revenue-generating countries
- Compute both revenue and quantity sold

#### 3. Top Customers by Revenue
- Rank all customers by total revenue
- Identify the top 10 highest-spending customers

#### 4. Global Product Demand
- Compute total quantity sold per country
- Remove the United Kingdom
- Rank countries by demand and highlight high-opportunity markets

---

## FINAL DELIVERABLES
You are expected to submit:
- The cleaned dataset stored in SQL
- The Python scripts for all four phases
- A short summary of key findings in text form
- Any supporting CSVs generated during the cleaning and analysis steps
```
