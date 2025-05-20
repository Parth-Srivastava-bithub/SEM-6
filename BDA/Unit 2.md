## 🐘 **1. Hadoop: The Big Data Giant**

### 📜 **1.1 History of Hadoop**

* **Who?** Doug Cutting (2005), named after his son’s toy elephant.
* **Why?** Needed something to handle web-scale search data.
* **Inspired by:** Google’s **MapReduce** + **GFS** papers.

💥 **Example:** Yahoo! used it to index **billions** of web pages—traditional SQL failed beyond a few TBs.

---

### 🛠️ **1.2 Apache Hadoop = 2 Superpowers**

1. **HDFS (Storage):** Breaks data into blocks, stores across machines.
2. **MapReduce (Processing):** Splits tasks, processes in parallel.

🧠 **Metaphor:** Like ants 🐜 carrying slices of a giant pizza 🍕 together—teamwork = speed.


---

## 🗂️ **2. Hadoop Distributed File System (HDFS)**

### 📦 **2.1 What is HDFS?**

A **fault-tolerant**, distributed storage system for Big Data.

✅ **Key Features:**

* Splits files into blocks (**128MB** default).
* Stores **3 copies** across different machines.
* Survives crashes—**no data loss**.

---

### 🧩 **2.2 How HDFS Works**

📝 **Upload:**

* 1GB file → split into **8 blocks**.
* 3 replicas each → saved on different machines.

🔎 **Read:**

* If **Machine A** fails → fetches from **B or C**.

📸 **Example:** Facebook stores **300PB+** photos in HDFS.

---

### 🧠 **2.3 Components of HDFS**

| Component        | Role                            | Metaphor                  |
| ---------------- | ------------------------------- | ------------------------- |
| **NameNode**     | Tracks block locations          | 📚 Librarian              |
| **DataNode**     | Stores actual data blocks       | 📦 Bookshelves            |
| **Secondary NN** | Helps recover NameNode metadata | 🧑‍💼 Assistant Librarian |


---

## 🔗 3. Hadoop Ecosystem (Key Tools & Their Roles)

| **Tool**  | **Purpose**                                                                 | **Detailed Use Case**                                                                                                                                    |
| --------- | --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **HBase** | Column-based NoSQL DB for real-time operations on large datasets.           | WhatsApp stores messages in HBase for quick read/write across billions of users. Ideal when you need random, real-time read/write access—not just batch. |
| **Hive**  | Data warehouse tool to run SQL-like queries on Hadoop using HiveQL.         | Analysts at Flipkart run `SELECT` queries over petabytes of sales data stored in HDFS to generate daily revenue reports.                                 |
| **Pig**   | High-level scripting language (Pig Latin) for writing data transformations. | Cleans messy logs at Netflix; devs write a 10-line Pig script instead of 200 lines of Java MapReduce.                                                    |
| **Sqoop** | Connects traditional RDBMS (MySQL, Oracle) with Hadoop.                     | Banks move structured data (like customer details) from Oracle DBs to HDFS for deep analytics.                                                           |
| **Flume** | Ingests massive volumes of log data into HDFS.                              | Used by e-commerce sites to stream web server logs, clickstreams, and user behavior in real-time.                                                        |
| **Oozie** | Workflow scheduler for coordinating Hadoop jobs.                            | A job that runs Pig → Hive → Email report can be scheduled to run every night using Oozie, just like cronjobs.                                           |

💡 *Think of this ecosystem like a production line—each tool has its job to make Big Data flow seamlessly.*

---

## 🧠 4. MapReduce: The Brain of Hadoop

### **4.1 What is MapReduce?**

* A **parallel processing model** designed to handle huge datasets.
* Breaks tasks into **two steps**:

  * **Map** → Break data into key-value pairs.
  * **Reduce** → Combine pairs with the same key.

**Metaphor:** Like organizing a classroom:

1. Every student (Mapper) counts words in a book → ("apple", 1)
2. Teacher (Reducer) sums counts from all students → ("apple", 25)

---

### **4.2 Step-by-Step Example: Word Count**

#### 🎯 Problem:

Count word occurrences from 1000 books.

---

**🔹 Step 1: Map Phase**

* Each Mapper reads a chunk (1 book).
* Emits key-value pairs: (`word`, 1)

Example Output:

```
Book 1: ("apple", 1), ("banana", 1)  
Book 2: ("apple", 1), ("cherry", 1)
```

---

**🔹 Step 2: Shuffle & Sort**

* All identical keys go to the same Reducer.

```
("apple", [1, 1])  
("banana", [1])  
("cherry", [1])
```

---

**🔹 Step 3: Reduce Phase**

* Reducer adds the values.

```
("apple", 2)  
("banana", 1)  
("cherry", 1)
```

---

**✅ Final Output:**

| Word   | Count |
| ------ | ----- |
| apple  | 2     |
| banana | 1     |
| cherry | 1     |

---

### **4.3 Real-World MapReduce Applications**

* **Google Search:**

  * Map = Crawl and tokenize web pages.
  * Reduce = Aggregate and rank pages by relevance.

* **Fraud Detection in Banks:**

  * Map = Analyze transactions across users.
  * Reduce = Flag accounts with unusual patterns.

* **Ad Click Prediction:**

  * Map = Collect click logs.
  * Reduce = Calculate CTR (click-through rate) per user group.

---


## ✅ 5. Developing a MapReduce Job (Step-by-Step)

### 🔹 5.1 Writing a MapReduce Program (Java Example)

```java
// Mapper Class
public class WordCountMapper extends Mapper<LongWritable, Text, Text, IntWritable> {
  public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
    String[] words = value.toString().split(" ");
    for (String word : words) {
      context.write(new Text(word), new IntWritable(1)); // ("apple", 1)
    }
  }
}

// Reducer Class
public class WordCountReducer extends Reducer<Text, IntWritable, Text, IntWritable> {
  public void reduce(Text key, Iterable<IntWritable> values, Context context) throws IOException, InterruptedException {
    int sum = 0;
    for (IntWritable val : values) {
      sum += val.get(); // Add all 1s
    }
    context.write(key, new IntWritable(sum)); // Final output: ("apple", 3)
  }
}
```

---

### 🔹 5.2 Running the Job

**Step 1: Upload input file to HDFS**

```bash
hdfs dfs -mkdir /data
hdfs dfs -put input.txt /data
```

**Step 2: Run the MapReduce Job**

```bash
hadoop jar wordcount.jar WordCount /data/input.txt /output
```

✅ Output will be in `/output/part-r-00000`

---

## 🛠 6. MapReduce Optimization & Failures

### 🔸 6.1 Handling Failures

* **Task Failure:** Retried automatically (default 3 times).
* **DataNode Failure:** HDFS uses replica blocks (default 3 replicas).
* **Job Tracker failure:** Handled via backup/HA setup.

---

### 🔸 6.2 Job Scheduling

| Scheduler          | Description                             | Use Case                        |
| ------------------ | --------------------------------------- | ------------------------------- |
| FIFO               | Default. Oldest job runs first.         | Simple setups                   |
| Fair Scheduler     | All jobs get equal cluster time         | Multi-user Hadoop clusters      |
| Capacity Scheduler | Allocate fixed resources per queue/user | Enterprise multi-tenant systems |

---

### 🔸 6.3 Shuffle & Sort Phase (⚠️ Bottleneck Area)

**What Happens:**

* Mapper output sent to Reducers based on key.
* Keys are sorted before Reduce.
* Heavy disk I/O + network traffic = bottleneck.

**Optimization:**

* Use **Combiner** to reduce local Mapper output before shuffle.

```java
public class WordCountCombiner extends Reducer<Text, IntWritable, Text, IntWritable> {
  public void reduce(Text key, Iterable<IntWritable> values, Context context) throws IOException, InterruptedException {
    int sum = 0;
    for (IntWritable val : values) {
      sum += val.get();
    }
    context.write(key, new IntWritable(sum)); // Partial reduce
  }
}
```

---


## ✅ 7. Hadoop Streaming & Pipes

### 🔹 7.1 Hadoop Streaming (For Non-Java Developers)

**Use Case:** Write MapReduce in Python, Bash, etc.

**Python Example:**

```python
# mapper.py
import sys
for line in sys.stdin:
    for word in line.strip().split():
        print(f"{word}\t1")
```

```python
# reducer.py
import sys
current_word = None
count = 0
for line in sys.stdin:
    word, val = line.strip().split("\t")
    if word == current_word:
        count += int(val)
    else:
        if current_word:
            print(f"{current_word}\t{count}")
        current_word = word
        count = 1
print(f"{current_word}\t{count}")
```

**Run Command:**

```bash
hadoop jar /path/to/hadoop-streaming.jar \
-input /data/input.txt \
-output /output \
-mapper mapper.py \
-reducer reducer.py
```

---

### 🔹 7.2 Hadoop Pipes (For C++ Developers)

* Interface for writing MapReduce programs in C++.
* Uses Protobuf for communication.
* Needs `hadoop pipes` and `hadoop c++` libraries.

---

## 🧠 Exam Cheat Sheet

**Q: What is Hadoop?**
→ Distributed storage (HDFS) + distributed processing (MapReduce)

**HDFS:**
→ Blocks, Replication, NameNode, DataNode

**MapReduce:**
→ Map → Shuffle & Sort → Reduce
→ Use Word Count Example

**Ecosystem Tools:**
→ Hive, Pig, HBase, Sqoop, Flume, Oozie

---

**Q: MapReduce Workflow?**
→ Input Splits (from HDFS)
→ Map Phase (local node processing)
→ Shuffle & Sort (data transfer + group by key)
→ Reduce Phase (aggregation/final output)

---
