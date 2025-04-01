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



