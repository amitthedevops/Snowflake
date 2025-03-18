# Snowflake Overview

## What is Snowflake?

Snowflake is a cloud-based data platform that enables organizations to store, analyze, and manage massive amounts of data. It is widely used for:
- **Data Warehousing**
- **Data Lakes**
- **Analytics**
- **Data Sharing**

Snowflake operates entirely on the cloud and is available on major cloud providers:
- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)

---

## Snowflake Competitors

1. **Google BigQuery**: Fully managed, serverless data warehouse by Google.
2. **Amazon Redshift**: Cloud-based data warehouse by AWS.
3. **Microsoft Azure Synapse Analytics**: Data integration, warehousing, and analytics platform by Azure.
4. **Databricks**: Primarily a data lake and analytics platform, but supports warehousing.
5. **Teradata**: On-premises and cloud-based data warehouse solution.


---

## Features of Snowflake

1. **Virtual Warehouses**:
   - Independent compute clusters that scale up or down dynamically.
   - Enable workload isolation and cost-effective compute resource usage.

2. **Data Cloning**:
   - Zero-copy cloning for databases, schemas, or tables.
   - Enables quick creation of test environments without duplicating data.

3. **Time Travel**:
   - Access historical versions of data for up to 90 days (depending on the plan).
   - Useful for recovering deleted or modified data.

4. **Data Governance with Access Control**:
   - Role-Based Access Control (RBAC) ensures security and compliance.
   - Supports Secure Views for masking sensitive data.

5. **Semi-Structured Data Handling**:
   - Natively supports JSON, Parquet, Avro, and more using the `VARIANT` data type.
   - SQL queries can be executed on nested or semi-structured data.

6. **Query Optimization**:
   - Automatic optimization of queries without requiring manual tuning.
   - No need for indexes or maintenance of query plans.

7. **Cross-Cloud and Multi-Region Support**:
   - Operates across AWS, Azure, and GCP.
   - Enables seamless data sharing and cross-cloud operations.

8. **Snowflake Marketplace**:
   - A data exchange platform to share or access third-party datasets.
   - Useful for adding external insights (e.g., weather, financial data).

9. **Integration with Tools**:
   - Works seamlessly with ETL tools (Informatica, Talend, Matillion).
   - Integrates with BI tools (Tableau, Power BI, Looker).
   - APIs available for Python, R, Java, and other programming languages.

10. **Automatic Storage Management**:
    - Compresses and partitions data automatically, reducing costs.
    - No need for users to define physical storage structures.

---


## Data Warehouse

A **data warehouse** is a system for storing and analyzing large volumes of structured and semi-structured data, optimized for querying and reporting.

### Key Features:
- **Purpose**: Primarily used to store **historical data** for analysis, reporting, and decision-making.

---

## Data Lakes

**Data Lakes** are centralized storage systems designed to hold large volumes of raw, unprocessed data in its native format, including:
- **Structured** data
- **Semi-structured** data (e.g., JSON, XML)
- **Unstructured** data (e.g., images, videos, logs)

### Key Features:
- **Flexible Schema**: No predefined schema; data is processed when needed (schema-on-read).
- **Scalability**: Can handle massive amounts of data.
- **Examples**:
  - Amazon S3
  - Azure Data Lake Storage (ADLS)
  - Google Cloud Storage

---

## Analytics

**Analytics** refers to the process of examining, interpreting, and visualizing data to gain meaningful insights and support decision-making.

### Types of Analytics:
1. **Descriptive Analytics**: Summarizes historical data to understand what happened.
   - **Example**: Sales reports showing revenue trends over the past year.
2. **Predictive Analytics**: Uses historical data and machine learning to predict future outcomes.
   - **Example**: Forecasting customer churn using patterns in user behavior.
3. **Prescriptive Analytics**: Suggests actions to optimize outcomes based on data.
   - **Example**: Recommending inventory adjustments based on demand predictions.

### Key Platforms:
- Snowflake: Centralized platform for data storage and analysis.
- Google BigQuery: Serverless data warehouse for running fast analytics queries.
- Microsoft Power BI: Visualize and analyze data from multiple sources.
- Tableau: Create dashboards to track key business metrics.

### Example Use Case:
A retail company uses analytics to:
- **Analyze customer purchase data for targeted marketing** (Descriptive).
- **Predict future sales during holiday seasons** (Predictive).
- **Optimize product pricing based on competitor data** (Prescriptive).

---

## Data Sharing

Snowflake allows secure and real-time sharing of data across organizations, teams, or external partners without the need for copying or moving data.

### Key Features:
1. **No Data Movement**:
   - Data is shared directly from Snowflake storage, ensuring real-time access.
2. **Controlled Access**:
   - Access is governed by roles and permissions.
3. **Cross-Cloud Sharing**:
   - Share data across different cloud providers (e.g., AWS, Azure, GCP).

### Example Use Cases:
- **Collaborating with Partners**:
  - A retail company shares sales data with suppliers for inventory optimization.
- **Data Monetization**:
  - A business provides analytics-ready datasets to clients as a service.
- **Cross-Department Sharing**:
  - Marketing and finance teams share live data for coordinated campaigns and budgeting.

---

# Snowflake Hierarchical Structure

## Structure Overview
## Snowflake Hierarchy

<pre>
<span style="color:#FF5733;"><b>ACCOUNT</b></span>  (<b>Highest Level</b>)
 ├── <span style="color:#33C3FF;"><b>Role</b></span> (<i>Global access control</i>)
 ├── <span style="color:#33FF57;"><b>DATABASE</b></span> (<i>Collection of schemas</i>)
 │    ├── <span style="color:#33C3FF;"><b>Role</b></span> (<i>Database-specific access control</i>)
 │    ├── <span style="color:#FFC300;"><b>SCHEMA</b></span> (<i>Collection of tables, views, etc.</i>)
 │    │    ├── <span style="color:#33C3FF;"><b>Role</b></span> (<i>Schema-specific access control</i>)
 │    │    ├── <span style="color:#FF5733;"><b>TABLE</b></span> (<i>Stores data</i>)
 │    │    ├── <span style="color:#33FF57;"><b>VIEW</b></span> (<i>Virtual table</i>)
 │    │    ├── <span style="color:#FF33A8;"><b>FUNCTION</b></span> (<i>User-defined function</i>)
 │    │    ├── <span style="color:#FF8C33;"><b>PROCEDURE</b></span> (<i>Stored procedure</i>)
 │    │    ├── <span style="color:#8C33FF;"><b>SEQUENCE</b></span> (<i>Auto-incrementing numbers</i>)
 │    │    ├── <span style="color:#33FFF3;"><b>STAGE</b></span> (<i>Data loading/unloading storage</i>)
 │    │    └── <span style="color:#A833FF;"><b>OTHER OBJECTS</b></span> (<i>Pipes, streams, tasks, etc.</i>)
 ├── <span style="color:#33FF57;"><b>DATABASE</b></span>
 ├── <span style="color:#FF5733;"><b>WAREHOUSE</b></span> (<i>Compute resources for query execution</i>)
 ├── <span style="color:#33C3FF;"><b>USERS</b></span> (<i>Accounts with assigned roles</i>)
 └── <span style="color:#FF33A8;"><b>OTHER ACCOUNT-LEVEL OBJECTS</b></span> (<i>Networks, integrations, etc.</i>)
</pre>



## Explanation

| **Component** | **Description** |
|--------------|----------------|
| **Account**  | The top-most level representing your Snowflake account. <br> - Includes global Roles for access control. |
| **Database** | Logical container grouping schemas and objects. <br> - Includes Roles for database-specific access control. |
| **Schema**   | Namespace within a database containing related objects: <br> - **Table**: Stores structured data. <br> - **View**: Virtual table created using queries. <br> - **Stage**: Temporary or semi-permanent storage for raw data. <br> - Includes Roles for schema-specific access control. |


## Example: How Access Control Works in Snowflake

```sql
-- 1️⃣ Create a Database & Schema
CREATE DATABASE RETAIL_DB;
CREATE SCHEMA RETAIL_DB.SALES;

-- 2️⃣ Create a Role for Schema Access
CREATE ROLE SALES_MANAGER;
GRANT USAGE, SELECT, INSERT ON SCHEMA RETAIL_DB.SALES TO SALES_MANAGER;

-- 3️⃣ Assign Role to a User
GRANT ROLE SALES_MANAGER TO USER alice;

-- 4️⃣ Check the Role’s Access
SHOW GRANTS TO ROLE SALES_MANAGER;

```

---

## Difference Between Database and Data Warehouse

| **Aspect**     | **Database**                               | **Data Warehouse**                          |
|-----------------|-------------------------------------------|---------------------------------------------|
| **Purpose**     | Stores current, transactional data.       | Stores historical data for analysis, reporting, and decision-making. |
| **Type of Data**| Real-time, operational data.              | Aggregated, structured, and historical data.|
| **Schema**      | Designed for frequent updates and transactions. | Optimized for queries and analytics (star/snowflake schema). |
| **Use Case**    | Running applications (e.g., e-commerce, ERP). | Analyzing trends, KPIs, and decision-making.|
| **Query Type**  | Simple, fast queries with frequent writes.| Complex queries for large datasets.         |
| **Examples**    | MySQL, PostgreSQL, MongoDB.               | Snowflake, Amazon Redshift, Google BigQuery.|

---


## Snowflake's Official Warehouse Sizes

Snowflake offers different warehouse sizes to allocate compute resources for query processing. The sizes range from **X-Small (XS)** to **4X-Large (4XL)**, each defined by the number of nodes (compute units).

Snowflake’s warehouse sizes provide flexibility to match compute resources with workloads. For large-scale data processing and analytics, warehouses can be scaled both vertically (larger sizes) and horizontally (multi-cluster setups).
In reality, it's best practice to combine workloads from many teams but separate workloads by size. This ensures most short, fast queries execute on an XSMALL warehouse while larger, more complex queries run on MEDIUM or size warehouses or even bigger.


### **Warehouse Sizes**

| **Size**         | **Cluster Nodes** |
|-------------------|-------------------|
| **X-Small (XS)**  | 1 Node           |
| **Small (S)**     | 2 Nodes          |
| **Medium (M)**    | 4 Nodes          |
| **Large (L)**     | 8 Nodes          |
| **X-Large (XL)**  | 16 Nodes         |
| **2X-Large (2XL)**| 32 Nodes         |
| **3X-Large (3XL)**| 64 Nodes         |
| **4X-Large (4XL)**| 128 Nodes        |

---

## Key Points About Warehouse Sizes

1. **Scalability**:
   - Warehouses can be scaled up or down based on workload requirements.
   - Larger warehouses support more concurrent queries and faster query processing.

2. **Concurrency**:
   - Larger warehouses allow more users or processes to run queries simultaneously.

3. **Costs**:
   - Each warehouse size consumes credits based on its compute capacity (e.g., X-Small uses 1 credit per hour, Small uses 2 credits per hour, etc.).

4. **Use Cases**:
   - **X-Small (XS)**: Lightweight queries, testing environments.
   - **Medium (M)**: General-purpose workloads for small teams.
   - **Large (L)**: Heavy workloads such as ETL or high-concurrency queries.
   - **4X-Large (4XL)**: Massive data processing, machine learning, or real-time analytics.

---

## Multi-Cluster Warehouses

For workloads requiring **higher scalability** than a single **4X-Large** warehouse, Snowflake supports **Multi-Cluster Warehouses**. This allows multiple clusters to run simultaneously for maximum performance and concurrency.

### Multi-Cluster Benefits:
- Automatically scale horizontally by adding more clusters when needed.
- Efficient for handling sudden surges in workload or high user concurrency.



---
## commands
```sql
-- Need SYSADMIN to create warehouses
use role SYSADMIN;

create warehouse PROD_REPORTING with
    warehouse_size     = SMALL
    auto_suspend        = 60
    auto_resume         = true
    initially_suspended = true
    comment = 'PROD Reporting Warehouse';


use warehouse PROD_REPORTING;


alter warehouse PROD_REPORTING set
    warehouse_size    = MEDIUM
    min_cluster_count = 1
    max_cluster_count = 5
    scaling_policy = ‘STANDARD’;   # STANDARD or ECONOMY



'''






## Summary

Snowflake is a powerful, cloud-native platform for modern data solutions, offering capabilities in **data warehousing**, **data lakes**, **analytics**, and **data sharing**. Its competitors include BigQuery, Redshift, Azure Synapse, Databricks, and Teradata. Snowflake's hierarchical structure and flexibility make it an excellent choice for both small and large-scale data operations.
