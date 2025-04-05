# 🗄️ Cassandra

## 🔍 What is Cassandra?

1. **Cassandra** is an **Open Source, NoSQL** Database.
2. Initially developed by **Facebook** in **July 2008**.
3. Later became a project under the **Apache Software Foundation**.
4. Written in the **Java** programming language.
5. It is a **Distributed NoSQL Database Management System** designed to handle **large volumes of data** across many **commodity servers**.

---

## 🚀 Features of Cassandra

1. **Decentralized Architecture**  
   - All nodes are equal in a Cassandra cluster—no single point of failure.
   - Enables horizontal scalability.

2. **Flexible Data Model**  
   - Uses a **column-family data model** with **partitioned-row store** methodology.
   - Highly dynamic and adaptable for semi-structured data.

3. **Replication**  
   - Offers configurable replication strategies for **high availability** and **fault tolerance**.

4. **Cassandra Query Language (CQL)**  
   - Similar to SQL, making it easy to learn for developers with RDBMS background.

5. **High Throughput**  
   - Optimized for **high read/write performance** on large-scale datasets.

---

## 💼 Use Cases of Cassandra

1. **High-Write Workloads**  
   - Example: Logging systems, social media feeds.  
   - Handles massive write operations with low latency.

2. **Real-Time Analytics**  
   - Ideal for dashboards, retail analytics, and recommendation engines.  
   - Supports **real-time decision-making**.

3. **Content Management Systems (CMS)**  
   - Scales to handle large-scale, dynamic content like media, articles, and user data.

4. **Distributed Databases**  
   - Best for **geo-distributed systems** that require **multi-region replication**.

5. **Catalog and Inventory Systems**  
   - E-commerce platforms benefit from **fast reads and flexible schema** design.

6. **Message Queues & Communication Platforms**  
   - Chat apps and real-time messaging systems leverage Cassandra for **low-latency message storage** and **high availability**.

## 🧱 Database Scalability

- **Scalability** is the **ability to expand or contract the capacity of system resources** in order to support the changing usage of your application.
- It refers to both **increasing and decreasing** the system’s capability as per application demands.

---

### ⚠️ Challenges Faced During Increased Usage:

1. **CPU and Memory Overload**  
   - The database server cannot handle the **request throughput** or starts responding **too slowly**.

2. **Storage Limitations**  
   - The **database server runs out of disk space** and fails to store incoming or growing datasets.

3. **Network Interface Bottleneck**  
   - The server’s **network bandwidth** cannot support the increasing volume of traffic, leading to **request failures or timeouts**.

## 🧍‍♂️ Vertical Scaling

- **Vertical Scaling** (also known as **Scale Up**) means **increasing the processing power of a single server or cluster**.
- Both relational and non-relational databases support this approach.
- However, it comes with **physical limitations** and **increased costs** due to high-performance hardware requirements.

---

### ✅ Pros of Vertical Scaling

1. **No Change in Infrastructure**  
   - Only the **hardware specs** are upgraded — not the database design or application logic.

2. **Transparent to Applications**  
   - Your **existing applications keep working** as before, but now with more memory, CPUs, or storage.

3. **Simple Starting Point**  
   - Ideal for applications that **don’t need massive scaling** — a quick win for small-to-medium scale systems.

---

### ❌ Cons of Vertical Scaling

1. **High Cost**  
   - Upgrading to powerful servers is **expensive** compared to other options.

2. **Physical Limits**  
   - You can only scale up to a point — limited by **max CPU, memory, disk**, etc.

3. **Potential Downtime**  
   - Scaling up might require **hardware migration**, which can cause **service interruptions**.

## 🧑‍🤝‍🧑 Horizontal Scaling

- **Horizontal Scaling** (also known as **Scale Out**) means **adding more nodes or machines** to handle the load.
- This is **challenging for relational databases** due to the complexity of distributing **related data across nodes**.
- In contrast, **non-relational (NoSQL) databases** like MongoDB simplify this process as their **data collections are self-contained** and not reliant on complex joins.

---

## 🌐 Horizontal Scaling in MongoDB

MongoDB supports horizontal scaling through:

### 1. 🔀 Sharding
- **Sharding** divides the dataset and spreads it across multiple nodes.
- Each node contains **only a subset** of the data.
- Useful for systems with **heavy write operations**, since writes are distributed.
- **Efficient and scalable**, as each shard only manages its own portion of the data.

### 2. 🧬 Replica Sets
- **Replica Sets** involve **copying the entire dataset** to multiple nodes.
- Benefits include:
  - **High availability**
  - **Data redundancy**
  - **Failover protection**
  - **Improved read performance** (reads can be split among replicas)
- Caveat: For **write-heavy applications**, all writes must **sync to all replica members**, which could introduce some delays or write conflicts.

---

📌 **Summary**:
- Use **Sharding** for **write scalability**.
- Use **Replica Sets** for **read scalability** and **fault tolerance**.

## 🌐 Cluster in Cassandra

A **cluster** in Cassandra is a **collection of nodes (servers)** that **work together** to store and manage large volumes of data.

- Each **node** in the cluster:
  - Holds a **portion of the data**.
  - Participates in **read and write operations**.
  - Contributes to the **overall performance and availability** of the system.

### 🛡️ Key Benefits:
- **High Availability**: If one node fails, others continue to serve data.
- **Fault Tolerance**: Replication across nodes ensures no data loss.
- **Scalability**: Easily add more nodes to handle increased load.

> ✅ Cassandra's decentralized architecture ensures there is **no single point of failure** — all nodes are equal. 

## 🖥️ Node in Cassandra

A **Node** in Cassandra is an **individual machine (server)** within a cluster.

- Each node:
  - Stores **a subset of the data**.
  - Can **operate independently**.
  - Communicates with other nodes to **replicate data** and maintain **consistency**.

### 🔁 Key Responsibilities:
- **Respond to read/write requests** from clients.
- **Replicate data** to and from other nodes.
- **Monitor the health** of neighboring nodes.

> ⚠️ If a node goes down, **other nodes continue to serve the data**, ensuring **fault tolerance and high availability**. 

## 🏢 Data Centre in Cassandra

A **Data Centre** in Cassandra is a **logical grouping of nodes** within a cluster.

### 🎯 Purpose:
- To manage **network latency**.
- To provide **fault tolerance** across different **geographical locations**.
- To enable **efficient data replication**.

### 📌 Key Points:
- A cluster can have **multiple data centres** (e.g., US-East, US-West, EU).
- Replication strategies can be configured **per data centre**, allowing **flexible disaster recovery** and **load balancing**.
- Useful for **hybrid cloud** or **multi-region deployments**.

> 💡 Organizing nodes into data centres ensures that **replica placement** is optimized, and **read/write operations** are resilient even if an entire data centre goes down.

## Cassandra Architecture (Textual Diagram)
```
Cassandra Cluster
└── Data Centre 1 (e.g., US-East)
    ├── Node 1
    ├── Node 2
    └── Node 3
└── Data Centre 2 (e.g., US-West)
    ├── Node 4
    ├── Node 5
    └── Node 6
```

## Rack (in Cassandra)

- A **Rack** in Cassandra is a **logical grouping of nodes** within a **Data Centre**.
- Think of it like a **bookshelf aisle in a library**: each **rack (aisle)** contains multiple **nodes (books)** that store parts of your data.
- Racks are used mainly to **optimize data replication** and **minimize network latency** within the same data centre.

### ✅ Why Are Racks Important?
- Cassandra replicates data **intelligently across different racks**.
- This ensures **high availability** and **fault tolerance** even if an **entire rack fails** (e.g., due to power loss or network issue).

### 📌 Real-World Analogy:
> Imagine a library (Data Centre) with multiple aisles (Racks). Each aisle has copies of important books (Nodes). If one aisle is blocked, readers can still find the books in other aisles.

### 💡 Key Point:
- If you define multiple racks, Cassandra **won't store all replicas of your data in the same rack**—it distributes them across racks to prevent data loss from rack-level failure.

### 🔁 Relation to Replication Strategy:
- In **NetworkTopologyStrategy**, you can define how many replicas should be stored in each **Data Centre** and spread them across **Racks** within that data centre.

---

### ✅ Summary:
| Term         | Meaning                                       |
|--------------|-----------------------------------------------|
| Node         | A single machine storing part of the data     |
| Rack         | A group of nodes within a data centre         |
| Data Centre  | A logical grouping of racks (often geographical) |
| Cluster      | The entire Cassandra database (all nodes)     |

## Cassandra Architecture (Cluster → Data Centre → Rack → Node)

```
Cassandra Cluster
└── Data Centre 1 (e.g., US-East)
    ├── Rack 1
    │   ├── Node 1
    │   └── Node 2
    └── Rack 2
        ├── Node 3
        └── Node 4
└── Data Centre 2 (e.g., US-West)
    ├── Rack 1
    │   ├── Node 5
    │   └── Node 6
    └── Rack 2
        ├── Node 7
        └── Node 8
```

## VNode (Virtual Node) in Cassandra

- A **VNode (Virtual Node)** is a **logical partition of data** within a physical node in a Cassandra cluster.
- Instead of assigning a single token range to a physical node, Cassandra assigns **multiple small token ranges (VNodes)** to each node.
- This allows for **finer-grained distribution of data**, which helps in balancing the load more evenly across the cluster.

---

### ✅ Why VNodes?
- **Better Load Balancing:** Prevents any one node from becoming a hotspot.
- **Simpler Scaling:** Adding or removing nodes becomes easier and quicker.
- **Faster Recovery:** In the case of node failure, recovery is quicker because the data from multiple small VNodes is redistributed across multiple nodes.

---

### 📌 Real-World Analogy:
> Imagine a classroom where each student (Physical Node) is given not one big textbook (data), but **many small booklets (VNodes)**. If a student leaves, it's easier for others to pick up and share the small booklets among them, rather than carrying one huge book.

---

### 🔧 Technical Insights:
- Earlier, each node handled **one large token range**, leading to **uneven distribution**.
- With VNodes, each node handles **multiple small token ranges**, leading to **balanced workloads**.

---

### ⚡ Benefits of VNodes
| Feature                     | With VNodes                     | Without VNodes                  |
|----------------------------|----------------------------------|----------------------------------|
| Load Distribution          | Even                             | May become skewed               |
| Node Addition/Removal      | Easier and quicker               | More complex                    |
| Data Recovery              | Parallelized and faster          | Slower                          |

---

### 💡 Tip:
- By default, Cassandra assigns **256 VNodes per node**, but this is configurable depending on the workload and hardware capacity.

---

### 🔁 VNode in Action:
When a new node is added to the cluster:
- It takes a few VNodes from **many existing nodes**, rather than large chunks from just a few.
- This results in **minimal disruption** and **faster rebalancing**.

## Primary Key in Cassandra

In Cassandra, the **Primary Key** is a critical concept that determines:

1. **Uniqueness** of each row.
2. **Data distribution** across nodes in the cluster.
3. **Sorting** of data within partitions.

---

### 🧩 Components of Primary Key

A **Primary Key** consists of two parts:

#### 1. 🗃 Partition Key
- Determines **which node** stores the data.
- Responsible for **distributing rows** evenly across the cluster.
- Acts like a **hashing input** to place data in the correct node.

#### 2. 📑 Clustering Columns (optional)
- Define **how rows are sorted** **within** a partition.
- Allow efficient **range queries** and **ordered retrieval** of data.

---

### 🔍 Syntax
```sql
PRIMARY KEY ((partition_key), clustering_column1, clustering_column2, ...)
```

🔸 **Note:** Double parentheses around the partition key are used when there are multiple fields in the partition key (**composite partition key**).

---

## 📦 Example of Primary Key Functioning in Cassandra

```sql
CREATE TABLE orders (
  order_id UUID,
  customer_id UUID,
  order_date DATE,
  product_name TEXT,
  amount DECIMAL,
  PRIMARY KEY ((customer_id), order_date)
);
```

### 🧠 Explanation:

- **Partition Key:** `customer_id`  
  Ensures that all orders of a specific customer go to the **same node**.

- **Clustering Column:** `order_date`  
  Ensures that orders for that customer are **sorted by date** within the partition.

---

### 📌 What this enables:

✅ Efficient queries like:

```sql
SELECT * FROM orders WHERE customer_id = ?;
```

✅ And ordered queries like:

```sql
SELECT * FROM orders WHERE customer_id = ? ORDER BY order_date DESC;
```

## 🚀 Summary

| Component         | Purpose                              |
|------------------|--------------------------------------|
| Partition Key     | Distributes data across nodes        |
| Clustering Column | Sorts data within the same partition |

⚡ **The right choice of partition key and clustering columns is crucial for query performance and load balancing in Cassandra.**

### 📘 Creating the Table: Compound Key in Cassandra

In Cassandra, the **Primary Key** must consist of at least **two columns** when you want to define both data **distribution** and **ordering**. 

> 🔸 We **do not** call it a *Composite Key*.  
> ✅ It is termed as a **Compound Key**.

---

### 🧠 What a Compound Key Does:

| Component         | Purpose                                                 |
|------------------|---------------------------------------------------------|
| **Partition Key**     | Determines **which node** the data resides on              |
| **Clustering Columns** | Define the **sort order** of rows **within a partition**   |

---

📌 This structure is crucial for **efficient data retrieval**, **query performance**, and **logical data grouping** in distributed systems like Cassandra.

## 🗂️ Keyspace in Cassandra

A **keyspace** in Cassandra is like a **namespace** or a **container** for your data, similar to a **database** in traditional relational systems.

It defines **how data is replicated** across nodes and acts as the **top-level structure** for organizing tables.

---

### 🧠 Key Concepts

#### 🔁 Replication Strategy
- Determines **where the replicas** of data will be placed.
- Two main types:
  - **SimpleStrategy**: Best for **single data center** setups.
  - **NetworkTopologyStrategy**: Ideal for **multiple data centers** and provides better control over data placement.

#### 🔢 Replication Factor
- Defines **how many copies** of the data are stored across different nodes.
- 📌 **Higher values** = **better fault tolerance**, but require **more storage**.

#### 🧩 Data Organization
- Each **keyspace can contain multiple tables**, each with its **own schema**.
- However, all tables **share the same replication settings** defined at the keyspace level.

---

### 📌 Summary

| Term                 | Description                                                       |
|----------------------|-------------------------------------------------------------------|
| **Keyspace**         | Top-level namespace for tables and data                          |
| **Replication Strategy** | Controls how and where data is replicated                        |
| **Replication Factor**   | Number of replicas of data stored across the cluster             |

Keyspaces are **essential** for managing **data distribution**, **redundancy**, and **fault tolerance** in a Cassandra cluster.

---

### 📦 Example: Creating a Keyspace

```sql
CREATE KEYSPACE my_keyspace
WITH REPLICATION = {
  'class': 'SimpleStrategy',
  'replication_factor': 3
};
```

🔸 If you're using **multiple data centers**, use `NetworkTopologyStrategy` instead:

```sql
CREATE KEYSPACE my_keyspace
WITH REPLICATION = {
  'class': 'NetworkTopologyStrategy',
  'datacenter1': 3,
  'datacenter2': 2
};
```

## Implementing Cassandra

### Cassandra Setup

The Cassandra setup can be done in two ways:

- **On-Premises Installation and Configuration**
- **Using Cloud Services**

---

### On-Premises Installation & Configuration

Cassandra setup for **Windows operating system** can be downloaded from the following URL:  
🔗 [Download Cassandra 3.11.0](https://archive.apache.org/dist/cassandra/3.11.0/)

#### Prerequisites:

- **Java** → JDK 1.8 is required for Cassandra Server  
- **Python 2.7** → Required for Cassandra Shell (CQLSH), the command line client interface

---

### Using Cloud Services

There is a real-time AI company called **DataStax**, based in Santa Clara, California.

🔹 **Astra DB** by DataStax is a **cloud database-as-a-service** built on Apache Cassandra.

🆓 You can get a **free one-month subscription** for learning Cassandra or creating a Proof of Concept (POC).

👉 [Register for Astra DB Free Tier](https://www.datastax.com/products/datastax-astra)

💼 For **commercial use**, Astra DB also provides **paid licensing** options.

## Cassandra on DataStax

- ✅ Created a **Database** in **Amazon Web Services**
- 🌍 The selected **region** is `us-east-2`
- ▶️ To start working with Cassandra, clicked on **CQL Console**
- 💻 You should be in the **CQL Editor environment** of the **Astra DB** database by **DataStax** to begin executing Cassandra queries.

## 🧪 Creating a Table in Cassandra – Step-by-Step Execution

```sql
CREATE TABLE t1(a int, b int, c int);  -- What happens???
```
### ❌ Error:
```bash
"No keyspace has been specified. USE a keyspace, or explicitly specify keyspace.tablename"
```

➡️ This means you must first **select a keyspace** before creating a table.

### ✅ Step 1: Use a Keyspace

```sql
USE default_keyspace;
```

### ❌ Error on Retry

```sql
CREATE TABLE t1(a int, b int, c int);
```

```bash
message="No PRIMARY KEY specified for table 't1' (exactly one required)"
```

➡️ This is because **Cassandra requires a PRIMARY KEY** for every table.

---

### ✅ Step 2: Create Table with PRIMARY KEY

```sql
CREATE TABLE t1(a int PRIMARY KEY, b int, c int);
```

✅ **Output**: No error — query executed successfully!

---

### 📌 Summary

| Requirement   | Explanation                                                                 |
|---------------|-----------------------------------------------------------------------------|
| **Keyspace**      | Cassandra requires a keyspace before any table is created.                 |
| **Primary Key**   | Every table must have a PRIMARY KEY — used for data distribution and efficient retrieval. |

```sql
INSERT INTO t1 VALUES (1, 100, 200);
```

✅ **Explanation:**

This inserts a row into table `t1` where:

- `a = 1` (Primary Key)
- `b = 100`
- `c = 200`

📌 Since column `a` is the **primary key**, this value must be **unique** in the table.

❌ **Error:**

```bash
SyntaxException: line 1:15 no viable alternative at input 'Values' (Insert into [t1] Values...)
```

➡️ **This error occurs because Cassandra requires you to specify the column names explicitly when inserting data.**

---

✅ **Correct Syntax for Inserting Data into a Table in Cassandra:**

```sql
INSERT INTO t1(a, b, c) VALUES(1, 100, 200);
```

✅ **Output:**  
No output — means the query has been **executed successfully**!

📌 **Note:**  
Always **mention column names** when inserting data in Cassandra.  
It helps ensure correctness and avoids ambiguity.

## ❌ Rollback in Cassandra

```sql
ROLLBACK;
```

```bash
SyntaxException: line 1:0 no viable alternative at input 'Rollback' ([Rollback]...)
```

## 🔄 Rollback in Cassandra — Not Supported

🔎 **Explanation:**
Cassandra does **not support `ROLLBACK` or traditional transactions** like relational databases.

Unlike RDBMSs (e.g., MySQL, PostgreSQL), Cassandra is built for **availability and partition tolerance** (AP in the **CAP theorem**), so it does **not offer full ACID transaction support** — and hence, no `ROLLBACK`.

---

🚨 **Important to Remember:**
- There’s **no undo** in Cassandra once an operation is performed.
- Always be **cautious** while inserting or updating data.
- To **simulate rollbacks**, you must design logic at the **application level** or use features like **Lightweight Transactions (LWT)** where applicable.

---

🧠 **Quick Tip:**
If you're **testing data** and want to "rollback", insert only sample or test-specific data, and then **delete it manually** if needed:

```sql
DELETE FROM t1 WHERE a = 1;
```

💡 Cassandra is **eventually consistent**, so always design your application with that in mind — think more in terms of **resilience and speed**, not rollback-and-retry like RDBMS.

## 📋 Displaying Table `t1`

To view all the rows from the table `t1`, use the `SELECT *` query:

```sql
SELECT * FROM t1;
```

✅ Output:
```bash
 a |  b  |  c
---+-----+-----
 1 | 100 | 200

(1 rows)
```

## 🧠 Explanation:

This query retrieves **all rows** and **all columns** from the table `t1`.

Since we had inserted only one record earlier (`a = 1, b = 100, c = 200`), we get a single row in the result.

---

📌 **Reminder:**
In Cassandra, every row must have a **primary key** (in this case, `a`), which:
- **Uniquely identifies** the row.
- **Determines** where the data is stored in the cluster (i.e., which node via partitioning).

## 🔄 Inserting a Record with the Same PRIMARY KEY

```sql
INSERT INTO t1(a, b, c) VALUES(1, 500, 700);
SELECT * FROM t1;
```

📤 Output:
```bash
 a | b   | c
---+-----+-----
 1 | 500 | 700

(1 rows)
```

## 🔁 Upsert Behavior in Cassandra

### 🧠 Explanation:
This may seem strange coming from a relational database background, but this behavior is **normal in Cassandra**.

When you insert a new record with an **existing primary key**, Cassandra **does not throw an error**. Instead, it performs an **upsert** operation:

- If the primary key already exists, the values are **updated/overridden**.
- If it doesn't exist, the row is **inserted as new**.

➡️ This is **by design**, not a drawback.

---

### 📌 Important Notes:

- ⚠️ Cassandra uses **upserts** instead of enforcing primary key uniqueness like traditional RDBMS systems.
- ✅ This behavior helps **optimize for speed and availability**—Cassandra avoids locks and constraints to remain highly performant and scalable.
- 💡 If you want to **prevent accidental overwrites**, you must:
  - Add checks in the **application layer**, or
  - Use **Lightweight Transactions (LWT)** with `IF NOT EXISTS`.

---

### ✅ Example with LWT (to avoid overwrite):

```sql
INSERT INTO t1(a, b, c) VALUES(1, 800, 900) IF NOT EXISTS;
```

🔐 **This ensures data is only inserted if the primary key `a = 1` doesn't already exist.**

⏳ **Cassandra prioritizes _availability_ and _partition tolerance_ over strict consistency** (as per the CAP theorem) — so always design with this in mind!

> ✅ Think in terms of high scalability, speed, and resilience — not transactional safety or rollbacks like traditional RDBMS.

### Creating new table transactions:
```sql
create table transactions
(trid int,
 country text,
 emailid text,
 amount int,
 Primary Key(country, emailid)
);  -- The above PK is known as Compound Key.
-- Country is partition key and emailid is cluster column

Insert into transactions (trid, country, emailid, amount) 
Values(1, 'India', 'a@abc.com', 3000);

Insert into transactions (trid, country, emailid, amount) 
Values(2, 'India', 'b@abc.com', 4000);

Insert into transactions (trid, country, emailid, amount) 
Values(3, 'Australia', 'c@abc.com', 9000);

Insert into transactions (trid, country, emailid, amount) 
Values(4, 'Australia', 'd@abc.com', 10000);
```

Output:
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
     India | a@abc.com |   3000 |    1
     India | b@abc.com |   4000 |    2
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```
### 📊 Table Example with Color Coding

 country   | emailid   | amount | trid
-----------+-----------+--------+------
     🟨India | 🟨a@abc.com | 🟩3000 | 🔴1
     🟨India | 🟨b@abc.com | 🟩4000 | 🔴2
 🟨Australia | 🟨c@abc.com | 🟩9000 | 🔴3
 🟨Australia | 🟨d@abc.com | 🟩10000 | 🔴4

## 🎨 Color Code Meaning in DataStax Console

| Emoji | Meaning                               |
|-------|----------------------------------------|
| 🔴    | Primary Key                            |
| 🟩    | Numeric Value (Row Value)              |
| 🟨    | Text/String Value                      |
| 🟣    | Numeric Column (like `amount`, `trid`) |


## 🔍 Querying with Non-Primary Columns in Cassandra

### ❌ Problematic Query:
```sql
SELECT * FROM transactions WHERE amount > 4000;
```

### ❗ Error:
```bash
Cannot execute this query as it might involve data filtering and thus may have unpredictable performance.
If you want to execute this query despite the performance unpredictability, use ALLOW FILTERING.
```

### ✅ Corrected Query:
```sql
SELECT * FROM transactions WHERE amount > 4000 ALLOW FILTERING;
```

### ✅ Output:
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```

## 🧠 Why This Happens:

In Cassandra, queries must use the **primary key** or **indexed columns** efficiently.

Since `amount` is **not part of the primary key** or **not indexed**, Cassandra **cannot quickly locate** data based on it.

Hence, Cassandra throws an error and warns about **unpredictable performance**.

---

## ⚠️ What is `ALLOW FILTERING`?

`ALLOW FILTERING` tells Cassandra:

> "I know this query might be inefficient. Run it anyway."

✅ **Useful for:**
- Small datasets
- Occasional analytics
- Testing and learning environments

❌ **Avoid in:**
- Large production datasets
- Frequently used queries

Because it **scans many partitions**, it may **hurt performance** and **overload the cluster**.

---

## 🚀 Pro Tip:

If you're querying on non-key columns frequently:

🔸 **Option 1:** Add a **secondary index**  
> Use with caution — can help for low-cardinality columns, but may add overhead.

🔸 **Option 2:** **Redesign the data model**  
> In Cassandra, **data modeling is query-driven**. Design tables based on how data will be retrieved.

📌 **Reminder:**  
Cassandra is optimized for **speed, scale, and availability**, not for ad-hoc or flexible querying like RDBMS.

## 🔍 Query Using Partition Key

```sql
SELECT * FROM transactions WHERE country = 'India';
```

### ✅ Output:
```bash
 country | emailid   | amount | trid
---------+-----------+--------+------
   India | a@abc.com |   3000 |    1
   India | b@abc.com |   4000 |    2
```

## 🧠 Why This Works

In Cassandra, the `WHERE` clause works only with the **partition key** or **indexed columns**.

Since `country` is a **partition key**, the query is efficient and runs without any issues.

---

## ❌ Query Without Partition Key

```sql
SELECT * FROM transactions WHERE emailid = 'a@abc.com';
```

## 🔥 Error (Expected)

This query fails unless you explicitly use `ALLOW FILTERING`.

---

## ⚠️ Why It Fails

- `emailid` is **not** a partition key or an indexed column.
- Cassandra cannot efficiently locate this data without scanning multiple partitions.
- To avoid performance issues, Cassandra blocks such queries **by default**.

---

## 📌 Key Takeaways

| Concept           | Rule                                                                 |
|------------------|----------------------------------------------------------------------|
| **Partition Key**  | Can be used directly in the `WHERE` clause                           |
| **Non-Key Columns**| Need `ALLOW FILTERING` to query (⚠️ not recommended for large data) |
| **Data Modeling Rule** | Always design tables around the **queries** you expect to run       |

---

## 💡 Pro Tip

If you plan to query by `emailid` frequently:

- 🔄 **Reconsider your data model**
- ➕ **Create a secondary index** on `emailid`  
  ⚠️ Use with caution — indexes may hurt performance in write-heavy workloads.

---

> 🧠 **Reminder:**  
> Cassandra is **not** a relational database.  
> It's built for **scalable**, **high-performance** reads, so always model your data with **read patterns** in mind!


### 🔄 Update Query in Cassandra

```sql
UPDATE transactions
SET amount = 10000
WHERE trid = 2;
```

### ❌ Error Message:
```bash
message="Some partition key parts are missing: country"
```

### 🧠 Why the Error?

Cassandra requires the **full primary key** (Partition Key + Clustering Key) in the `WHERE` clause for `UPDATE` queries.

In this case, `trid` is **not** the partition key.

To successfully run the update, you **must provide**:
- The **Partition Key** (`country`)
- The **Clustering Key** (`emailid`)

---

### ✅ Correct Query:

```sql
UPDATE transactions
SET amount = 10000
WHERE country = 'India' AND emailid = 'b@abc.com';
```

### 🔎 Check the Update with:

```sql
SELECT * FROM transactions;
```

Output:
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
     India | a@abc.com |   3000 |    1
     India | b@abc.com |  10000 |    2
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```

### 📌 Summary

| Rule                        | Explanation                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| Partition Key Requirement   | Cassandra requires the **partition key** in `WHERE` clause for updates     |
| Clustering Key (if exists)  | Include the **clustering key** if your table schema uses one               |
| No Partial Updates          | You **cannot** update using only non-key columns like `trid`               |

> 💡 **Pro Tip**: Always know your **primary key structure** (both partition and clustering keys) when writing `UPDATE`, `DELETE`, or `SELECT` queries in Cassandra.

### 🗑️ Delete Query

```sql
DELETE FROM transactions
WHERE country = 'India' AND emailid = 'b@abc.com';
```

✅ Followed by:
```sql
SELECT * FROM transactions;
```

**Output:**
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
     India | a@abc.com |   3000 |    1
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```

🧠 **Explanation:**

The record for `emailid = 'b@abc.com'` is deleted successfully.

The `DELETE` operation in Cassandra also requires the **full primary key** — including both the **partition key** and the **clustering key**, if applicable.

---

### ❌ Unsupported Constraints in Cassandra

Cassandra does **not support** the following constraints that are common in relational databases:

| Constraint Type      | Support in Cassandra |
|----------------------|----------------------|
| NOT NULL             | ❌ Not Supported      |
| UNIQUE KEY           | ❌ Not Supported      |
| CHECK CONSTRAINT     | ❌ Not Supported      |
| DEFAULT              | ❌ Not Supported      |
| FOREIGN KEY          | ❌ Not Supported      |

🧠 **Reason**:  
Cassandra is built for **distributed performance** and **high availability**.  
It avoids strict schema enforcement to support **horizontal scalability** and **eventual consistency** in large-scale systems.

## ⏱️ TTL (Time-To-Live) in Cassandra

**TTL (Time-To-Live)** in Cassandra allows you to set an **expiration time (in seconds)** for a record. Once this time passes, the data is **automatically deleted** — no manual deletion required!

---

### 🛠️ How TTL Works

- When **inserting or updating** a row, you can specify a TTL in **seconds**.
- After the TTL expires, the row is **marked as deleted**.
- The actual deletion happens during the **next compaction** process.
- If **TTL is not specified**, the data persists **forever**.

---

### 🧪 Example: Using TTL on INSERT

```sql
CREATE TABLE tx3 (
    Id int PRIMARY KEY,
    Name text,
    Descr text
);

-- Record will only be available for 20 seconds!
INSERT INTO tx3(Id, Name, Descr) 
VALUES (1, 'a', 'b') 
USING TTL 20;

-- Query immediately
SELECT * FROM tx3;

-- Wait 20 seconds, then:
SELECT * FROM tx3;  -- ❌ No record found!
```

### 🔁 Example: Using TTL on UPDATE
```sql
-- Insert a permanent record
INSERT INTO tx3(Id, Name, Descr) 
VALUES (2, 'x', 'c');

-- Update with TTL applied only to the updated column
UPDATE tx3
USING TTL 20
SET Name = 'z'
WHERE Id = 2;

-- Immediately check:
SELECT * FROM tx3;

-- After 20 seconds, Name becomes NULL:
SELECT * FROM tx3;
```

> 📝 **Note**: TTL applies only to the columns **updated or inserted** in the statement.  
> In the example above, `Descr` remains **even after** TTL expires for `Name`.

---

## ✅ When to Use TTL

Use TTL for data that should **automatically expire** after a set duration:

- 🔐 **Session management** (auto-expire user sessions)
- 🧠 **Caching** (store API responses temporarily)
- 📜 **Event logging** (auto-remove old logs)
- 🔐 **OTP or Token expiry** (short-lived security data)

---

### 🧠 Pro Tip

TTL is a powerful feature for managing **time-sensitive data**, but:

- Use it **cautiously** in tables with **multiple columns**.
- TTL on only **part of a row** can lead to **incomplete or unexpected data** later.
- Always document and monitor TTL usage, especially in **production systems**.
