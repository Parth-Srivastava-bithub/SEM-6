## 🔷 **Hadoop Ecosystem and YARN**

### 1. **Hadoop Ecosystem Components**

* Hadoop sirf ek software nahi hai, balki **ek poora ecosystem** hai jisme kaafi tools kaam karte hain together:

  * **HDFS (Hadoop Distributed File System)** – data ko store karta hai.
  * **MapReduce** – data ko process karta hai.
  * **YARN (Yet Another Resource Negotiator)** – resources manage karta hai.
  * Tools jaise Pig, Hive, HBase, Sqoop, Flume, Oozie, Zookeeper etc. bhi part hain.

### 2. **Schedulers in YARN**

* YARN system mein kaunse job ko pehle chalana hai, kitne resources dene hain – ye decide karne ke liye **Schedulers** use hote hain.

#### Types:

* **FIFO Scheduler**: Pehle aayi job pehle chalegi.
* **Fair Scheduler**: Har user ko equal chance milta hai – har job ko thoda-thoda resource diya jata hai.
* **Capacity Scheduler**: Large clusters mein different users/groups ko **fixed capacity** di ja sakti hai.

### 3. **Hadoop 2.0 New Features**

* Hadoop 2.0 mein kaafi **major improvements** aaye:

#### 🔹 **NameNode High Availability**

* Pehle agar NameNode down hota tha, pura system ruk jata tha.
* Ab **2 NameNodes** ho sakte hain (ek active, ek standby) – system crash hone ke chances kam.

#### 🔹 **HDFS Federation**

* Ek se zyada NameNodes ka support – jisse data **scale** karna easy hota hai.

#### 🔹 **MRv2 (MapReduce Version 2)**

* Pehle MapReduce system tight-coupled tha. MRv2 mein ye **YARN** ke upar run hota hai, jisse flexibility milti hai.

#### 🔹 **YARN**

* Ye Hadoop ka **Resource Manager** hai.
* Jobs ke liye **CPU, memory, scheduling** ka kaam karta hai.
* Different types of applications (not just MapReduce) ko bhi handle karta hai – jaise Spark, Tez etc.

#### 🔹 **Running MRv1 in YARN**

* Hadoop 2.0 mein bhi aap **MapReduce v1 applications** ko YARN pe run kara sakte ho via compatibility mode.

---

## 🔷 **NoSQL Databases – Introduction**

### 🔹 Kya hota hai?

* **NoSQL** ka matlab hai **Not Only SQL** – yaani traditional relational databases ke alawa naye tarah ke databases.
* Ye **big data, unstructured data** ke liye banaye gaye hain.
* Mostly **schema-less** hote hain (structure flexible hota hai).
* Types:

  * **Document-based** (MongoDB)
  * **Key-Value Store**
  * **Column-oriented** (jaise HBase)
  * **Graph-based**

---

## 🔷 **MongoDB (NoSQL Database)**

### 1. **Introduction**

* MongoDB ek **document-based NoSQL database** hai.
* Isme data **JSON-like documents** (BSON) mein store hota hai.

### 2. **Data Types**

* MongoDB support karta hai: String, Number, Date, Boolean, Array, Object etc.

### 3. **Creating, Updating, Deleting Documents**

* Aap documents ko create, modify (update) aur delete kar sakte ho easily – just like records in RDBMS, but more flexible.

### 4. **Querying**

* MongoDB mein aap queries run kar sakte ho jaise:

  * Find a document
  * Find based on condition (like greater than, equals etc.)

### 5. **Indexing**

* Index lagane se **queries fast** chalti hain.
* MongoDB support karta hai **single, compound, text, geospatial** indexing.

### 6. **Capped Collections**

* Ye fixed-size collections hote hain.
* Jaise hi limit exceed hoti hai, **oldest document delete** ho jaata hai.
* Real-time logging ke liye useful.

---

## 🔷 **Apache Spark**

### 1. **Installing Spark**

* Spark ko aap **standalone**, Hadoop ke saath (YARN pe), ya cloud par install kar sakte ho.

### 2. **Spark Applications, Jobs, Stages, Tasks**

* Spark program = **Application**
* Ek Application multiple **Jobs** mein divide hoti hai.
* Har Job multiple **Stages** mein hoti hai.
* Stage mein multiple **Tasks** hote hain – actual execution units.

### 3. **RDD (Resilient Distributed Dataset)**

* Spark ka core data structure – **fault-tolerant, distributed memory object**.
* RDD allows parallel processing of data in-memory (fast).

### 4. **Anatomy of Spark Job Run**

* Steps:

  1. Code submit hota hai.
  2. Spark Job banta hai.
  3. Divide into Stages.
  4. Tasks create hote hain.
  5. Scheduler decide karta hai kahan kaunsa Task run kare.

### 5. **Spark on YARN**

* Spark ko aap YARN resource manager ke upar bhi run kara sakte ho.
* Isse Spark Hadoop ke ecosystem ke andar ache se integrate ho jata hai.

---

## 🔷 **Scala (Language for Spark)**

### 1. **Introduction**

* Scala ek modern programming language hai – **Java + Functional programming** ka combo.
* Spark ka core Scala mein likha gaya hai, isliye Spark ke saath Scala preferred language hai.

### 2. **Classes and Objects**

* Scala mein sab kuch **object-oriented** hota hai.
* Class = template, Object = real instance.

### 3. **Basic Types and Operators**

* Basic types: Int, String, Boolean etc.
* Operators: +, -, \*, == etc. – Java jaise hi.

### 4. **Built-in Control Structures**

* `if`, `while`, `for`, `match` – Java ke jaise control structures.

### 5. **Functions and Closures**

* Scala mein functions ko **first-class citizen** mana jata hai – aap functions ko variable ki tarah use kar sakte ho.
* Closures = functions jo outer variables access kar sakti hain.

### 6. **Inheritance**

* Scala mein classes inherit kar sakti hain other classes ya traits se.
* `extends` keyword se inheritance hota hai.

---

## 🔚 Final Summary Table:

| Topic                | Summary                                                     |
| -------------------- | ----------------------------------------------------------- |
| **Hadoop Ecosystem** | HDFS, MapReduce, YARN, Hive, Pig, HBase etc.                |
| **YARN**             | Resource manager for Hadoop; runs MRv2 & Spark              |
| **NoSQL**            | Flexible, schema-less databases like MongoDB                |
| **MongoDB**          | Document-based NoSQL database with indexing, flexible data  |
| **Spark**            | Fast big data engine using in-memory processing             |
| **Scala**            | Language used in Spark with object + functional programming |

---

