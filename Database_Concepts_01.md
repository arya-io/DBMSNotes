DATABASE CONCEPTS - NOTES PART 1


In context of Database Software data gets stored in some medium.
As and when required it will be retrieved.

Prior to Database software data was getting stored in “Flat File System” (FFS).

Delimeter (used for seperator).

Properties of Flat File System :

1)Entire data gets stored in a “single file”. No will physical and logical division is done.
2)Heavy amount of “Data Redundancy” (Data Repetition). 
3)Unnecessary more disk space will be required.
4)More processing time is required.
5)No datatype support. Only text datatype is there.
6)No inherent support for doing “Data Validation”.
7)No inherent support for “Data Security”.
8)No inherent support for “Back up Strategy”.
9)No inherent easy mechanism to create reports quickly. Programming languages had to be used to generate report. It was difficult.
10)For updating data, a new record has to be entered. We cannot override the existing values.
11)To delete record no mechanism.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

RDBMS (Relational Database Management System) was introduced by Dr. Codd in late 1970s.

Properties of RDBMS:

1.Do NOT enter everything in a single table or file. Make sure “Subject or Context Specific” tables.
2.Heavy amount of data redundancy gets eliminated. Only marginal (very small amount of) data, i.e., IDs will get repeated.
3.Unnecessary more disk space will NOT be required.
4.More processing time is NOT required.
5.For updating data, a new record has NOT to be entered. We can override the existing values.
6.Datatype support is there.
7.Inherent support for doing “Data Validations”.
8.Inherent support for “Data Security”.
9.Inherent support for “Backup Strategy”. (This is Database specific)
10.Inherent easy mechanism to create reports quickly. Programming languages NOT to be used to generate report.
11.Simple mechanism to delete records.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SQL


1.RDBMS is a framework.
2.SQL will implement RDBMS via scripting.
3.Fourth Generation Language.
4.Based on English Words.
5.Keywords are not Case-Sensitive.
6.No coding knowledge required.
7.Data Validation can be done easily.

ANSI SQL:
1.Syntaxes are common for all DBs.
2.Supported by all DBs.



![Alt text](Databases.png)





Data Integrity Rules:

1.Primary Key (PK) -> It is a value or set of values, which will uniquely identify a record from the SQL database table.
a.It has to be unique.
b.It cannot be blank or NULL.
c.There can be ONLY 1 PK per table.

2.Unique Key (UK) -> Value has to be unique.
3.Not Null (NN) -> Value is mandatory.

4.Foreign Key (FK) -> FK is a value taken from the PK or UK column of a different or same table.
a.FK can repeat. (It may happen that a student issues multiple books)
b.FK can be NULL. (It may happen that a book is not being issued by any student)

Table which contains PK is called as Parent Table (Master Table).
Table which contains FK is called as Child Table.
Table which contains FK and PK can act as both Parent and Child Table.

5.Check Constraint (Ch) -> It will check exactly which value needs to be entered.
For e.g. Salary -> 50000, City should be Pune or Mumbai or Bangalore,
Return Date >= Issue Date

Combining Data Integrity Rules for one column:
1.UK + NN
2.PK + Ch
3.NN + Ch
4.FK + Ch

Composite PK -> Combination cannot repeat, individual values can repeat.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Student_Master Table
Rollno(PK),Name,Address,Mobile_No
1,A,Pune,xxxxx
2,B,Mumbai,rrrr
3,C,Pune,tttt
4,D,Delhi,tttt

Result_Details Table
Rollno (FK) + (PK), Marks
2,89
3,78

Certificate_Details Table
Rollno (FK from Result_Details), Certificate_ID
2,C1
3,C2

Foreign Key can also act as a Primary Key for another Table.





TYPES OF SQL COMMANDS


1.DDL (Data Definition Language): CREATE, DROP, ALTER
- Focuses on Structure of Data.

2.DML (Data Manipulation Language): INSERT, UPDATE, DELETE, MERGE
- Focuses on Manipulation of Data.

3.**DQL (Data Query Language) OR DRL (Data Retrieval Language)** : SELECT, FROM, WHERE….

-------------------------------------

4.DCL (Data Control Language): GRANT, REVOKE

5.TCL (Transactional Control Language): COMMIT, ROLLBACK

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SQL Database Structure:

1.It is a Software based on Client-Software Architecture.

Server means the physical copy of database gets created.
Data physically gets saved in that machine.

Client means only the s/w which has networking configuration required to connect and access the server.

2.It will have some implicit set of users.
By default they are DBA users.

3.There will be some implicit databases created at the time of installation.
Database will be collections of:

4.Editors:
i.CUI - Command prompt
ii.GUI

5.Sample tables are provided. Useful in training for learning Select commands.


6.Service Configuration (operation system connection)
7.Database booting or starting

