# 🏗️ MS Fabric Elite Architect — Medallion Architecture

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
Contact
Created by @serdbay - feel free to contact me!
