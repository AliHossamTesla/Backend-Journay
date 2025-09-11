# 4. Indexing & Query Optimization  

This note covers **indexes and query optimization** — critical for scaling databases.  
Goal: understand how queries are executed, and how indexes + optimizers improve performance.  

---

## 📌 Index basics: B+ trees, hash indexes  
- **B+ trees:** balanced tree structure, default for most RDBMS (Postgres, MySQL InnoDB). Good for range queries.  
- **Hash indexes:** direct key lookups, fast for equality checks. Not suitable for ranges.  

**Resources:**  
- [B+ Tree Indexing - YouTube](https://www.youtube.com/watch?v=aZjYr87r1b8)  
- [Postgres Index Types](https://www.postgresql.org/docs/current/indexes-types.html)  
- *Database System Concepts* – Chapter 11 (Indexing & Hashing)  

---

## 📌 Clustered vs non-clustered indexes  
- **Clustered index:** table rows are physically stored in index order (e.g., InnoDB’s PK). One per table.  
- **Non-clustered index:** separate structure pointing to rows, allows multiple per table.  

**Resources:**  
- [Clustered vs Non-Clustered Index - GFG](https://www.geeksforgeeks.org/difference-between-clustered-and-non-clustered-index/)  
- [MySQL InnoDB Clustered Index docs](https://dev.mysql.com/doc/refman/8.0/en/innodb-index-types.html)  

---

## 📌 Composite & covering indexes  
- **Composite index:** index on multiple columns.  
- **Covering index:** index that includes all needed columns to satisfy a query without touching the table.  

**Resources:**  
- [Composite Index in SQL - DataSchool](https://dataschool.com/sql-optimization/composite-indexes/)  
- [Covering Index Explained - SQLShack](https://www.sqlshack.com/sql-server-covering-index/)  

---

## 📌 Query execution plans (EXPLAIN, ANALYZE)  
- `EXPLAIN` (MySQL, Postgres) → shows how the DB plans to execute a query.  
- `EXPLAIN ANALYZE` (Postgres) → runs the query and shows actual costs.  
- Helps debug slow queries and verify index usage.  

**Resources:**  
- [Using EXPLAIN in Postgres](https://www.postgresql.org/docs/current/using-explain.html)  
- [MySQL EXPLAIN tutorial](https://dev.mysql.com/doc/refman/8.0/en/explain.html)  
- [Execution Plans Deep Dive (YouTube)](https://www.youtube.com/watch?v=9Pzj7Aj25lw)  

---

## 📌 Join algorithms: nested loop, hash join, merge join  
- **Nested loop:** simple, compares each row (good for small sets).  
- **Hash join:** builds hash table for one side, fast for equality joins.  
- **Merge join:** requires sorted input, efficient for large joins.  

**Resources:**  
- [Join Algorithms - CMU DB](https://15445.courses.cs.cmu.edu/fall2021/slides/13-joins.pdf)  
- [Join Algorithms - GFG](https://www.geeksforgeeks.org/join-algorithms-in-dbms/)  
- [Query Processing & Joins (YouTube)](https://www.youtube.com/watch?v=53hva0a43tg)  

---

## 📌 Cost-based optimization  
- The DB optimizer chooses query plans based on estimated **cost** (I/O, CPU, memory).  
- Uses statistics (table size, histograms, cardinality).  
- Goal: minimize total cost, not always intuitive to humans.  

**Resources:**  
- [Query Optimization Overview - IBM Docs](https://www.ibm.com/docs/en/db2/11.5?topic=performance-query-optimization)  
- [Postgres Query Planning](https://www.postgresql.org/docs/current/planner-optimizer.html)  
- *Database System Concepts* – Chapter 15 (Query Optimization)  

---

## ✅ Next Steps  
1. On your **Library System DB**:  
   - Create a composite index on `(user_id, book_id)` for loans.  
   - Compare `EXPLAIN` results before vs after index.  
   - Try `JOIN` queries and identify which algorithm is chosen (nested loop, hash join).  
2. Add queries that can benefit from covering indexes.  
3. Benchmark queries with and without indexes (Postgres recommended).  
