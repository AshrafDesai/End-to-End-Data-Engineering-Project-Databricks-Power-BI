# 📊 End-to-End Data Engineering Project — Databricks & Power BI

## 🚀 Project Overview

This project demonstrates a **complete end-to-end Data Engineering pipeline** using **Databricks (Lakehouse Architecture)** and **Power BI**. The pipeline follows the **Bronze–Silver–Gold (Medallion) architecture**, transforming raw data into analytics-ready tables and finally into an interactive business dashboard.

This project is suitable for:

* Data Engineering portfolios
* Internship/Job applications
* College assignments
* GitHub showcases

---

## 🏗️ Architecture

```
Financial Sample.csv (Raw Data)
            |
            v
      Databricks Volume
            |
            v
       Bronze Layer  → (Raw Ingestion)
            |
            v
       Silver Layer  → (Cleaned & Standardized Data)
            |
            v
       Gold Layer  → (Star Schema: Fact + Dimension Tables)
            |
            v
   Unity Catalog SQL Tables
            |
            v
        Power BI Dashboard
```

---

## 🛠️ Tech Stack

| Component      | Tool                            |
| -------------- | ------------------------------- |
| Cloud Platform | Databricks (Unity Catalog)      |
| Storage        | Databricks Volumes (Data Lake)  |
| Processing     | PySpark                         |
| Data Format    | Delta Lake                      |
| Data Modeling  | Star Schema (Fact + Dimensions) |
| Analytics      | Databricks SQL                  |
| Visualization  | Power BI                        |

---

## 📁 Dataset

### **Dataset Name**

`Financial Sample (2).csv`

### **Source**

A sample financial dataset containing sales, profit, and cost-related business metrics.

### **Key Columns (Before Cleaning)**

* Product
* Segment
* Country
* Discount Band
* Units Sold
* Manufacturing Price
* Gross Sales
* Sales
* COGS
* Profit
* Date

---

## 🔄 Data Pipeline (Step-by-Step)

### **1️⃣ Bronze Layer — Raw Ingestion**

* Load CSV file into Databricks
* Clean column names (remove spaces & special characters)
* Store as Delta table

### **2️⃣ Silver Layer — Cleaned & Standardized Data**

* Convert date format
* Add derived columns (year, month, quarter)
* Standardize text fields (uppercase, trimmed)

### **3️⃣ Gold Layer — Dimensional Model (Star Schema)**

#### **Dimension Tables**

* `dim_product` (product, segment, discount_band, product_key)
* `dim_date` (date, year, month, quarter, day, date_key)

#### **Fact Table**

* `fact_sales`

  * product_key
  * date_key
  * units_sold
  * sales
  * profit
  * cogs

---

## 📊 Power BI Dashboard

### Visuals Created

✔ **Total Sales by Year** — Line Chart
✔ **Profit by Product** — Bar Chart
✔ **Units Sold by Segment** — Donut Chart

### Relationships (Star Schema in Power BI)

* `fact_sales.product_key → dim_product.product_key`
* `fact_sales.date_key → dim_date.date_key`

---

## 📈 Business Insights

Using this dashboard, users can:

* Track yearly sales trends
* Identify most profitable products
* Compare performance across segments
* Analyze business performance over time

---

## 🔮 Future Enhancements

* Add **Dim_Country** table
* Automate pipeline using **Databricks Workflows**
* Implement **incremental loading** instead of full overwrite
* Add **data quality checks**

---

## 👨‍💻 Author

As
Data Engineering Enthusiast

---

⭐ If you like this project, feel free to star the repository!
Let me know if you want me to add **code files, diagrams, or screenshots** to this README. 🚀
