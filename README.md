# ELT-pipeline-for-10M-records-using-GCP
This project builds an end-to-end ETL pipeline using Apache Airflow and Google Cloud Platform (GCP) to process global health data.

The pipeline:

1.Extracts CSV data from Google Cloud Storage (GCS)

2.Loads it into BigQuery

3.Transforms data into country-specific tables

4.Creates reporting views for analytical use

**#TECH STACK**
1.Apache Airflow
2.Python
3.Google Cloud Storage(GCS)
4.BigQuery

**#Architecture**
        +---------------------+
        |  GCS (CSV File)     |
        | global_health_data  |
        +----------+----------+
                   |
                   ▼
        +---------------------+
        | Airflow DAG         |
        | (Orchestration)     |
        +----------+----------+
                   |
                   ▼
        +---------------------+
        | BigQuery (Raw Layer)|
        | global_data         |
        +----------+----------+
                   |
        -------------------------
        |         |            |
        ▼         ▼            ▼
 Country Tables (Transform Layer)
        |
        ▼
 Reporting Views (Analytics Layer)
