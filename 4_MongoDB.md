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
  db.Emp5.find()
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




















