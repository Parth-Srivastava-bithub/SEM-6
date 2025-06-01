## **🔷 PIG (Apache Pig)**

### 1. **Introduction to Pig**

* Pig ek **high-level platform** hai jo Hadoop ke upar chalta hai.
* Iska kaam hota hai **large datasets** ko process karna.
* Pig ka khud ka ek language hoti hai – **Pig Latin** – jo easy hai aur SQL jaise lagti hai.

### 2. **Execution Modes of Pig**

* Pig do tarike se run ho sakta hai:

  1. **Local Mode**: Jab aapke paas chhoti file ho aur aapke system par hi sab kuch chalana ho.
  2. **MapReduce Mode**: Jab large data Hadoop cluster par ho.

### 3. **Comparison of Pig with Databases**

* Databases mein hum SQL use karte hain, Pig mein **Pig Latin**.
* Databases mostly **structured data** ke liye use hote hain, Pig **semi-structured aur unstructured data** bhi handle kar sakta hai.
* SQL declarative hai (aap bataate ho kya karna hai), Pig procedural hai (aap bataate ho kaise karna hai).

### 4. **Grunt**

* Ye Pig ka **interactive shell** hota hai jahan aap commands likh ke test kar sakte ho.

### 5. **Pig Latin**

* Pig ki khud ki language hai, jo data ko process karne ke liye use hoti hai – filtering, joining, grouping etc.

### 6. **User Defined Functions (UDFs)**

* Agar Pig ke existing functions kaafi nahi hain, to aap khud ke functions bana sakte ho.
* Inhe bolte hain **UDFs**, Java, Python ya kisi aur language mein bana sakte ho.

### 7. **Data Processing Operators**

* Pig mein kuch built-in operators hote hain jaise:

  * `LOAD` – data load karna
  * `FILTER` – unwanted data hataana
  * `GROUP` – grouping karna
  * `FOREACH` – record wise operations
  * `JOIN` – data ko merge karna

---

## **🔷 Hive (Apache Hive)**

### 1. **Apache Hive architecture and installation**

* Hive ek data warehouse infrastructure hai jo Hadoop ke upar SQL jaise queries chalane ke liye banaya gaya hai.
* Isme data ko query karne ke liye **HiveQL** (SQL jaise language) use hoti hai.

### 2. **Hive Shell**

* Ye command line interface hai jahan user HiveQL commands likhta hai.

### 3. **Hive Services**

* Hive ke kuch main parts hote hain:

  * **Driver** – queries ko process karta hai.
  * **Compiler** – query ko MapReduce mein convert karta hai.
  * **Metastore** – tables ki info store karta hai.

### 4. **Hive Metastore**

* Ye database hota hai jisme Hive ke tables, schema aur partitioning info store hoti hai.

### 5. **Comparison with Traditional Databases**

* Traditional databases **real-time processing** ke liye hote hain, Hive **batch processing** ke liye.
* Hive mein **queries MapReduce mein convert hoti hain**, database mein directly execute hoti hain.

### 6. **HiveQL, Tables, Querying Data**

* HiveQL = SQL jaise syntax.
* Hive mein **managed aur external tables** hoti hain.
* Data ko query karne ke liye SELECT, WHERE, GROUP BY jaise commands use hoti hain.

### 7. **User Defined Functions (UDFs)**

* Jaise Pig mein, yahan bhi aap apne khud ke functions bana sakte ho.

### 8. **Sorting and Aggregating**

* HiveQL mein aap sorting (`ORDER BY`) aur aggregate functions (`SUM()`, `COUNT()`) use kar sakte ho.

### 9. **Map Reduce Scripts**

* Hive ke queries backend mein **MapReduce job** mein convert hoti hain, jo Hadoop par run hoti hain.

### 10. **Joins & Subqueries**

* Hive support karta hai **joins** (tables ko jodne ke liye) aur **subqueries** (queries ke andar queries).

---

## **🔷 HBase (Apache HBase)**

### 1. **HBase Concepts**

* HBase ek **NoSQL database** hai jo Hadoop ke upar chalta hai.
* Ye **column-oriented** hota hai (RDBMS ke row-oriented ke opposite).
* Huge amount of sparse data ko efficiently store karta hai.

### 2. **Clients**

* HBase ko access karne ke liye **Java APIs**, **Thrift**, **REST** etc. use kiya ja sakta hai.

### 3. **Example**

* E-commerce site ke user activity logs ya IoT sensor data ko HBase mein store kiya ja sakta hai.

### 4. **HBase vs RDBMS**

* RDBMS mein fixed schema hota hai, HBase mein flexible schema.
* RDBMS transactional systems ke liye better hai, HBase big data ke liye.

### 5. **Advanced Usage**

* Real-time read/write access to big data.
* Use cases: Facebook’s Messenger, Flipkart logs, etc.

### 6. **Schema Design**

* HBase mein table ke andar rows hoti hain, aur har row ke andar columns – jo groups mein divided hote hain (column families).

### 7. **Advanced Indexing**

* HBase indexing ke liye secondary tools ya manually indexing design ki jaati hai.

### 8. **Zookeeper**

* HBase Zookeeper ka use karta hai cluster ko manage karne ke liye.
* Ye coordination ka kaam karta hai – jaise leader election, configuration management, node monitoring.

### 9. **Applications with Zookeeper**

* Distributed apps jaise HBase, Kafka Zookeeper ko use karte hain cluster ke health ko monitor karne ke liye.

---

## 🔷 **IBM Big Data Strategy – Overview**

IBM ka focus hai **Big Data ko manage, analyze aur use karna** aise tools ke through jo **enterprise level pe kaam aayen** – yaani bade businesses ke liye reliable, scalable solutions dena.

IBM ka Big Data Strategy mainly 4 tools par based hai:

---

## ✅ 1. **IBM Infosphere**

### 🔹 Kya hai?

* **Infosphere ek data integration platform** hai.
* Ye alag-alag sources se data **collect, clean, transform aur deliver** karta hai.

### 🔹 Use kab karte hain?

* Jab aapke paas **multiple systems** se data aa raha ho – jaise databases, flat files, cloud etc.
* Aapko data ko **standard format** mein lana ho for analysis.

### 🔹 Kya karta hai?

* Data ko **quality check** karta hai.
* Data ko **transform** karta hai (jaise kisi column ka format change karna).
* Ye **ETL (Extract, Transform, Load)** tool ka kaam karta hai.

---

## ✅ 2. **IBM BigInsights**

### 🔹 Kya hai?

* IBM ka khud ka **Hadoop-based platform** hai.
* Ye Hadoop ke upar extra features add karta hai, jaise better UI, monitoring tools, aur analytics options.

### 🔹 Kyu use karein?

* Jab aapko Hadoop chahiye ho lekin aap **open source setup manage nahi karna chahte**.
* Business users ke liye easy interface chahiye hota hai Hadoop ke upar kaam karne ke liye.

### 🔹 Features:

* Built-in support for **text analytics**, **machine learning**, aur **data visualization**.
* Enterprise support aur **security** better hoti hai as compared to open-source Hadoop.

---

## ✅ 3. **IBM BigSheets**

### 🔹 Kya hai?

* Ek **Excel jaisa web-based tool** hai.
* Big Data ko analyse karne ke liye banaya gaya hai, especially for **non-technical users**.

### 🔹 Use kaise hota hai?

* Drag-and-drop interface hota hai jisme user **data explore, filter, group, visualize** kar sakta hai.
* Coding ki zarurat nahi padti – isliye **business analysts** bhi easily use kar sakte hain.

### 🔹 Best for:

* Jo log data se kaam karna chahte hain lekin **programming nahi jaante**.
* Visual reports aur dashboards banana for decision-making.

---

## ✅ 4. **IBM Big SQL**

### 🔹 Kya hai?

* Ek SQL engine hai jo Hadoop, Hive, HBase aur DB2 jese sources pe query run karne deta hai.

### 🔹 Main Benefit:

* **Ek hi SQL query** se aap multiple data sources access kar sakte ho – bina alag-alag tools ke.

### 🔹 Features:

* High performance – traditional Hive se fast.
* JDBC/ODBC support – easily tools jaise Tableau ya Excel ke saath connect hota hai.
* ACID support (transactions ke liye) – jo Hadoop mein rare hota hai.

---

## 🎯 IBM Big Data Strategy ka Goal:

* **Enterprise-level tools dena** jo scalable, secure aur easy-to-use ho.
* **Data scientists, business analysts aur developers** – sab ke liye alag tools, but ek shared platform.
* **Structured + Unstructured** data ko process karna – analytics, reporting aur machine learning ke liye.

---

### 🔚 Final Summary:

| Tool            | Use                                   |
| --------------- | ------------------------------------- |
| **Infosphere**  | Data collect & transform (ETL)        |
| **BigInsights** | Hadoop with enterprise features       |
| **BigSheets**   | Excel-type tool for Big Data analysis |
| **Big SQL**     | SQL queries across Hadoop & databases |

---



