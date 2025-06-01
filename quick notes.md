## 🔐 NameNode High Availability

**Keyword:** No more dependency on single NameNode

In **Hadoop 1.x**, the system was dependent on **one NameNode only**.  
If that NameNode crashed, the **entire cluster became unavailable**.  
This issue is called **Single Point of Failure (SPoF)**.

### ✅ Solution in Hadoop 2.x:
- **Active NameNode** → Handles all operations
- **Standby NameNode** → Stays in backup mode, ready to take over

Both NameNodes **share metadata** using:
- **Shared Storage (NFS)** — older approach, risk of SPOF
- **Quorum Journal Manager (QJM)** — better option  
  → Uses **three JournalNodes**, writes metadata edits to all, and proceeds if **majority agrees**

### 🧠 ZooKeeper
- Monitors the health of the Active NameNode
- If Active fails, **automatically promotes** the Standby to Active

**🔁 Result:** Even if one NameNode fails, the cluster **remains available and functional**

## 🧩 HDFS Federation

**Problem:**  
HDFS originally had a **single NameNode** managing **one namespace**.  
As data volume grew, this caused **performance bottlenecks** and **limited scalability**.

### ✅ Solution:
- Use **multiple independent NameNodes**
- Each NameNode manages its **own namespace**
- All NameNodes share the same set of **DataNodes**

### 🧠 Block Pools:
- Each namespace has its **own block pool**
- **DataNodes** store blocks from **multiple block pools**

### 🎯 Benefits:
- 🔄 **Horizontal scalability** → Add more namespaces as needed  
- 🔐 **Isolation** → Keeps data of different apps/teams separated
