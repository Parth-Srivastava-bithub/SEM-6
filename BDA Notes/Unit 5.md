# **Ultra-Detailed Guide to Hadoop Ecosystem Frameworks**

## **1. Apache Pig (Data Flow Language for Hadoop)**

### **1.1 Introduction to Pig**
- **Purpose:** High-level platform for creating MapReduce programs
- **Components:**
  - **Pig Latin:** Scripting language (procedural SQL-like syntax)
  - **Grunt Shell:** Interactive shell for executing Pig commands
  - **Execution Engine:** Converts scripts to MapReduce jobs

### **1.2 Execution Modes**
| Mode | Description | Use Case |
|------|------------|----------|
| **Local Mode** | Runs on single JVM (no HDFS) | Development/testing |
| **MapReduce Mode** | Runs on Hadoop cluster | Production processing |

### **1.3 Pig vs Traditional Databases**
| Feature | Pig | RDBMS |
|---------|-----|-------|
| Schema | Optional (schema-on-read) | Required (schema-on-write) |
| Data Types | Simple (int, chararray, etc.) | Complex (date, decimal, etc.) |
| Language | Procedural (Pig Latin) | Declarative (SQL) |
| Optimization | Limited | Advanced query optimization |

### **1.4 Pig Latin Fundamentals**
**Basic Operations:**
```pig
-- Loading data
data = LOAD 'input.txt' USING PigStorage(',') AS (name:chararray, age:int);

-- Transformation
filtered = FILTER data BY age > 18;

-- Storage
STORE filtered INTO 'output' USING PigStorage();
```

**Key Operators:**
- `LOAD`/`STORE`: Data input/output
- `FILTER`: Row selection
- `FOREACH`: Column operations
- `GROUP`: Aggregation
- `JOIN`: Table combining
- `ORDER BY`: Sorting
- `DISTINCT`: Deduplication

### **1.5 User Defined Functions (UDFs)**
**Types:**
1. **Eval Functions:** Process fields and return values
2. **Filter Functions:** Return boolean for filtering
3. **Load/Store Functions:** Custom data formats

**Example Java UDF:**
```java
public class UpperCase extends EvalFunc<String> {
    public String exec(Tuple input) throws IOException {
        return input.get(0).toString().toUpperCase();
    }
}
```

## **2. Apache Hive (Data Warehouse System)**

### **2.1 Architecture**
![Hive Architecture](https://hadoop.apache.org/hive/images/hive_architecture.jpg)

**Key Components:**
1. **Driver:** Manages session and query execution
2. **Compiler:** Converts HiveQL to execution plan
3. **Metastore:** Stores schema metadata (usually in RDBMS)
4. **Execution Engine:** Runs on MapReduce/Tez/Spark

### **2.2 Installation & Services**
**Installation Steps:**
1. Download and extract Hive
2. Configure `hive-site.xml`
3. Set up Metastore (embedded/local/remote)
4. Initialize schema: `schematool -initSchema -dbType derby`

**Services:**
- **CLI:** Command Line Interface
- **HiveServer2:** Remote JDBC/ODBC access
- **WebHCat:** REST API
- **HCatalog:** Table management layer

### **2.3 HiveQL vs SQL**
| Feature | HiveQL | SQL |
|---------|--------|-----|
| Transactions | Limited support | Full ACID |
| Indexes | Limited | Extensive |
| Latency | High (batch-oriented) | Low |
| Schema | Schema-on-read | Schema-on-write |

### **2.4 Advanced Hive Features**
**Partitioning:**
```sql
CREATE TABLE logs (msg STRING)
PARTITIONED BY (dt STRING, country STRING);
```

**Bucketing:**
```sql
CREATE TABLE users (id INT, name STRING)
CLUSTERED BY (id) INTO 32 BUCKETS;
```

**Window Functions:**
```sql
SELECT name, salary,
       RANK() OVER (PARTITION BY dept ORDER BY salary DESC) as rank
FROM employees;
```

**MapReduce Scripts:**
```sql
-- Using TRANSFORM
FROM (
  MAP employee_data USING 'mapper.py'
  AS name, salary
) map_output
REDUCE map_output USING 'reducer.py'
AS name, avg_salary;
```

## **3. Apache HBase (NoSQL Database)**

### **3.1 Core Concepts**
**Data Model:**
- **Table:** Collection of rows
- **Row:** Unique row key + columns
- **Column Family:** Group of columns (physical storage unit)
- **Column Qualifier:** Unique within family
- **Cell:** {row, column, version} → value
- **Timestamp:** Version identifier

**Example Structure:**
```
Row Key | Column Family:Qualifier | Value | Timestamp
--------|-------------------------|-------|----------
user1   | info:name               | John  | t1
user1   | info:email              | j@x.co| t2
```

### **3.2 HBase vs RDBMS**
| Feature | HBase | RDBMS |
|---------|-------|-------|
| Schema | Flexible | Rigid |
| Scaling | Linear horizontal | Vertical |
| Transactions | Single-row | Multi-row |
| Joins | Not supported | Supported |
| Indexes | Only primary | Multiple |

### **3.3 Advanced Usage**
**Schema Design Principles:**
1. **Row Key Design:**
   - Should distribute writes evenly
   - Common patterns: Salting, hashing, sequential
2. **Column Families:**
   - Keep related data together
   - Typically 1-3 per table
3. **Versioning:**
   - Configure number of versions to keep
   - Automatic timestamp assignment

**Secondary Indexing Options:**
1. **Client-managed:** Maintain separate index table
2. **Coprocessors:** Server-side indexing
3. **External Solutions:** Phoenix, Solr

### **3.4 ZooKeeper Integration**
**Roles in HBase:**
1. **Master Election:** Active/standby coordination
2. **Region Server Tracking:** Server availability
3. **Schema Changes:** Table modifications
4. **Namespace Management:** Database-like grouping

**Monitoring Example:**
```bash
# List ZooKeeper nodes
echo "ls /hbase" | zkCli.sh
```

## **4. IBM Big Data Solutions**

### **4.1 Big Data Strategy**
**Four Pillars:**
1. **Hadoop-based Analytics:** InfoSphere BigInsights
2. **Stream Computing:** InfoSphere Streams
3. **Data Warehousing:** Db2 Warehouse
4. **System of Record:** Db2 and Informix

### **4.2 InfoSphere BigInsights**
**Components:**
- **Big SQL:** SQL interface for Hadoop
- **Big Sheets:** Excel-like analysis tool
- **Text Analytics:** Unstructured data processing
- **Machine Learning:** Predictive modeling

**Architecture:**
1. **Data Layer:** HDFS, HBase, Hive
2. **Processing Layer:** MapReduce, Spark
3. **Analytics Layer:** Big SQL, Big Sheets
4. **Management Layer:** Security, monitoring

### **4.3 Big SQL Features**
**Key Capabilities:**
- ANSI SQL compliant
- Federated queries across Hadoop and RDBMS
- Cost-based optimization
- Columnar storage format

**Example Query:**
```sql
-- Join Hadoop and Db2 data
SELECT h.customer_id, d.customer_name, SUM(h.amount)
FROM hadoop.sales h
JOIN db2.customers d ON h.customer_id = d.customer_id
GROUP BY h.customer_id, d.customer_name;
```

### **4.4 Big Sheets**
**Features:**
- Spreadsheet interface for Hadoop data
- Visual data exploration
- Pre-built analytic functions
- Collaborative analysis

**Workflow:**
1. Connect to Hadoop data source
2. Create worksheet with data subset
3. Apply transformations and formulas
4. Visualize with charts and graphs
5. Share results with team

## **Practical Implementation Guide**

### **Pig for ETL Pipeline**
```pig
-- Load weblogs
logs = LOAD '/data/weblogs' USING PigStorage() AS (ip:chararray, timestamp:chararray, url:chararray);

-- Extract date
dated = FOREACH logs GENERATE ip, 
       SUBSTRING(timestamp, 0, 10) AS date,
       url;

-- Filter for specific domain
filtered = FILTER dated BY url MATCHES '.*example\\.com.*';

-- Group by IP and date
grouped = GROUP filtered BY (ip, date);

-- Count visits per IP/date
counts = FOREACH grouped GENERATE 
         group.ip, 
         group.date, 
         COUNT(filtered) AS visits;

-- Store results
STORE counts INTO '/output/visit_counts' USING PigStorage(',');
```

### **Hive for Data Analysis**
```sql
-- Create partitioned table
CREATE EXTERNAL TABLE sales (
    product_id STRING,
    amount DOUBLE,
    currency STRING
)
PARTITIONED BY (sale_date STRING)
STORED AS PARQUET
LOCATION '/data/sales';

-- Add partition
ALTER TABLE sales ADD PARTITION (sale_date='2023-01-01');

-- Analytical query
SELECT 
    product_id,
    AVG(amount) AS avg_sale,
    PERCENTILE_APPROX(amount, 0.5) AS median_sale
FROM sales
WHERE sale_date BETWEEN '2023-01-01' AND '2023-01-31'
GROUP BY product_id
HAVING COUNT(*) > 100
ORDER BY avg_sale DESC;
```

### **HBase Java API Example**
```java
// Create configuration
Configuration config = HBaseConfiguration.create();
config.set("hbase.zookeeper.quorum", "zk1.example.com");

// Create connection
Connection connection = ConnectionFactory.createConnection(config);

// Get table reference
Table table = connection.getTable(TableName.valueOf("users"));

// Put operation
Put put = new Put(Bytes.toBytes("user123"));
put.addColumn(Bytes.toBytes("info"), 
             Bytes.toBytes("email"),
             Bytes.toBytes("user@example.com"));
table.put(put);

// Get operation
Get get = new Get(Bytes.toBytes("user123"));
Result result = table.get(get);
byte[] email = result.getValue(Bytes.toBytes("info"),
                          Bytes.toBytes("email"));

// Close resources
table.close();
connection.close();
```
