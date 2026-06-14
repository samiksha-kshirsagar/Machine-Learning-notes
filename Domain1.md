# Domain 1: Data Preparation for Machine Learning (28%)

---

# Task 1.1: Ingest and Store Data

## Overview

Data ingestion is the process of collecting data from various sources and storing it in a format suitable for machine learning workloads.

---

# Data Formats

## CSV (Comma-Separated Values)

### Characteristics
- Plain text format
- Easy to read and edit
- Supported by almost all tools

### Advantages
- Human-readable
- Easy to create

### Disadvantages
- Large storage size
- No schema support
- Slower query performance

### Best Use Cases
- Small datasets
- Data exchange between systems

---

## JSON (JavaScript Object Notation)

### Characteristics
- Semi-structured format
- Key-value pair structure

### Advantages
- Flexible schema
- Commonly used in APIs

### Disadvantages
- Larger than Parquet
- Slower analytical queries

### Best Use Cases
- API responses
- Log files
- Event data

---

## Apache Parquet

### Characteristics
- Columnar storage format

### Advantages
- High compression
- Faster analytical queries
- Reduced storage costs

### Disadvantages
- Not human-readable

### Best Use Cases
- Machine learning datasets
- Data lakes
- Athena queries
- Redshift Spectrum

### Exam Tip
Parquet is usually the preferred format for analytics and machine learning workloads.

---

## Apache ORC

### Characteristics
- Columnar storage format

### Advantages
- Excellent compression
- Optimized for Hive

### Best Use Cases
- Hadoop ecosystems

---

## Apache Avro

### Characteristics
- Row-based storage

### Advantages
- Supports schema evolution
- Efficient serialization

### Best Use Cases
- Data exchange
- Streaming systems

---

## RecordIO

### Characteristics
- Binary format optimized for SageMaker

### Advantages
- Faster training performance

### Best Use Cases
- SageMaker built-in algorithms

### Exam Tip
When a SageMaker built-in algorithm requires optimized input, RecordIO is often a good choice.

---

# AWS Storage Services

## Amazon S3

### Description
Object storage service used as the primary storage layer for machine learning workloads.

### Common Use Cases
- Training datasets
- Model artifacts
- Feature storage
- Data lakes
- Batch inference outputs

### Advantages
- Highly durable
- Virtually unlimited scalability
- Cost-effective

### Exam Tip
S3 is the default storage service for most SageMaker workloads.

---

## Amazon EBS (Elastic Block Store)

### Description
Persistent block storage attached to EC2 instances.

### Best Use Cases
- Databases
- High IOPS workloads

### Performance Options
- General Purpose SSD
- Provisioned IOPS SSD

### Exam Tip
Choose Provisioned IOPS when applications require consistent high performance.

---

## Amazon EFS (Elastic File System)

### Description
Fully managed shared file system.

### Best Use Cases
- Distributed training
- Shared datasets

### Advantages
- Multiple instances can access simultaneously
- Automatically scales

### Exam Tip
Choose EFS when multiple training instances need access to the same files.

---

## Amazon FSx for NetApp ONTAP

### Description
Enterprise-grade file storage service.

### Best Use Cases
- Large-scale enterprise ML workloads
- Existing ONTAP environments

### Advantages
- High performance
- Advanced storage features

---

# Streaming Data Sources

## Amazon Kinesis Data Streams

### Purpose
Real-time data ingestion service.

### Use Cases
- Clickstream analytics
- IoT telemetry
- Application logs

### Key Features
- Low latency
- High throughput

---

## Amazon Managed Streaming for Apache Kafka (MSK)

### Purpose
Managed Apache Kafka service.

### Use Cases
- Event streaming
- Real-time ML pipelines

---

## Amazon Managed Service for Apache Flink

### Purpose
Real-time stream processing.

### Use Cases
- Feature engineering on streaming data
- Fraud detection

---

# Storage Selection Guide

| Requirement | Recommended Service |
|------------|--------------------|
| Data Lake | Amazon S3 |
| Shared File Access | Amazon EFS |
| High IOPS | Amazon EBS |
| Enterprise NAS | Amazon FSx |
| Streaming Data | Kinesis |

---

# SageMaker Data Wrangler

## Purpose

Simplifies data preparation and feature engineering.

---

## Supported Sources

- Amazon S3
- Amazon Athena
- Amazon Redshift
- Snowflake

---

## Common Transformations

- Missing value handling
- Feature scaling
- Encoding
- Outlier detection
- Data normalization

---

## Benefits

- Visual interface
- No-code transformations
- Direct SageMaker integration

---

# SageMaker Feature Store

## Purpose

Centralized repository for storing and managing features.

---

## Components

### Offline Store

Used for:
- Model training
- Historical analysis

Typically stored in S3.

---

### Online Store

Used for:
- Real-time inference

Provides low-latency access.

---

## Benefits

- Feature consistency
- Feature reuse
- Reduced duplicate work

### Exam Tip
If multiple teams need the same engineered features, choose SageMaker Feature Store.

---

# Data Merging Techniques

## Join

Combines rows from multiple datasets using common keys.

### Example

Customer Table + Orders Table

Joined using Customer ID.

---

## Union

Combines rows from datasets with identical schemas.

---

## Aggregation

Summarizes data.

Examples:
- Average
- Sum
- Count
- Maximum

---

# AWS Services for Data Processing

## AWS Glue

### Purpose
Serverless ETL service.

### Functions
- Extract
- Transform
- Load

### Common Use Cases
- Data lake creation
- Data preparation

---

## Amazon EMR

### Purpose
Managed Hadoop and Spark service.

### Best Use Cases
- Large-scale processing
- Distributed machine learning

---

# Data Ingestion Troubleshooting

## Slow Data Transfer to S3

### Solution
Use S3 Transfer Acceleration.

---

## Low EBS Performance

### Solution
Use Provisioned IOPS SSD volumes.

---

## Large Query Processing Times

### Solution
Convert datasets from CSV to Parquet.

---

# Exam Tips for Task 1.1

- S3 is the default storage service for ML workloads.
- Parquet is preferred for analytics and ML.
- EFS is ideal for shared file access.
- Kinesis is used for real-time streaming ingestion.
- Feature Store provides reusable features.
- Data Wrangler simplifies feature engineering.