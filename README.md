
# SHOPIFY Customer & Sales Analytics

![MIT License](https://img.shields.io/badge/license-MIT-blue.svg) ![PowerBI](https://img.shields.io/badge/PowerBI-Dashboard-yellow) ![Python](https://img.shields.io/badge/Python-Data--Science-green) ![CSV](https://img.shields.io/badge/CSV-Data--Prep-lightgrey)

> An ETL-ready analytics repo and interactive Power BI / notebook starter kit for Shopify order and customer analysis — reusable schemas, example transforms, and dashboard-ready outputs.

---

### Demo Site

**Live preview:** https://faizankhan71.github.io/

---

## 📸 Preview

(Place your dashboard screenshots or GIFs in /docs/assets and reference them here.)

<img width="900" alt="dashboard-preview" src="docs/assets/dashboard-preview.png" />

---

## 🏗️ Project Architecture

This project standardizes Shopify exports into an analysis-ready pipeline and dashboard:

- 🔄 Data ingestion: raw Shopify CSV/GraphQL exports or connector dumps.  
- 🧹 Data cleaning (Python / Excel): normalize names, addresses, currencies, and variants.  
- 🗃️ Data modeling: canonical tables for orders, customers, products, and order_lines.  
- 📊 Visualization: Power BI report (.pbix) and Jupyter notebooks for exploration.

---

## ✨ Key Features

- **Canonical data dictionary** for consistent joins across orders, customers, and products.  
- **ETL templates** in Python (pandas) for cleaning, currency standardization, and variant joins.  
- **Example SQL** for common analytics: LTV, repeat purchase rate, sales by region, tax reporting.  
- **Power BI template** for quick dashboarding with interactive filters and drill-throughs.  
- **Export-ready outputs** (CSV / Parquet) for downstream reporting and sharing.

---

## 📂 Dataset & Canonical Fields

Provide your Shopify raw export (CSV/JSON) and the repo will normalize to these canonical column names.

| Field | Description |
|---|---|
| **admin_graphql_api_id** | Globally unique GraphQL identifier for precise record queries. |
| **order_number** | Human-facing order code (e.g., #12345). |
| **billing_city** | City from billing address for tax and fraud checks. |
| **billing_country** | Country from billing address for tax rules and region reporting. |
| **billing_first_name** | First name on billing address for invoicing. |
| **billing_last_name** | Last name on billing address for invoicing. |
| **billing_province** | State/province used for tax calculations. |
| **billing_zip** | Postal / ZIP code for shipping and validation. |
| **shipping_city** | Shipping city (if different from billing). |
| **currency** | Transaction currency in ISO format (USD, INR, EUR). |
| **customer_id** | Internal unique ID linking orders to customers. |
| **invoice_date** | Invoice or order created date (ISO format). |
| **gateway** | Payment processor (Stripe, PayPal, Razorpay, etc.). |
| **product_id** | Internal product identifier. |
| **product_type** | Product category for filtering (Clothing, Electronics). |
| **variant_id** | Specific SKU/variant identifier. |
| **quantity** | Units of the item sold in that order line. |
| **subtotal_price** | Order subtotal before taxes, shipping, and discounts. |
| **total_price_usd** | Order total converted to USD for standardized reporting. |
| **total_tax** | Total tax amount applied to the order. |

---

## ⚙️ Installation & Quick Start

1. Clone the repository  
   git clone https://github.com/Faizan-26079/shopify-sales-analytics.git

2. Prepare raw data  
   Place Shopify CSV export(s) into /data/raw (orders.csv, order_lines.csv, products.csv).

3. Create virtual environment and install dependencies  
   pip install -r requirements.txt

4. Run ETL cleaning script  
   python scripts/etl_normalize_shopify.py --input data/raw --output data/clean

5. Open notebooks or Power BI  
   - Jupyter: open notebooks/exploration.ipynb  
   - Power BI: open powerbi/Shopify_Sales.pbix and point to /data/clean CSVs

---

## 🧩 Example Usage Snippets

- Normalize addresses and currencies (Python):  
  python scripts/etl_normalize_shopify.py --input data/raw --output data/clean

- Aggregate sales by country (SQL example in /sql/sales_by_country.sql):  
  SELECT billing_country, SUM(total_price_usd) AS revenue_usd FROM order_table GROUP BY billing_country;

- Create cohort analysis (notebook):  
  Open notebooks/cohort_analysis.ipynb and run all cells.

---

## 🗂️ Repository Layout

- **/data** — raw/clean sample exports (CSV, Parquet).  
- **/notebooks** — Jupyter notebooks for EDA, cohort analysis, and modeling.  
- **/sql** — reusable SQL queries and examples.  
- **/powerbi** — .pbix Power BI template and usage notes.  
- **/scripts** — Python ETL scripts and helpers.  
- **/docs** — README assets, GIFs, and schema docs.  
- **/tests** — basic data-quality checks and sample test cases.

---

## ✅ Recommended Inputs From You

To produce a final README and populate repo assets in the same polished style as your BMW example, provide the following:

- Repository name (exact) and one-line tagline.  
- Demo/GitHub Pages URL (you already gave: https://faizankhan71.github.io/).  
- 3–6 short feature bullets you want highlighted (optional tweaks to the default list).  
- A complete data dictionary CSV (FieldName, CanonicalName, Type, Description, ExampleValue) if you want full table included.  
- Sample raw files to include in /data (names and formats; a ~100–500 row sample is ideal).  
- Power BI .pbix filename to reference and any screenshots you want shown (place in /docs/assets).  
- requirements.txt or list of Python packages with versions.  
- Author contact details to display (name, email, portfolio link, phone optional).  
- Preferred license (MIT, Apache-2.0, etc.).  
- Any badges you specifically want added (build, coverage, python version).

You can paste small CSVs or the data dictionary directly in chat, or attach files to the repo. I will generate a polished README.md and small assets list for /docs/assets in the next message.

---

## 📄 License

Licensed under **MIT** by default unless you specify otherwise.

---

## 👨‍💻 Author

**Faizan** — Data Analytics & Power BI Professional  
📬 fk9822647@gmail.com  
💼 https://github.com/Faizan-26079  
🌐 https://faizankhan71.github.io/  

---
