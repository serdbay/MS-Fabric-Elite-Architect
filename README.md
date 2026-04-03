# 🏗️ MS Fabric Architect — Medallion Architecture

## 📌 Project Overview
This project demonstrates an **enterprise-grade Medallion Architecture** 
built entirely on **Microsoft Fabric**. Raw sales data is ingested, 
cleaned, and transformed through Bronze → Silver → Gold layers 
using PySpark and Delta Lake.

## 🛠️ Tech Stack
- **Microsoft Fabric** — Lakehouse, Notebooks, Pipelines
- **PySpark** — Data transformation & processing
- **Delta Lake** — ACID-compliant table format
- **Power BI** — Business intelligence & reporting

## 🏅 Architecture
```
Raw CSV (Bronze)
     ↓
Cleaned Delta Table — silver_sales (Silver)
     ↓
Business Summary — gold_country_sales (Gold)
     ↓
Power BI Dashboard
```

## 📊 Dataset
- **Source:** Sample Sales Data (Kaggle)
- **Size:** 2,823 rows × 25 columns
- **Content:** Global sales orders across multiple countries & product lines

## 🚀 Layers Explained

| Layer | Table | Description |
|-------|-------|-------------|
| Bronze | Files/sales_data_sample.csv | Raw ingested data |
| Silver | silver_sales | Cleaned, typed, deduplicated |
| Gold | gold_country_sales | Country & year level aggregations |

## 👤 Author
Created by [@serdbay](https://github.com/serdbay) - feel free to contact me!


## 🌟 Week 2: Star Schema & Data Modeling

### Data Model Architecture
fact_sales (center)
├──* CUSTOMERNAME →── dim_customer (1)
├──* PRODUCTCODE  →── dim_product (1)
├──* COUNTRY      →── dim_geography (1)
└──* ORDERDATE    →── dim_date (1)

### Dimension Tables
| Table | Rows | Key Column |
|-------|------|------------|
| dim_customer | 92 | CUSTOMERNAME |
| dim_product | 109 | PRODUCTCODE |
| dim_geography | 79 | COUNTRY |
| dim_date | 252 | ORDERDATE |

### Fact Table
| Table | Rows | Columns |
|-------|------|---------|
| fact_sales | 2,823 | 12 |

### DAX Measures
- Total Revenue, Total Orders, Avg Revenue per Order
- Previous Year Revenue, YoY Growth %
- Running Total Revenue
