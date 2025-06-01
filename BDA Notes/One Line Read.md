# Unit 1

1. **Types of Digital Data** – Structured, semi-structured, and unstructured data forms.
2. **History of Big Data** – Evolution from traditional DBs to scalable, distributed systems.
3. **Introduction to Big Data Platform** – Tools & infra used to handle massive datasets.
4. **Drivers for Big Data** – IoT, social media, and digital transformation fueling growth.
5. **Big Data Architecture** – Layers like data source, ingestion, storage, processing & visualization.
6. **Characteristics of Big Data** – Volume, Variety, Velocity, Veracity, and Value (5Vs).
7. **5 Vs of Big Data** – Key traits that define Big Data challenges and opportunities.
8. **Big Data Technology Components** – Tools like Hadoop, Spark, NoSQL, etc.
9. **Big Data Importance** – Helps in better decisions, innovation, and business growth.
10. **Big Data Applications** – Used in healthcare, finance, marketing, and more.
11. **Big Data Features** – Includes security, compliance, auditing, and protection measures.
12. **Big Data Privacy and Ethics** – Ensuring responsible and fair data use.
13. **Big Data Analytics** – Extracting useful insights from massive datasets.
14. **Challenges of Conventional Systems** – Can't handle big, fast, or varied data efficiently.
15. **Intelligent Data Analysis** – Using AI/ML to make sense of complex data.
16. **Nature of Data** – Data is often huge, noisy, and comes from various sources.
17. **Analytic Processes and Tools** – Steps & software used to analyze data (like ETL, ML).
18. **Analysis vs Reporting** – Analysis finds patterns, reporting shows what happened.
19. **Modern Data Analytic Tools** – Advanced tools like Power BI, Tableau, Spark, etc.

---

# Unit 2

## **Hadoop**

1. **History of Hadoop** – Inspired by Google File System & MapReduce papers.
2. **Apache Hadoop** – Open-source framework for distributed data processing.
3. **HDFS** – Breaks big files into blocks & stores across cluster nodes.
4. **Components of Hadoop** – HDFS, YARN, MapReduce, and Common utilities.
5. **Data Format** – Supports Text, Avro, Parquet, Sequence, etc.
6. **Analyzing Data with Hadoop** – Distributed processing of large datasets.
7. **Scaling Out** – Add more nodes to handle more data (horizontal scaling).
8. **Hadoop Streaming** – Run MapReduce with any language using stdin/stdout.
9. **Hadoop Pipes** – C++ API to write MapReduce programs.
10. **Hadoop Ecosystem** – Tools like Hive, Pig, HBase, Sqoop, Flume, Zookeeper.

---

## **MapReduce**

1. **MapReduce Framework** – Processes data in Map → Shuffle → Reduce phases.
2. **How it Works** – Mapper filters/sorts, Reducer summarizes results.
3. **Developing App** – Write Mapper & Reducer classes, package & run on cluster.
4. **Unit Tests with MRUnit** – Framework to test MapReduce logic.
5. **Test Data & Local Tests** – Run on small test sets before cluster deployment.
6. **Anatomy of a Job** – Submit job → split input → map tasks → shuffle → reduce → output.
7. **Failures** – Auto-retries and node replacement if tasks fail.
8. **Job Scheduling** – YARN allocates resources to different jobs.
9. **Shuffle & Sort** – Intermediate data sorted & grouped before reduce phase.
10. **Task Execution** – Handled by NodeManager under YARN.
11. **MapReduce Types** – Simple, chained, or complex custom jobs.
12. **Input Formats** – TextInputFormat, KeyValueInputFormat, etc.
13. **Output Formats** – TextOutputFormat, SequenceFileOutputFormat, etc.
14. **MapReduce Features** – Scalable, fault-tolerant, parallel processing.
15. **Real-world Use** – Log analysis, indexing, data transformation, etc.

---

# Unit 3

## **HDFS**

1. **Design of HDFS** – Designed for large-scale, fault-tolerant storage.
2. **HDFS Concepts** – Namenode (master), Datanodes (slaves), block storage.
3. **Benefits & Challenges** – Scalable & fault-tolerant but not for low-latency ops.
4. **File & Block Sizes** – Default 128MB block; files split into these blocks.
5. **Block Abstraction** – Logical division of files for distributed storage.
6. **Data Replication** – Each block stored in 3 copies for fault tolerance.
7. **File Storage Process** – Namenode manages metadata, Datanodes store blocks.
8. **Read/Write Process** – Client talks to Namenode for metadata, then to Datanodes for data.
9. **Java Interfaces** – Java API for programmatic file operations.
10. **CLI** – Shell commands for managing files (like `hdfs dfs -ls /`).
11. **Hadoop FS Interfaces** – Supports multiple storage backends (e.g., S3, local FS).
12. **Data Flow** – Flow of file read/write through client, NN, and DN.
13. **Flume** – Ingest streaming data into HDFS (like logs).
14. **Sqoop** – Transfer data between RDBMS and HDFS.
15. **Hadoop Archives** – Efficient way to store large numbers of small files.
16. **Compression** – Reduce storage size and improve performance.
17. **Serialization** – Convert objects to byte streams (Writable, Avro).
18. **Avro** – Row-based, schema-evolution-friendly data format.
19. **File-based Data Structures** – SequenceFile, MapFile, etc.

---

## **Hadoop Environment**:

1. **Hadoop Cluster Setup** – Multi-node setup for distributed processing.
2. **Cluster Specs** – CPU, RAM, storage needs for Namenode/Datanodes.
3. **Installation** – Hadoop binaries setup, SSH config, permissions.
4. **Configuration** – Core, HDFS, MapReduce, YARN config files.
5. **Security in Hadoop** – Kerberos for authentication, encryption, access control.
6. **Administering Hadoop** – User management, disk space, service monitoring.
7. **Monitoring & Maintenance** – Tools like Ambari, metrics, logs.
8. **Hadoop Benchmarks** – Performance testing using TeraSort, TestDFSIO.
9. **Hadoop in Cloud** – Deploy on AWS, Azure, GCP with managed services.

---

# Unit 4

### **Hadoop Ecosystem & YARN**

1. **Components** – Hive, Pig, HBase, Flume, Oozie, etc., all integrate with Hadoop.
2. **Schedulers** – Decide job resource allocation (FIFO, Fair, Capacity).
3. **Fair & Capacity** – Fair shares resources equally; capacity reserves fixed slots.
4. **Hadoop 2.0** – Major upgrades like HA Namenode, HDFS Federation, and YARN.
5. **MRv2 (YARN)** – MapReduce 2 runs as an app on YARN, not a core service.
6. **MRv1 on YARN** – Old MR jobs still run on new YARN architecture.

---

### **NoSQL & MongoDB**

1. **NoSQL Intro** – Non-relational, flexible schema DBs for big & unstructured data.
2. **MongoDB Intro** – Document-based NoSQL DB, JSON-like storage.
3. **Data Types** – Supports int, float, string, date, array, object, etc.
4. **CRUD Ops** – Create, update, delete, and query documents.
5. **Querying** – Use operators like `$gt`, `$in`, `$or`, etc.
6. **Indexing** – Improves query speed, supports compound and text indexes.
7. **Capped Collections** – Fixed-size collections that auto-delete old entries.

---

### **Spark**

1. **Installing Spark** – Easy install via pre-built packages or from source.
2. **Spark App Flow** – Runs in jobs → stages → tasks hierarchy.
3. **RDDs** – Immutable distributed collections enabling parallel processing.
4. **Spark Job Anatomy** – Driver → DAG Scheduler → Task Scheduler → Executor.
5. **Spark on YARN** – Spark can use Hadoop YARN for cluster resource management.

---

### **Scala**

1. **Intro** – JVM-based language blending OOP & functional programming.
2. **Classes & Objects** – Scala's basic structure for defining logic and data.
3. **Basic Types** – Int, String, Boolean, etc., with powerful operators.
4. **Control Structures** – `if`, `while`, `for`, `match`, like in Java but cleaner.
5. **Functions & Closures** – First-class functions with support for closures.
6. **Inheritance** – OOP style inheritance with traits and abstract classes.

---

# Unit 5

### **Pig**

1. **Intro & Modes** – Data flow language for big data; runs in local & MapReduce modes.
2. **Pig vs DB** – Procedural (Pig) vs Declarative (SQL).
3. **Grunt Shell** – Interactive shell to run Pig commands.
* **Pig Latin** – High-level language for data transformation.
* **UDFs & Operators** – Custom logic + built-in operators for filtering, grouping, joining.

---

### **Hive**

* **Architecture** – SQL-like tool built on top of Hadoop.
* **Hive Shell & Services** – Interface to run HiveQL; services manage query execution.
* **Metastore** – Stores schema & metadata.
* **Hive vs RDBMS** – Hive is read-optimized, not meant for real-time writes.
* **HiveQL** – SQL-like querying, supports joins, subqueries, etc.
* **MapReduce Integration** – HiveQL auto-converts to MR jobs.

---

### **HBase**

* **Concepts** – NoSQL, columnar store built on HDFS for real-time reads/writes.
* **Clients & Examples** – APIs to interact with HBase.
* **HBase vs RDBMS** – Schema-less, scalable, better for sparse data.
* **Advanced Use** – Secondary indexing, time-series data.
* **Zookeeper** – Ensures coordination and health of HBase clusters.

---

### **IBM Big Data**

* **Strategy** – Enterprise-level big data solutions.
* **Infosphere** – Data integration and governance platform.
* **BigInsights** – IBM’s Hadoop-based big data platform.
* **Big Sheets** – Spreadsheet-like analysis tool on big data.
* **Big SQL** – Run SQL queries on Hadoop data.



