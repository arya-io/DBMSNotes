# DATABASE CONCEPTS - NOTES PART 1


In context of Database Software data gets stored in some medium.
As and when required it will be retrieved.

Prior to Database software data was getting stored in “Flat File System” (FFS).

Delimeter (used for seperator).

## Properties of Flat File System :

1. Entire data gets stored in a “single file”. No will physical and logical division is done.
2. Heavy amount of “Data Redundancy” (Data Repetition). 
3. Unnecessary more disk space will be required.
4. More processing time is required.
5. No datatype support. Only text datatype is there.
6. No inherent support for doing “Data Validation”.
7. No inherent support for “Data Security”.
8. No inherent support for “Back up Strategy”.
9. No inherent easy mechanism to create reports quickly. Programming languages had to be used to generate report. It was difficult.
10. For updating data, a new record has to be entered. We cannot override the existing values.
11. To delete record no mechanism.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

RDBMS (Relational Database Management System) was introduced by Dr. Codd in late 1970s.

## Properties of RDBMS:

1. Do NOT enter everything in a single table or file. Make sure “Subject or Context Specific” tables.
2. Heavy amount of data redundancy gets eliminated. Only marginal (very small amount of) data, i.e., IDs will get repeated.
3. Unnecessary more disk space will NOT be required.
4. More processing time is NOT required.
5. For updating data, a new record has NOT to be entered. We can override the existing values.
6. Datatype support is there.
7. Inherent support for doing “Data Validations”.
8. Inherent support for “Data Security”.
9. Inherent support for “Backup Strategy”. (This is Database specific)
10. Inherent easy mechanism to create reports quickly. Programming languages NOT to be used to generate report.
11. Simple mechanism to delete records.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## SQL

1. RDBMS is a framework.
2. SQL will implement RDBMS via scripting.
3. Fourth Generation Language.
4. Based on English Words.
5. Keywords are not Case-Sensitive.
6. No coding knowledge required.
7. Data Validation can be done easily.

## ANSI SQL:
1. Syntaxes are common for all DBs.
2. Supported by all DBs.



![Alt text](Databases.png)


## Data Integrity Rules:

1. Primary Key (PK) -> It is a value or set of values, which will uniquely identify a record from the SQL database table.
  a. It has to be unique.
  b. It cannot be blank or NULL.
  c. There can be ONLY 1 PK per table.

2. Unique Key (UK) -> Value has to be unique.
3. Not Null (NN) -> Value is mandatory.

4. Foreign Key (FK) -> FK is a value taken from the PK or UK column of a different or same table.
  a. FK can repeat. (It may happen that a student issues multiple books)
  b. FK can be NULL. (It may happen that a book is not being issued by any student)

`Table which contains PK is called as Parent Table (Master Table).
Table which contains FK is called as Child Table.
Table which contains FK and PK can act as both Parent and Child Table.`

5. Check Constraint (Ch) -> It will check exactly which value needs to be entered.
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

## TYPES OF SQL COMMANDS

1. DDL (Data Definition Language): CREATE, DROP, ALTER
- Focuses on Structure of Data.

2. DML (Data Manipulation Language): INSERT, UPDATE, DELETE, MERGE
- Focuses on Manipulation of Data.

3. **DQL (Data Query Language) OR DRL (Data Retrieval Language)** : SELECT, FROM, WHERE….

-------------------------------------

4. DCL (Data Control Language): GRANT, REVOKE

5. TCL (Transactional Control Language): COMMIT, ROLLBACK

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## SQL Database Structure:

1. It is a Software based on Client-Software Architecture.

Server means the physical copy of database gets created.
Data physically gets saved in that machine.

Client means only the s/w which has networking configuration required to connect and access the server.

2. It will have some implicit set of users.
By default they are DBA users.

3. There will be some implicit databases created at the time of installation.
Database will be collections of:

4. Editors:
  i. CUI - Command prompt
  ii. GUI

5. Sample tables are provided. Useful in training for learning Select commands.

6. Service Configuration (operation system connection)

7. Database booting or starting.

----------------------------------------------------------------------------------------------------------------------------

```sql
Select user();  -- To show current user.
```

```
+----------------+
| user()         |
+----------------+
| root@localhost |
+----------------+
```

```sql
System cls; -- To clear screen.
```

```sql
select user FROM mysql.user; -- To show all users.
```

```
+------------------+
| user             |
+------------------+
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
+------------------+
```

```sql
Show tables; --To show tables.
```

```
+-----------------+
| Tables_in_mydb3 |
+-----------------+
| australia       |
| comp            |
| d               |
| dept            |
| dept1           |
| e               |
| emp             |
| emp1            |
| india           |
| mech            |
| p               |
| pcodes          |
| period          |
| rates           |
+-----------------+
```

### Display records of employees who earns sal greater than or equal to 3000.

```sql
select *
from emp
where sal >= 3000;
```
```
+-------+-------+-----------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+-----------+------+------------+------+------+--------+
|  7788 | SCOTT | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     20 |
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     10 |
|  7902 | FORD  | ANALYST   | 7566 | 1981-03-06 | 3000 | NULL |     20 |
+-------+-------+-----------+------+------------+------+------+--------+
```


## Types of compile time errors in SQL:
1. Table name and column name is wrong.
2. WRONG keywords.
3. Permission denied.
4. Tables are locked.
5. Tables or Databases are offline.
6. Not reaching server.

`MySQL is super case-insensitive.`
`Use Single Quotes only.`

- Display clerks who earn salary > 1000
- SELECT * FROM emp WHERE job = 'manager' or sal < 1000;
- Combining different sets of conditions
- Display clerks earning sal less than 1000 as well as display salesmen who earn less than 1300

## Special SQL Operators:

1. Between (Range of values)
```sql
SELECT *
FROM emp 
WHERE sal BETWEEN 1250 AND 3000;
```

  NOT BETWEEN
```sql
SELECT *
FROM emp 
WHERE sal NOT BETWEEN 1250 AND 3000;
```

2. IN Operator (Used to filter rows by checking if a value matches any value in a given list)
```sql
SELECT * FROM emp
WHERE job IN ('CLERK', 'MANAGER');
```

  NOT IN Operator
```sql
SELECT * FROM emp
WHERE job NOT IN ('CLERK', 'MANAGER');
```

3. IS NULL (used to SHOW null value record)
```SQL
SELECT * FROM emp
WHERE comm IS NULL;
```

IS NOT NULL
```SQL
SELECT * FROM emp
WHERE comm is NOT NULL;
```

## Pattern Matching Operators of SQL:

Two Wildcard Characters:
- Percentage (%)
- Underscore (_)

## Display Records that starts with 'S'
```sql
SELECT *
FROM emp
WHERE ename LIKE 'S%';
```
```
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7369 | SMITH | CLERK   | 7902 | 1980-12-17 |  800 | NULL |     20 |
|  7788 | SCOTT | ANALYST | 7566 | 1982-12-09 | 3000 | NULL |     20 |
+-------+-------+---------+------+------------+------+------+--------+
```
## Display Records that ends with 'R'
```sql
SELECT *
FROM emp
WHERE ename LIKE '%R';
```
```
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7844 | TURNER | SALESMAN | 7698 | 1981-08-09 | 1500 |    0 |     30 |
|  7934 | MILLER | CLERK    | 7782 | 1982-01-23 | 1300 | NULL |     10 |
+-------+--------+----------+------+------------+------+------+--------+
```
```SQL
SELECT *
FROM PCODES
WHERE CODE LIKE 'pq_%01';
```
```
+-------+------+
| Code  | Qty  |
+-------+------+
| PQR01 |   29 |
+-------+------+
```

## ESCAPE OPERATOR

```SQL
SELECT *
FROM pcodes
WHERE code LIKE 'A?%C01' ESCAPE '?';
```

## COLUMN ALIASES
```sql
SELECT ename AS "Name Of Employee",
sal AS "Salary"
FROM emp;
```
```
+------------------+--------+
| Name Of Employee | Salary |
+------------------+--------+
| SMITH            |    800 |
| ALLEN            |   1600 |
| WARD             |   1250 |
| JONES            |   2975 |
| MARTIN           |   1250 |
| BLAKE            |   2850 |
| CLARK            |   2450 |
| SCOTT            |   3000 |
| KING             |   5000 |
| TURNER           |   1500 |
| ADAMS            |   1100 |
| JAMES            |    950 |
| FORD             |   3000 |
| MILLER           |   1300 |
+------------------+--------+
```

## ORDER BY (SORTING)
```sql
SELECT * FROM emp
ORDER BY sal DESC;
```
```
+-------+--------+-----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+-----------+------+------------+------+------+--------+
|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     10 |
|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     20 |
|  7902 | FORD   | ANALYST   | 7566 | 1981-03-06 | 3000 | NULL |     20 |
|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL |     20 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-08 | 2450 | NULL |     10 |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-05-20 | 1600 |  300 |     30 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-08-09 | 1500 |    0 |     30 |
|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL |     10 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-05-22 | 1250 |  500 |     30 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-20 | 1250 | 1400 |     30 |
|  7876 | ADAMS  | CLERK     | 7788 | 1983-12-01 | 1100 | NULL |     20 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |
|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  800 | NULL |     20 |
+-------+--------+-----------+------+------------+------+------+--------+
```

## ORDER BY (MULTIPLE COLUMN SORTING)
```sql
SELECT DEPTNO, ENAME, SAL
FROM EMP
ORDER BY DEPTNO, SAL DESC;
```
```
+--------+--------+------+
| DEPTNO | ENAME  | SAL  |
+--------+--------+------+
|     10 | KING   | 5000 |
|     10 | CLARK  | 2450 |
|     10 | MILLER | 1300 |
|     20 | SCOTT  | 3000 |
|     20 | FORD   | 3000 |
|     20 | JONES  | 2975 |
|     20 | ADAMS  | 1100 |
|     20 | SMITH  |  800 |
|     30 | BLAKE  | 2850 |
|     30 | ALLEN  | 1600 |
|     30 | TURNER | 1500 |
|     30 | WARD   | 1250 |
|     30 | MARTIN | 1250 |
|     30 | JAMES  |  950 |
+--------+--------+------+
```

## ALIAS WITH ORDER BY
```sql
SELECT ENAME AS Name,
SAL AS Salary,
DEPTNO FROM EMP
ORDER BY Name;
```
```
+--------+--------+--------+
| Name   | Salary | DEPTNO |
+--------+--------+--------+
| ADAMS  |   1100 |     20 |
| ALLEN  |   1600 |     30 |
| BLAKE  |   2850 |     30 |
| CLARK  |   2450 |     10 |
| FORD   |   3000 |     20 |
| JAMES  |    950 |     30 |
| JONES  |   2975 |     20 |
| KING   |   5000 |     10 |
| MARTIN |   1250 |     30 |
| MILLER |   1300 |     10 |
| SCOTT  |   3000 |     20 |
| SMITH  |    800 |     20 |
| TURNER |   1500 |     30 |
| WARD   |   1250 |     30 |
+--------+--------+--------+
```

## ORDER BY COLUMN NUMBER
```sql
SELECT * FROM EMP
ORDER BY 3;
```
```
+-------+--------+-----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+-----------+------+------------+------+------+--------+
|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     20 |
|  7902 | FORD   | ANALYST   | 7566 | 1981-03-06 | 3000 | NULL |     20 |
|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  800 | NULL |     20 |
|  7876 | ADAMS  | CLERK     | 7788 | 1983-12-01 | 1100 | NULL |     20 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |
|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL |     10 |
|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL |     20 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-08 | 2450 | NULL |     10 |
|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     10 |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-05-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-05-22 | 1250 |  500 |     30 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-20 | 1250 | 1400 |     30 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-08-09 | 1500 |    0 |     30 |
+-------+--------+-----------+------+------------+------+------+--------+
```

## COLUMN EXPRESSIONS OR DERIVED COLUMNS IN THE PROJECTIONS
```sql
SELECT ENAME, SAL, SAL * 12 FROM EMP;
```
```
+--------+------+----------+
| ENAME  | SAL  | SAL * 12 |
+--------+------+----------+
| SMITH  |  800 |     9600 |
| ALLEN  | 1600 |    19200 |
| WARD   | 1250 |    15000 |
| JONES  | 2975 |    35700 |
| MARTIN | 1250 |    15000 |
| BLAKE  | 2850 |    34200 |
| CLARK  | 2450 |    29400 |
| SCOTT  | 3000 |    36000 |
| KING   | 5000 |    60000 |
| TURNER | 1500 |    18000 |
| ADAMS  | 1100 |    13200 |
| JAMES  |  950 |    11400 |
| FORD   | 3000 |    36000 |
| MILLER | 1300 |    15600 |
+--------+------+----------+
```
```sql
SELECT ENAME, SAL, SAL * 12 AS "Annual Salary" FROM EMP;
```
```
+--------+------+---------------+
| ENAME  | SAL  | Annual Salary |
+--------+------+---------------+
| SMITH  |  800 |          9600 |
| ALLEN  | 1600 |         19200 |
| WARD   | 1250 |         15000 |
| JONES  | 2975 |         35700 |
| MARTIN | 1250 |         15000 |
| BLAKE  | 2850 |         34200 |
| CLARK  | 2450 |         29400 |
| SCOTT  | 3000 |         36000 |
| KING   | 5000 |         60000 |
| TURNER | 1500 |         18000 |
| ADAMS  | 1100 |         13200 |
| JAMES  |  950 |         11400 |
| FORD   | 3000 |         36000 |
| MILLER | 1300 |         15600 |
+--------+------+---------------+
```

## Types of BUILT-IN SQL Function as per their execution :
1. Single Row Function(Scaler Function)
2. Multi Row Functions or Aggregate Functions or Group Functions

1. Single Row Functions: They will return 

```sql
SELECT ENAME, LOWER(ENAME) FROM EMP;
```
```
+--------+--------------+
| ENAME  | LOWER(ENAME) |
+--------+--------------+
| SMITH  | smith        |
| ALLEN  | allen        |
| WARD   | ward         |
| JONES  | jones        |
| MARTIN | martin       |
| BLAKE  | blake        |
| CLARK  | clark        |
| SCOTT  | scott        |
| KING   | king         |
| TURNER | turner       |
| ADAMS  | adams        |
| JAMES  | james        |
| FORD   | ford         |
| MILLER | miller       |
+--------+--------------+
```
```sql
SELECT 5 + NULL;
```
```
+----------+
| 5 + NULL |
+----------+
|     NULL |
+----------+
```
```sql
SELECT ENAME, SAL, COMM, SAL + COMM AS "Total" FROM EMP;
```
```
+--------+------+------+-------+
| ENAME  | SAL  | COMM | Total |
+--------+------+------+-------+
| SMITH  |  800 | NULL |  NULL |
| ALLEN  | 1600 |  300 |  1900 |
| WARD   | 1250 |  500 |  1750 |
| JONES  | 2975 | NULL |  NULL |
| MARTIN | 1250 | 1400 |  2650 |
| BLAKE  | 2850 | NULL |  NULL |
| CLARK  | 2450 | NULL |  NULL |
| SCOTT  | 3000 | NULL |  NULL |
| KING   | 5000 | NULL |  NULL |
| TURNER | 1500 |    0 |  1500 |
| ADAMS  | 1100 | NULL |  NULL |
| JAMES  |  950 | NULL |  NULL |
| FORD   | 3000 | NULL |  NULL |
| MILLER | 1300 | NULL |  NULL |
+--------+------+------+-------+
```

### ifnull(column name or expression, value or expression if the first parameter is null)
```sql
SELECT ENAME, SAL, COMM, SAL + ifnull (COMM,0) AS "Total" FROM EMP;
```
```
+--------+------+------+-------+
| ENAME  | SAL  | COMM | Total |
+--------+------+------+-------+
| SMITH  |  800 | NULL |   800 |
| ALLEN  | 1600 |  300 |  1900 |
| WARD   | 1250 |  500 |  1750 |
| JONES  | 2975 | NULL |  2975 |
| MARTIN | 1250 | 1400 |  2650 |
| BLAKE  | 2850 | NULL |  2850 |
| CLARK  | 2450 | NULL |  2450 |
| SCOTT  | 3000 | NULL |  3000 |
| KING   | 5000 | NULL |  5000 |
| TURNER | 1500 |    0 |  1500 |
| ADAMS  | 1100 | NULL |  1100 |
| JAMES  |  950 | NULL |   950 |
| FORD   | 3000 | NULL |  3000 |
| MILLER | 1300 | NULL |  1300 |
+--------+------+------+-------+
```

## Coalesce
```sql
SELECT ENAME, SAL, COMM, SAL + coalesce(COMM,0) AS "Total" FROM EMP;
```
```
+--------+------+------+-------+
| ENAME  | SAL  | COMM | Total |
+--------+------+------+-------+
| SMITH  |  800 | NULL |   800 |
| ALLEN  | 1600 |  300 |  1900 |
| WARD   | 1250 |  500 |  1750 |
| JONES  | 2975 | NULL |  2975 |
| MARTIN | 1250 | 1400 |  2650 |
| BLAKE  | 2850 | NULL |  2850 |
| CLARK  | 2450 | NULL |  2450 |
| SCOTT  | 3000 | NULL |  3000 |
| KING   | 5000 | NULL |  5000 |
| TURNER | 1500 |    0 |  1500 |
| ADAMS  | 1100 | NULL |  1100 |
| JAMES  |  950 | NULL |   950 |
| FORD   | 3000 | NULL |  3000 |
| MILLER | 1300 | NULL |  1300 |
+--------+------+------+-------+
```
```sql
SELECT COALESCE(null, null, 78, null, 76, null, 54);
```
```
+----------------------------------------------+
| COALESCE(null, null, 78, null, 76, null, 54) |
+----------------------------------------------+
|                                           78 |
+----------------------------------------------+
```
