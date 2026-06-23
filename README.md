# Snowflake SCD1 CDC Pipeline

## Business Problem

Customer records change over time and must be kept accurate to support reporting, analytics, and business operations. Manually identifying and updating changed records is inefficient, error-prone, and difficult to scale. Organizations need an automated solution to detect incoming customer data changes and maintain current customer information with minimal manual intervention.

## Project Objective

Build an automated Change Data Capture (CDC) pipeline that detects customer data changes and applies SCD1 updates within Snowflake. The solution leverages Snowflake Streams, Tasks, and JavaScript Stored Procedures to automate ingestion, change detection, and record updates.

## Architecture Overview

Customer CSV Files
→ AWS S3
→ Snowflake Storage Integration
→ Snowflake Stage
→ Snowpipe Auto-Ingest
→ CUSTOMER_SOURCE
→ CUSTOMER_STREAM
→ CUSTOMER_TASK
→ JavaScript Stored Procedure
→ SCD Type 1 MERGE Logic
→ CUSTOMER Target Table

## Technologies Used

* Snowflake
* AWS S3
* Snowpipe
* Snowflake Streams
* Snowflake Tasks
* SQL
* JavaScript Stored Procedures

## Key Results

* Successfully automated ingestion of customer data from AWS S3 into Snowflake using Snowpipe.
* Implemented Change Data Capture (CDC) monitoring using Snowflake Streams.
* Automated pipeline execution through Snowflake Tasks and JavaScript Stored Procedures.
* Applied SCD Type 1 logic using MERGE statements to maintain current customer records.
* Validated customer record updates through changes to existing customer information, including phone number and city updates.
* Successfully inserted new customer records when no matching customer record existed in the target table.

## Repository Contents

* `scd1_architecture_diagram.png` – Architecture diagram illustrating the end-to-end Snowflake CDC pipeline workflow.
* `scd1_cdc_pipeline_snowflake.sql` – Complete SQL implementation including Snowpipe, Streams, Tasks, Stored Procedures, and SCD Type 1 logic.
* `customer_full_data.csv` – Initial customer dataset used for the full data load.
* `customer_change_data.csv` – Incremental customer dataset used to simulate change events and validate CDC processing.

## How to Review This Project

1. Review the architecture diagram to understand the end to end pipeline design.
2. Open the SQL file to examine the Snowpipe configuration, Stream creation, Task automation, Stored Procedure logic, and SCD Type 1 MERGE implementation.
3. Compare the source datasets to understand how customer record changes were introduced into the pipeline.
4. Review the validation examples demonstrating successful automated customer record updates.
