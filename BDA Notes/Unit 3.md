---

## 📦 HDFS: The Storage Backbone of Hadoop (Detailed Notes)

---

### 🔹 1.1 Design of HDFS

* **Distributed Storage**:
  Large files are broken into **blocks** (default size: **128MB or 256MB**) and spread across multiple nodes.

* **Fault Tolerance**:
  Each block is **replicated 3 times** (by default) on different DataNodes to avoid data loss if one fails.

* **Scalability**:
  Just **add more machines (nodes)** to increase both storage and processing power. Scales to petabytes.

* **Write Once, Read Many (WORM)**:
  Once a file is written, it **can’t be modified**, only read. Optimized for large file reads, not updates.

🧠 **Metaphor**:

| Hadoop Term | Library Analogy                                 |
| ----------- | ----------------------------------------------- |
| File        | A full book                                     |
| Block       | A page of the book                              |
| NameNode    | The librarian who tracks where books are stored |
| DataNode    | The bookshelves that hold the pages (blocks)    |

---

### 🔹 1.2 Core HDFS Components

#### 1. **NameNode (Master Node)**

* **Manages all metadata** – filenames, directories, permissions, block mapping.
* **Does NOT store actual data**.
* **Single Point of Failure (SPOF)**: If it goes down, HDFS becomes inaccessible (mitigated via HA).
* Only one active NameNode at a time in most setups.

#### 2. **DataNode (Worker Node)**

* Stores actual **blocks** of data.
* Each block gets replicated to **ensure fault tolerance**.
* Regularly sends **heartbeat** signals to NameNode → confirms it's alive.
* Sends block reports to update the NameNode.

#### 3. **Secondary NameNode**

* 💥 **Misunderstood! Not a backup.**
* Job: Periodically **merge**:

  * **Fsimage** (stored metadata snapshot)
  * **Edit logs** (recent changes)
* Goal: Reduce NameNode memory pressure.
* Can help restart the NameNode faster, but not a real-time failover.

---

### 🔹 1.3 Benefits & Challenges of HDFS

| ✅ **Benefits**                                | ❌ **Challenges**                                           |
| --------------------------------------------- | ---------------------------------------------------------- |
| **Handles petabytes/exabytes of data**        | Struggles with **lots of small files** (metadata overhead) |
| **Replication ensures fault tolerance**       | Not suitable for **low-latency/real-time** data needs      |
| **Scales linearly** → Add nodes easily        | **NameNode = bottleneck**, needs memory                    |
| Ideal for **batch processing** with MapReduce | Random access is **slow & inefficient**                    |

---

---

## 📂 2. HDFS File Operations: How Data is Stored, Read & Written

---

### 🔹 2.1 File Sizes & Block Abstraction

* **Default Block Size**: 128MB (can be changed in config).
* **Why large blocks?**

  * Less metadata for NameNode (saves memory).
  * Better performance for sequential reads (ideal for big files).

🧠 **Example**:
1GB file → 8 blocks of 128MB each → Spread across cluster.

---

### 🔹 2.2 Data Replication

* **Default Replication**: 3 copies (can be increased/decreased).

📍 **Replica Placement Strategy**:

1. 1st copy → Local DataNode (same node as client, if possible)
2. 2nd copy → Different rack (ensures fault tolerance)
3. 3rd copy → Same rack as 2nd (saves bandwidth)

🎯 **Why rack-aware?**
Even if one rack crashes, data is safe elsewhere.

---

### 🔹 2.3 How HDFS **Reads** a File

1. **Client → NameNode**: "Where’s the file?"
2. **NameNode → Client**: Block locations (e.g., on DN1, DN2, DN3)
3. **Client reads in parallel** directly from DataNodes.

🧠 **Metaphor**:
Like downloading parts of a movie from 3 fast mirror servers.

---

### 🔹 2.4 How HDFS **Writes** a File

1. **Client splits file** → into blocks.
2. **NameNode assigns** DataNodes for each block.
3. **Pipeline Writing**:

   * Data flows: Client → DN1 → DN2 → DN3
   * All DNs acknowledge back to client (after success)

🔁 **Failure Handling**:

* If a DataNode dies mid-write, HDFS selects a new node and retries.
* Replication ensures data survives hardware failures.

---

---

## 3. Interacting with HDFS

---

### 3.1 Command Line Interface (CLI)

| Command                         | Description               |
| ------------------------------- | ------------------------- |
| `hdfs dfs -ls /`                | List files in HDFS root   |
| `hdfs dfs -put local.txt /data` | Upload local file to HDFS |
| `hdfs dfs -cat /data/file.txt`  | View file content         |
| `hdfs dfs -rm /data/file.txt`   | Delete a file from HDFS   |

---

### 3.2 Java API for HDFS (Basic Example)

* Use `Configuration` and `FileSystem` classes.
* Upload file with `copyFromLocalFile`.
* Read file with `fs.open` and `readUTF`.
* Always close the FileSystem after operations.

---

## 4. Data Flow in Hadoop

---

### 4.1 Data Ingest Tools

| Tool  | Purpose                      | Example                        |
| ----- | ---------------------------- | ------------------------------ |
| Flume | Collect streaming logs       | Ingesting server logs (tweets) |
| Sqoop | Import SQL DB data into HDFS | Migrating MySQL tables         |

---

### 4.2 Hadoop Archives (HAR)

* Problem: Too many small files hurt HDFS performance.
* Solution: Bundle small files into a HAR file (like `.zip` for HDFS).

**CLI Example:**
`hadoop archive -archiveName data.har -p /input /output`

---

**5. Hadoop I/O: Compression, Serialization, Avro**

* Compression Formats:

  * Gzip: Medium speed, High compression, Archival use
  * Snappy: Fast speed, Low compression, Real-time processing

* Enable Compression CLI Example:
  `hadoop jar job.jar -Dmapreduce.output.fileoutputformat.compress=true -Dmapreduce.output.fileoutputformat.compress.codec=org.apache.hadoop.io.compress.SnappyCodec`

* Serialization Formats:

  * Avro: Schema-based, Row-oriented, Good for logging
  * Parquet: Schema-based, Columnar, Good for analytics

---

**6. Setting Up a Hadoop Cluster**

* Cluster Specs:

  * NameNode: 16+ GB RAM, SSD recommended
  * DataNode: 8+ GB RAM, HDD for storage
  * Replication Factor: 3 (default)

* Installation Steps:

  * Install Java & SSH: `sudo apt install openjdk-8-jdk ssh`
  * Download Hadoop: `wget https://archive.apache.org/dist/hadoop/core/hadoop-3.3.1/hadoop-3.3.1.tar.gz`
  * Configure `core-site.xml`:

    ```xml
    <property>
      <name>fs.defaultFS</name>
      <value>hdfs://namenode:9000</value>
    </property>
    ```
  * Format & start HDFS:
    `hdfs namenode -format`
    `start-dfs.sh`

---

### 7. Hadoop Security & Monitoring

#### 7.1 Security in Hadoop

* **Kerberos Authentication:** Like a secure VIP pass system preventing strangers from entering the Hadoop party. Ensures only authorized users access data.
* **HDFS Permissions:** Unix-style file permissions (rwx for user/group/others) controlling who can read/write/execute files — like house keys for different family members and guests.

#### 7.2 Monitoring Tools

* **HDFS Web UI:** Browser dashboard (e.g., `http://namenode:9870`) to check cluster health and file status — like your car’s dashboard showing speed, fuel, and engine stats.
* **Ganglia:** Specialized tool to monitor cluster performance metrics (CPU, memory, network) — like a fitness tracker for your Hadoop nodes.

---

### 8. Hadoop in the Cloud (AWS EMR, GCP Dataproc)

* **Why Cloud?** No need to buy or manage hardware; auto-scaling adapts to workload like a self-growing plant.
* **AWS EMR Example:** Spin up a Hadoop cluster in 5 minutes, pay only for what you use — like renting a car for exactly the trip length you need.
* Cloud services handle setup, maintenance, and scaling, letting you focus on data processing.

---

### Exam Cheat Sheet

**If Asked “Explain HDFS”:**

* Design: Files split into blocks, replicated across DataNodes; NameNode manages metadata.
* Data Flow: Client asks NameNode for block locations → reads/writes directly with DataNodes.
* Common CLI commands: `hdfs dfs -ls`, `hdfs dfs -put`, `hdfs dfs -cat`.

**If Asked “Hadoop Cluster Setup”:**

* Hardware: NameNode uses SSD + high RAM; DataNodes use HDDs.
* Configuration: Edit `core-site.xml` and `hdfs-site.xml`.
* Security: Enabled via Kerberos and Unix-like permissions.

---
