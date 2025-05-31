# **Ultra-Detailed Guide to Hadoop Ecosystem, NoSQL, Spark & Scala**

## **1. Hadoop Ecosystem & YARN (Deep Dive)**

### **1.1 Hadoop Ecosystem Components (Extended Definition)**

The Hadoop ecosystem is a collection of tools that extend Hadoop's core capabilities (HDFS + MapReduce) to address various big data challenges:

1. **HDFS (Hadoop Distributed File System)**
   - Distributed storage system designed to run on commodity hardware
   - Uses block storage (default 128MB blocks)
   - Implements replication (default 3x) for fault tolerance
   - Architecture: Single NameNode (manages metadata) + multiple DataNodes (store actual data)

2. **YARN (Yet Another Resource Negotiator)**
   - Cluster resource management system
   - Separates resource management from data processing
   - Components:
     - ResourceManager (global resource allocator)
     - NodeManager (per-machine agent)
     - ApplicationMaster (per-application manager)

3. **MapReduce**
   - Original Hadoop processing framework
   - Batch-oriented, disk-based processing model
   - Two-phase execution:
     - Map phase (processes input data)
     - Reduce phase (aggregates results)

4. **Hive**
   - Data warehouse infrastructure
   - Provides SQL-like interface (HiveQL)
   - Translates queries to MapReduce/Tez/Spark jobs
   - Includes metastore for schema management

5. **Pig**
   - High-level data flow language (Pig Latin)
   - Suitable for ETL (Extract, Transform, Load) pipelines
   - Compiles to MapReduce execution plans

6. **HBase**
   - Distributed, column-oriented NoSQL database
   - Built on top of HDFS
   - Provides real-time read/write access
   - Uses ZooKeeper for coordination

7. **ZooKeeper**
   - Distributed coordination service
   - Maintains configuration information
   - Provides distributed synchronization
   - Used for leader election, status tracking

### **1.2 YARN Schedulers (In-Depth Comparison)**

#### **Fair Scheduler**
- Design Goal: Equal resource allocation across applications
- Key Features:
  - Dynamically balances resources
  - Applications get minimum guaranteed shares
  - Excess capacity distributed equally
- Configuration:
  - Uses allocation files (fair-scheduler.xml)
  - Supports hierarchical queues
- Use Case: Multi-tenant environments where fairness is critical

#### **Capacity Scheduler**
- Design Goal: Predictable resource allocation
- Key Features:
  - Dedicated queues with guaranteed capacities
  - Elasticity (unused capacity can be allocated)
  - Supports hierarchical queues
- Configuration:
  - Uses capacity-scheduler.xml
  - Queue capacities specified as percentages
- Use Case: Organizations with multiple departments/teams

**Comparison Table:**

| Feature               | Fair Scheduler              | Capacity Scheduler         |
|-----------------------|-----------------------------|----------------------------|
| Allocation Principle  | Equal share                 | Guaranteed minimums        |
| Queue Organization    | Hierarchical                | Hierarchical               |
| Elasticity            | Dynamic rebalancing         | Within queue constraints   |
| Best For              | Ad-hoc workloads            | Production environments    |
| Configuration         | Allocation files            | XML configuration          |

### **1.3 Hadoop 2.0 New Features (Technical Details)**

#### **NameNode High Availability**
- Problem: Single NameNode = Single Point of Failure
- Solution:
  - Active/Standby NameNode configuration
  - Uses:
    - Shared storage (NFS/Quorum Journal Manager)
    - ZooKeeper for failover coordination
  - Failover process:
    1. Health monitoring detects failure
    2. ZooKeeper initiates failover
    3. Standby becomes active (typically <1 minute)

#### **HDFS Federation**
- Problem: Single namespace limitation
- Solution:
  - Multiple independent NameNodes
  - Each manages portion of namespace
  - Benefits:
    - Horizontal scalability
    - Isolation between namespaces
  - Block pools:
    - Each namespace has dedicated block pool
    - DataNodes store blocks from multiple pools

#### **MRv2 (YARN) Architecture**
- Fundamental changes from MRv1:
  - Separates resource management (YARN) from programming model (MapReduce)
  - Components:
    - ResourceManager (global)
    - ApplicationMaster (per-application)
    - NodeManager (per-node)
  - Benefits:
    - Better cluster utilization
    - Support for non-MapReduce frameworks

#### **Running MRv1 in YARN**
- Compatibility layer for legacy applications
- Uses MR AM (MapReduce ApplicationMaster)
- Translates MRv1 API calls to YARN requests
- Configuration:
  - Set mapreduce.framework.name=yarn
  - Requires MRv1 libraries on cluster

## **2. NoSQL Databases (Comprehensive Overview)**

### **2.1 Introduction to NoSQL**
- Definition: Non-relational databases designed for specific data models
- Characteristics:
  - Schema-less design
  - Horizontal scalability
  - Flexible data models
  - BASE properties (Basically Available, Soft state, Eventually consistent)

**CAP Theorem Implications:**
- Consistency, Availability, Partition Tolerance - can only guarantee 2/3
- NoSQL types by CAP focus:
  - CP: HBase, MongoDB (with strong consistency)
  - AP: Cassandra, CouchDB

**Data Model Classification:**
1. **Document Stores** (MongoDB, CouchDB)
   - Store semi-structured documents (JSON/BSON)
   - Nested data structures
   - Dynamic schemas

2. **Key-Value Stores** (Redis, DynamoDB)
   - Simple data model (key → value)
   - High performance
   - Limited query capabilities

3. **Column-Family Stores** (Cassandra, HBase)
   - Sparse, distributed multi-dimensional maps
   - Column-oriented storage
   - Good for time-series data

4. **Graph Databases** (Neo4j, JanusGraph)
   - Nodes, edges, properties
   - Efficient for relationship-heavy data
   - Complex queries about connections

**Use Case Analysis:**

| Database Type   | Best For                          | Not Good For               |
|-----------------|-----------------------------------|----------------------------|
| Document        | Content management, catalogs      | Complex transactions       |
| Key-Value       | Caching, session storage          | Complex queries            |
| Column-Family   | Time-series, event logging        | ACID transactions          |
| Graph           | Social networks, recommendations  | Tabular reporting          |

## **3. MongoDB (Technical Deep Dive)**

### **3.1 Core Concepts**
- **Document**: Basic unit (JSON-like BSON format)
- **Collection**: Group of documents (analogous to table)
- **Database**: Set of collections
- **BSON Types**:
  - String, Integer, Boolean
  - Date, Timestamp
  - ObjectId (primary key)
  - Binary data
  - Array, Embedded document

### **3.2 CRUD Operations (Detailed)**

#### **Creating Documents**
- `insertOne()`: Single document insertion
- `insertMany()`: Batch insertion
- Write concerns:
  - w:1 (default)
  - w:"majority"
  - j:true (journaled)

**Example:**
```javascript
db.products.insertOne({
  _id: ObjectId("507f191e810c19729de860ea"),
  name: "Laptop",
  price: 999.99,
  tags: ["electronics", "portable"],
  stock: { warehouse: "A", qty: 50 }
})
```

#### **Updating Documents**
- Update operators:
  - `$set`: Set field value
  - `$unset`: Remove field
  - `$inc`: Increment numeric value
  - `$push/$addToSet`: Array operations

**Example:**
```javascript
db.products.updateOne(
  { _id: ObjectId("507f191e810c19729de860ea") },
  { $inc: { "stock.qty": -1 } }
)
```

#### **Deleting Documents**
- `deleteOne()`: Remove single document
- `deleteMany()`: Remove multiple
- Bulk write operations

#### **Querying (Advanced)**
- Query operators:
  - Comparison: `$eq`, `$gt`, `$in`
  - Logical: `$and`, `$or`, `$not`
  - Element: `$exists`, `$type`
  - Array: `$all`, `$elemMatch`

**Example:**
```javascript
db.products.find({
  price: { $lt: 1000 },
  tags: { $in: ["electronics"] },
  "stock.qty": { $gt: 0 }
})
```

### **3.3 Indexing (Performance-Critical)**

**Index Types:**
1. **Single Field**: `db.collection.createIndex({ field: 1 })`
2. **Compound**: Multiple fields
3. **Multikey**: Array fields
4. **Text**: Full-text search
5. **Geospatial**: Location data
6. **Hashed**: Sharding key
7. **TTL**: Auto-expiring documents

**Index Properties:**
- Unique constraint
- Sparse (only index documents with field)
- Partial (filtered indexes)

**Query Optimization:**
- Explain plans (`explain("executionStats")`)
- Covered queries (projection + index)
- Index intersection

### **3.4 Capped Collections**
- Fixed-size collections (circular buffers)
- Characteristics:
  - Insertion order preserved
  - Automatic oldest document removal
  - High-throughput writes
- Use cases:
  - Logging
  - Cache systems
  - Real-time analytics

**Creation Example:**
```javascript
db.createCollection("logs", { capped: true, size: 1000000, max: 1000 })
```

## **4. Apache Spark (Architectural Details)**

### **4.1 Installation & Deployment**
**Cluster Modes:**
1. **Local Mode**: Single JVM (development)
2. **Standalone**: Spark's built-in cluster manager
3. **YARN**: Hadoop integration
4. **Mesos**: Alternative cluster manager
5. **Kubernetes**: Containerized deployment

**Installation Steps:**
1. Download binaries
2. Configure:
   - `spark-env.sh` (environment variables)
   - `spark-defaults.conf` (runtime properties)
3. Deploy to cluster
4. Verify with `spark-submit`

### **4.2 Spark Application Anatomy**

**Execution Hierarchy:**
1. **Application**: User program (contains jobs)
2. **Job**: Sequence of stages triggered by action
3. **Stage**: Set of parallel tasks (pipeline of transformations)
4. **Task**: Smallest unit of work (operates on RDD partition)

**Example Workflow:**
1. User submits application
2. Driver program creates DAG (Directed Acyclic Graph)
3. DAGScheduler divides into stages
4. TaskScheduler launches tasks on executors
5. Results returned to driver

### **4.3 Resilient Distributed Datasets (RDDs)**

**Characteristics:**
- Immutable distributed collection
- Partitioned across cluster
- Can be rebuilt if lost (lineage)
- Two types of operations:
  - Transformations (lazy)
  - Actions (eager)

**RDD Operations:**
- Transformations:
  - `map()`, `filter()`, `flatMap()`
  - `reduceByKey()`, `join()`
  - `repartition()`, `coalesce()`
- Actions:
  - `count()`, `collect()`
  - `reduce()`, `saveAsTextFile()`

**Fault Tolerance:**
- Lineage tracking
- Checkpointing (persists RDD to storage)
- Shuffle replication

### **4.4 Spark on YARN**

**Deployment Modes:**
1. **Client Mode**:
   - Driver runs on client machine
   - Good for interactive sessions
   - Client must remain active
2. **Cluster Mode**:
   - Driver runs in YARN container
   - Better for production
   - Client can disconnect

**Configuration:**
- Set `--master yarn`
- Resource allocation:
  - `spark.executor.memory`
  - `spark.executor.cores`
  - `spark.yarn.queue`

**Performance Considerations:**
- Container sizing
- Dynamic allocation
- Data locality

## **5. Scala (Language Deep Dive)**

### **5.1 Object-Oriented Features**

**Classes:**
```scala
class Person(val name: String, var age: Int) {
  // Constructor parameters become fields
  def greet(): String = s"Hello, $name!"
  
  // Auxiliary constructor
  def this(name: String) = this(name, 0)
}
```

**Objects (Singletons):**
```scala
object Logger {
  private var level = "INFO"
  
  def setLevel(newLevel: String): Unit = {
    level = newLevel
  }
  
  def log(message: String): Unit = {
    println(s"[$level] $message")
  }
}
```

**Case Classes:**
- Immutable by default
- Auto-generated:
  - equals/hashCode
  - toString
  - copy method
  - companion object with apply

```scala
case class Point(x: Int, y: Int)
```

### **5.2 Functional Programming Features**

**Functions:**
```scala
// Anonymous function
val square = (x: Int) => x * x

// Higher-order function
def operate(f: (Int, Int) => Int, a: Int, b: Int) = f(a, b)
```

**Closures:**
```scala
def multiplier(factor: Int) = (x: Int) => x * factor
val timesTwo = multiplier(2)
timesTwo(5) // Returns 10
```

**Pattern Matching:**
```scala
def matchTest(x: Any): String = x match {
  case 1 => "one"
  case "two" => 2
  case _: Int => "other integer"
  case _ => "unknown"
}
```

### **5.3 Type System**

**Basic Types:**
- `Byte`, `Short`, `Int`, `Long`
- `Float`, `Double`
- `Char`, `String`
- `Boolean`
- `Unit` (like void)

**Type Inference:**
```scala
val x = 1 // Inferred as Int
val y = "hello" // Inferred as String
```

**Type Hierarchy:**
- `Any` (supertype of all types)
  - `AnyVal` (value types)
  - `AnyRef` (reference types)
- `Nothing` (subtype of all types)
- `Null` (subtype of all reference types)

### **5.4 Control Structures**

**Conditionals:**
```scala
val result = if (x > 0) "positive" else "negative"
```

**Loops:**
```scala
// While loop
while (condition) {
  // code
}

// For comprehension
for {
  i <- 1 to 5
  j <- 1 until i
  if i % 2 == 0
} yield (i, j)
```

**Exception Handling:**
```scala
try {
  riskyOperation()
} catch {
  case e: IOException => println("IO error")
  case _: Exception => println("General error")
} finally {
  cleanup()
}
```
