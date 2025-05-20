### **1.1 Introduction to Pig**

**What is Pig?**
Apache Pig is a **high-level platform** for processing large datasets on Hadoop.
It uses **Pig Latin**, a data flow language that abstracts the complexity of writing raw MapReduce code.

**Why Use Pig?**

* Writing Java-based MapReduce is tedious.
* Pig simplifies it with a few lines of script.
* It **automatically optimizes** the execution under the hood.
* Best for **ETL tasks** like data cleaning, transformation, and preparation.

**Real-Life Use Case:**
You're cleaning millions of log entries — remove bot traffic, extract useful fields, and generate user stats — Pig does this easily.

---

### **1.2 Execution Modes**

| **Mode**  | **Description**                          | **When to Use**                 |
| --------- | ---------------------------------------- | ------------------------------- |
| Local     | Runs on a single JVM without Hadoop/HDFS | Testing or dev with small files |
| MapReduce | Converts Pig script into MapReduce jobs  | Production & large-scale jobs   |

**Commands:**

```bash
pig -x local script.pig    # Local mode
pig script.pig             # Default is MapReduce mode
```

---

### **1.3 Pig vs Traditional Databases**

| **Feature** | **Pig**                     | **SQL DB**                  |
| ----------- | --------------------------- | --------------------------- |
| Schema      | Optional (schema-on-read)   | Mandatory (schema-on-write) |
| Latency     | High (batch jobs)           | Low (interactive queries)   |
| Scale       | Massive (petabytes)         | Limited (terabytes usually) |
| Programming | Procedural (how data flows) | Declarative (what you want) |

**TLDR:** Pig = Data pipelines, SQL = Interactive querying.

---

### **1.4 Pig Latin Basics**

#### **Data Types:**

* **Scalar:** int, float, chararray (string), long, double, boolean.
* **Complex:**

  * **Tuple:** ordered set of fields → `(1, "apple")`
  * **Bag:** collection of tuples → `{(1,"a"), (2,"b")}`
  * **Map:** key-value pairs → `[name#“Parth”, age#21]`

#### **Example Pig Script Breakdown:**

```pig
-- Load CSV data from HDFS
logs = LOAD '/data/weblogs' USING PigStorage(',') AS (user:chararray, url:chararray);

-- Remove bots
clean_logs = FILTER logs BY NOT (url MATCHES '.*bot.*');

-- Group by user
user_groups = GROUP clean_logs BY user;

-- Count how many times each user visited
user_counts = FOREACH user_groups GENERATE group, COUNT(clean_logs);

-- Store output in HDFS
STORE user_counts INTO '/output/user_analytics';
```

---

### **1.5 User Defined Functions (UDFs)**

Sometimes Pig’s built-in functions aren’t enough. So, you can write **custom functions** in:

* **Java (official way)**
* **Python (via Jython/PyPig)**

#### **Java UDF Example:**

```java
package com.example;
public class ToUpper extends EvalFunc<String> {
  public String exec(Tuple input) {
    return input.get(0).toString().toUpperCase();
  }
}
```

#### **Registering and Using in Pig:**

```pig
REGISTER 'udfs.jar';
DEFINE ToUpper com.example.ToUpper();

output = FOREACH data GENERATE ToUpper(name);
```

---

### **2.1 Hive Architecture (Simplified Flow)**

* 🧠 **Metastore**: Think of it as the "brain" storing table schemas, locations, and metadata (usually in MySQL/PostgreSQL).
* 🎯 **Driver**: Translates HiveQL (your SQL-like queries) into executable jobs (MapReduce/Tez/Spark).
* 💻 **CLI / Beeline**: Interfaces for running queries, just like MySQL shell or pgAdmin.

**Workflow:**
`Query → Driver → Compiler → Execution Engine (MR/Tez/Spark) → Results`

---

### **2.2 Hive vs RDBMS (Battle Mode ⚔️)**

| **Feature**    | **Hive (Big Data)**             | **RDBMS (e.g., MySQL)**     |
| -------------- | ------------------------------- | --------------------------- |
| Transactions   | Limited (Hive 3+ supports ACID) | Full ACID support           |
| Speed          | Slow (batch processing)         | Fast (row-based, real-time) |
| Schema         | Schema-on-read                  | Schema-on-write             |
| Storage        | On HDFS                         | On local disk               |
| Query Language | HiveQL (SQL-like)               | SQL                         |

**Summary**: Hive is not for OLTP. It's built for **big data analytics**, not fast real-time queries.

---

### **2.3 HiveQL (SQL for Hadoop)**

#### **Create Table:**

```sql
CREATE TABLE users (
  id INT,
  name STRING,
  age INT
) 
ROW FORMAT DELIMITED 
FIELDS TERMINATED BY ',';
```

Means: Treat each line like a CSV row.

#### **Load Data:**

```sql
LOAD DATA INPATH '/data/users.csv' INTO TABLE users;
```

Just brings data from HDFS into Hive's table format.

#### **Query Data:**

```sql
SELECT name, age FROM users WHERE age > 25;
```

Standard SQL-style querying.

#### **Joins Example:**

```sql
SELECT a.name, b.order_id 
FROM users a 
JOIN orders b ON a.id = b.user_id;
```

Supports inner, outer, left/right joins — just like SQL.

---

### **2.4 Hive UDFs (User Defined Functions)**

You can define your own logic if built-in functions don't cut it.

#### **Python UDF Example:**

`udf.py`

```python
def square(n):
  return n * n
```

**Register & Use:**

```sql
ADD FILE /path/to/udf.py;
CREATE TEMPORARY FUNCTION py_square AS 'udf.square';
SELECT py_square(age) FROM users;
```

Works with Python using **HiveStreaming/PyHive**.

---

### **3. Apache HBase – NoSQL on Hadoop**

#### **3.1 Core Concepts**

* 🧱 **Column-Oriented DB**: Unlike row-based SQL, HBase stores data by **column families**. Great for sparse, large datasets.

* ⚡ **Real-time use**: Best for fast read/write, e.g., chat apps, IoT data streams.

#### **HBase vs. RDBMS:**

| Feature | HBase                       | RDBMS                     |
| ------- | --------------------------- | ------------------------- |
| Schema  | Flexible (add cols anytime) | Fixed (predefined schema) |
| Scaling | Horizontal (scale-out)      | Vertical (scale-up)       |
| Access  | No SQL – uses API/Shell     | SQL                       |
| Joins   | ❌ Not supported             | ✅ Native joins            |

---

### **3.2 HBase Shell Commands 🐚**

```bash
create 'users', 'personal', 'professional'   # Table with 2 column families
put 'users', '1', 'personal:name', 'Alice'   # Add name to row key 1
put 'users', '1', 'professional:job', 'Engineer' # Add job info
scan 'users'                                 # Read all data
```

**Think of it like this:**

* Row key = Primary key (e.g., user ID)
* Column family = Category (e.g., personal)
* Column qualifier = Field (e.g., name)

---

### **3.3 Schema Design Tips 📐**

* ✅ **Denormalize**: Store related info in same row (no foreign keys or joins).
* ✅ **Good Row Keys**: Use hashed/timestamp-based keys to spread load.
* ❌ **Don’t use sequential keys**: Leads to server **hotspotting**.

---

### **4. ZooKeeper – The Cluster Manager 🦁**

#### **4.1 Role in Hadoop Ecosystem:**

* ⚙️ Keeps track of **which node is active**, dead, or elected.
* 📍 **Lock service**: Ensures only one leader (e.g., NameNode).
* 💬 **Coordination center**: Apps like HBase **use ZooKeeper** to track their region servers.

---

### **5. IBM Big Data Tools**

#### **5.1 IBM BigInsights**

Think of it as **IBM’s customized Hadoop** distribution—adds tools to make life easier:

* **BigSheets** 🧾: Analyze big data using spreadsheet-style UI. No coding, drag-n-drop magic. Great for business analysts.
* **Big SQL** ⚡: SQL engine for querying Hadoop data. Supports **ANSI SQL** and is much faster than Hive due to optimization techniques.

---

### **5.2 Big SQL vs. Hive – Quick Battle 🥊**

| Feature          | Big SQL                       | Hive                   |
| ---------------- | ----------------------------- | ---------------------- |
| Speed            | Low latency, highly optimized | Batch-based, slower    |
| Language Support | Full SQL-2016                 | HiveQL (SQL-like)      |
| Integration      | Deep with IBM ecosystem       | Open-source & flexible |
| Use Case         | Real-time analytics on Hadoop | Large-scale batch jobs |

---

### **Exam Tips ☑️**

* **Pig vs Hive**:
  Pig = Script, step-by-step (procedural).
  Hive = SQL, what-to-do (declarative).

* **HBase Design**:

  * Avoid joins, denormalize.
  * Row keys must spread load evenly.

* **ZooKeeper**:
  Think of it as a **distributed traffic cop** – keeps services coordinated, locks, configs, and node status synced.

---

