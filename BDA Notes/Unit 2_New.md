## 🔷 **Hadoop kya hai?**

Hadoop ek **open-source framework** hai jo **large data** ko process karne ke liye use hota hai. Ye **data ko store** bhi karta hai aur **analyze** bhi.

### 🔹 History of Hadoop:

* Iska idea **Google ke paper "MapReduce"** se aaya.
* **Doug Cutting** ne isko banaya, aur isne apne bete ke toy elephant ka naam "Hadoop" isko diya.
* Pehle **Yahoo** ne isko adopt kiya, phir **Apache Software Foundation** ke under isko launch kiya gaya.

---

## 🔷 **Apache Hadoop:**

Apache Hadoop ek **platform** hai jisme kai components milke kaam karte hain:

1. **HDFS (Hadoop Distributed File System)** – Data store karta hai.
2. **MapReduce** – Data process karta hai.
3. **YARN (Yet Another Resource Negotiator)** – Resource manage karta hai.
4. **Common Utilities** – Baki tools ke liye support provide karta hai.

---

## 🔷 **HDFS (Hadoop Distributed File System):**

Samjho tumhare paas 1 TB ka file hai. Isse ek normal system me rakhna mushkil hai.

### Example:

Agar tumhare paas 10 computers ka cluster hai, toh HDFS is 1 TB file ko **blocks** me todta hai (jaise 128 MB ke parts) aur sabhi computers pe **distributed** way me save kar deta hai.

* Har block ka **replica (copy)** 3 jagah rakha jaata hai for safety.
* Agar ek system fail ho jaaye, toh data lost nahi hota.

---

## 🔷 **Components of Hadoop:**

1. **HDFS** – Storage ke liye
2. **MapReduce** – Processing ke liye
3. **YARN** – Job scheduling aur resource allocation
4. **Hadoop Common** – Jaruri libraries aur files

---

## 🔷 **Data Format in Hadoop:**

Hadoop mostly use karta hai:

* **Text files**
* **Sequence files**
* **Avro, Parquet** (for structured data)
* Binary formats (efficient data processing ke liye)

---

## 🔷 **Analyzing Data with Hadoop:**

Tum petabytes (1 PB = 1000 TB) ka data analyze kar sakte ho MapReduce jobs ke through.

### Example:

Tumhare paas Flipkart ka data hai — kaunse product sabse zyada bik rahe hain? Kis time pe sale zyada hoti hai? MapReduce se ye sab analyze kiya ja sakta hai.

---

## 🔷 **Scaling Out (Horizontal Scaling):**

Jab data badh jaaye, toh tumhe naye computers (nodes) add karne padte hain cluster me. Isse **horizontal scaling** kehte hain.

* Hadoop easily scale ho jaata hai by adding new machines.

---

## 🔷 **Hadoop Streaming:**

Yeh allow karta hai tumhe **Python, Perl, Bash scripts** se MapReduce likhne ki ability, bina Java ke.

---

## 🔷 **Hadoop Pipes:**

Agar tum C++ me programming karna chahte ho Hadoop ke saath, toh **Pipes** use karte ho.

---

## 🔷 **Hadoop Ecosystem:**

Ye tools Hadoop ke aas-paas kaam karte hain:

| Tool      | Kaam                          |
| --------- | ----------------------------- |
| Hive      | SQL-like queries for big data |
| Pig       | Data flow language            |
| HBase     | NoSQL database                |
| Sqoop     | RDBMS ↔ Hadoop                |
| Flume     | Streaming data ingestion      |
| Oozie     | Job scheduling                |
| Zookeeper | Coordination service          |
| Mahout    | Machine Learning              |
| Spark     | Fast in-memory processing     |

---

## 🔷 **MapReduce:**

MapReduce ek **programming model** hai jo data ko **map** karta hai (sort & filter) aur phir **reduce** karta hai (aggregate or summarize).

---

### 🔹 How MapReduce Works (Simple Example):

**Problem:** Tumhare paas 1 lakh logon ke shopping invoices hain. Tumhe dekhna hai ki **kis product ka kitna sale hua**.

#### Step 1: Map

Har invoice ka ek item lo aur uska count 1 karo.

```text
Map Output:
Shoes → 1
Shirt → 1
Shoes → 1
Shoes → 1
Shirt → 1
```

#### Step 2: Shuffle and Sort

Same keys (products) ek jagah group ho jaate hain.

```text
Grouped:
Shoes → [1, 1, 1]
Shirt → [1, 1]
```

#### Step 3: Reduce

Group ki values ko add karo.

```text
Reduce Output:
Shoes → 3
Shirt → 2
```

---

## 🔷 **MapReduce Job Run (Anatomy):**

1. **Client** job submit karta hai.
2. **YARN** job ko allocate karta hai.
3. **Map tasks** start hote hain → intermediate data banta hai.
4. **Reduce tasks** run hote hain → final result aata hai.

---

## 🔷 **Failures in MapReduce:**

* Agar koi task fail ho jaata hai, toh Hadoop us task ko **automatically retry** karta hai kisi aur node pe.

---

## 🔷 **Job Scheduling:**

YARN decide karta hai kis node pe kaun sa task chalega based on availability.

---

## 🔷 **Shuffle and Sort:**

Map ke baad jo output aata hai, usko **sort** aur **group** karke reducers tak bhejna — is process ko shuffle & sort kehte hain.

---

## 🔷 **MapReduce Types:**

1. **Mapper only**
2. **Reducer only**
3. **Mapper + Reducer**
4. **Combiner** (Mini reducer jo mapper ke baad run karta hai)

---

## 🔷 **Input/Output Formats:**

* **Input:** TextInputFormat, KeyValueTextInputFormat
* **Output:** TextOutputFormat, SequenceOutputFormat

---

## 🔷 **Real-world Use Cases of MapReduce:**

1. **Web indexing** – Google style
2. **Log analysis** – Server logs
3. **Retail analytics** – Top selling items
4. **Social media trends** – Hashtag analysis

---

