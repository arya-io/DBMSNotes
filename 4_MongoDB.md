# Introducing MongoDB

- MongoDB is a **NoSQL** database.
- It comes under the category of **Document Database**.
- MongoDB is written in **C++** language.
- MongoDB is used as **backend (or database)** software by websites.

## Document Databases
- A document database is a database that stores information in documents.

## What are Documents?
- A document is a **record** in a document database.
- A document typically stores information about one object and any of its related metadata.
- Document stores data **in filed value-pairs**.
- The values can be a varity of types and structure, including strings, number, dates, arrays, or objects. Documents can be stored in format like JSON and XML.

## SQL and NoSQL Terminologies

| **SQL (RDBMS)**       | **MongoDB (NoSQL)**            |
|------------------------|-------------------------------|
| **Table**             | Collection                   |
| **Row**               | Document                     |
| **Column**            | Field                        |
| **Primary Key**       | ObjectId (also known as `_id`)|
| **Index**             | Index                        |
| **View**              | View                         |

## Relational Versus Document Model
- Relational Data Model in tabular form
- Document Store Model in the form of documents

## Advantage of Document Database
- An intuitive data model that is **fast and easy** for developers to work with.
- A **flexible schema** that allows for the data model to evolve as **application needs change**.
 Because RDBMS cannot be efficient always.
- A document's schema is dynamic and self-describing, **so developers don't need to first pre-define it in the database**.
- **Not all documents in a collection are required to have the same fields**, because document databases have a **flexible schema**.
- Developers can **modify the structure at any time**, avoiding disruptive schema migrations.
- The ability to **horizontally scale out**.

## Drawbacks of Document Databases
- **No inherent Security** mechanism.
  No GRANT, REVOKE command. By coding, security can be provided. But the default commands are not present.
- **No** inherent mechanism for **validating the data**.
  Document Database is going back to Flat File System but it is not much like that. They are much powerful than FFS.
- Are not really **made for running multiple, complex operations or complex queries.**

## Use Cases of Document Databases
- Large eCommerce platforms (Like Amazon)
- Blogging sites (such as Twitter)
- Content management systems (Wordpress, windows registry)
- IoT
- Product Catalogs
- Payment Processing
- Real-time Analytics (Live Streaming Data: Text, Video, Audio, Images, etc.)

## Mongo Shell
- The mongo shell provides a JavaScript API for database operations.
- In the mongo shell, **db is the variable that references the current database**.
- The variable is automatically set to the default database mydb3 or is set when you use the use <database_name>
to switch current database.

## Mongo Shell Steps:
- If you want to get connected to local server, just press ENTER.
- Test is the default database which is created internally when the installation of MongoDB happens.
- To see the available databases, use:
  ```bash
  show dbs
  ```
  
- When a database is not present and we run:
  ```bash
  use x100
  ```
  The database with name x100 will be created at the same time even if it wasn't present in MongoDB.
  
- Next step is to create collection:
  Creating **collection** Emp5 and add **documents**
  ```bash
  db.Emp5.insert({"empno": 1, "ename": "Smith", sal:6000});
  ```
  `Emp5` is the collection name.
  Here, `{"empno": 1, "ename": "Smith", sal:6000}` is the document.
  We use double quotes for columns to tackle the situation in which the column name contains two or more words (i.e., whitespaces).
    
  The output is as follows:
  ```bash
  {
  acknowledged: true,
  insertedIds: { '0': ObjectId('67ecb69aa646f14991b71236') }
  }
  ```
  Here, ObjectId is the auto-generated Id.
  
- Adding another Document
  ```bash
  db.Emp5.insert({"empid": 2, "name": "Martin", bonus: 7000, incentive: 500});
  ```
  
- Now, to find the documents in the collection, we use the command:
  ```bash
  db.Emp5.find();
  ```
  When no parameter is given inside the parenthesis of find(), then it is considered as all like (*) of SQL.
  The output of the above command is as follows:
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

- **Keywords are highly case-sensitive in MongoDB.**

Now we are creating a new collection name Emp6

```bash
db.Emp6.insert({"empno": 1, "ename": "Smith", sal: 6000});
db.Emp6.insert({"empno": 2, "ename": "Martin", sal: 7000});
db.Emp6.insert({"empno": 3, "ename": "James", sal: 5000});
db.Emp6.insert({"empno": 4, "ename": "King", sal: 4000});
db.Emp6.find();
```

Output:
```bash
[
  {
    _id: ObjectId('67ecc514a646f14991b71239'),
    empno: 1,
    ename: 'Smith',
    sal: 6000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123a'),
    empno: 2,
    ename: 'Martin',
    sal: 7000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123b'),
    empno: 3,
    ename: 'James',
    sal: 5000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123c'),
    empno: 4,
    ename: 'King',
    sal: 4000
  }
]
```
```bash
db.Emp6.find({});
```
The above command also gives the same output.

```bash
db.Emp6.find({}, {ename:1});
```
First parameter is for the records filter. Currently, we don't have any.

Output:
```bash
[
  { _id: ObjectId('67ecc514a646f14991b71239'), ename: 'Smith' },
  { _id: ObjectId('67ecc515a646f14991b7123a'), ename: 'Martin' },
  { _id: ObjectId('67ecc515a646f14991b7123b'), ename: 'James' },
  { _id: ObjectId('67ecc515a646f14991b7123c'), ename: 'King' }
]
```

- Displaying multiple fields but all documents

```bash
db.Emp6.find({}, {ename:1, sal:2});
```
Output:
```bash
[
  {
    _id: ObjectId('67ecc514a646f14991b71239'),
    ename: 'Smith',
    sal: 6000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123a'),
    ename: 'Martin',
    sal: 7000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123b'),
    ename: 'James',
    sal: 5000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123c'),
    ename: 'King',
    sal: 4000
  }
]
```

- To exclude the id field (when we don't have Object Id in the output, we use _id:0)
```bash
db.Emp6.find({}, {ename:1, sal:2, _id:0});
```
Output:
```bash
[
  { ename: 'Smith', sal: 6000 },
  { ename: 'Martin', sal: 7000 },
  { ename: 'James', sal: 5000 },
  { ename: 'King', sal: 4000 }
]
```

Mixing field inclusion (`1`) and exclusion (`0`) in a MongoDB projection is not allowed, except for the `_id` field. Using any non-zero value, such as `1` or `2`, will include the specified field in the query result.

### Filtering Rows and Columns

`find(document filter (where clause), projection filter (column list of select))`

#### Display documents having salary greater than 5000

```bash
db.Emp6.find({"sal": {$gt: 5000}});
```
Output:
```bash
[
  {
    _id: ObjectId('67ecc514a646f14991b71239'),
    empno: 1,
    ename: 'Smith',
    sal: 6000
  },
  {
    _id: ObjectId('67ecc515a646f14991b7123a'),
    empno: 2,
    ename: 'Martin',
    sal: 7000
  }
]
```

Output without ObjectID:

```bash
db.Emp6.find({"sal": {$gt: 5000}}, {_id:0});
```
Output:
```bash
[
  { empno: 1, ename: 'Smith', sal: 6000 },
  { empno: 2, ename: 'Martin', sal: 7000 }
]
```
```bash
db.Emp6.find({"ename": {$eq: "SMITH"}});
```
This query will not work as "Smith" is saved in mixed case and we are trying uppercase.

To work with queries without worrying about case-sensitiveness, use this command:

```bash
db.Emp6.find({"ename": /smith/i});
```
Output:
```bash
[
  {
    _id: ObjectId('67ecc514a646f14991b71239'),
    empno: 1,
    ename: 'Smith',
    sal: 6000
  }
]
```

The below query will work successfully:
```bash
db.Emp6.find({"ename": {$eq: "Smith"}});
```
Output:
```bash
[
  {
    _id: ObjectId('67ecc514a646f14991b71239'),
    empno: 1,
    ename: 'Smith',
    sal: 6000
  }
]
```

Following is the query to find a value in uppercase:

```bash
db.Emp6.find({"ename": "smith".toUpperCase()});
```
It will show the output if 'SMITH' is present in the collection's documents.

- We have added a new Employees collection in MongoDB. The queries have been taken from Drive.

### Which employees have names matching either "ROGER" or "MARTIN"?

```bash
db.Employees.find({"ENAME": {$in: ["ROGER", "MARTIN"]}});
```
Output:
```bash
[
  {
    _id: ObjectId('67ecd251a646f14991b7123d'),
    EMPNO: 1,
    ENAME: 'ROGER',
    JOB: 'ANALYST',
    SAL: 3500,
    DEPTNO: 10
  },
  {
    _id: ObjectId('67ecd251a646f14991b71249'),
    EMPNO: 13,
    ENAME: 'MARTIN',
    JOB: 'SALESMAN',
    SAL: 1250,
    DEPTNO: 20
  }
]
```

Single quote can also work for above query for entries after `$in` operator.
```bash
db.Employees.find({"ENAME": {$in: ["ROGER", "MARTIN"]}});
```
Opposite of $in is $nin.
It will return all entries except given in the query.

### Logical and or operators.

#### Which employees work as clerks and have a salary less than 1200?
```bash
db.Employees.find({ $and: [{JOB:"CLERK"}, {SAL:{$lt: 1200}}]});
```
Output:
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

#### Display name and job for employees earning sal less than 1200 from job type clerk. Don't show object id.

```bash
db.Employees.find({ $and: [{JOB:"CLERK"}, {SAL:{$lt: 1200}}]}, {"ENAME":1, "JOB":2, _id:0});
```
Output:
```bash
[
  { ENAME: 'ADAMS', JOB: 'CLERK' },
  { ENAME: 'JAMES', JOB: 'CLERK' },
  { ENAME: 'MARY', JOB: 'CLERK' }
]
```

###### With Salary:

```bash
db.Employees.find({ $and: [{JOB:"CLERK"}, {SAL:{$lte: 1200}}]}, {"ENAME":1, "JOB":2, SAL: 3, _id:0});
```
Output:
```bash
[
  { ENAME: 'ADAMS', JOB: 'CLERK', SAL: 1100 },
  { ENAME: 'JAMES', JOB: 'CLERK', SAL: 950 },
  { ENAME: 'MARY', JOB: 'CLERK', SAL: 1000 }
]
```

### OR Operator

```bash
db.Employees.find({ $or: [{JOB:"CLERK"}, {SAL:{$lt: 1200}}]});
```
```bash
db.Employees.find({ $or: [{JOB:"CLERK"}, {SAL:{$lte: 1200}}]}, {"ENAME":1, "JOB":2, SAL: 3, _id:0});
```
Output:
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

## CRUD Operations

## MongoDB Collections

- A collection in MongoDB is similar to a table in RDBMS.
- MongoDb collections do not enforce schemas.
- Each MongoDB collection can have multiple documents. A document is equivalent to row in a table in RDBMS.
- To create a collection, use the following command:
  ```bash
  db.createCollection("Emp100");
  ```
  Output:
  ```bash
  { ok: 1 }
  ```

## Listing all the collections

Shows collections in the current database.

```bash
show collections;
```
Output:
```bash
Emp100
Emp5
Emp6
Employees
```

We have 4 collections in x100 database.

##### To delete a collection:

```bash
db.Emp100.drop();
```
Output:
```bash
true
```

Using `db.Emp108.drop();` and `db.Emp108.drop();` also gives `true`.
This behavior is because MongoDB interprets the command as successfully completing the operation, regardless of whether the collection was present or not. Essentially, the `drop()` command ensures that the collection no longer exists, and if it was already absent, the result is still considered a success. This design choice simplifies operations by not requiring additional checks.

Database - Collection - Documents
- A Database will have Collections

## BSON
- MongoDB

## Inserting Documents into Collection:

MongoDB provides the following emthods to insert documents into a collection:
1. insertOne(): Inserts a single document into a collection.
2. insert(): Inserts one or more documents into a collection.
   Note -> insert() is the method from older versions.
   No difference in insert() and insertMany() as such.
   Takes single document by default, but there is an option to insert multiple documents supplied as an array.
3. insertMany(): Insert Multiple Documents into a Collection.

## Insert _id Manually

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
        },
     ]
);
```
Output:
```bash
{ acknowledged: true, insertedIds: { '0': '1', '1': '2' } }
```

## findOne()

- The findOne() returns the first document from a collection if no parameter is passed.
  `db.employees.findOne()`
- Passing parameter to findOne()
  the following finds the first document where salary is greater than 2000.
  `db.employees.findOne({salary: {$gt: 2000}})`

## find()

The find() method finds all the documents that matches with the specified criteria and returns the cursor object. The cursor object is a pointer to the resutl set.

For example, the following
---

## Sorting
```bash
db.Employees.find().sort({ENAME: 1});
```
Output:
Data is sorted according to Names of Employees, i.e., according to ENAME.

#### Syntax of Sort:
sort({Field Name: Sorting Order Number});

Sorting Order Number will be -1 for Ascending.
Sorting Order Number will be -1 for Descending.

---

## Updating Records

- MongoDB provides the following methods to update existing documents in a collection:
  1.

---

filter means where clause
document means set clause

## Update

---

## Deleting Documents

db.Employees.find({}, {SAL:1});
Output:
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

Delete Documents having salary < 1500

db.Employees.deleteMany({SAL: {$lt: 1500}});

### Deleting all the Documents

db.employees.deleteMany({});

---

### Usage of $sum operator

aggregate becomes one of the important methods of the collection object.
group becomes the first argument.
It has two properties:
- _id which contains the column which we are grouping
- aggregation which should be column alias
Alias name is mandatory here

###### accumulator object: It is the columns/fields whose distinct values will be used for aggregation (GROUP BY column of SQL).

#### Display Job wise total salaries.

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",
            Total_Salary: { $sum: "$SAL"}
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

#### Multiple Columns Group By:

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: ["$JOB", "$DEPTNO"],
            Total_Salary: { $sum: "$SAL"}
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

#### Average

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",
            Average: { $avg: "$SAL"}
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

Same can be done for max and min.

Maximum
```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",
            Maximum: { $max: "$SAL"}
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
Minimum
```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",
            Minimum: { $min: "$SAL"}
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

#### Use of count function
```bash
db.Employees.aggregate([
    {
        $group: {
            _id: "$JOB",
            Count: { $count: {}}
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

### Note -> **_id:{} or _id:null** means no column's distinct values to be grouped.

```bash
db.Employees.aggregate([
    {
        $group: {
            _id: {},
            Grand_Total: { $sum: "$SAL"}
                }
    }
]);
```
Output:
```bash
[ { _id: {}, Grand_Total: 32250 } ]
```

#### Display the name of the first employee in each job sorted as per empno in that job type.

$first:
$last:

---

#### Simulation of Sub Query, Derived Tables and Join of ANSI SQL 

To find employees with the highest salary

- $LOOKUP operator: It is used for joining documents. It will be equi join as per SQL's logic.
- $unwind: Converts the joined array into separate documents.
- $project: projection. Displays only ENAME and SAL fields.

---

#### To find employees who earn less than the average salary for their own job.

$match is similar to WHERE clause.
















