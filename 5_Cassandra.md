# Cassandra

## What is Cassandra?
1. Cassandra is **Open Source, NoSQL** Database.
2. Initially developed by **Facebook** in July 2008.
3. Later became **Apache** Software Foundation project.
4. Programming Language used is **Java**.
5. It is **Distributed** NoSQL database management system designed to handle large amounts of data across many commodity servers.

## Features of Cassandra
1. **Decentralized Architecture:** All nodes in a Cassandra cluster are equal, eliminating single points of failure and allowing for easy scaling.
2. **Data Model:** It uses a **column-family data model**, which is flexible and allows for dynamic data storage. It uses **partitioned-row store** methodology.
3. **Replication:** Cassandra supports configurable replication strategies, ensuring that data is duplicated across multiple nodes for resilience.
4. Query Language: It offers **CQL (Cassandra Query Language)**, which is similar to SQL, making it easier for developers familiar with relational databases to get started.
5. **High Write and Read Throughput:** Designed for high-performance operations, it can handle large volumes of data and high request rates.

## Use Cases of Cassandra
1. **High-write workloads:** Logging systems, social media platforms, and other systems that have high-write workloads, benefit from Cassandra's ability to handle many write operations across distributed nodes while maintaining low-latency performance.
2. **Real-time analytics:** Cassandra supports real-time data processing, so it's valuable for applications that require instant analytics and reporting. These use cases include online retail platforms, recommendation engines, and dynamic dashboards that rely on up-to-the-minute insights.
3. **Content management systems (CMS):** CMS platforms leverage Cassandra for its scalability and flexibility in managing unstructured or semi-structured data. It can be expecially useful when your CMS serves large-scale websites and applications with diverse content types.
4. **Distributed databases:** Cassandra is commonly used in scenarios where a decentralized and distributed database architecture is imperative. This can include environments with geographically dispersed data centres, or global deployments that require data replication across regions for improved availability and fault tolerance.
5. **Catalog and inventory systems:** Applications that handle cataloging and inventory management - such as e-commerce platforms - benefit from Cassandra's efficiency in handling large datasets, its dynamic and flexible schema design, and its low-latency access for real-time inventory updates.
6. **Message queues and communication platforms:** Chat applications, communication systems, and message queues all can benefit from Cassandra's ability to handle high-throughput, low-latency write operations, which ensures both real-time communication and relable message storage.

## Database Scalability?
- Scalability is the **ability to expand or contract the capacity of system resources in order to support the changing usage of your application**. This can refer both to increasing and decreasing usage of the application.
- Increased

## Vertical Scaling
- **Vertical Scaling,** (aka Scale up) refers to **increasing the processing power of a single server or cluster**. Both relational and non-relational databases can scale up, but eventually, there will be a limit in terms of maximum processing power and throughput. Additionally, there are increased costs with high-performance hardware.

## Pros and Cons of Vertical Scaling

### Pros
1. The main benefit of vertical scaling is that **nothing changes about your database infrastructure** other than the hardware specifications of the machine running the database.
2. As such, it's **transparent to the application**. The only difference is that you have more CPU's, memory, and/or storage space.
3. Vertical scaling is a good option to try **first if massive storage and processing are not required**.

---

## Horizontal Scaling

- **Horizontal scaling,** (aka scale-out) refers to bringing on additional nodes to share the load.
- This is difficult with relational databases due to the difficulty in spreading out related data across nodes.
- With non-relational databases, this is made simpler since collections are self-contained.

---

## Horizontal Scaling in MongoDB
In MongoDB, the horizontal scaling is done by 2 ways:
1. Sharding
2. Replica Sets

## Sharding
- Sharding is horizontal scaling by spreading data across multiple nodes. **Each node contains a subset of the overall data.**
- This is especially **effective where there are significant amounts of write operations,** as each operation only affects one of the nodes and the partition of data it is managing.

## Replica Sets
- In **Replica Sets** the **dataset is duplicated**.
- Replication allows for **high availability, redundancy/failover handling, and decreased bottlenecks on read operations**.
- However, they can also introduce issues for applications with large amounts of write transactions, as each update must be propagated over to every replica set member.

## Cluster

---

## Node

---

## Data Centre

---

## Rack

---

## VNode

---

## Cassandra on DataStrax

- Created a Database in Amazon Web Services
- The region is us-east-2
- To start, we clicked on CQL Console
- You should be in the CQL Editor environment first of Astra DB database of DataStax
---
```sql
create table  t1(a int, b int, c int); --- What happens????
```
We got an error after running above command:
```bash
"No keyspace has been specified. USE a keyspace, or explicitly specify keyspace.tablename"
```
Then run:
```sql
default_keyspace;
```

Again running the same create command, we get another error:
```bash
message="No PRIMARY KEY specifed for table 't1' (exactly one required)"
```
Now, we run:
```sql
create table t1(a int Primary Key, b int, c int);
```
There's no output that means the query has been executed successfully.

```sql
Insert into t1 Values(1, 100, 200);
```
```bash
SyntaxException: line 1:15 no viable alternative at input 'Values' (Insert into [t1] Values...)
```

Now, the correct syntax of Inserting Data into Table in Cassandra:
```sql
Insert into t1(a, b, c) Values(1, 100, 200);
```
No output but the query has been executed successfully.

```sql
Rollback;
```
```bash
SyntaxException: line 1:0 no viable alternative at input 'Rollback' ([Rollback]...)
```

Displaying table t1
```sql
select * from t1;
```
Output:
```bash
 a | b   | c
---+-----+-----
 1 | 100 | 200

(1 rows)
```

Adding record with same PRIMARY KEY value:

```sql
Insert into t1(a, b, c) Values(1, 500, 700);
select * from t1;
```
Output:
```bash
 a | b   | c
---+-----+-----
 1 | 500 | 700

(1 rows)
```

This is weird behavior. The value is getting overrided while we have PRIMARY KEY. This isn't the DRAWBACK of Cassandra.

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

Green color is for numeric value.
Yellow color is for text.
Red color is for PRIMARY KEY.
Purple color is for numeric column.
Blue color is for 

Query:
```sql
select * from transactions where amount > 4000;
```
```bash
"Cannot execute this query as it might involve data filtering and thus may have unpredictable performance. If you want to execute this query despite the performance unpredictability, use ALLOW FILTERING"
```

Correct Query:
```sql
select * from transactions where amount > 4000 Allow Filtering;
```
Output:
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```

```sql
select * from transactions where country = 'India';
```
Output:
```bash
 country | emailid   | amount | trid
---------+-----------+--------+------
   India | a@abc.com |   3000 |    1
   India | b@abc.com |   4000 |    2
```
Where clause can be used with Partition Key.
In other situations, we have to use ALLOW FILTERING.

The below query won't work:
```sql
select * from transactions where emailid = 'a@abc.com;
```

### Update Query

```sql
update transactions
set amount = 10000
where trid = 2;
```
We get error message:
```bash
message="Some partition key parts are missing: country"
```
WHERE clause can only contain PARTITION KEY OR COMPOUND KEY to work in Cassandra.

Corrected Query:

```sql
update transactions
set amount = 10000
where country = 'India' and emailid = 'b@abc.com';

select * from transactions;
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

### Delete Query

```sql
delete from transactions
where country = 'India' and emailid = 'b@abc.com';

select * from transactions;
```
Output:
```bash
 country   | emailid   | amount | trid
-----------+-----------+--------+------
     India | a@abc.com |   3000 |    1
 Australia | c@abc.com |   9000 |    3
 Australia | d@abc.com |  10000 |    4
```

`NOT NULL, UNIQUE KEY, CHECK CONSTRAINT, DEFAULT and FOREIGN KEY is not present and supported in Cassandra.`

## TTL (Time-To-Live) in Cassandra

TTL (Time-To-Live) in Cassandra is a feature that allows you to set an expiration time (in seconds) for data. After the TTL expires, the data is automatically deleted without requiring manual deletion.

### How TTL Works?
- When inserting or updating a row, you can specify a TTL value in seconds.
- Once the TTL expires, the row is marked as deleted and will be removed permanently after the next comparision

TTL can also be used with UPDATE.

























































































































































































































































