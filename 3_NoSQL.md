# Introduction to NoSQL Databases

Nowadays, SQL supports structured and semi-structured data but not unstructured.
Unstructured: Flat File System.
Structured: Data in tabular form, i.e., in rows and columns.

## What is NoSQL?
- Rapid pace of progression.
- NoSQL stands for **N**ot **O**nly **SQL**.
- Developed in the late **2000s**.
- **Non-tabular** Databases.
- Store data **differently** than relational tables.
- Provide **flexible schema**.
- **Scale easily** with **large amounts of data** and **high user loads**.

## Why NoSQL?
1. Fast-paced **Agile**(quick) development.
2. Storage of structured, **semi-structured** and **unstructured** data.
3. **Huge Volumes** of Data.
4. Requirements for **scale out architecture**.
5. Modern application paradigms like real-time streaming.

## Difference between RDBMS and NoSQL

NoSQL does not have Primary Key, Foreign Key concept.
NoSQL eliminates the need for JOINS resulting in faster queries.

| **Feature**             | **SQL Databases (RDBMS)**                            | **NoSQL Databases**                                     |
|------------------------ |------------------------------------------------------|---------------------------------------------------------|
| **Data Storage Mode**   | Tables with fixed rows and columns                   | JSON documents, key-value pairs                         |
| **Primary Purpose**     | 1. General Purpose                                   | 1. Large Amounts of Data                                |
|                         | 2. For OLTP systems (e.g., Banking)                  | 2. Analyzing and traversing relationships between connected data |
| **Schemas**             | Rigid                                                | Flexible                                                |
| **Scaling**             | Vertical (scale-up with larger servers)              | Horizontal (scale-out across commodity servers)         |
| **Transaction Support** | Supported                                            | Most do not support, however MongoDB supports.          |
| **Joins**               | Typically Required                                   | Typically not required.                                 |
| **Data to Object Mapping** | Requires ORM (Object Relational Mapping)          | Maps directly to data structures in most popular programming languages. |

## Types of NoSQL Databases
**There are four types of NoSQL Databases**
1. Document Database
2. Key-value Databases
3. Column Store Databases
4. Graph Databases

## Document Databases

- Store data in
  **JSON** (JavaScript Object Notation) OR
  **BSON** (Binary JSON) OR
  **XML** (Extensible Markup Language) objects.
- Each document contains **pairs of fields and values**.
- The values can typically be a variety of types including things like strings, numbers, booleans, **arrays, or objects**.
- Document databases are popular with developers **because they have the flexibility to rework their document structures as needed to suit their application**, shaping their data structures as their application requirements change over time.
- Example -> MongoDB

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

### Key-Value Databases

- Every data element in the database is stored as a **key value pair** consisting of an attribute name (or "key) and a value.
- In a sense, a key-value store is like a relational database with only two columns: the key or attribute name (such as "State") and the value (such as "Maharashtra").
- Use cases include **shopping carts, user preferences, and user profiles**.
- Example -> Couchbase, Amazon dynamo.

### Document Database vs Key-Value Databases

- Document databases organize documents into groups called collections, which are analogous to the tables in relational databases.
- By contrast, key-value databases store all key-value pairs together in a single namespace, which is analogous to a relational schema.
- If you usually retrieve data by key or ID value and don't need to support complex queries, a key-value database is a good option.
- If you have different types of entities and need complex querying, choose a document database.

### Column Store Databases

- Column Store Databases store data in tables, rows, and **dynamic columns**.
- While a relational database stores data in rows and reads data row by row, **a column store is organized as a set of columns**.
- This means that when you want to run analytics on a small number of columns, you can read those columns directly without consuming memory with the unwanted data.
- Columnar databases are great for analytic, but the way in which they write data makes it very difficult for them to be strongly consistent as writes of all the columns require multiple write events on disk.
- Example -> **Apache Cassandra, Microsoft Azure Cosmos DB**

##### Explanation of above's 4th point:
Row-Oriented vs Column-Oriented
`Row-oriented:` rows stored sequentially in a file
`Column-oriented:` each column is stored in a separate file
Each column for a given row is at the same offset.

### Graph Databases

- A graph database focuses on the **relationship between data elements**. Each element is stored as a node (such as a person in a social media graph).
- The connections between elements are called links or relationships.
- A graph database is optimized to capture and search the connections between data elements, **overcoming the overhead associated with joining multiple tables in SQL**.
- Use cases include **social network**.
Example:
![Alt Text](Images/gd.png)

