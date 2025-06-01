## **1. HDFS (Hadoop Distributed File System) – Overview**

HDFS Hadoop ka ek distributed file system hai, jo large data ko store karne ke liye design kiya gaya hai — wo bhi multiple machines (nodes) par distribute karke. Ye mainly **big data** environments ke liye banaya gaya hai.

---

## **2. Design of HDFS**

* **Designed for Big Data:** HDFS ka design aise kiya gaya hai ki ye huge amount of data ko efficiently store aur process kar sake.
* **Write Once, Read Many:** Ek baar data likhne ke baad usse baar-baar read kiya jaata hai, isliye ye design aise hai ki writing time pe zyada optimization na ho, lekin reading bahut fast ho.
* **Distributed Architecture:** Data ko chhote-chhote blocks mein tod ke alag-alag nodes (machines) pe store kiya jaata hai.

---

## **3. HDFS Concepts**

* **Namenode:** Ye master node hota hai jo metadata handle karta hai (e.g., file ka naam, block location, permissions).
* **Datanode:** Ye actual data ko store karta hai blocks ke form mein.
* **Block:** HDFS data ko blocks mein todta hai (default size: 128 MB or 256 MB).
* **Replication:** Har block ka multiple copy banaya jaata hai (default: 3 copies) for fault tolerance.

---

## **4. Benefits of HDFS**

* **Fault Tolerant:** Agar ek node fail ho jaye, toh data dusre replicated block se mil jaata hai.
* **Scalable:** Easily new machines add kar ke storage badha sakte ho.
* **Cost-effective:** Commodity hardware (sasti machines) pe kaam karta hai.

---

## **5. Challenges of HDFS**

* **Latency:** Real-time systems ke liye suitable nahi hai.
* **Small Files:** Bahut zyada chhoti files handle karna inefficient hota hai.
* **Security:** Basic level pe security hoti hai, strong configurations chahiye.

---

## **6. File Sizes & Block Sizes in HDFS**

* **Large Files:** HDFS large files ke liye optimized hai.
* **Block Size:** Default block size 128MB or 256MB hoti hai (much bigger than traditional OS block sizes like 4KB).
* **Block Abstraction:** User ko pata bhi nahi chalta ki file kaunse blocks mein hai, HDFS handle karta hai.

---

## **7. Data Replication**

* Har block ki multiple copies (replicas) banayi jaati hain.
* **Default replication factor** = 3.
* Agar ek Datanode down ho jaye, toh data safe rehta hai kyunki dusri nodes pe bhi copy hoti hai.

---

## **8. HDFS File Operations**

### **Store (Write)**

* Client request karta hai file likhne ka.
* Namenode decide karta hai blocks kaha store honge.
* Data Datanodes pe jaata hai, replicated blocks ke saath.

### **Read**

* Client namenode se metadata leta hai.
* Namenode batata hai file ke blocks kis-kis datanode pe hain.
* Client directly datanode se data read karta hai.

---

## **9. Java Interfaces to HDFS**

* Java APIs provide ki jaati hain jo developers ko HDFS se interact karne deti hain.
* Jaise file read/write karna, file list karna, permissions set karna, etc.

---

## **10. Command Line Interface (CLI)**

* Hadoop ke saath kuch basic commands milte hain:

  * `hadoop fs -ls /`
  * `hadoop fs -put localfile /hdfs/path`
  * `hadoop fs -get /hdfs/path localfile`
* CLI se hum HDFS ko UNIX jaise command style mein access kar sakte hain.

---

## **11. Hadoop File System Interfaces**

* **FSDataInputStream & FSDataOutputStream:** Java-based input/output stream handling.
* **FileSystem Class:** Abstract layer hai jo local, HDFS ya other file systems ke sath work karta hai.

---

## **12. Data Flow in Hadoop**

* Data flow ka matlab hai ki data system mein kaise enter karta hai (ingestion), process hota hai, aur output generate hota hai.
* Ek simple flow:

  1. Ingest with tools like Flume or Sqoop.
  2. Store in HDFS.
  3. Process with MapReduce/Spark.
  4. Output store or visualize.

---

## **13. Data Ingest: Flume & Sqoop**

* **Flume:** Logs & real-time data streaming ke liye use hota hai (e.g., from servers to HDFS).
* **Sqoop:** RDBMS (MySQL, Oracle, etc.) se data import/export ke liye use hota hai.

---

## **14. Hadoop Archives (HAR files)**

* HAR files ka use chhoti files ko bundle karke ek large logical archive banane ke liye hota hai.
* Ye performance improve karta hai jab chhoti files bahut zyada ho.

---

## **15. Hadoop I/O:**

### **Compression:**

* Data compress karna space save karne ke liye.
* Common formats: Gzip, Snappy.

### **Serialization:**

* Data ko byte stream mein convert karna taaki transmission aur storage easy ho.
* Java mein `Writable` interface hota hai for custom serialization.

### **Avro:**

* Apache Avro ek data serialization system hai.
* Self-describing format hota hai (schema ke saath data store hota hai).

### **File-based Data Structures:**

* SequenceFile, AvroFile, Parquet, ORC: structured storage ke liye use hote hain.

---

## **16. Hadoop Environment Setup**

### **Cluster Specification:**

* Master-Slave architecture.
* Master node: NameNode, ResourceManager.
* Slave nodes: DataNode, NodeManager.

### **Cluster Setup & Installation:**

* Java + Hadoop install karna padta hai har node pe.
* SSH setup hota hai for passwordless access.
* Configuration files edit karni hoti hain: `core-site.xml`, `hdfs-site.xml`, `mapred-site.xml`, `yarn-site.xml`.

---

## **17. Hadoop Configuration**

* Configuration XML files mein hoti hai.
* Important parameters: replication factor, block size, memory limits, etc.

---

## **18. Security in Hadoop**

* Basic authentication: Simple & Kerberos based.
* Authorization: Access control lists (ACLs), file permissions.
* Encryption: At rest & in-transit encryption supported.

---

## **19. Administering Hadoop**

* Monitor logs, manage services, handle disk space, backup and recovery, add/remove nodes.

---

## **20. HDFS Monitoring & Maintenance**

* Tools: Ambari, Cloudera Manager, Nagios.
* Monitor: Node status, disk usage, replication factor, corrupted blocks.
* Maintenance: Balancing blocks, decommissioning nodes.

---

## **21. Hadoop Benchmarks**

* Benchmarks performance measure karne ke liye:

  * **TestDFSIO** – I/O performance.
  * **TeraSort** – Sorting performance.
  * **NNBench** – Namenode performance.

---

## **22. Hadoop in the Cloud**

* Cloud providers (AWS, Azure, GCP) Hadoop clusters offer karte hain.
* Benefits:

  * Elasticity: Need ke hisaab se scale up/down.
  * No hardware management.
  * Pay-as-you-go model.

---
