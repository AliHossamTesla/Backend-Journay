# 3. SQL Mastery  

This note covers **SQL essentials → advanced features**.  
Goal: be fluent in both **MySQL** and **PostgreSQL**, with skills portable to any RDBMS.  

---

## 📌 DDL: CREATE, ALTER, DROP  
- **CREATE** → define database objects (tables, views, indexes).  
- **ALTER** → change schema (add/remove columns, constraints).  
- **DROP** → delete objects.  

**Resources:**  
- [W3Schools SQL DDL](https://www.w3schools.com/sql/sql_ref_sqlserver.asp)  
- [PostgreSQL CREATE TABLE docs](https://www.postgresql.org/docs/current/sql-createtable.html)  
- *Database System Concepts* – SQL chapter  

---

## 📌 DML: SELECT, INSERT, UPDATE, DELETE  
- **SELECT** → query data.  
- **INSERT** → add new rows.  
- **UPDATE** → modify rows.  
- **DELETE** → remove rows.  

**Resources:**  
- [SQL Tutorial - Mode Analytics](https://mode.com/sql-tutorial/)  
- [Postgres SELECT docs](https://www.postgresql.org/docs/current/sql-select.html)  
- [MySQL DML docs](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  

---

## 📌 Joins: INNER, LEFT, RIGHT, FULL  
- **INNER JOIN:** rows with matches in both tables.  
- **LEFT JOIN:** all left rows + matched right.  
- **RIGHT JOIN:** all right rows + matched left.  
- **FULL JOIN:** all rows from both (Postgres only).  

**Resources:**  
- [Visual Guide to Joins](https://sql-joins.leopard.in.ua/)  
- [Joins in SQL - GFG](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)  

---

## 📌 Aggregations: COUNT, SUM, GROUP BY, HAVING  
- Aggregate functions summarize groups of rows.  
- `GROUP BY` defines the grouping key.  
- `HAVING` filters groups after aggregation.  

**Resources:**  
- [SQL Aggregates - Mode Analytics](https://mode.com/sql-tutorial/sql-aggregate-functions/)  
- [Postgres Aggregates docs](https://www.postgresql.org/docs/current/functions-aggregate.html)  

---

## 📌 Subqueries (nested, correlated)  
- **Nested:** subquery runs independently.  
- **Correlated:** subquery depends on outer query row.  

**Resources:**  
- [SQL Subqueries - W3Schools](https://www.w3schools.com/sql/sql_subqueries.asp)  
- [Correlated vs Nested - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-correlated-and-nested-sub-query/)  

---

## 📌 Views, triggers, stored procedures  
- **View:** saved query as a virtual table.  
- **Trigger:** automatic action when an event happens (INSERT, UPDATE).  
- **Stored procedure:** saved routine with parameters.  

**Resources:**  
- [Postgres Views](https://www.postgresql.org/docs/current/sql-createview.html)  
- [MySQL Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html)  
- [Stored Procedures in SQL Server (concepts apply)](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/stored-procedures-database-engine)  

---

## 📌 Window functions (ROW_NUMBER, RANK, LEAD/LAG)  
- Operate on a **window of rows** relative to the current row.  
- Examples:  
  - `ROW_NUMBER()` → sequential numbering.  
  - `RANK()` → rank with ties.  
  - `LEAD()/LAG()` → access next/previous row.  

**Resources:**  
- [Postgres Window Functions](https://www.postgresql.org/docs/current/tutorial-window.html)  
- [Window Functions Intro (Mode)](https://mode.com/sql-tutorial/sql-window-functions/)  
- [Window Functions Visual Guide (YouTube)](https://www.youtube.com/watch?v=emFMHH2Bfvo)  

---

## 📌 [[MySQL]]  
- Popular for web apps.  
- Great documentation & wide support.  
- Strong with simple queries, but weaker advanced features (window funcs, CTEs pre-8.0).  

**Resources:**  
- [MySQL Official Docs](https://dev.mysql.com/doc/)  
- [MySQL Tutorial (YouTube)](https://www.youtube.com/watch?v=7S_tz1z_5bA)  

---

## 📌 [[PostgreSQL]]  
- Advanced, feature-rich RDBMS.  
- Full JOIN support, rich window functions, CTEs, JSON support.  
- Excellent for **Spring Boot + JPA projects**.  

**Resources:**  
- [PostgreSQL Official Docs](https://www.postgresql.org/docs/)  
- [Postgres Full Course (YouTube)](https://www.youtube.com/watch?v=qw--VYLpxG4)  

---

## ✅ Next Steps  
- Reuse your **Library System schema**.  
- Practice:  
  - Write DDL to create tables.  
  - Insert sample data.  
  - Run JOIN queries (books borrowed by each user).  
  - Use `GROUP BY` (books borrowed per user).  
  - Add a view (`active_loans`).  
  - Write a trigger (`update_return_date`).  
  - Try a window function (`ROW_NUMBER()` on loans).  
- Implement queries inside **Spring Data JPA** (`@Query` + JPQL).  
