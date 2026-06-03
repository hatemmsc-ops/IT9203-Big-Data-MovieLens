# IT9203 Big Data MovieLens

Top-Rated Movies per Genre Tracker built on Azure Databricks using the MovieLens 25M dataset. This is the individual project for IT9203 Big Data Tools and Techniques at Bahrain Polytechnic.

## Overview

The project builds a scalable pipeline that tracks the top rated movies per genre and generates personalised recommendations using collaborative filtering. It processes 25 million ratings end to end, from raw CSV ingestion to a queryable Azure SQL database.

## Dataset

MovieLens 25M from GroupLens, University of Minnesota.

* 25,000,095 ratings
* 62,423 movies
* 162,541 users
* 20 genres
* Rating scale 0.5 to 5.0

The dataset files are not included in this repository. See DATASET_SOURCE.txt for the download link and citation.

## Five Big Data Tools

1. DBFS plus Databricks cluster: distributed storage and compute, the HDFS plus YARN equivalent
2. Auto Loader (Structured Streaming): incremental CSV ingestion with schema inference
3. Apache Spark Core plus MLlib: distributed processing, aggregation, and ALS collaborative filtering
4. Apache Hive and Spark SQL: SQL analytics over Delta tables
5. Azure SQL Database: final queryable output store via JDBC

## Pipeline

DBFS CSVs to Auto Loader to Apache Spark and MLlib to Hive Delta tables to Azure SQL Database.

## Notebooks

| Stage | Notebook |
| --- | --- |
| Infrastructure setup | infrastructure_setup_databricks.ipynb |
| Data ingestion | data_ingestion_autoloader.ipynb |
| Data processing | data_processing_spark.ipynb |
| Data analysis and AI | data_analysis_spark_ml.ipynb |
| Data migration | data_migration_azure_sql.ipynb |

Each notebook has a matching HTML export with cell outputs.

## Key Results

* ALS recommender: RMSE 0.8013, MAE 0.6066
* 200 ranked movies, 10 per genre across 20 genres
* 10 recommendations generated for all 162,541 users
* 1,625,610 rows migrated to Azure SQL with zero data loss

## Repository Contents

* IT9203_202508993_Report.pdf: full project report
* IT9203_Project_Demo.pdf: demo presentation
* DATASET_SOURCE.txt: dataset link and citation
* References.zip: supporting literature
* Notebooks and HTML exports: the five pipeline stages

## Author

Hatem Isa, 202508993
Master of Science in Artificial Intelligence, Bahrain Polytechnic
