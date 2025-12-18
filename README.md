# Project 2: Fashion Retail Streaming Data Lakehouse

**Student:** Simon Alam  
**Course:** DS-2002 Data Science Systems  
**Institution:** University of Virginia  
**Date:** December 2025

## Project Overview

A streaming data lakehouse implementation for fashion retail analytics using PySpark structured streaming and medallion architecture (Bronze/Silver/Gold layers).

## Architecture

### Data Sources
- **Streaming Data:** 10 JSON files (3,400 sales transactions)
- **Dimension Data:** CSV files (customers, products)
- **NoSQL Ready:** Architecture supports MongoDB Atlas for dimensions

### Medallion Architecture
- **Bronze Layer:** Raw JSON → Parquet (3,400 records)
- **Silver Layer:** Cleaned + dimension joins (3,400 records)
- **Gold Layer:** Business aggregations (31 category + 18 loyalty)

## Technology Stack
- PySpark 3.5.4
- Python 3.13
- Jupyter Notebooks
- Parquet file format

## Project Structure
```
Project2/
├── data/                           # Dimension data
│   ├── customers.csv
│   ├── products.csv
│   └── Fashion_Retail_Sales.csv
├── streaming/sales/                # Streaming fact data
│   ├── sales_001.json → sales_010.json
├── notebooks/
│   ├── 0_prepare_streaming_data.ipynb
│   ├── 1_setup_dimensions.ipynb
│   ├── 2_streaming_etl.ipynb
│   └── 3_analytical_queries.ipynb
├── lakehouse/sales/                # Output layers
│   ├── bronze/
│   ├── silver/
│   └── gold/
└── README.md
```

## Setup Instructions

### 1. Create Virtual Environment
```bash
cd Project2
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2. Run Notebooks in Order
1. `0_prepare_streaming_data.ipynb` - Splits CSV into streaming JSON
2. `1_setup_dimensions.ipynb` - Loads dimension tables
3. `2_streaming_etl.ipynb` - Implements Bronze/Silver/Gold layers
4. `3_analytical_queries.ipynb` - Runs business intelligence queries

## Key Results

- **Total Revenue:** $238,370.50
- **Total Customers:** 166
- **Total Transactions:** 3,400
- **Average Order Value:** $93.57

### Business Insights
- Loyalty members generate 2.4x more revenue than non-members
- Accessories is top category ($63,996 revenue)
- Peak sales months: September, May, March
- Hartford, CT has highest customer lifetime value ($238.53/customer)

## Requirements Met

- Built on midterm project foundation  
- Implemented PySpark structured streaming  
- Medallion architecture (Bronze/Silver/Gold)  
- Multiple data sources (JSON, CSV, programmatic)
- Star schema with dimension/fact tables
- 7 analytical queries with multi-table joins
- Business analytical insights

## Author
Simon Alam  
University of Virginia  
nnd4zb@virginia.edu
