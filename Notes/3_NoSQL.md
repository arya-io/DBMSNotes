# 🗃️ Introduction to NoSQL Databases

Nowadays, SQL supports **structured** and **semi-structured** data but not **unstructured** data.  
- **Unstructured:** Flat File System  
- **Structured:** Data in tabular form (rows and columns)

---

## 🔍 What is NoSQL?

- NoSQL stands for **Not Only SQL**
- Emerged in the **late 2000s**
- Supports **non-tabular** database models
- Stores data **differently** than traditional relational tables
- Offers **flexible schema** design
- Easily **scales horizontally** to handle **large volumes of data** and **high user loads**

---

## ❓ Why NoSQL?

1. ✅ Fast-paced **Agile development**
2. 📦 Handles **structured, semi-structured, and unstructured** data
3. 📊 Supports **huge volumes** of data
4. ⚙️ Enables **scale-out architecture** (horizontal scaling)
5. 🕒 Built for **modern application needs**, including **real-time data streaming**

## 🔄 Difference between RDBMS and NoSQL

- NoSQL does **not** have **Primary Key** or **Foreign Key** concepts.
- NoSQL eliminates the need for **JOINS**, resulting in **faster queries**.

| **Feature**               | **SQL Databases (RDBMS)**                                | **NoSQL Databases**                                                |
|--------------------------|----------------------------------------------------------|---------------------------------------------------------------------|
| **Data Storage Mode**     | Tables with fixed rows and columns                       | JSON documents, key-value pairs                                     |
| **Primary Purpose**       | 1. General Purpose                                       | 1. Handling Large Amounts of Data                                   |
|                           | 2. Used in OLTP systems (e.g., Banking)                  | 2. Analyzing relationships between connected data                   |
| **Schemas**               | Rigid (Predefined Schema)                                | Flexible (Dynamic Schema)                                           |
| **Scaling**               | Vertical (Scale-up with larger servers)                  | Horizontal (Scale-out across commodity servers)                     |
| **Transaction Support**   | Fully supported (ACID compliant)                         | Most NoSQL systems do not support full ACID; MongoDB partially does |
| **Joins**                 | Typically Required                                       | Not required; denormalized data models are used                     |
| **Data to Object Mapping**| Requires ORM (Object Relational Mapping)                 | Directly maps to data structures in modern programming languages    |

## 🗂️ Types of NoSQL Databases

**There are four main types of NoSQL Databases:**

1. **📄 Document Databases**
   - Store data in **documents** (usually JSON or BSON format).
   - Each document is a **self-contained unit** with its own structure.
   - Best for **semi-structured** data.
   - 🔍 *Example:* MongoDB, CouchDB

2. **🔑 Key-Value Databases**
   - Data is stored as a **key-value pair**.
   - Extremely fast lookups using unique keys.
   - Best for caching, session management, or real-time applications.
   - 🔍 *Example:* Redis, DynamoDB, Riak

3. **📊 Column Store Databases**
   - Store data in **columns** instead of rows.
   - Optimized for **analytical queries** and **large-scale data retrieval**.
   - Best for **data warehousing** and **business intelligence** use cases.
   - 🔍 *Example:* Apache Cassandra, HBase

4. **🔗 Graph Databases**
   - Data is represented in terms of **nodes**, **edges**, and **properties**.
   - Best for analyzing **relationships** and **connected data**.
   - Ideal for **social networks**, **recommendation engines**, and **fraud detection**.
   - 🔍 *Example:* Neo4j, Amazon Neptune


## 📄 Document Databases

- Store data in:
  - **JSON** (JavaScript Object Notation)  
  - **BSON** (Binary JSON)  
  - **XML** (Extensible Markup Language) objects  
- Each document contains **pairs of fields and values**.
- The values can typically be a variety of types including:
  - Strings  
  - Numbers  
  - Booleans  
  - **Arrays**, or  
  - **Objects**

- Document databases are popular with developers because they offer:
  - **Schema flexibility**
  - The ability to **rework document structures** as application needs evolve
  - Great for **agile development and modern applications**

- 🔍 **Example**: MongoDB

### 📦 Sample Document:
```json
{
  "_id": "12345",
  "first_name": "John",
  "last_name": "Doe",
  "cell": "+1-555-1234",
  "city": "Pune",
  "hobbies": [
    "reading",
    "cycling",
    "playing guitar"
  ]
}
```

### 🔑 Key-Value Databases

- Every data element in the database is stored as a **key-value pair** consisting of:
  - A **key** (or attribute name), and
  - A **value**
- Think of it like a relational table with only **two columns**:
  - **Key** → e.g., "State"
  - **Value** → e.g., "Maharashtra"
- Common use cases include:
  - 🛒 Shopping carts
  - ⚙️ User preferences
  - 👤 User profiles
- 🔍 **Examples**: Couchbase, Amazon DynamoDB

---

### 📊 Document Database vs 🔑 Key-Value Database

| Feature                         | Document Database                          | Key-Value Database                         |
|---------------------------------|--------------------------------------------|--------------------------------------------|
| Structure                       | Organizes data in **documents** (JSON, etc.) | Stores data as **key-value** pairs         |
| Grouping                        | Uses **collections** (like tables)          | Uses a **single namespace**                |
| Best Use Case                   | Complex entities and **flexible queries**   | Simple lookups by **key or ID**            |
| Querying                        | Supports **complex queries**                | Limited querying, usually key-based only   |
| Flexibility                     | High (schema-less, nested structure)        | Simple (flat structure)                    |

✅ Choose **Key-Value DB** if:
- You primarily retrieve data by key/ID
- You need extremely fast lookups
- You don’t require complex queries

✅ Choose **Document DB** if:
- You have multiple entity types
- You need to perform **advanced filtering or aggregations**

### 🧱 Column Store Databases

- Column Store Databases store data in **tables, rows, and dynamic columns**.
- Unlike traditional relational databases (which are **row-oriented**), a **column store** is organized as a **set of columns**.
- 📊 This allows analytics on a **subset of columns** without loading unnecessary data — boosting performance!
- Columnar databases are **ideal for analytical workloads**, but they **struggle with strong consistency** because writing to multiple columns involves multiple write events.

🔍 **Examples**:
- Apache Cassandra
- Microsoft Azure Cosmos DB

---

#### 🧠 Row-Oriented vs Column-Oriented Storage

| Storage Type      | Description                                                     |
|-------------------|-----------------------------------------------------------------|
| **Row-Oriented**  | Rows stored **sequentially** in a file                          |
| **Column-Oriented**| Each column is stored in a **separate file**                   |

➡️ Each **column** for a given row is found at the **same offset** across its respective files.

---

✅ **Use Column Store DB when**:
- You run **complex analytical queries** on **huge datasets**
- You often need only a few **columns** from a large table
- You value **read performance** over **write consistency**

### 🕸️ Graph Databases

- A **graph database** focuses on the **relationship between data elements**.
- Each data element is stored as a **node** (e.g., a person in a social media graph).
- The **connections** between elements are called **links** or **relationships**.
- Graph databases are **optimized to store and query relationships**, eliminating the performance cost of **JOINs** in traditional SQL systems.

🔍 **Use Case**:
- Perfect for applications like **social networks**, recommendation systems, fraud detection, etc.

📌 **Example Visualization**:

![Alt Text](Images/gd.png)


