## 📋 DBMS Interview Questions with Answers

1. **What is RDBMS? Why RDBMS? Advantages?**  
   A Relational Database Management System (RDBMS) stores data in tables.  
   - Supports relations between tables using keys  
   - Enforces data integrity  
   - Allows complex queries using SQL  
   - Examples: MySQL, Oracle, SQL Server  

2. **What types of keys are there in RDBMS?**  
   - Primary Key  
   - Unique Key  
   - Foreign Key  
   - Composite Key  
   - Candidate Key  
   - Alternate Key  

3. **Difference between PRIMARY KEY and UNIQUE KEY**  
   - PRIMARY KEY: No NULLs allowed, only one per table  
   - UNIQUE KEY: Allows one NULL, multiple unique keys possible  

4. **Data Types in SQL**  
   - `CHAR`, `VARCHAR`, `TEXT`, `INT`, `FLOAT`, `DECIMAL`, `DATE`, `BOOLEAN`, etc.

5. **Difference between CHAR and VARCHAR**  
   - `CHAR`: Fixed length (padded with spaces)  
   - `VARCHAR`: Variable length (saves space)

6. **Precision and Scale — What is `NUMERIC(8, 2)`?**  
   - Precision = total digits (8)  
   - Scale = digits after decimal (2)  
   - Ex: `123456.78`

7. **Difference between SQL and MySQL**  
   - SQL: Language used to interact with DBs  
   - MySQL: RDBMS that uses SQL as its query language  

8. **Transaction Management — Types? DDL effect?**  
   - Types: Implicit and Explicit  
   - DDL auto-commits — cannot be rolled back  
   - `ROLLBACK`, `COMMIT` used in DML  

9. **String Functions**  
   - `SUBSTR`, `SUBSTRING`, `UPPER`, `LOWER`, `IFNULL`, `COALESCE`

10. **NULL Handling?**  
    - `IS NULL`, `IS NOT NULL`  
    - Use `IFNULL()`, `COALESCE()` to handle NULLs in queries

11. **YEAR Functions?**  
    - `YEAR(date_column)`, `MONTH()`, `DAY()`, `DATEDIFF()`, `NOW()`  

12. **Software Analysis: 2nd Highest Salary**  
    ```sql
    SELECT MAX(salary) 
    FROM employees 
    WHERE salary < (SELECT MAX(salary) FROM employees);
    ```

13. **Window Functions**  
    - `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LAG()`, `LEAD()`

14. **Difference between HAVING and WHERE**  
    - `WHERE`: Used before aggregation  
    - `HAVING`: Used after `GROUP BY` for filtering aggregated results  

15. **Execution Order of SQL Clauses**  
    `FROM` → `WHERE` → `GROUP BY` → `HAVING` → `SELECT` → `ORDER BY` → `LIMIT`

16. **Normalization**  
    - Process to remove redundancy and improve data integrity  
    - **2NF**: Remove partial dependency from 1NF

17. **How to resolve many-to-many relationships?**  
    - Use a **junction table** with foreign keys from both tables  

18. **Types of Cardinality**  
    - One-to-One  
    - One-to-Many  
    - Many-to-Many  
    - Example: One customer can place many orders  

19. **Referential Integrity?**  
    - Ensures foreign keys refer to valid rows in parent table  

20. **Strong Entity vs Weak Entity**  
    - **Strong**: Has primary key  
    - **Weak**: Depends on another table (uses foreign + partial key)

21. **Purpose of LIMIT Clause**  
    - Restricts number of rows in result  
    - Execution happens last (after `ORDER BY`)

22. **Example use case of Derived Table**  
    - Use it to filter based on aggregates  
    ```sql
    SELECT * FROM (
      SELECT empno, salary, RANK() OVER (ORDER BY salary DESC) as rnk
      FROM employees
    ) AS ranked_emps
    WHERE rnk <= 3;
    ```

23. **Top 4 Salaries using Derived Table**  
    ```sql
    SELECT * FROM (
      SELECT *, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk
      FROM employees
    ) AS top_salaries
    WHERE rnk <= 4;
    ```

24. **SET Operators: UNION vs INTERSECT**  
    - `UNION`: Combines unique rows from two queries  
    - `INTERSECT`: Returns common rows between two queries  

25. **Correlated Subqueries**  
    - Subquery uses value from outer query  
    ```sql
    SELECT name FROM emp e1 
    WHERE salary > (SELECT AVG(salary) FROM emp WHERE dept_id = e1.dept_id);
    ```

26. **CTE (Common Table Expression)**  
    - Temporary result set  
    ```sql
    WITH temp AS (
      SELECT dept_id, COUNT(*) AS emp_count FROM emp GROUP BY dept_id
    )
    SELECT * FROM temp WHERE emp_count > 5;
    ```

27. **Window Functions You Know**  
    - `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LAG()`, `LEAD()`, `NTILE()`

28. **Difference between OLTP and OLAP**  
    - **OLTP**: Day-to-day operations (Insert, Update, Delete)  
    - **OLAP**: Analytical processing (aggregations, summaries)  

29. **SQL vs NoSQL Databases**  
    - SQL: Structured, tabular format  
    - NoSQL: Unstructured, schema-less (JSON, key-value, etc.)

30. **Types of NoSQL Databases**  
    - **Document-based** (MongoDB)  
    - **Columnar** (Cassandra)  
    - **Key-Value** (Redis)  
    - **Graph-based** (Neo4j)

31. **Difference between TRUNCATE and DELETE**  
    - `DELETE`: Can have WHERE clause, is transactional  
    - `TRUNCATE`: Removes all rows, faster, cannot be rolled back


## ✅ Interview Mindset & Answering Strategy

- 🎯 **Stick to the question.**  
  If asked about `GROUP BY`, talk *only* about `GROUP BY`.  
  Don’t jump to `HAVING` or additional clauses unless specifically asked.

- 🤐 **Don’t overshare.**  
  Even if you know more, hold it back.  
  Focused answers show clarity and control.

- ❌ **Don’t guess.**  
  If you don’t know the answer, simply say:  
  `"I’m not able to recollect at the moment."`  
  – It’s better to be humble than wrong.

- 🧠 **Explain logic if name is forgotten.**  
  If you forget a function's name but know its purpose, explain what it does.  
  The interviewer might help you remember the name.

> 🚀 Being accurate, humble, and concise leaves a better impression than trying to show off everything you know.


# 💼 How to Crack an SQL Interview

## ✅ Top Strategy:
When you're asked **"What have you learned in SQL?"**, **start with Window Functions** — they are high-impact, frequently used in the industry, and demonstrate depth.

> 💡 **Pro Tip:** Recruiters love candidates who go beyond `SELECT *` and show expertise in analytical querying.

---

## 🎯 Key Topics to Emphasize:

1. **Window Functions**  
   Start strong with `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LAG()`, `LEAD()`, etc.
   - Talk about how they're **more efficient and readable** compared to derived tables or subqueries.
   - Share use cases like **running totals, rankings, comparisons, and first/last value retrievals**.

2. **Common Table Expressions (CTEs)**  
   Show your ability to write modular, readable queries.
   - Use examples with `WITH` clause and recursive CTEs if possible.

3. **Joins & Subqueries**  
   - Demonstrate confidence in different join types and use-cases.
   - Be able to explain **correlated vs non-correlated subqueries**.

4. **GROUP BY vs Window Functions**  
   - Show how `GROUP BY` collapses rows, while **window functions preserve row-level detail**.

5. **Data Transformation & Aggregation**  
   - Pivoting/unpivoting data.
   - Using `CASE WHEN` for conditional aggregation.

6. **Performance & Optimization**  
   - Talk about indexes, `EXPLAIN`, and query optimization basics if you're applying for data engineering or backend-heavy roles.

---

## 🔥 Final Tips:

- 🧠 Practice SQL on platforms like **LeetCode**, **Hackerrank**, and **StrataScratch**.
- ✍️ Be ready to **write queries live** (e.g., Google Docs or online SQL editors).
- 🌐 Understand **real-world use cases**:
  - Reporting
  - Dashboards
  - Analytics
- 🔧 Emphasize how **SQL fits into the data pipeline** or application logic in a project you’ve worked on.

---

> 💬 “**SQL isn’t just about querying — it’s about telling the story hidden in the data.**”  
> Make sure that comes across in your interview!
