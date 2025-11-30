1️⃣ Data Source – API Producer

A Python producer script:

Fetches real-time stock market data from a public API

Streams the data continuously

Outputs records in JSON format

2️⃣ Data Lake – AWS S3 Bucket

Streaming data is stored in an S3 bucket for durability and scalability:

/raw/ → Contains raw JSON data directly from the API

/processed/ → Contains cleaned, validated, and structured data

3️⃣ Data Warehouse – Snowflake

Snowflake is used to store and manage the ingested data:

Stores raw data ingested from S3 (via Snowpipe or file load)

Stores transformed DBT layers:

Staging

Intermediate

Fact & dimension tables

4️⃣ Transformation Layer – DBT

DBT is used for SQL-based transformations, including:

Building staging models

Applying data cleaning, normalization, and business logic

Creating analytical tables for dashboards and reporting

5️⃣ Orchestration – Apache Airflow

Airflow automates the entire pipeline through a DAG that performs:

API data ingestion

Uploading data to S3

Loading data into Snowflake

Executing DBT models

Monitoring and scheduling automated workflow runs

6️⃣ Visualization – Power BI

Power BI connects directly to Snowflake to deliver impactful analytics:

Real-time stock price updates

Tracking price movements

Monitoring volume and volatility

Displaying interactive trend analysis dashboards
