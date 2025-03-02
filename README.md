# Data-platform-architecture
A Data Engineering Platform Projects

# Introduction

This assignment is designed to evaluate your ability to work with real-time and batch data pipelines, as well as your knowledge of data engineering best practices. You will work with MySQL as the source database, ClickHouse as the data warehouse, and InfluxDB to simulate IoT data ingestion. You are free to choose your pipeline and monitoring tools. **Your solution must only use open source**.

---

## Assignment Requirements

### 1. Environment Setup

You will need to deploy the following components on your local machine:

- **MySQL Master** – To act as the master transactional database.  
- **MySQL Replica** – To act as the MySQL Master replica.  
- **InfluxDB** – To store time-series IoT data.  
- **ClickHouse** – To act as the analytical data warehouse.

---

### 2. Data Generation

- Generate **fake IoT sensor data** and insert it into InfluxDB. Check the *Appendix* section below on an example of IoT data columns.
- Generate **transactional data** (e.g., orders, customers) and insert it into MySQL.
- The examples provided in the *Appendix* section are just for guidance, so feel free to work beyond them.
- For data size, generate **at least 100k records** for each data table in the data stores.  
  - To manage resource usage on your laptops, please start with **smaller data subsets** (e.g., 10k records) and scale up after initial testing.  
  - Keep data field sizes reasonable, avoid overly complex generation scripts, and monitor your system resources (RAM, CPU, disk I/O).  
  - If using Docker, set appropriate container resource limits.  
  - Remember that demonstrating a **functional pipeline** is the priority, so simple but representative data is better than extremely complex data.  
  - Also, be mindful of storage space and test with small batches before generating the full 100k records.  
  - Focus on clear functionality within the time limit, rather than perfect, large-scale data generation.

---

### 3. Data Pipelines

- Create a pipeline to **stream data from MySQL to ClickHouse**.
- Ensure efficient transformation and storage in ClickHouse.
- Choose any **open-source** data pipeline tool such as Debezium, Airbyte, NiFi, or custom Python scripts, etc.

---

### 4. Monitoring & Logging

- Implement monitoring for **data integrity**, pipeline failures, and performance.
- Use an open-source tool of your choice, such as **Prometheus, Grafana, or OpenTelemetry**, etc.

---

### 5. Data Platform Architecting

- Come up with an **architectural diagram** for your data platform capturing all the tools, pipelines, data flows, etc.

---

### 6. Nice to Have (Not Mandatory)

- Clustering the datastores especially MySQL using Docker or Minikube Kubernetes orchestrator.
- Data redaction (a column or two) for data being pipelined into ClickHouse.
- Implementing data visualization using ClickHouse as a source.
- Taking advantage of **ClickHouse Materialized Views (MVs)** for the visualization task above.
- Metadata management, data cataloging, and data discovery.

> **Note**: The above (Nice to have) are optional and you are free to incorporate them only if you have time and expertise. **Not covering the nice-to-have items will not affect grading of your solution.**

