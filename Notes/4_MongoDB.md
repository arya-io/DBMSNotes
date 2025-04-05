# 🚀 Introducing MongoDB

- **MongoDB** is a **NoSQL** database.
- It belongs to the category of **Document Databases**.
- MongoDB is written in **C++**.
- Commonly used as **backend database software** by many web applications.

---

## 📄 What are Document Databases?

- A **Document Database** stores data in **documents**, not in traditional rows and columns.
- They are considered **non-relational** databases.
- Data is stored in **flexible**, semi-structured formats (e.g., JSON, BSON, or XML).
- Suitable for storing complex hierarchical data.

---

## 🧾 What are Documents?

- A **document** is a **record** in a document database.
- It typically stores information about **one object**, along with related **metadata**.
- Documents store data as **field-value pairs**.
- Field values can be of various types and structures:
  - Strings
  - Numbers
  - Dates
  - Arrays
  - Nested objects

📦 Documents are usually stored in formats like:
- **JSON**
- **BSON**
- **XML**


## 🔁 SQL vs NoSQL Terminologies

| 💾 **SQL (RDBMS)**   | 📂 **MongoDB (NoSQL)**          |
|----------------------|-------------------------------|
| **Table**            | **Collection**                |
| **Row**              | **Document**                  |
| **Column**           | **Field**                     |
| **Primary Key**      | **ObjectId** (also known as `_id`) |
| **Index**            | **Index**                     |
| **View**             | **View**                      |

---

🧠 **Quick Notes:**

- In MongoDB, each document is a JSON-like structure stored in a **collection**.
- The `_id` field is automatically generated if not provided and uniquely identifies each document — just like a **Primary Key**.
- Collections in MongoDB are schema-less, meaning each document can have a different structure.


## 🔍 Relational vs Document Model

| 🧱 **Relational Model**                | 📄 **Document Model**                      |
|---------------------------------------|--------------------------------------------|
| Data is stored in **tables (rows and columns)** | Data is stored as **documents (JSON/BSON)** |
| Has a **fixed schema**                | **Schema-less** or flexible schema          |
| Uses **SQL** for querying             | Uses **MongoDB Query Language (MQL)**       |
| **Joins** are used to relate tables   | Embedding or referencing is used            |
| Ideal for **structured data**         | Great for **semi-structured or nested data**|

---

### 🧾 Relational Data Model
- Stores data in **tabular form**.
- Each table represents an entity.
- Columns define attributes, and rows store individual records.

### 📄 Document Store Model
- Stores data in the form of **documents**.
- Documents are **key-value pairs** similar to JSON.
- More **flexible and scalable**, especially when dealing with varied data structures.

🧠 **Pro Tip**: 
Use the **Relational Model** when data relationships are complex and require strict schema enforcement.  
Use the **Document Model** when working with hierarchical, nested, or frequently evolving data.

## ✅ Advantages of Document Databases

- 🧠 An **intuitive data model** that is fast and easy for developers to work with.
- 🔄 A **flexible schema** that allows the data model to evolve as **application needs change** — unlike rigid RDBMS schemas.
- 📝 A document's schema is **dynamic and self-describing** — developers don't need to pre-define it before inserting data.
- 🎯 **Not all documents in a collection need to have the same fields**, making it ideal for storing varied or evolving data structures.
- 🛠️ Developers can **modify the structure anytime**, avoiding complex and disruptive schema migrations.
- 🚀 The ability to **horizontally scale out**, which means you can handle more data and traffic by simply adding more servers.

---

🧠 **Why it matters?**
Document databases like MongoDB give developers the **freedom and agility** to build modern applications faster — without being slowed down by rigid schemas or performance bottlenecks that come with traditional relational databases.

## ⚠️ Drawbacks of Document Databases

- 🔐 **No Inherent Security Mechanism**
  - Unlike SQL databases, document databases **do not support built-in commands like `GRANT` or `REVOKE`** for access control.
  - Security must be implemented **manually via application logic** or external configurations.

- 🚫 **No Built-in Data Validation**
  - There is **no strict schema enforcement**, meaning invalid or inconsistent data can be inserted unless validation is handled manually.
  - It's more flexible but **puts the burden on the developer** to maintain data consistency.

- ⚙️ **Not Ideal for Complex Queries**
  - Document databases are **not optimized for running multiple joins, aggregations, or complex transactions** like relational databases.
  - Designed for **performance and scalability**, not complex business logic across multiple collections.

---

🧠 **Note:** 
While these drawbacks exist, document databases like MongoDB are still **powerful tools** when used in the right context — especially for projects requiring flexibility, speed, and scale.


## 📚 Use Cases of Document Databases

Document databases like **MongoDB** are well-suited for applications that require **flexibility, scalability, and high performance**. Below are some common real-world use cases:

---

### 🛒 Large eCommerce Platforms
- Example: **Amazon**
- Store complex product details with varying attributes.
- Dynamic schema supports frequent changes to product data structures.

---

### ✍️ Blogging & Microblogging Platforms
- Example: **Twitter**, **Medium**
- Ideal for storing posts, comments, likes, user metadata.
- Each document can represent a blog post with nested data like tags, authors, reactions, etc.

---

### 🗂️ Content Management Systems (CMS)
- Examples: **WordPress**, **Windows Registry**
- Store unstructured and semi-structured content.
- Flexible schema allows rapid iteration of layouts, templates, and metadata.

---

### 🌐 IoT (Internet of Things)
- Store real-time data streams from connected devices.
- Great for handling **varied device data** structures and **high insert rates**.

---

### 🛍️ Product Catalogs
- Varying attributes per product (e.g., size, color, specs).
- Documents can easily model **rich, hierarchical product data**.

---

### 💳 Payment Processing
- Store **transaction logs**, **user payments**, **audit trails**.
- Flexible and performant for writing large volumes of data quickly.

---

### 📊 Real-Time Analytics & Live Streaming
- Handle large streams of **text, video, audio, images**.
- Useful for logging, media processing, telemetry, etc.

---

✅ **Why Suitable?**
- Flexible schema
- Easy to scale horizontally
- High write performance
- Schema-less design fits evolving application needs


## 🐚 Mongo Shell

The **Mongo Shell** is an interactive JavaScript interface to MongoDB. It allows you to query and manipulate data directly using JavaScript syntax.

---

### 🔹 Key Features:
- Provides a **JavaScript API** to perform database operations.
- Allows direct execution of commands like `insert()`, `find()`, `update()`, etc.
- Great for testing queries and exploring databases quickly.

---

### 🔸 Important Variable: `db`

- `db` is a **built-in variable** in the shell that **references the current database**.
- When you switch databases using the `use <database_name>` command, the `db` variable automatically updates.

```javascript
use mydb3    // Switches to mydb3 database
db           // Now points to mydb3
```

## 💡 Quick Commands in Mongo Shell

| **Command**            | **Description**                                      |
|------------------------|------------------------------------------------------|
| `show dbs`             | List all databases                                   |
| `use mydb3`            | Switch to (or create) a database named `mydb3`       |
| `db`                   | Show the current active database                     |
| `show collections`     | List all collections in the current database         |

---

✅ **Note:**  
The traditional **Mongo shell** is being replaced by **MongoDB Shell (`mongosh`)** in newer MongoDB versions.  
However, the **commands and functionality remain mostly the same**, just with improved features and support.

## 🖥️ Mongo Shell Steps

- If you want to connect to the **local MongoDB server**, just press `ENTER` when starting the shell.
- **`test`** is the default database that is automatically created during MongoDB installation.

---

### 🔍 To view all available databases:
```bash
show dbs
```

## ➕ Creating or Switching to a Database

```bash
use x100
```

## 📂 Lazy Creation of Databases in MongoDB

If a database with the name `x100` does not exist, MongoDB will **create it automatically** when you run:

## 🔄 Lazy Creation Approach in MongoDB

- MongoDB **does not create the database on disk immediately** when you run the `use` command.
- The database is **officially created only** when:
  - A **document is inserted**, or
  - A **collection is added**.

📝 **Note:**
Simply switching to a database using `use <db_name>` does **not persist it to disk** until some actual data (a document or collection) is inserted.

  
## ➕ Creating a Collection and Inserting Documents in MongoDB

- The next step after switching/creating a database is to **create a collection** and add **documents** to it.

### 📥 Example:
```bash
db.Emp5.insert({"empno": 1, "ename": "Smith", sal: 6000});
```

🔍 **Breakdown**:

- `Emp5` is the **collection name**.
- `{"empno": 1, "ename": "Smith", sal: 6000}` is the **document** being inserted.
- Use **double quotes** around field names — especially helpful when field names contain **spaces** or **special characters**.

---

✅ **Output:**
```bash
{
  acknowledged: true,
  insertedIds: { '0': ObjectId('67ecb69aa646f14991b71236') }
}
```

- `ObjectId` is the **auto-generated unique ID** assigned by MongoDB to the inserted document.

🧠 **Tip**: MongoDB automatically **creates the collection (`Emp5`)** if it doesn’t already exist when you insert the first document into it.

  
## ➕ Adding Another Document to a Collection

To insert a new document into the `Emp5` collection:

```bash
db.Emp5.insert({"empid": 2, "name": "Martin", bonus: 7000, incentive: 500});
```

## 📌 Explanation

- `Emp5` is the name of the collection.
- The inserted document contains the fields: `empid`, `name`, `bonus`, and `incentive`.
- Note that this document doesn't have the same schema (field names) as the first one — and that’s **perfectly fine** in MongoDB.
- MongoDB supports **flexible schemas**, meaning **not all documents** in a collection are required to have the same fields.

🧠 **Tip (from ChatGPT):**
> MongoDB is **schema-less at the collection level** — it allows different structures for different documents in the same collection. This is very powerful for **agile development**, where data requirements change frequently.

---

## 🔎 Retrieving All Documents from a Collection

To retrieve documents from the `Emp5` collection:

```bash
db.Emp5.find();
```

## 🧠 Explanation:

This is equivalent to:

```sql
SELECT * FROM Emp5;
```

In MongoDB:
```bash
db.Emp5.find();
```

## 🔍 Retrieving All Documents from a Collection

When no parameters are passed to `find()`, MongoDB returns **all documents** from the collection — similar to SQL's `SELECT *`.

### ✅ Output Example:
```bash
[
  {
    _id: ObjectId('67ecb6b0a646f14991b71237'),
    empno: 1,
    ename: 'Smith',
    sal: 6000
  },
  {
    _id: ObjectId('67ecb9daa646f14991b71238'),
    empid: 2,
    name: 'Martin',
    bonus: 7000,
    incentive: 500
  }
]
```

## 🧠 Quick Recap

- `_id` is automatically added by MongoDB as a **unique identifier** for each document.
- **Document structure can differ** between entries in the same collection:
  - One document has: `empno`, `ename`, `sal`
  - Another document has: `empid`, `name`, `bonus`, `incentive`
- This flexibility is possible because **MongoDB uses a flexible schema**, which supports:
  - ✅ Semi-structured data
  - 🔁 Evolving data formats
  - ⚡ Rapid application development

---

## 📚 SQL vs MongoDB: Terminology Comparison

| SQL Term              | MongoDB Equivalent       |
|-----------------------|--------------------------|
| `SELECT * FROM Emp5`  | `db.Emp5.find()`         |
| Row                   | Document                 |
| Table                 | Collection               |
| Primary Key           | `_id` (auto-generated)   |


# 🗃️ MongoDB Notes: Creating and Inserting into a Collection

> **Important:** Keywords in **MongoDB are case-sensitive**.  
> Always use the correct casing for commands and field names (e.g., `find()` is not the same as `Find()`).

---

## 📌 Creating a Collection and Inserting Documents

We are creating a new collection named `Emp6` and inserting employee records into it.

```js
db.Emp6.insert({ "empno": 1, "ename": "Smith", sal: 6000 });
db.Emp6.insert({ "empno": 2, "ename": "Martin", sal: 7000 });
db.Emp6.insert({ "empno": 3, "ename": "James", sal: 5000 });
db.Emp6.insert({ "empno": 4, "ename": "King", sal: 4000 });
```

> ✅ **Note:** MongoDB does not require you to explicitly create a collection.  
> It is automatically created when you first insert a document.

---

## 🔍 Fetching All Documents

Use the `find()` method to retrieve all documents from the collection:

```js
db.Emp6.find();
```

### 📤 Sample Output

```json
[
  {
    _id: ObjectId("67ecc514a646f14991b71239"),
    empno: 1,
    ename: "Smith",
    sal: 6000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123a"),
    empno: 2,
    ename: "Martin",
    sal: 7000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123b"),
    empno: 3,
    ename: "James",
    sal: 5000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123c"),
    empno: 4,
    ename: "King",
    sal: 4000
  }
]
```

## 💡 Tips

- Each inserted document automatically gets a unique `_id` field generated by MongoDB.
- You can also use `insertMany()` instead of multiple `insert()` calls when inserting multiple documents at once:

```js
db.Emp6.insertMany([
  { empno: 1, ename: "Smith", sal: 6000 },
  { empno: 2, ename: "Martin", sal: 7000 },
  { empno: 3, ename: "James", sal: 5000 },
  { empno: 4, ename: "King", sal: 4000 }
]);
```

## 🔍 Using Filters and Projections in `find()`

You can use parameters inside the `find()` method for **filtering** and **projecting** specific fields.

---

### 🟢 Example 1: Basic `find()` with Empty Filter

```bash
db.Emp6.find({});
```

## 🔍 Using Filters and Projections in `find()`

This returns **all documents** from the `Emp6` collection — just like `db.Emp6.find()` — because the filter object is empty:

```js
db.Emp6.find({});
```

### 🟢 Example 2: `find()` with Projection

```js
db.Emp6.find({}, { ename: 1 });
```

### 📌 Understanding Parameters in `find()` with Projection

- The first parameter `{}` is the **filter** — here, we are not applying any conditions.
- The second parameter `{ ename: 1 }` is the **projection**, which tells MongoDB to return **only the `ename` field**.
- MongoDB includes the `_id` field by default unless explicitly excluded.

---

### 📤 Sample Output

```json
[
  { _id: ObjectId("67ecc514a646f14991b71239"), ename: "Smith" },
  { _id: ObjectId("67ecc515a646f14991b7123a"), ename: "Martin" },
  { _id: ObjectId("67ecc515a646f14991b7123b"), ename: "James" },
  { _id: ObjectId("67ecc515a646f14991b7123c"), ename: "King" }
]
```

> 🧠 **Tip:** To exclude the `_id` field from the output, set `_id: 0` in the projection:

```js
db.Emp6.find({}, { ename: 1, _id: 0 });
```

This command will return only the `ename` values without the `_id` field.

```json
[
  { ename: "Smith" },
  { ename: "Martin" },
  { ename: "James" },
  { ename: "King" }
]
```

### 🟢 Example 3: Displaying Multiple Fields for All Documents

To retrieve multiple specific fields from all documents in a collection, you can pass a projection object with those field names set to `1` (or any truthy number like `2` — MongoDB treats any non-zero value the same in projection).

```js
db.Emp6.find({}, { ename: 1, sal: 2 });
```

✅ **Note:** `sal: 2` behaves the same as `sal: 1` here — any non-zero number includes the field.

---

### 📤 Sample Output

```json
[
  {
    _id: ObjectId("67ecc514a646f14991b71239"),
    ename: "Smith",
    sal: 6000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123a"),
    ename: "Martin",
    sal: 7000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123b"),
    ename: "James",
    sal: 5000
  },
  {
    _id: ObjectId("67ecc515a646f14991b7123c"),
    ename: "King",
    sal: 4000
  }
]
```

> 🧠 **Tip:** If you want to hide the `_id` field as well, just set `_id: 0` in the projection:

```js
db.Emp6.find({}, { ename: 1, sal: 1, _id: 0 });
```

---

### 🧾 Excluding the `_id` Field in Projection

To exclude the `_id` field from the result (so that the ObjectId does not appear), set `_id: 0` in the projection object.

```bash
db.Emp6.find({}, { ename: 1, sal: 2, _id: 0 });
```

✅ **Note:** `sal: 2` works the same as `sal: 1` — any non-zero value includes the field.

---

### 📤 Output

```json
[
  { "ename": "Smith", "sal": 6000 },
  { "ename": "Martin", "sal": 7000 },
  { "ename": "James", "sal": 5000 },
  { "ename": "King", "sal": 4000 }
]
```

⚠️ **Important Rule:**  
Mixing field **inclusion (`1`)** and **exclusion (`0`)** in the same projection is **not allowed**,  
**except** for the `_id` field.

---

✅ **Valid Example:**

```js
{ ename: 1, sal: 1, _id: 0 }
```

❌ **Invalid Example:**

```js
{ ename: 1, sal: 0 }
```

### 📌 Filtering Rows and Columns

MongoDB’s `find()` method follows this syntax:

```js
find(<document filter>, <projection filter>)
```

### 🔍 Filtering Rows and Columns in MongoDB

- **Document Filter**: Similar to the `WHERE` clause in SQL — used to filter rows/documents.
- **Projection Filter**: Similar to the `SELECT column_list` in SQL — used to choose which fields/columns to display.

---

#### 📌 Display documents having salary greater than 5000

```js
db.Emp6.find({ "sal": { $gt: 5000 } });
```

### 📤 Sample Output:

```json
[
  {
    "_id": ObjectId("67ecc514a646f14991b71239"),
    "empno": 1,
    "ename": "Smith",
    "sal": 6000
  },
  {
    "_id": ObjectId("67ecc515a646f14991b7123a"),
    "empno": 2,
    "ename": "Martin",
    "sal": 7000
  }
]
```

💡 **Note:**

- `$gt` → *greater than*
- `$lt` → *less than*
- `$gte` → *greater than or equal to*
- `$lte` → *less than or equal to*
- `$eq` → *equal to*
- `$ne` → *not equal to*

🔍 **Output without ObjectID**

You can exclude the `_id` field from the result by setting `_id: 0` in the projection:

```js
db.Emp6.find({ "sal": { $gt: 5000 } }, { _id: 0 });
```

### 📤 Sample Output:

```json
[
  { "empno": 1, "ename": "Smith", "sal": 6000 },
  { "empno": 2, "ename": "Martin", "sal": 7000 }
]
```

### 🔍 Case-Insensitive Search in MongoDB

```js
db.Emp6.find({ "ename": { $eq: "SMITH" } });
```

❌ This query will not work if the stored value is `"Smith"` (mixed case) and you're querying in all uppercase:

```js
db.Emp6.find({ "ename": { $eq: "SMITH" } });
```

✅ To perform a **case-insensitive search**, use a **regular expression** with the `i` (ignore case) flag:

```js
db.Emp6.find({ "ename": /smith/i });
```

### 📤 Sample Output:
```
[
  {
    "_id": ObjectId("67ecc514a646f14991b71239"),
    "empno": 1,
    "ename": "Smith",
    "sal": 6000
  }
]
```

✅ The below query will work successfully because the case in the query matches the case stored in the document:

```js
db.Emp6.find({ "ename": { $eq: "Smith" } });
```

### 📤 Output:
```json
[
  {
    "_id": ObjectId("67ecc514a646f14991b71239"),
    "empno": 1,
    "ename": "Smith",
    "sal": 6000
  }
]
```

### 🔍 Finding a Value in Uppercase

You can use JavaScript's `toUpperCase()` method in the MongoDB shell to convert a string to uppercase before querying:

```js
db.Emp6.find({ "ename": "smith".toUpperCase() });
```

✅ This will effectively search for:

```js
db.Emp6.find({ "ename": "SMITH" });
```

📌 It will return a document **only if** `'SMITH'` exists in the collection **exactly in uppercase**.

📂 **Note:** A new `Employees` collection has been added in MongoDB.  
📝 The queries are referenced from shared Drive resources.


### 🔍 Which employees have names matching either **"ROGER"** or **"MARTIN"?  

```bash
db.Employees.find({ "ENAME": { $in: ["ROGER", "MARTIN"] } });
```

### 📤 Sample Output:

```json
[
  {
    "_id": ObjectId("67ecd251a646f14991b7123d"),
    "EMPNO": 1,
    "ENAME": "ROGER",
    "JOB": "ANALYST",
    "SAL": 3500,
    "DEPTNO": 10
  },
  {
    "_id": ObjectId("67ecd251a646f14991b71249"),
    "EMPNO": 13,
    "ENAME": "MARTIN",
    "JOB": "SALESMAN",
    "SAL": 1250,
    "DEPTNO": 20
  }
]
```

✅ Note: The $in operator checks if the field matches any value from the given array.

### 🔍 Find Employees with Names Matching "ROGER" or "MARTIN"

```bash
db.Employees.find({ "ENAME": { $in: ["ROGER", "MARTIN"] } });
```

### 📤 Sample Output:
```json
[
  {
    "_id": ObjectId("67ecd251a646f14991b7123d"),
    "EMPNO": 1,
    "ENAME": "ROGER",
    "JOB": "ANALYST",
    "SAL": 3500,
    "DEPTNO": 10
  },
  {
    "_id": ObjectId("67ecd251a646f14991b71249"),
    "EMPNO": 13,
    "ENAME": "MARTIN",
    "JOB": "SALESMAN",
    "SAL": 1250,
    "DEPTNO": 20
  }
]
```

🧠 **Concepts Covered:**

The `$in` operator is used to check if a field matches any value from a specified list.

It works like the **SQL IN** clause:

```sql
-- SQL
WHERE ENAME IN ('ROGER', 'MARTIN')
```

✅ **Note:**  
You can also use single quotes instead of double quotes — both are valid in JavaScript:

```bash
db.Employees.find({ "ENAME": { $in: ['ROGER', 'MARTIN'] } });
```

🔎 **Tip:**  
MongoDB is case-sensitive by default, so `"ROGER"` will not match `"Roger"`.  
To make a case-insensitive search, use a regular expression with the `i` flag:

```bash
db.Employees.find({ "ENAME": /roger/i });
```

🔄 **Opposite of `$in`: `$nin`**

The `$nin` operator in MongoDB stands for **"not in"** — it is the exact opposite of `$in`.

It returns all documents where the field's value **does not match** any value in the specified array.

📘 **Syntax Example:**

```bash
db.Employees.find({ "ENAME": { $nin: ['ROGER', 'MARTIN'] } });
```

This query will return **all employees except** those whose `ENAME` is `'ROGER'` or `'MARTIN'`.

✅ **Note:**  
Just like `$in`, `$nin` also works with both **strings** and **numbers**.

🔎 **Tip:**  
- If you're filtering a **large collection** and using `$nin`, consider **indexing** the field you're querying for better performance.  
- `$nin` does **not** match documents where the field is **missing** or contains **`null`**, unless `null` is explicitly included in the list.

🧠 **Quick Revision:**

- `$in`: matches **any** of the values.  
- `$nin`: **excludes** all the listed values.

```pgsql
-- Example (conceptual, not actual PostgreSQL syntax)
-- Think of it like:
SELECT * FROM Employees WHERE ENAME NOT IN ('ROGER', 'MARTIN');
```

### 🔀 Logical `$and` / `$or` Operators in MongoDB

#### ❓ **Which employees work as clerks and have a salary less than 1200?**

You can use the `$and` operator to combine multiple conditions in a MongoDB query:

```bash
db.Employees.find({ 
  $and: [
    { JOB: "CLERK" }, 
    { SAL: { $lt: 1200 } }
  ]
});
```

**🟢 Output:**
```bash
[
  {
    _id: ObjectId('67ecd251a646f14991b71244'),
    EMPNO: 8,
    ENAME: 'ADAMS',
    JOB: 'CLERK',
    SAL: 1100,
    DEPTNO: 20
  },
  {
    _id: ObjectId('67ecd251a646f14991b71245'),
    EMPNO: 9,
    ENAME: 'JAMES',
    JOB: 'CLERK',
    SAL: 950,
    DEPTNO: 30
  },
  {
    _id: ObjectId('67ecd251a646f14991b71246'),
    EMPNO: 10,
    ENAME: 'MARY',
    JOB: 'CLERK',
    SAL: 1000,
    DEPTNO: 30
  }
]
```

✅ **Note:**  
`$and` is **implicit** in MongoDB — if you pass multiple key-value pairs in the same object, MongoDB treats it as an **AND query** by default.

You only need `$and` when combining more **complex conditions**, like multiple comparisons or logical operators together.

🧠 **Quick Example Without `$and`:**

```bash
db.Employees.find({ JOB: "CLERK", SAL: { $lt: 1200 } });
```

It does the **same thing** as the earlier `$and` query.

#### 📋 Display `ENAME` and `JOB` for employees earning salary less than 1200 from job type "CLERK".  
Do **not** show the `_id` field in the output.

```bash
db.Employees.find(
  { $and: [{ JOB: "CLERK" }, { SAL: { $lt: 1200 } }] },
  { "ENAME": 1, "JOB": 1, _id: 0 }
);
```

**🟢 Output:**
```bash
[
  { ENAME: 'ADAMS', JOB: 'CLERK' },
  { ENAME: 'JAMES', JOB: 'CLERK' },
  { ENAME: 'MARY', JOB: 'CLERK' }
]
```

✅ **Note:**  
The **second parameter** in the `find()` function is the **projection** — it controls which fields are **included** or **excluded** in the result.

- Setting `_id: 0` ensures that the default `_id` field is **not returned**.
- Field values `1` (or `true`) **include** a field.
- Field values `0` (or `false`) **exclude** a field.

🧠 **Quick Tip:**  
You can also use **dot notation** in projection to include **nested fields** if needed.

```bash
// Example with nested projection
db.Employees.find({}, { "address.city": 1, _id: 0 });
```

###### 📄 With Salary:

```bash
db.Employees.find(
  { $and: [{ JOB: "CLERK" }, { SAL: { $lte: 1200 } }] },
  { "ENAME": 1, "JOB": 1, "SAL": 1, _id: 0 }
);
```

**🟢 Output:**
```bash
[
  { ENAME: 'ADAMS', JOB: 'CLERK', SAL: 1100 },
  { ENAME: 'JAMES', JOB: 'CLERK', SAL: 950 },
  { ENAME: 'MARY', JOB: 'CLERK', SAL: 1000 }
]
```

✅ **Note:**

- The `$lte` operator means **"less than or equal to"** (equivalent to `<=` in SQL).
- In the **projection**, `"SAL": 3` works because MongoDB treats any **truthy number** as a signal to include the field.
- However, using `1` is the **standard and recommended practice** for clarity and consistency.

🧠 **Best Practice:**  
Stick to `1` for including fields and `0` for excluding them to keep your queries clean and easy to read.

### 🔁 OR Operator

The `$or` operator in MongoDB is used to **match documents that satisfy at least one** of the given conditions.

#### 🧪 Example 1:

```bash
db.Employees.find({ 
  $or: [
    { JOB: "CLERK" }, 
    { SAL: { $lt: 1200 } }
  ]
});
```

### 🧪 Example 2 (With Projection):

```bash
db.Employees.find(
  { 
    $or: [
      { JOB: "CLERK" }, 
      { SAL: { $lte: 1200 } }
    ] 
  },
  { "ENAME": 1, "JOB": 1, "SAL": 1, _id: 0 }
);
```

**🟢 Output:**
```bash
[
  { ENAME: 'MILLER', JOB: 'CLERK', SAL: 1300 },
  { ENAME: 'JULIE', JOB: 'CLERK', SAL: 1500 },
  { ENAME: 'SMITH', JOB: 'CLERK', SAL: 4500 },
  { ENAME: 'ADAMS', JOB: 'CLERK', SAL: 1100 },
  { ENAME: 'JAMES', JOB: 'CLERK', SAL: 950 },
  { ENAME: 'MARY', JOB: 'CLERK', SAL: 1000 }
]
```

✅ **Note:**

- `$or` matches **any document** that satisfies **at least one** of the conditions.
- Just like SQL's `OR`, it’s useful when multiple **alternate conditions** should result in a match.

🧠 **SQL Equivalent:**

```sql
SELECT ENAME, JOB, SAL 
FROM Employees 
WHERE JOB = 'CLERK' OR SAL <= 1200;
```

## 🔧 CRUD Operations in MongoDB

CRUD stands for:

- **C**: Create (Insert documents)
- **R**: Read (Query documents)
- **U**: Update (Modify documents)
- **D**: Delete (Remove documents)

MongoDB provides built-in methods to perform each of these operations efficiently.

---

### 1️⃣ Create — `insertOne()` / `insertMany()`

```bash
// Insert a single document
db.Employees.insertOne({
  EMPNO: 101,
  ENAME: "ALICE",
  JOB: "MANAGER",
  SAL: 5000,
  DEPTNO: 10
});

// Insert multiple documents
db.Employees.insertMany([
  { EMPNO: 102, ENAME: "BOB", JOB: "CLERK", SAL: 1200, DEPTNO: 20 },
  { EMPNO: 103, ENAME: "CAROL", JOB: "ANALYST", SAL: 3000, DEPTNO: 30 }
]);
```

### 2️⃣ Read — `find()` / `findOne()`
```bash
// Find all documents
db.Employees.find();

// Find one document
db.Employees.findOne({ ENAME: "ALICE" });
```

### 3️⃣ Update — `updateOne()` / `updateMany()`
```bash
// Update a single document
db.Employees.updateOne(
  { ENAME: "BOB" },
  { $set: { SAL: 1500 } }
);

// Update multiple documents
db.Employees.updateMany(
  { JOB: "CLERK" },
  { $inc: { SAL: 100 } }
);
```

### 4️⃣ Delete — `deleteOne()` / `deleteMany()`
```bash
// Delete a single document
db.Employees.deleteOne({ ENAME: "ALICE" });

// Delete multiple documents
db.Employees.deleteMany({ JOB: "CLERK" });
```

✅ **Note:**

- MongoDB operations are **schema-less**, meaning you can insert documents with varying fields.  
  However, for **cleaner querying and maintainability**, it's best to follow a **consistent document structure**.

- Use `.pretty()` with `find()` for more **readable and formatted output** in the Mongo shell:

```bash
db.Employees.find().pretty();
```

## 🗃️ MongoDB Collections

- A **collection** in MongoDB is similar to a **table** in an RDBMS.
- MongoDB collections **do not enforce schemas** — meaning documents in the same collection can have different structures.
- Each MongoDB **collection** can hold multiple **documents**. A **document** is equivalent to a **row** in an RDBMS table.

---

### 📦 Creating a Collection

To create a collection explicitly, use:

```bash
db.createCollection("Emp100");
```

**🟢 Output:**
```bash
{ ok: 1 }
```

✅ **Note:**

- In practice, you usually **don't need to manually create a collection**.
- MongoDB will **automatically create** a collection when you insert the first document into it.

```bash
// Implicit collection creation
db.NewCollection.insertOne({ name: "Test" });
```

🧾 **To list all collections in the current database:**

```bash
show collections
```

## 📂 Listing All the Collections

Shows all collections in the **current database**:

```bash
show collections;
```

**🟢 Output:**
```bash
Emp100
Emp5
Emp6
Employees
```

➡️ We have 4 collections in the `x100` database.

##### 🗑️ To Delete a Collection:

Use the `.drop()` method on the collection you want to remove:

```bash
db.Emp100.drop();
```

**🟢 Output:**
```bash
true
```

✅ **Note:**

- This command **permanently deletes** the entire collection and all its documents.
- ⚠️ **Use with caution — there's no undo!**


### ✅ Behavior of `drop()` in MongoDB

Using `db.Emp108.drop();` multiple times will return `true` even if the collection does not exist.

```bash
db.Emp108.drop(); // returns true
db.Emp108.drop(); // also returns true
```

🧠 **Why?**

- MongoDB interprets the `drop()` command as successfully **ensuring the collection no longer exists**.
- If the collection is **already absent**, the operation still returns `true`.
- This behavior eliminates the need for **pre-checks**, simplifying **scripting** and **automation**.

✅ **Note:**

> The `drop()` command is **idempotent** — calling it multiple times has the same effect as calling it once.

---

### 🧭 Database → Collection → Documents

- A **Database** contains one or more **Collections**.
- A **Collection** holds multiple **Documents**.
- This structure is the MongoDB equivalent of:

**Database → Table → Rows (in traditional RDBMS)**


---

## 📦 BSON (Binary JSON)

- MongoDB stores data in a format called **BSON (Binary JSON)**.
- BSON extends JSON by supporting **additional data types** such as:
  - `Date`
  - `ObjectId`
  - `Binary`
  - `Decimal128`, etc.
- It is **efficient** for both **storage** and **network transmission**.
- Internally, MongoDB uses **BSON** for storing and transferring documents, even though you interact with them using **JSON-like syntax**.

✅ **Example MongoDB Document:**

```json
{
  "_id": ObjectId("624f8fba9f1b8c001c8e4d9c"),
  "name": "Alice",
  "age": 30,
  "joined": ISODate("2023-06-15T00:00:00Z")
}
```

You can use typeof checks and shell methods like ObjectId.isValid() when working with these types in queries or applications.

🧠 **Tip:**

You can use `typeof` checks and shell methods like:

```js
ObjectId.isValid("624f8fba9f1b8c001c8e4d9c")
```
**to validate or work with special BSON types** (like `ObjectId`) in queries or applications.

## 📝 Inserting Documents into a Collection

MongoDB provides the following methods to insert documents into a collection:

### 1. `insertOne()`

- Inserts a **single document** into a collection.

```bash
db.Employees.insertOne({ ENAME: "JACK", JOB: "CLERK", SAL: 1300 });
```

### 2. `insert()`

- Can insert **one or more documents**.
- This is the **older method**, still supported for **backward compatibility**.
- Works like `insertMany()` if passed an array.

```bash
// Single document
db.Employees.insert({ ENAME: "LUCY", JOB: "MANAGER", SAL: 5000 });

// Multiple documents
db.Employees.insert([
  { ENAME: "TINA", JOB: "CLERK", SAL: 1200 },
  { ENAME: "ROB", JOB: "SALESMAN", SAL: 2200 }
]);
```

✅ **Note:**  
There’s no functional difference between `insert()` and `insertMany()` when inserting multiple documents —  
but `insertMany()` is **preferred in modern code** for clarity and consistency.

---

### 3. `insertMany()`

- Explicitly used to insert **multiple documents at once**.
- Requires passing an **array of objects**.

```bash
db.Employees.insertMany([
  { ENAME: "MARK", JOB: "ANALYST", SAL: 4000 },
  { ENAME: "NINA", JOB: "CLERK", SAL: 1100 }
]);
```

🧠 **Tip:**  
All three methods return an **acknowledgment** with the inserted **ID(s)**.

To view the inserted documents in a clean and readable format, use:

```bash
db.Employees.find().pretty()
```

## Insert `_id` Manually

You can explicitly define the `_id` field while inserting documents. This is useful when you want to control the primary key yourself.

```bash
db.Emp201.insertMany(
  [
    {
      _id: "1",
      ename: "John"
    },
    {
      _id: "2",
      ename: "Martin"
    }
  ]
);
```

Output:
```bash
{ acknowledged: true, insertedIds: { '0': '1', '1': '2' } }
```

✅ **Note:**  
- If you insert documents with the same `_id` again, **MongoDB will throw a duplicate key error**.
- The `_id` field can be of **any data type** (e.g., string, number, ObjectId, etc.),  
  but it **must be unique** within the collection.

## `findOne()`

- The `findOne()` method returns the **first document** from a collection if **no parameter** is passed.

```bash
db.employees.findOne()
```

You can also pass a **query** to return the **first matching document**.

The following example finds the **first document** where `salary` is greater than 2000:

```bash
db.employees.findOne({ salary: { $gt: 2000 } })
```

✅ **Note:**  
Unlike `find()`, which returns a **cursor** to all matching documents,  
`findOne()` returns **only a single document** — the **first match** it finds.


## `find()`

The `find()` method retrieves **all documents** that match the specified criteria and returns a **cursor object**.  
The cursor is a pointer to the result set and can be iterated over to access each document.

### 📌 Example 1:  
Return all employees with a salary of `8000`:

```bash
db.employees.find({ salary: 8000 })
```

📌 **Example 2:**  
Return all employees whose salary is **greater than 4500** and **less than 10000**:

```bash
db.employees.find({ salary: { $gt: 4500, $lt: 10000 } })
```

✅ **Note:**

- The **cursor** returned by `find()` can be:
  - Iterated using `.forEach()`  
  - Converted into an array using `.toArray()` (in drivers like Node.js, Python, etc.)

- Use `find().pretty()` in the **Mongo shell** for a more readable and well-indented output.

## Sorting

```bash
db.Employees.find().sort({ ENAME: 1 });
```

🔽 **Output:**  
Data is sorted according to the names of employees — i.e., sorted by `ENAME` in **ascending** order.

---

🧠 **Syntax of `sort()`:**

```javascript
sort({ FieldName: SortingOrder });
```

### 🔃 Sorting in MongoDB

**Sorting Order:**

- `1` for **Ascending order** (A → Z / 0 → 9)  
- `-1` for **Descending order** (Z → A / 9 → 0)

---

✅ **Example (Descending by ENAME):**

```bash
db.Employees.find().sort({ ENAME: -1 });
```

🧠 **Tip: Sorting by Multiple Fields**

You can sort by multiple fields as well. For example:

```bash
db.Employees.find().sort({ DEPTNO: 1, SAL: -1 });
```

This query:

- Sorts `DEPTNO` in **ascending** order.
- Within each department, sorts `SAL` in **descending** order.

## 🔧 Updating Records

MongoDB provides the following methods to update existing documents in a collection:

### 1. `db.collection.updateOne()`
- Modifies a **single** document in a collection that matches the given filter (first match only).

### 2. `db.collection.updateMany()`
- Modifies **one or more** documents in a collection that match the given filter.

---

🧠 **Quick Understanding:**

- `filter` → works like a **WHERE clause** in SQL.
- `document` → defines the **SET clause** (i.e., what changes to apply).

✅ **Example:**

```bash
db.Employees.updateOne(
  { ENAME: "JAMES" },                // filter
  { $set: { SAL: 1200 } }            // document
);
```

```bash
db.Employees.updateMany(
  { JOB: "CLERK" },
  { $inc: { SAL: 200 } }             // increment salary
);
```

🧠 **Tips:**

- Use `$set` to **change specific fields** without overwriting the entire document.
- Use `$inc` to **increase or decrease numeric values** (e.g., salaries, counts).
- Always **double-check your filters** to avoid unintentionally updating multiple or wrong documents!

## `db.collection.updateOne()`

### 🧩 Syntax:
```bash
db.collection.updateOne(filter, document, options)
```

## 📌 Parameters for `updateOne()`

- **filter**: The selection criteria for the update — similar to the `find()` method.
- **document**: A document or update operator (`$set`, `$inc`, etc.) containing modifications to apply.
- **options** *(optional)*:
  - **upsert**: If `true`, creates a new document if no match is found.
  - **writeConcern**: Controls acknowledgment of write operations.
  - **collation**: Specifies language-specific rules for string comparison.

---

## ✅ Example:
Update the salary of employee **TINA** to `2000`:

```bash
db.Employees.updateOne(
  { ENAME: "TINA" },
  { $set: { SAL: 2000 } }
)
```

🧠 **Tip**:  
If you accidentally omit update operators like `$set`, MongoDB will **replace the entire document** — not just update the field.

✅ Always use update operators (`$set`, `$inc`, etc.) unless you **intentionally** want to overwrite the whole document.

## 🛠️ Update

The following command updates a **single field in a single document** in the `employees` collection.

It changes the name of the employee with `_id: 1` from **John** to **Morgan**:

```bash
db.employees.updateOne(
  { _id: 1 },
  { $set: { name: "Morgan" } }
);
```

🧠 Note:

This uses $set to modify only the name field.

Without $set, the entire document would be replaced — be cautious!

## 🔁 Updating Multiple Documents

Let's first insert two more documents into the `employees` collection:

```bash
db.employees.insertMany([
  { 
    _id: 3,
    name: "Turner",
    email: "turner@abc.com",
    salary: 5000
  },
  { 
    _id: 4,
    name: "Miller",
    email: "miller@abc.com",
    salary: 7000
  }
]);
```

✅ Now the `employees` collection contains multiple records — useful for demonstrating `updateMany()` in the next step.

🧠 **Tip:** Use the following command to view all current records in a clean and readable format:

```bash
db.employees.find().pretty()
```

## Deleting Documents

MongoDB provides the following methods to delete one or more documents from a collection:

- `db.collection.deleteOne()` – Deletes the **first matching document** in the collection.
- `db.collection.deleteMany()` – Deletes **all matching documents** in the collection.

---

### Example: Viewing Salaries Before Deletion

```bash
db.Employees.find({}, { SAL: 1 });
```

**🔽 Output:**

```bash
[
  { _id: ObjectId('67ecd251a646f14991b7123d'), SAL: 3500 },
  { _id: ObjectId('67ecd251a646f14991b7123e'), SAL: 2000 },
  { _id: ObjectId('67ecd251a646f14991b7123f'), SAL: 3000 },
  { _id: ObjectId('67ecd251a646f14991b71240'), SAL: 4000 },
  { _id: ObjectId('67ecd251a646f14991b71241'), SAL: 1300 },
  { _id: ObjectId('67ecd251a646f14991b71242'), SAL: 1500 },
  { _id: ObjectId('67ecd251a646f14991b71243'), SAL: 4500 },
  { _id: ObjectId('67ecd251a646f14991b71244'), SAL: 1100 },
  { _id: ObjectId('67ecd251a646f14991b71245'), SAL: 950 },
  { _id: ObjectId('67ecd251a646f14991b71246'), SAL: 1000 },
  { _id: ObjectId('67ecd251a646f14991b71247'), SAL: 1600 },
  { _id: ObjectId('67ecd251a646f14991b71248'), SAL: 1250 },
  { _id: ObjectId('67ecd251a646f14991b71249'), SAL: 1250 },
  { _id: ObjectId('67ecd251a646f14991b7124a'), SAL: 1500 },
  { _id: ObjectId('67ecd251a646f14991b7124b'), SAL: 2000 },
  { _id: ObjectId('67ecd251a646f14991b7124c'), SAL: 1800 }
]
```

🧠 **Tip:**  
Always **double-check your filter** before using `deleteMany()` — it can wipe out large chunks of data if misused.

## Deleting Documents with Salary Less Than 1500

To delete all employees whose salary is less than 1500, use:

```bash
db.Employees.deleteMany({ SAL: { $lt: 1500 } });
```

✅ This command will remove **all documents** from the `Employees` collection where the `SAL` field is less than 1500:

🧠 **Tip:**  
Always review your filter condition before running `deleteMany()` — it can **permanently remove large portions of data** if not used carefully.

### 🔥 `db.collection.deleteOne()`

Use the `db.<collection>.deleteOne()` method to delete **only the first document** that matches the specified filter criteria in a collection.

📌 Example:
```bash
db.employees.deleteOne({})
```

This deletes the **first document** in the `employees` collection.

### 🧠 Syntax:
```javascript
db.collection.deleteOne(filter, options)
```

### 📌 Parameters:

- **filter**: The selection criteria — same as in the `find()` method.
- **options** *(optional)*: May include:
  - `writeConcern`
  - `collation`
  - `hint`

---

### ✅ Use Case:
We want to delete the **first document** where `salary: 8000`.

There are two such documents — one for **Martin** and one for **James**.

---

### 📌 Command:
```bash
db.employees.deleteOne({ salary: 8000 })
```

🔽 **Result:**  
Only **Martin** (the first match) will be deleted.  
**James** remains in the collection.

---

🧠 **Tip:**  
To delete **all** documents with a specific salary, use `deleteMany()` instead:

```bash
db.employees.deleteMany({ salary: 8000 })
```

### 🔥 Deleting All the Documents

You can use the `db.<collection>.deleteMany()` method to delete **all documents** that match the specified filter criteria in a collection.

---

#### 📌 Syntax:
```javascript
db.collection.deleteMany(filter, options)
```

### 🗑️ Deleting Multiple or All Documents

#### 📌 Parameters:

- **filter**: The selection criteria — same as in the `find()` method.
- **options** *(optional)*: May include:
  - `writeConcern`
  - `collation`
  - `hint`

---

#### ✅ Example: Delete employees with salary < 8500

```bash
db.employees.deleteMany({ salary: { $lt: 8500 } })
```

### 🧨 Delete All Documents

If you pass an empty filter `{}`, **all documents** in the collection will be removed:

```bash
db.employees.deleteMany({})
```

⚠️ **Warning:** This operation is **irreversible** and will **wipe out all data** in the collection.  
🔁 **Always double-check** your filter before executing `deleteMany()`.

### Usage of $sum Operator in MongoDB Aggregation

The `$sum` operator is often used in the **aggregation pipeline** to compute the sum of numeric values. It can be particularly useful in grouping data and performing calculations on distinct values.

#### Key Points:

- **Aggregation**: Aggregation is one of the core operations in MongoDB. The `$sum` operator is used within an aggregation pipeline to compute the sum of values for grouped data.
- **group**: The `group` stage is where the aggregation operation begins. It takes in a group object as its argument.
- **group Object Structure**:
  - **_id**: This property defines the field (or column) by which we want to group the data. In SQL, this would be similar to the `GROUP BY` clause.
  - **aggregation**: This is the alias (or the resulting field name) for the aggregated value. It is mandatory to define this alias for the computed result, e.g., `sumValue`.
  
  Example of the group object:
  ```javascript
  { 
    _id: "$category",  // Group by 'category'
    totalAmount: { $sum: "$amount" }  // Calculate sum of 'amount'
  }
  ```
### Accumulator Object in MongoDB Aggregation

The **accumulator object** defines the fields (or columns) whose distinct values will be used for aggregation.

Think of it like the `GROUP BY` clause in SQL, where values are aggregated based on certain criteria (in this case, by `category`).

#### Example:
In the example below:
- **_id: "$category"** groups documents by the `category` field.
- **totalAmount: { $sum: "$amount" }** computes the sum of the `amount` field for each group.

```javascript
{ 
  _id: "$category",  // Group by 'category'
  totalAmount: { $sum: "$amount" }  // Calculate sum of 'amount'
}
```

By using `$sum`, we can easily perform sum aggregations, similar to SQL's `SUM()` function, and group data based on certain fields.

### Explanation:
- **_id**: This is crucial because it defines the groups (like SQL's `GROUP BY`).
- **Alias (aggregation)**: The alias name is mandatory. Without this, MongoDB wouldn't know what to call the result of the aggregation.

By including this explanation, you'll have a better grasp of how to use the `$sum` operator effectively.


#### Display Job-wise Total Salaries

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",  // Group by 'JOB' field
            Total_Salary: { $sum: "$SAL" }  // Sum of 'SAL' field for each job
        }
    }
]);
```

Output:
```bash
[
  { _id: 'ANALYST', Total_Salary: 12500 },
  { _id: 'CLERK', Total_Salary: 10350 },
  { _id: 'SALESMAN', Total_Salary: 9400 }
]
```

This example uses the `$group` stage in the aggregation pipeline to calculate the total salaries (`Total_Salary`) for each job (`JOB`), by summing the values in the `SAL` field.

#### Multiple Columns Group By

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: ["$JOB", "$DEPTNO"],  // Group by both 'JOB' and 'DEPTNO' fields
            Total_Salary: { $sum: "$SAL" }  // Sum of 'SAL' field for each group
        }
    }
]);
```

Output:
```bash
[
  { _id: [ 'ANALYST', 20 ], Total_Salary: 7000 },
  { _id: [ 'ANALYST', 10 ], Total_Salary: 5500 },
  { _id: [ 'CLERK', 30 ], Total_Salary: 1950 },
  { _id: [ 'SALESMAN', 20 ], Total_Salary: 2750 },
  { _id: [ 'CLERK', 20 ], Total_Salary: 5600 },
  { _id: [ 'CLERK', 10 ], Total_Salary: 2800 },
  { _id: [ 'SALESMAN', 10 ], Total_Salary: 2850 },
  { _id: [ 'SALESMAN', 30 ], Total_Salary: 3800 }
]
```

In this example, the `$group` stage groups the data by both `JOB` and `DEPTNO` fields. The `Total_Salary` for each combination of job and department is calculated using the `$sum` operator on the `SAL` field.


#### Average

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",  // Group by 'JOB' field
            Average: { $avg: "$SAL" }  // Calculate average of 'SAL' field for each job
        }
    }
]);
```

Output:
```bash
[
  { _id: 'ANALYST', Average: 3125 },
  { _id: 'CLERK', Average: 1725 },
  { _id: 'SALESMAN', Average: 1566.6666666666667 }
]
```

In this example, the `$group` stage groups the data by the `JOB` field. The `Average` value for each job is calculated using the `$avg` operator on the `SAL` field.

#### Maximum

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",  // Group by 'JOB' field
            Maximum: { $max: "$SAL" }  // Calculate maximum of 'SAL' field for each job
        }
    }
]);
```

Output:
```bash
[
  { _id: 'ANALYST', Maximum: 4000 },
  { _id: 'CLERK', Maximum: 4500 },
  { _id: 'SALESMAN', Maximum: 2000 }
]
```

In this example, the $group stage groups the data by the JOB field. The Maximum value for each job is calculated using the $max operator on the SAL field.

In this example, the `$group` stage groups the data by the `JOB` field. The `Maximum` value for each job is calculated using the `$max` operator on the `SAL` field.

#### Minimum

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",  // Group by 'JOB' field
            Minimum: { $min: "$SAL" }  // Calculate minimum of 'SAL' field for each job
        }
    }
]);
```

Output:
```bash
[
  { _id: 'CLERK', Minimum: 950 },
  { _id: 'ANALYST', Minimum: 2000 },
  { _id: 'SALESMAN', Minimum: 1250 }
]
```

In this example, the `$group` stage groups the data by the `JOB` field. The `Minimum` value for each job is calculated using the `$min` operator on the `SAL` field.

#### Use of `$count` Function

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",  // Group by 'JOB' field
            Count: { $count: {} }  // Count the number of documents for each job
        }
    }
]);
```

Output:
```bash
[
  { _id: 'ANALYST', Count: 4 },
  { _id: 'CLERK', Count: 6 },
  { _id: 'SALESMAN', Count: 6 }
]
```

In this example, the `$group` stage groups the data by the `JOB` field. The `Count` value represents the number of documents for each job, calculated using the `$count` function.

### Note -> **_id: {}** or **_id: null** means no column's distinct values to be grouped.

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: {},  // No grouping by column
            Grand_Total: { $sum: "$SAL" }  // Calculate total salary for all employees
        }
    }
]);
```

Output:
```bash
[ { _id: {}, Grand_Total: 32250 } ]
```

In this example, the `$group` stage groups all documents together without any specific field (because `_id` is set to `{}`). The `Grand_Total` is calculated by summing all the `SAL` values across all documents.


#### Display the Name of the First Employee in Each Job Sorted by EMPNO

**Usage of `$first` operator:**

```bash
/* Usage of $first operator */
db.Employees.aggregate(
   [
     { $sort: { EMPNO: 1 } },  // Sort by EMPNO in ascending order
     {
       $group: {
         _id: "$JOB",  // Group by 'JOB' field
         First_Employee: { $first: "$ENAME" }  // Get the first employee's name in each job
       }
     }
   ]
);
```

In this example:

- The `$sort` stage sorts the documents by `EMPNO` in ascending order.
- The `$group` stage groups the documents by the `JOB` field and uses the `$first` operator to select the first employee's name (`ENAME`) in each job group based on the sorted `EMPNO`.

This will display the first employee in each job type, sorted by their employee number.

#### Display the Name of the Last Employee in Each Job Sorted by EMPNO

**Usage of `$last` operator:**

```bash
/* Usage of $last operator */
db.Employees.aggregate(
   [
     { $sort: { EMPNO: 1 } },  // Sort by EMPNO in ascending order
     {
       $group: {
         _id: "$JOB",  // Group by 'JOB' field
         Last_Employee: { $last: "$ENAME" }  // Get the last employee's name in each job
       }
     }
   ]
);
```

In this example:

- The `$sort` stage sorts the documents by `EMPNO` in ascending order.
- The `$group` stage groups the documents by the `JOB` field and uses the `$last` operator to select the last employee's name (`ENAME`) in each job group based on the sorted `EMPNO`.

This will display the last employee in each job type, sorted by their employee number.

#### Simulation of Sub Query, Derived Tables and Join of ANSI SQL

**To find employees with the highest salary:**

```sql
db.Employees.aggregate([
  { $group: { _id: null, maxSalary: { $max: "$SAL" } } },  // Find the maximum salary
  { $lookup: {
      from: "Employees",  // Join with the Employees collection
      localField: "maxSalary",  // Use the maxSalary from the previous stage
      foreignField: "SAL",  // Match the SAL field
      as: "highest_earners"  // Store the results in highest_earners
    }
  },
  { $unwind: "$highest_earners" },  // Flatten the array of highest earners
  { $project: { _id: 0, ENAME: "$highest_earners.ENAME", SAL: "$maxSalary" } }  // Select the relevant fields
]);
```

In this example:

- The `$group` stage calculates the maximum salary (`maxSalary`).
- The `$lookup` stage performs a join between the current collection and the "Employees" collection, using the `maxSalary` to find the employees with the highest salary.
- The `$unwind` stage flattens the resulting array to get the highest earners.
- The `$project` stage selects the employee name (`ENAME`) and the `maxSalary` to be displayed in the final output.

- `$LOOKUP` operator: It is used for joining documents. It performs an equi join similar to SQL's join logic.
- `$unwind`: Converts the joined array into separate documents.
- `$project`: Projection. Displays only the `ENAME` and `SAL` fields.
- `$group` → Finds the maximum salary (`$max: "$SAL"`).

#### To Find Employees Who Earn Less Than the Average Salary for Their Own Job

**Usage of `$match` (similar to the SQL WHERE clause):**

```bash
db.Employees.aggregate([
  {
    $group: {
      _id: "$JOB",  // Group by JOB
      avgSalary: { $avg: "$SAL" }  // Calculate average salary for each job
    }
  },
  {
    $lookup: {
      from: "Employees",  // Join with the Employees collection
      localField: "_id",  // Match the JOB field
      foreignField: "JOB",  // Match the JOB field in the Employees collection
      as: "employees"  // Store the result in 'employees'
    }
  },
  { $unwind: "$employees" },  // Flatten the employees array
  {
    $match: {
      $expr: { $lt: ["$employees.SAL", "$avgSalary"] }  // Find employees whose salary is less than the average salary for their job
    }
  },
  {
    $project: {
      _id: 0,
      ENAME: "$employees.ENAME",  // Display employee name
      JOB: "$employees.JOB",  // Display job title
      SAL: "$employees.SAL",  // Display employee salary
      avgSAL: "$avgSalary"  // Display the average salary for the job
    }
  }
]);
```

In this example:

- The `$group` stage calculates the average salary (`avgSalary`) for each job (`JOB`).
- The `$lookup` stage performs a join to retrieve all employees for each job.
- The `$unwind` stage flattens the array of employees.
- The `$match` stage filters employees whose salary is less than the average salary for their job using the `$expr` operator and `$lt` condition.
- The `$project` stage selects the employee name, job, salary, and the average salary for display in the final output.
