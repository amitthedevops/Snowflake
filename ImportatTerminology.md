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
| **Schema**   | Namespace within a database containing related objects: <br> - 
| **Table**    | Stores structured data.  |
| **View**:    | Virtual table created using queries.|
| **Stage**:   | Temporary or semi-permanent storage for raw data.|


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
---


## Snowflake’s Columnar Storage

## Overview

Snowflake uses **columnar storage**, which is optimized for analytical queries by storing data column by column, rather than row by row. This approach contrasts with traditional row-based storage used in transactional databases.

---

## Comparison: Row-Based vs. Columnar Storage

### **Row-Based Storage (Traditional Databases)**

Consider the following table in Excel:

| Order ID | Product Name | Quantity | Price | Total Price |
|----------|--------------|----------|-------|-------------|
| 1        | Pen          | 2        | 5.00  | 10.00       |
| 2        | Notebook     | 1        | 3.00  | 3.00        |
| 3        | Eraser       | 4        | 1.00  | 4.00        |

In **row-based storage**:
- Data is stored **row by row**.
- Example: Row 1 (`1, Pen, 2, 5.00, 10.00`), Row 2 (`2, Notebook, 1, 3.00, 3.00`), etc.

### Use Case:
- Best for **transactional queries**, such as updating or inserting specific rows (e.g., updating Order ID `2`).

---

### **Columnar Storage (Snowflake)**

In **columnar storage**, data is stored **column by column** instead of row by row. For the same table:

- Column 1: `1, 2, 3` (Order ID)
- Column 2: `Pen, Notebook, Eraser` (Product Name)
- Column 3: `2, 1, 4` (Quantity)
- Column 4: `5.00, 3.00, 1.00` (Price)
- Column 5: `10.00, 3.00, 4.00` (Total Price)

| **Order ID** | **Product Name** | **Quantity** | **Price** | **Total Price** |
|--------------|------------------|--------------|-----------|-----------------|
| 1            | Pen              | 2            | 5.00      | 10.00           |
| 2            | Notebook         | 1            | 3.00      | 3.00            |
| 3            | Eraser           | 4            | 1.00      | 4.00            |

### Key Characteristics:
- Each **column is stored separately** in the system.
- Queries can focus on specific columns (e.g., `Total Price`) without scanning entire rows.

---

## Handling Repeated Values in Columnar Storage

### **Scenario**

If the value `Pen` is repeated in the **Product Name** column, does Snowflake store it repeatedly? **No.**

Instead, Snowflake uses **dictionary encoding** to handle repeated values efficiently.

---

### **How It Works: Dictionary Encoding**

1. **Assign Unique Identifiers**:
   - Each distinct value in the column is assigned a **unique identifier (pointer)**.
   - Example:
     - `Pen` → `ID 1`
     - `Notebook` → `ID 2`
     - `Eraser` → `ID 3`

2. **Storage Representation**:
   - **Dictionary Table**: A separate table stores unique values.
     - `{1: "Pen", 2: "Notebook", 3: "Eraser"}`
   - **Column Data**: Only pointers are stored in the column:
     - `[1, 2, 3]`

---

### Example: Repeating `Pen`

If `Pen` appears again:
1. Snowflake checks if `Pen` is already in the dictionary.
2. If found, it stores the corresponding **pointer** (e.g., `ID 1`) instead of the full value.
3. This reduces redundancy and saves storage space.

---

## Advantages of Columnar Storage

1. **Data Compression**:
   - Repeated values (e.g., `Pen`) are stored only once in the dictionary.
   - Pointers replace duplicate values in the column data.

2. **Efficient Query Execution**:
   - Queries like filtering, grouping, or aggregating (e.g., `WHERE Product Name = 'Pen'`) are faster because Snowflake uses the dictionary for lookups.

3. **Optimized for Analytics**:
   - Ideal for queries like calculating averages, totals, or filtering on specific columns.

---

## Excel Analogy Example

Say you want to calculate the **sum of Total Price**:

1. **Row-Based Storage**:
   - You would scan through every row to pick the `Total Price` column (inefficient for large datasets).

2. **Columnar Storage**:
   - Since `Total Price` is stored as a separate column, Snowflake directly processes only that column, making the operation faster.

---

## Summary

### **Comparison Table**

| **Aspect**            | **Row-Based Storage**           | **Columnar Storage in Snowflake**           |
|------------------------|---------------------------------|---------------------------------------------|
| **Storage Pattern**    | Row by row                      | Column by column                            |
| **Handling Repeated Values** | Values are stored repeatedly in each row. | Values are replaced with pointers to a dictionary. |
| **Efficiency**         | Higher storage requirements.   | Reduced storage due to compression.         |
| **Query Performance**  | Slower for repeated values.    | Faster due to dictionary references.        |
| **Best Use Case**      | Transactional queries           | Analytical queries                          |

---

## Why Snowflake Uses Columnar Storage

- Snowflake’s columnar storage is ideal for **data warehousing** and **analytics**.
- It ensures:
  - **Fast query performance** by focusing only on relevant data.
  - **Cost-effective storage** through compression and dictionary encoding.


---------------------


## What is Time Travel in Snowflake?

With Time Travel, you can query, restore, or recover past versions of your data for a certain period (up to 90 days, depending on your plan).

Snowflake automatically keeps historical snapshots of your data when:



A table is updated (UPDATE, INSERT, DELETE).

A table is dropped (DROP TABLE).

A table is truncated (TRUNCATE TABLE).



## How to Use It?

You can query older versions of a table using:



A specific timestamp:

```sql
SELECT * FROM my_table AT(TIMESTAMP => '2024-03-01 12:00:00');
```



A specific query ID (if you know the query that modified data):

```sql
SELECT * FROM my_table BEFORE(STATEMENT => 'query-id');
```



A relative time (e.g., 5 minutes ago):

```sql
SELECT * FROM my_table AT(OFFSET => -300);
```



To restore a table that was dropped:

```sql
UNDROP TABLE my_table;
```





-------------------

## What is Micro-Partitioning?

it automatically breaks large tables into small, optimized chunks (each around 50–500MB in size) for fast and efficient access.



## How Does It Work?

Automatic Partitioning: Unlike traditional databases where you must manually define partitions, Snowflake automatically organizes data as it’s loaded.

Columnar Storage: Within each micro-partition, data is stored in a highly compressed, column-based format, making queries super fast.

Pruning (Skipping Unneeded Data): When you query data, Snowflake only scans the relevant micro-partitions instead of the entire table, which speeds up queries significantly.

Metadata Optimization: Snowflake keeps metadata about each micro-partition (like min/max values), so it knows exactly where to look for data.



Why is This Useful?

No Manual Partitioning Needed: Snowflake handles it for you.

Faster Queries: Only the necessary partitions are read.

Efficient Storage: Data is compressed and optimized.

Better Performance for Large Tables: Even if you have billions of rows, Snowflake efficiently manages them with micro-partitions.





## What is Zero-Copy Cloning?

Snowflake lets you create an exact copy of a table (or database or schema) instantly, without using extra storage. This is called Zero-Copy Cloning.

## Key Features:

Instant Copy: No waiting, no expensive duplication.

No Extra Storage Cost (at first) – since it references the same data.

Independent Changes: Once cloned, the two tables can be modified separately.

Works on Any Object: You can clone tables, schemas, or even entire databases.

You can clone a table like this:

```sql
CREATE TABLE sales_clone CLONE sales;
```

Or an entire schema:

```sql
CREATE SCHEMA analytics_clone CLONE analytics;
```

Or even an entire database:

```sql
CREATE DATABASE sales_db_clone CLONE sales_db;
```



What Happens When You Modify the Clone?

Before modification, the clone shares the same data as the original.

After modification, only the changed data takes up extra storage.

- 🔹 Example:


You clone a table:

```sql
CREATE TABLE orders_clone CLONE orders;
```

At this point, no extra storage is used.

You insert new data into orders_clone:

```sql
INSERT INTO orders_clone VALUES (1001, 'New Order', 500);
```

Now, only this new row takes up additional storage. The rest still references the original.





---------------------



## What is Snowflake Caching?

Caching in Snowflake is like a "memory shortcut" that speeds up queries by storing recently used data. Instead of re-reading and re-processing the same data from storage, Snowflake remembers what you used recently and serves it faster.



## How Does It Work?

Snowflake has three levels of caching that help speed up queries:



### 1️⃣ Result Cache (Fastest 🚀)

Stores query results for 24 hours.

If you run the same query again, Snowflake instantly returns the stored result (without scanning the data again).

- ✅ No extra cost since it doesn’t need to reprocess the data.
- 📌 Example:
```sql
SELECT COUNT(*) FROM sales;
```

Run it once → Takes 3 seconds (processing data).

Run it again (same query) → Instant result (0 seconds!).



### 2️⃣ Local Disk Cache (Fast ⚡)

Stores recently accessed data in the virtual warehouse (server memory).

If you re-run a similar query, Snowflake fetches data from memory instead of reloading from cloud storage.

Only applies while the warehouse is running (cache is cleared if the warehouse is suspended).

- 📌 Example:
```sql
SELECT * FROM orders WHERE order_date > '2024-01-01';
```

First run → Reads data from storage.

Second run → Uses cached data from memory, making it much faster!



### 3️⃣ Remote Disk Cache (Still Faster ⏩)

Stores data in SSD storage for faster retrieval.

Persists even when the warehouse is suspended (unlike local disk cache).

Helps speed up queries even after a restart.





------------------------

## What is Data Sharing in Snowflake?

you can securely share live data with others without copying or moving it.



## How Does It Work?

You don’t need to export or transfer data.

The recipient sees real-time data updates.

You control what they can access (specific tables, views, or even whole databases).

It works between different Snowflake accounts, even across different cloud providers (AWS, Azure, GCP).

Types of Data Sharing

### 1️⃣ Direct Sharing → Share data with another Snowflake account

### 2️⃣ Data Marketplace → Publish data for multiple customers

### 3️⃣ Reader Accounts → Share data with people who don’t have a Snowflake account



## How to Share Data?

To share a table with another account:



### 1️⃣ Create a Share:



```sql
CREATE SHARE sales_share;
```

```sql
SHOW SHARES;
```



### 2️⃣ Grant Access to a Table:


```sql
GRANT USAGE ON DATABASE sales_db TO SHARE sales_share;

GRANT SELECT ON TABLE sales_db.sales TO SHARE sales_share;

SHOW GRANTS TO SHARE sales_share;
```

### 3️⃣ Add the Recipient’s Snowflake Account:



```sql
ALTER SHARE sales_share ADD ACCOUNTS = 'ACCOUNT123';
```

### 4️⃣ Recipient Uses the Shared Data: They can access it like a normal table:



```sql
SELECT * FROM sales_db.sales;
```

- 🚀 No data copying, no ETL, just instant access!


------------------------------

## What are Streams in Snowflake?

Snowflake Streams let you track table changes efficiently, making real-time data updates and ETL much faster and easier!



## Example Use Cases

- 📌 Data Syncing → Keep Snowflake tables updated with changes from an external system
- 📌 Auditing & Compliance → Track who changed what in your data
- 📌 ETL Optimizations → Only load changed records into a Data Warehouse
- 📌 Real-Time Reporting → Send updates to BI dashboards immediately


## How to Process & Apply Stream Changes?

- ✅ Example: Applying Changes to a Target Table
Let’s say we have a sales table and a sales_history table that needs to stay updated.



### 1️⃣ Create a Stream to Track Changes in sales:

```sql
CREATE STREAM sales_stream ON TABLE sales;
```



### 2️⃣ Process the Changes using MERGE:

```sql
MERGE INTO sales_history AS target

USING sales_stream AS source

ON target.product_id = source.product_id

WHEN MATCHED AND source.METADATA$ACTION = 'DELETE' THEN DELETE

WHEN MATCHED AND source.METADATA$ACTION = 'UPDATE' THEN

UPDATE SET target.price = source.price, target.name = source.name

WHEN NOT MATCHED THEN

INSERT (product_id, name, price) VALUES (source.product_id, source.name, source.price);
```

- 📌 What This Does:


Deletes rows in sales_history if they were deleted in sales

Updates existing rows in sales_history if they were updated

Inserts new rows if they were newly added to sales



### 3️⃣ Clear the Stream After Processing

Once changes are processed, the stream resets automatically (so you only get fresh changes next time).





## Scenario: Keeping a Reporting Table Updated

Imagine we have: 1️⃣ A main table (orders) where new orders are inserted, updated, or deleted.

### 2️⃣ A reporting table (orders_history) that needs to stay in sync with orders.



- 💡 Goal: Whenever data in orders changes, we want to update orders_history automatically.


Step 1: Create the Main Table (orders)

This table stores customer orders.





```sql
CREATE TABLE orders (

order_id INT PRIMARY KEY,

customer_name STRING,

order_amount FLOAT,

order_status STRING

);

- ✅ Insert some sample data:

INSERT INTO orders VALUES (1, 'Alice', 100, 'Pending'),(2, 'Bob', 200, 'Shipped'),(3, 'Charlie', 150, 'Pending');
```

Step 2: Create a Stream to Track Changes

Now, let's create a stream to capture any INSERT, UPDATE, or DELETE on the orders table.





```sql
CREATE STREAM orders_stream ON TABLE orders;
```

This does not store data, but it logs changes made to orders.

Step 3: Create the Reporting Table (orders_history)

This will store a historical record of all orders.





```sql
CREATE TABLE orders_history (

order_id INT PRIMARY KEY,

customer_name STRING,

order_amount FLOAT,

order_status STRING

);

```

- ✅ Initialize it with existing orders:




```sql
INSERT INTO orders_history SELECT * FROM orders;
```

Step 4: Make Some Changes in orders

Now, let’s simulate real-world updates.





-- Insert a new order

```sql
INSERT INTO orders VALUES (4, 'David', 250, 'Pending');
```



-- Update an existing order

```sql
UPDATE orders SET order_status = 'Delivered' WHERE order_id = 2;
```



-- Delete an order

```sql
DELETE FROM orders WHERE order_id = 3;
```

Step 5: Process & Apply Changes to orders_history

We use MERGE to apply the changes from the stream to the orders_history table.



```sql
MERGE INTO orders_history AS target

USING orders_stream AS source

ON target.order_id = source.order_id

WHEN MATCHED AND source.METADATA$ACTION = 'DELETE' THEN

DELETE

WHEN MATCHED AND source.METADATA$ACTION = 'UPDATE' THEN

UPDATE SET target.customer_name = source.customer_name,

target.order_amount = source.order_amount,

target.order_status = source.order_status

WHEN NOT MATCHED THEN

INSERT (order_id, customer_name, order_amount, order_status)

VALUES (source.order_id, source.customer_name, source.order_amount, source.order_status);
```



What This Does:

- ✅ Deletes rows in orders_history if they were deleted in orders.
- ✅ Updates existing rows in orders_history if they were updated in orders.
- ✅ Inserts new rows if they were added to orders.




Step 6: Verify the Updated orders_history Table

```sql
SELECT * FROM orders_history;
```

You should now see:



The new order from David added.

The order from Bob updated to "Delivered".

The order from Charlie removed.





Step 7: Automate This Using a Task (Optional)

```sql
CREATE TASK sync_orders_history 
WAREHOUSE my_warehouse
SCHEDULE = '5 MINUTE'
AS
MERGE INTO orders_history
```

USING orders_stream

ON orders_history.order_id = orders_stream.order_id

WHEN MATCHED AND orders_stream.METADATA$ACTION = 'DELETE' THEN DELETE

WHEN MATCHED AND orders_stream.METADATA$ACTION = 'UPDATE' THEN

```sql
UPDATE SET orders_history.customer_name = orders_stream.customer_name,

orders_history.order_amount = orders_stream.order_amount,

orders_history.order_status = orders_stream.order_status

WHEN NOT MATCHED THEN

INSERT (order_id, customer_name, order_amount, order_status)

VALUES (orders_stream.order_id, orders_stream.customer_name, orders_stream.order_amount, orders_stream.order_status);
```



------------------------------



## What is Clustering in Snowflake?

- 💡 Snowflake Clustering is the process of organizing data within a table to improve query performance. Instead of scanning the whole table, Snowflake can skip unnecessary data and read only what's needed.


## How Does It Work?

Snowflake stores data in micro-partitions (small storage units).

Each partition contains metadata about the data it holds (min/max values, etc.).

When you run a query with a WHERE clause, Snowflake tries to prune (skip) unnecessary partitions.

If the data is well-clustered, pruning is more efficient and queries run faster. 🚀



## When Do You Need Clustering?

Snowflake automatically manages partitions, but sometimes tables become less organized over time. This happens when: ✅ The table is very large (millions or billions of rows).

- ✅ Data is inserted in random order instead of being naturally sorted.
- ✅ Queries frequently filter on specific columns (e.g., DATE, REGION, CUSTOMER_ID).


- 💡 If your queries scan too much data instead of using pruning, clustering can help!




## How to Cluster a Table?

### 1️⃣ Identify the Right Clustering Keys

Choose columns that are frequently used in filters (WHERE, JOIN).

Common examples: DATE, CUSTOMER_ID, REGION, PRODUCT_ID.

### 2️⃣ Manually Cluster a Table

```sql
ALTER TABLE sales CLUSTER BY (region, order_date);
```

This tells Snowflake to organize data based on region and order_date.

### 3️⃣ Check Clustering Information

```sql
SELECT system$clustering_information('sales');
```

This shows how well-clustered the table is.

### 4️⃣ Recluster the Table (If Needed)

```sql
ALTER TABLE sales RECLUSTER;
```

This physically reorganizes the table to improve performance.





## Automatic Clustering (No Manual Work!)

Instead of manually clustering, Snowflake can do it for you automatically. 🎉



```sql
ALTER TABLE sales SET AUTOMATIC_CLUSTERING = TRUE;
```





## What is  Materialized & regular  Views?

Difference Between Materialized View & Regular View in Snowflake ❄️📊

| Feature | Materialized View (MV) 🏗️ | Regular View 👀 |
|---|---|---|
| Definition | A precomputed, stored version of a query result. | A saved SQL query that runs dynamically when accessed. |
| Storage | Physically stores data (takes up extra storage). | Does not store data, only stores query definition. |
| Performance | Faster (data is precomputed & stored). | Slower (query is computed in real-time). |
| Query Execution | Returns results instantly since data is precomputed. | Executes the SQL query every time you select from it. |
| Updates | Automatically updates when source data changes. | Always reflects the latest data but requires query execution. |
| Joins Allowed? | ❌ No (Cannot contain JOIN). | ✅ Yes (Can use JOIN on multiple tables). |
| Aggregation Support? | ✅ Yes (Great for SUM(), AVG(), etc.). | ✅ Yes, but recomputes on every query. |
| Window Functions? | ❌ Not Supported (e.g., ROW_NUMBER() is not allowed). | ✅ Supported (Can use ROW_NUMBER(), RANK(), etc.). |
| Use Case | Ideal for precomputed reports & dashboards that run frequently. | Best for ad-hoc analysis and complex queries. |
| Cost | Uses extra storage, but saves compute costs. | No storage cost, but can be expensive on large datasets. |
| Best For | Speeding up frequent, repetitive queries. | Dynamic, real-time queries that don’t need storage. |


When to use MVs?

When you frequently aggregate large datasets (SUM, COUNT, AVG).





create & use Materialized view

How to Create a Materialized View?

Let’s say we have a sales table and we frequently query total revenue per region.







- 📌 Without an MV, each query scans the full table:


```sql
SELECT region, SUM(sales_amount)
FROM sales
GROUP BY region;
```

- ❌ This is slow if sales has millions of rows.


- 📌 With an MV, Snowflake stores the result:


```sql
CREATE MATERIALIZED VIEW mv_sales_by_region AS
SELECT region, SUM(sales_amount) AS total_revenue
FROM sales
GROUP BY region;
```

- ✅ Now, querying the view is super fast:


```sql
SELECT * FROM mv_sales_by_region;
```



How Does an MV Update Itself?

Snowflake automatically tracks changes in sales.

If new rows are added, updated, or deleted, Snowflake incrementally refreshes the MV.

Only the changed data is updated (not the whole table).



Checking MV Refresh Status

- 🔍 Check when an MV was last refreshed:


```sql
SHOW MATERIALIZED VIEWS;
```

- 🔍 See detailed refresh history:


```sql
SELECT * FROM TABLE(INFORMATION_SCHEMA.MATERIALIZED_VIEW_REFRESH_HISTORY());
```





## Limitations of MVs in Snowflake

- ❌ No Joins Allowed – MVs can’t use JOIN (use a regular view instead).
- ❌ No Window Functions – Functions like ROW_NUMBER() aren’t allowed.
- ❌ Storage Cost – MVs take up extra storage because Snowflake physically stores the data.


- 📌 If you need more flexibility, you can use regular views instead:




```sql
CREATE VIEW vw_sales_by_region AS
SELECT region, SUM(sales_amount)
FROM sales
GROUP BY region;
```





## When to Use Which?

- ✅ Use a Materialized View when:


You need fast, frequent queries.

You’re working with aggregated data (SUM, COUNT, AVG).

You want to reduce compute cost by precomputing data.

- ✅ Use a Regular View when:


You need a dynamic, always up-to-date query.

Your queries involve JOINs or window functions.

Storage cost is a concern.





---------------------------

##What are External Tables in Snowflake?

An External Table in Snowflake allows you to query data stored outside of Snowflake (e.g., in Amazon S3, Google Cloud Storage, or Azure Blob Storage) without loading it into Snowflake.



## How to Create an External Table?

- 📌 Step 1: Create an External Stage (Point to Cloud Storage)
If your data is in Amazon S3, first create a stage to access it:



```sql
CREATE STAGE my_s3_stage
URL = 's3://my-bucket/snowflake-data/'
STORAGE_INTEGRATION = my_s3_integration;
```
- 🔹 This connects Snowflake to the external storage location.


- 📌 Step 2: Create the External Table


```sql
CREATE EXTERNAL TABLE my_external_table (
id INT AS (value:c1::INT),
name STRING AS (value:c2::STRING),
created_at TIMESTAMP AS (value:c3::TIMESTAMP)
)
WITH LOCATION = '@my_s3_stage'
FILE_FORMAT = (TYPE = PARQUET);
```

- 🔹 This tells Snowflake that data files in s3://my-bucket/snowflake-data/ contain a table.
- 🔹 Instead of storing data in Snowflake, it reads directly from cloud storage!


- 📌 Step 3: Query the External Table


```sql
SELECT * FROM my_external_table;
```

- ✅ You can now query the external data just like a normal table!


##Key Differences Between External Tables & Regular Tables

| Feature | External Table 📂 | Regular Table 🏛️ |
|---|---|---|
| Storage | Data stays in cloud storage (S3, GCS, Azure). | Data is physically stored inside Snowflake. |
| Performance | Slower (reads from external storage). | Faster (data is inside Snowflake). |
| Cost | Cheaper (No Snowflake storage cost). | Costs more (Snowflake storage fees). |
| Best for | Big data & data lakes. | Frequent queries & performance-sensitive workloads. |




---------------------------




## explain Temporary Table 🏷️ , Transient Table 🔄 , Permanent Table 🏛️? 


| Table Type | Temporary Table 🏷️ | Transient Table 🔄 | Permanent Table 🏛️ |
|---|---|---|---|
| Stored Permanently? | ❌ No | ❌ No | ✅ Yes |
| Survives Session? | ❌ No (Deleted when session ends) | ✅ Yes (Persists) | ✅ Yes |
| Time Travel Support? | ❌ No | ❌ No | ✅ Yes (Default: 1 Day) |
| Storage Cost? | Lower (Session-based) | Lower (No Fail-safe) | Standard Snowflake Storage Costs |
| Best For? | Short-term data processing | Intermediate tables with longer use | Long-term storage & production data |

##How to Create a Temporary Table:

```sql
CREATE TEMPORARY TABLE temp_sales AS
SELECT * FROM sales WHERE order_date > '2024-01-01';
```

##How to Create a Transient Table:

```sql
CREATE TRANSIENT TABLE fast_sales AS
SELECT * FROM sales WHERE region = 'West';
```

##When to Use Temporary vs. Transient Tables?

| UseCase                     | Use Temporary Table | Use Transient Table  | 
|-----------------------------|---------------------|----------------------|
| One-time calculations       | ✅                  | ❌                  |
| Session-based data          | ✅                  | ❌                  |
| Intermediate ETL tables     | ❌                  | ✅                  |
| Short-term reporting tables | ❌                  | ✅                  |
| Saving compute costs        | ✅                  | ✅                  |

## Key Takeaways

- ✔ Temporary Tables = Best for one-session, short-term data (deleted automatically).
- ✔ Transient Tables = Best for multi-session, short-term storage with no Time Travel.
- ✔ Permanent Tables = Best for long-term, production data with full Snowflake features.



## Summary

Snowflake is a powerful, cloud-native platform for modern data solutions, offering capabilities in **data warehousing**, **data lakes**, **analytics**, and **data sharing**. Its competitors include BigQuery, Redshift, Azure Synapse, Databricks, and Teradata. Snowflake's hierarchical structure and flexibility make it an excellent choice for both small and large-scale data operations.
