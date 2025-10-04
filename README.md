
# 🛍️ SHOPIFY Customer & Sales Analytics  

![MIT License](https://img.shields.io/badge/license-MIT-blue.svg) 
![PowerBI](https://img.shields.io/badge/PowerBI-Dashboard-yellow) 
![Python](https://img.shields.io/badge/Python-Data--Science-green) 
![CSV](https://img.shields.io/badge/CSV-Data--Prep-lightgrey) 
![Status](https://img.shields.io/badge/Project-Active-brightgreen)  

> **An ETL-ready analytics repository and interactive Power BI / Python starter kit for Shopify order and customer analysis — reusable schemas, example transforms, and dashboard-ready outputs.**

---

## 🚀 Live Demo  

🔗 **[View on GitHub Pages](https://faizankhan71.github.io/)**  

---

## 📸 Dashboard Preview  

<p align="center">
  <img width="857" alt="Shopify Dashboard 1" src="https://github.com/user-attachments/assets/f9ccb8a7-a20b-4490-8457-34248ba1e961" style="margin-bottom:20px;" />
</p>

<p align="center">
  <img width="856" alt="Shopify Dashboard 2" src="https://github.com/user-attachments/assets/63cea104-12d9-44b5-a828-b8777c6e34f7" style="margin-bottom:20px;" />
</p>

<p align="center">
  <img width="861" alt="Shopify Dashboard 3" src="https://github.com/user-attachments/assets/1825e978-ee8b-46df-b968-52df1b1d4d8a" />
</p>

---

## 🏗️ Project Architecture  

This project standardizes Shopify exports into an **analysis-ready pipeline** and dashboard:  

- 🔄 **Data Ingestion**: Raw Shopify CSV/GraphQL exports or connector dumps  
- 🧹 **Data Cleaning (Python / Excel)**: Normalize names, addresses, currencies, and variants  
- 🗃️ **Data Modeling**: Canonical tables for orders, customers, products, and order_lines  
- 📊 **Visualization**: Power BI report (.pbix) and Jupyter notebooks for exploration  

---

## ✨ Key Features  

✅ Canonical **data dictionary** for consistent joins across orders, customers, and products  
✅ **ETL templates** in Python (pandas) for cleaning, currency standardization, and variant joins  
✅ **SQL examples** for LTV, repeat purchase rate, sales by region, and tax reporting  
✅ **Power BI template** with interactive filters and drill-throughs  
✅ **Export-ready outputs** (CSV / Parquet) for downstream reporting and sharing  

---

## 📂 Dataset & Canonical Fields  

<details>
<summary>📖 Expand Data Dictionary</summary>

| Field | Description |
|---|---|
| **admin_graphql_api_id** | Globally unique GraphQL identifier for precise record queries |
| **order_number** | Human-facing order code (e.g., #12345) |
| **billing_city** | City from billing address for tax and fraud checks |
| **billing_country** | Country from billing address for tax rules and reporting |
| **billing_first_name** | First name on billing address |
| **billing_last_name** | Last name on billing address |
| **billing_province** | State/province used for tax calculations |
| **billing_zip** | Postal / ZIP code for shipping and validation |
| **shipping_city** | Shipping city (if different from billing) |
| **currency** | Transaction currency in ISO format (USD, INR, EUR) |
| **customer_id** | Unique ID linking orders to customers |
| **invoice_date** | Invoice or order created date |
| **gateway** | Payment processor (Stripe, PayPal, Razorpay, etc.) |
| **product_id** | Internal product identifier |
| **product_type** | Product category (Clothing, Electronics, etc.) |
| **variant_id** | Specific SKU/variant identifier |
| **quantity** | Units of the item sold |
| **subtotal_price** | Order subtotal before taxes, shipping, and discounts |
| **total_price_usd** | Order total converted to USD |
| **total_tax** | Total tax amount applied to the order |

</details>

---

## ⚙️ Installation & Quick Start  

```bash
# 1. Clone the repository
git clone https://github.com/Faizan-26079/shopify-sales-analytics.git

# 2. Prepare raw data
# Place Shopify CSV export(s) into /data/raw (orders.csv, order_lines.csv, products.csv)

# 3. Create virtual environment and install dependencies
pip install -r requirements.txt

# 4. Run ETL cleaning script
python scripts/etl_normalize_shopify.py --input data/raw --output data/clean

# 5. Open notebooks or Power BI
# - Jupyter: notebooks/exploration.ipynb
# - Power BI: powerbi/Shopify_Sales.pbix (point to /data/clean CSVs)
```

---

## 🧩 Example Usage  

- **Normalize addresses & currencies (Python):**  
  ```bash
  python scripts/etl_normalize_shopify.py --input data/raw --output data/clean
  ```

- **Aggregate sales by country (SQL):**  
  ```sql
  SELECT billing_country, SUM(total_price_usd) AS revenue_usd
  FROM order_table
  GROUP BY billing_country;
  ```

- **Cohort analysis (Notebook):**  
  Open `notebooks/cohort_analysis.ipynb` and run all cells.  

---

## 🗂️ Repository Layout  

```
/data        → raw/clean sample exports (CSV, Parquet)
/notebooks   → Jupyter notebooks for EDA, cohort analysis, modeling
/sql         → Reusable SQL queries and examples
/powerbi     → Power BI template (.pbix)
/scripts     → Python ETL scripts and helpers
/docs        → README assets, GIFs, schema docs
/tests       → Data-quality checks and test cases
```

---

## 🛣️ Roadmap  

- 🔮 Predictive analytics for sales forecasting  
- 📦 Customer segmentation & RFM analysis  
- ☁️ Cloud integration with Azure Data Factory / AWS Redshift  
- 📈 Automated KPI dashboards with scheduled refresh  

---

## 🤝 Contributing  

Contributions are welcome!  

1. Fork the repo  
2. Create a feature branch (`git checkout -b feature-name`)  
3. Commit changes (`git commit -m "Add feature"`)  
4. Push branch (`git push origin feature-name`)  
5. Open a Pull Request  

---

## 📄 License  

Licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.  

---

## 👨‍💻 Author  

**Faizan** — Data Analytics & Power BI Professional  
📬 [Email](mailto:faizankhanofficial71@gmail.com)  
💼 [GitHub](https://github.com/Faizan-26079)  
🌐 [Portfolio](https://faizankhan71.github.io/)  

---

## 🙌 Acknowledgements  

- Shopify API & Export Documentation  
- Power BI Community for dashboarding best practices  
- Python open-source libraries: pandas, numpy, matplotlib, seaborn  

---

✨ With this README, your repo will look **professional, modern, and portfolio-ready**. It mirrors the design of your BMW project but tailored for Shopify.  

Would you like me to also create a **matching `index.html` landing page** (like your BMW one) so your GitHub Pages site looks polished and interactive?
