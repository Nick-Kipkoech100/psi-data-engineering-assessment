# PSI Data Engineering Internship Assessment

## Project Overview

This project implements an end-to-end PySpark ETL pipeline for an e-commerce dataset. The pipeline ingests raw CSV files, performs data cleaning and validation, enriches transactional data, and generates analytical outputs.

The project was developed using PySpark 3.x in Google Colab.

---

## Dataset Tables

The pipeline processes the following datasets:

- customers.csv
- orders.csv
- order_items.csv
- returns.csv

---

## Pipeline Stages

### 1. Data Ingestion
- Explicit schema enforcement
- CSV loading using Spark
- Type casting and validation

### 2. Data Cleaning
- Duplicate removal
- Date normalization
- NULL handling
- Customer tier standardization
- Negative amount flagging

### 3. Data Enrichment
- Joining orders, customers, and order_items
- Anti-join for orphaned records
- Net amount calculation

### 4. Analytics
- Customer lifetime spend ranking
- Rolling order counts
- Monthly revenue share analysis

---

## Technologies Used

- Python 3.x
- PySpark 3.x
- Google Colab

---

## How To Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the pipeline:

```bash
python pipeline.py
```

---

## Design Decisions

- Native Spark functions were used instead of Python UDFs for performance and scalability.
- Left joins were used to preserve transactional records.
- Anti joins were used to isolate orphaned order items.
- Negative amounts were flagged instead of dropped to preserve anomalies.

---

## Known Limitations

Due to time constraints, Task 5 and Task 6 were partially implemented. The intended next steps would include:
- Return rate analysis
- Refund anomaly detection
- Parquet partitioned outputs
- Additional data quality gates

---

## Repository Structure

```text
pipeline.py
README.md
requirements.txt
notebooks/
```
