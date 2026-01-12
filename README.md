# 🚗 Used Car Price & Features Analysis | AWS Athena & Cloud Analytics


## Project Overview
This project analyzes how different car features impact vehicle pricing using AWS cloud-native analytics services. The solution demonstrates a complete serverless data analytics pipeline using:
- Amazon S3
- AWS Glue Crawler
- Amazon Athena
- Amazon QuickSight
The goal is to provide business insights into pricing trends, depreciation, usage impact, and feature-driven price variations.


## Architecture
### CSV Dataset → Amazon S3 → AWS Glue Crawler → AWS Glue Data Catalog → Amazon Athena → Amazon QuickSight Dashboard


### AWS Services Used
- **Amazon S3** – Raw and cleaned data storage
- **AWS Glue** – Data cataloging and schema discovery
- **AWS Athena** – SQL-based querying, transformation, and analytics
- **QuickSight** – Visualization connected to Athena

## AWS Services Used
| Service               | Purpose                                       |
| --------------------- | --------------------------------------------- |
| Amazon S3             | Data storage (raw, cleaned, analytics layers) |
| AWS Glue Crawler      | Auto schema detection and cataloging          |
| AWS Glue Data Catalog | Central metadata repository                   |
| Amazon Athena         | SQL-based data querying                       |
| Amazon QuickSight     | Visualization & dashboard creation            |


##  Data Modeling & SQL Processing

### Raw Data
Raw data is stored in S3 and queried directly using Athena.

### Cleaned Data (CTAS)
A cleaned table is created using **CTAS (Create Table As Select)**:
- Removed nulls
- Standardized column types
- Stored in optimized **Parquet format**

### Feature Engineering
Analytical buckets were created:
- Kilometers Driven Buckets
- Mileage (KMPL) Buckets
- Engine Power (BHP) Buckets

These buckets help reduce noise and improve interpretability in analysis.


## Dashboard Overview

## Page 1 – Executive Overview
- Total number of cars listed
- Average car price
- Average kilometers driven
- Average mileage (KMPL)
- Fuel type distribution
- Brand-wise average price
- Overall price distribution
![Executive Overview](Page1.png)

## Page 2 – Price Drivers Analysis
- Average price by fuel type
- Average price by transmission type
- Impact of seating capacity on price
- Ownership history vs resale price
![Price Drivers Analysis](Page2.png)

## Page 3 – Usage & Depreciation Analysis
- Average price by kilometers driven buckets
- Average price by mileage (KMPL) buckets
- Average price by engine power (BHP) buckets
- Price trends across model years (market perspective)
![Usage & Depreciation Analysis](Page3.png)

## Key Business Insights
- Cars with lower usage (fewer kilometers driven) retain higher resale value
- Mid to high mileage-efficient cars (15–25 kmpl) show stronger pricing
- Higher engine power increases price, but with diminishing returns
- First-owner vehicles command a clear resale premium
- Model year reflects market pricing preference rather than physical wear
