# Customer Segmentation & Sales Analysis (Online Retail)

This repository contains an end-to-end analysis of the **Online Retail** e-commerce transaction dataset.  
Each row represents an invoice line item (InvoiceNo, StockCode/Description, Quantity, UnitPrice, InvoiceDate, CustomerID, Country).  
The project focuses on two goals:

1) **Sales performance analysis** (time trend, country distribution, top products)  
2) **Customer segmentation** using **RFM (Recency–Frequency–Monetary)** to identify revenue-driving customer groups

---

## Project Files

- `DA_Final.ipynb` — Main notebook (data loading, cleaning, EDA, RFM segmentation + plots)
- `README.md` — Project overview and instructions

---

## Dataset

- Dataset name: **Online Retail**
- File expected by the notebook: **`Online Retail.xlsx`**

> Place `Online Retail.xlsx` in the same folder as `DA_Final.ipynb` before running.

---

## What the Notebook Does

### 1) Data Loading & Cleaning
- Loads the Excel dataset into pandas
- Standardizes column names (lowercase, underscores)
- Converts `InvoiceDate` to datetime
- Creates `Revenue = Quantity * UnitPrice`
- Separates **returns** (negative quantities) from **sales**
- Removes invalid rows (e.g., missing `CustomerID`, non-positive `Quantity`/`UnitPrice`)

### 2) Sales Performance Analysis (EDA)
- **Monthly revenue trend** (line chart)
- **Top 10 countries by revenue** (bar chart)
- **Top 10 products by revenue** (horizontal bar chart)
- Calculates revenue concentration (e.g., top products’ revenue share)

### 3) Customer Segmentation (RFM)
- Defines a snapshot date and computes:
  - **Recency**: days since last purchase
  - **Frequency**: number of unique invoices
  - **Monetary**: total revenue
- Creates R/F/M scores using quantiles (1–5)
- Assigns customers into interpretable segments (rule-based), such as:
  - **Champions**
  - **Loyal Customers**
  - **Potential Loyalists**
  - **At Risk**
  - **Lost Customers**
- Compares segments by:
  - total revenue contribution
  - average RFM metrics per segment
  - visualizes revenue contribution by segment (bar chart)

---

## Key Takeaways (High-Level)
- Revenue tends to be **concentrated among a relatively small subset of customers**, making retention and targeted campaigns valuable.
- The analysis suggests revenue performance is often driven more by **customer behavior** than a tiny set of products.
- RFM segmentation provides actionable groups for:
  - retention (At Risk)
  - reactivation (Lost Customers)
  - loyalty/upsell (Champions, Loyal)

---

## How to Run

### Option A — Jupyter Notebook
1. Install requirements
2. Put `Online Retail.xlsx` next to `DA_Final.ipynb`
3. Open and run all cells

### Requirements
- Python 3.x
- pandas, numpy, matplotlib, openpyxl

Example install:
```bash
pip install pandas numpy matplotlib openpyxl
