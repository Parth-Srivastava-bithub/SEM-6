
# 1. Hadoop Ecosystem & YARN — Detailed Notes for You

---

### 1.1 Hadoop Ecosystem Components

**Hadoop = More than just HDFS + MapReduce.**
It’s a whole toolkit for Big Data stuff, each part with a specific job, like a squad of superheroes.

| Tool          | What It Does                                        | Real-Life Example                                 |
| ------------- | --------------------------------------------------- | ------------------------------------------------- |
| **HBase**     | NoSQL database, fast reads/writes                   | WhatsApp storing millions of messages instantly   |
| **Hive**      | SQL-like queries for analysts                       | Creating sales reports easily                     |
| **Pig**       | Script language for ETL (cleaning & moving data)    | Cleaning messy log files before analysis          |
| **Sqoop**     | Transfers data from traditional SQL DBs into Hadoop | Moving CRM customer data into Hadoop              |
| **Flume**     | Streams live data into Hadoop                       | Tracking live website clicks & social media feeds |
| **Oozie**     | Job scheduler, like cron for Hadoop                 | Running your daily batch jobs at night            |
| **ZooKeeper** | Coordinates cluster, keeps it stable                | Making sure NameNode failover happens smoothly    |

**Why it matters?**
Each tool handles a different puzzle piece in Big Data. Hive = SQL comfort, Pig = ETL magic, Sqoop = bridge to old SQL systems, etc.

---

### 1.2 What is YARN? (Yet Another Resource Negotiator)

**Think of YARN as Hadoop’s brain for managing resources** — CPU, memory, and more — like a smart office manager distributing tasks perfectly.

**YARN components:**

* **ResourceManager (RM):** The HR guy. Decides who gets which resource across the whole cluster.
* **NodeManager (NM):** Team leads. They manage resources on each individual worker machine.
* **ApplicationMaster (AM):** Project managers. Each job (like MapReduce or Spark) has one, negotiating resources with RM.

**How YARN works:**

1. You (client) send a job (e.g., Spark job).
2. RM assigns an AM to manage your job.
3. AM asks RM for containers (CPU + RAM units).
4. NM launches tasks inside those containers on nodes.

**Metaphor:**
YARN = Office manager

* RM = HR assigning projects
* NM = Team leads managing workers
* AM = Project manager handling a single project

---

### 1.3 Hadoop 2.0 New Features

**Why Hadoop 2.0 is better?**

| Feature                             | Problem in Hadoop 1                              | Hadoop 2 Solution & Example                                                                                |
| ----------------------------------- | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| **NameNode High Availability (HA)** | Single NameNode = SPOF (Single Point of Failure) | Now Active-Standby NameNodes with ZooKeeper failover. If active crashes, standby kicks in instantly.       |
| **HDFS Federation**                 | Only one namespace limits scale                  | Multiple NameNodes manage different directories. E.g., NameNode1 → `/sales` data, NameNode2 → `/logs` data |
| **MRv1 vs MRv2 (YARN)**             | MRv1 limited scalability & only MapReduce        | MRv2 supports 10K+ nodes & other frameworks like Spark, Tez                                                |

**Quick example:**
If your original Hadoop cluster was a small shop (one boss, one register), Hadoop 2.0 made it a supermarket with many counters and managers, so no bottlenecks or crashes kill the shop.

---

### Bonus: Running MRv1 on YARN

To run old MapReduce jobs on new YARN clusters:

```bash
mapred --config /etc/hadoop-conf yarn jar old-mr-job.jar
```

---

# 2. NoSQL Databases — Easy & Detailed Notes

---

### 2.1 What is NoSQL?

**NoSQL = Not just “No SQL,” but “Not Only SQL.”**
These are databases designed for unstructured or semi-structured data, unlike traditional SQL DBs.

---

### Why do we need NoSQL?

* **Scale:** SQL can choke on millions of writes per second. NoSQL handles huge data streams easily.
* **Flexibility:** No rigid tables or fixed schemas. You can store varied and evolving data formats without stress.

---

### Types of NoSQL Databases & When to Use Them

| Type          | Best Use Case                                          | Popular Examples |
| ------------- | ------------------------------------------------------ | ---------------- |
| **Document**  | Stores JSON-like data (complex, nested)                | MongoDB, CouchDB |
| **Key-Value** | Simple, super-fast lookups                             | Redis, DynamoDB  |
| **Columnar**  | Big data analytics (billions of rows)                  | Cassandra, HBase |
| **Graph**     | Data with complex relationships (like social networks) | Neo4j            |

---

### Quick real-life examples:

* **Document:** Storing user profiles with varying info in MongoDB.
* **Key-Value:** Redis caching session data for super quick access.
* **Columnar:** Cassandra powering analytics for huge e-commerce logs.
* **Graph:** Neo4j mapping friends & connections on Facebook.

---

NoSQL = When you want speed, scale, and flexibility beyond rigid tables.

---


# 3. MongoDB (Document NoSQL Database) — Detailed Notes


### 3.1 MongoDB Basics

* **Data Format:** Uses BSON (Binary JSON) — basically JSON but optimized for speed and size.

* **Example Document:**

```json
{
  "_id": 1,
  "name": "Alice",
  "age": 25,
  "hobbies": ["coding", "hiking"]
}
```

Think of this as a flexible JSON profile for Alice.

---

### 3.2 CRUD Operations (Create, Read, Update, Delete)

| Operation | Command Example                                     | What it does             |
| --------- | --------------------------------------------------- | ------------------------ |
| Insert    | `db.users.insert({name: "Bob", age: 30})`           | Add a new user Bob       |
| Update    | `db.users.update({name: "Bob"}, {$set: {age: 31}})` | Change Bob’s age to 31   |
| Delete    | `db.users.remove({name: "Bob"})`                    | Remove Bob from users    |
| Query     | `db.users.find({age: {$gt: 25}})`                   | Find users older than 25 |

---

### 3.3 Indexing in MongoDB

* Purpose: Like an index in a book, it speeds up searches.
* Example:

```js
db.users.createIndex({age: 1})  // 1 means ascending order
```

* Types of indexes:

  * Single-field (on one key)
  * Compound (on multiple keys)
  * Text (for searching text)
  * Geospatial (for location data)

---

### 3.4 Capped Collections

* Fixed-size collections — once full, old data gets overwritten automatically.
* Use case: Perfect for logs or streaming data.
* Example:

```js
db.createCollection("logs", {capped: true, size: 1000000})
```

This creates a "logs" collection capped at about 1MB.

---

MongoDB is like your flexible, JSON-based friend who’s great with semi-structured data and fast queries.

---

# 4. Apache Spark — Clear & Detailed Notes

---

### 4.1 Installing Spark

Run these commands in terminal:

```bash
wget https://archive.apache.org/dist/spark/spark-3.2.1/spark-3.2.1-bin-hadoop3.2.tgz
tar -xvf spark-3.2.1-bin-hadoop3.2.tgz
./bin/spark-shell
```

This downloads, extracts, and launches Spark’s interactive shell.

---

### 4.2 Spark Concepts: Applications, Jobs, Stages & Tasks

| Term            | Meaning                                      |
| --------------- | -------------------------------------------- |
| **Application** | A whole Spark program (like a script).       |
| **Job**         | Triggered by an action (e.g., `count()`).    |
| **Stage**       | A group of tasks, divided by shuffle points. |
| **Task**        | Smallest work unit, runs on one CPU core.    |

**Example:**

```scala
val data = sc.textFile("hdfs://data.txt")
val words = data.flatMap(_.split(" "))
val counts = words.count()  // This triggers a Job
```

Here, reading file → splitting words → counting words = stages and tasks under the hood.

---

### 4.3 Resilient Distributed Datasets (RDDs)

* **What?** Immutable, partitioned data spread across the cluster.
* **Key Features:**

  * **Lineage:** Tracks transformations so if something fails, it can recompute lost data from the start.
  * **Lazy Evaluation:** Doesn’t run until an action like `count()` or `collect()` is called.

---

### 4.4 Running Spark on YARN (Hadoop’s resource manager)

* **Cluster Mode:** Spark runs fully on cluster nodes, no client needed after submit.

```bash
spark-submit --master yarn --deploy-mode cluster app.jar
```

* **Client Mode:** Driver runs on your machine, workers run on cluster.

```bash
spark-submit --master yarn --deploy-mode client app.jar
```

---

Spark is like your high-speed data engine, breaking big jobs into small tasks and running them in parallel. 

**Scala** is a programming language that runs on the Java Virtual Machine (JVM). It combines **Object-Oriented Programming (OOP)** and **Functional Programming** in one language. Spark’s native language is Scala because it’s super fast on JVM and handles big data well.

In short:

* Think of Scala as Java + superpowers for functional style.
* Spark is built on Scala, so knowing it helps you write efficient Spark apps.

---

# 5. Scala (Spark’s Native Language)

### 5.1 Intro to Scala

* Runs on JVM, combines OOP + functional styles.
* Why Scala for Spark? Native JVM support = faster than Python.

---

### 5.2 Basic Syntax

* Variables:

  ```scala
  val immutable = 10  // can't change
  var mutable = 20    // can change
  ```
* Functions:

  ```scala
  def square(x: Int): Int = x * x
  ```
* Control flow:

  ```scala
  if (x > 10) println("Big") else println("Small")
  ```

---

### 5.3 Classes & Objects

```scala
class Person(name: String, age: Int) {
  def greet(): Unit = println(s"Hello, $name!")
}

val alice = new Person("Alice", 25)
alice.greet()
```

---

# Exam Cheat Sheet — Rapid Fire

| Question         | Answer                                                                                           |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| YARN vs MRv1     | YARN: manages resources separately, supports Spark, Tez.<br>MRv1: only MapReduce, less scalable. |
| MongoDB Indexing | Speeds queries.<br>Types: single-field, compound, text.                                          |
| Spark RDDs       | Immutable, fault-tolerant (lineage).<br>Lazy evaluation (run on action).                         |
| Scala Basics     | `val` immutable, `var` mutable.<br>Function example: `def square(x: Int): Int = x * x`.          |

---

