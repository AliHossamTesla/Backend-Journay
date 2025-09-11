# 1. Foundations of Databases  

This note introduces the **core foundations** of databases, answering the *why* and the *what* before diving into design and SQL.  

---

## 📌 What is a database? Why not just files?  
- A **database** is an organized collection of data that ensures consistency, concurrency, durability, and efficient querying.  
- Filesystems are good for raw storage, but:  
  - No integrity constraints.  
  - Hard to manage relationships.  
  - Poor scalability with concurrent users.  
  - No query language for flexible retrieval.  

**Resources:**  
- [CMU Database Intro Lecture (YouTube)](https://www.youtube.com/watch?v=4cWkVbC2bNE)  
- [DBMS vs Filesystem - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-file-system-and-dbms/)  
- *Database System Concepts* (Silberschatz et al.) – Chapter 1  

---

## 📌 Relational model: tables, rows, columns, relations  
- **Table (relation):** collection of tuples (rows).  
- **Row (tuple):** a record.  
- **Column (attribute):** property of the entity.  
- **Primary key:** uniquely identifies a row.  
- **Foreign key:** enforces relationships between tables.  

**Resources:**  
- [Intro to Relational Databases - freeCodeCamp](https://www.youtube.com/watch?v=HXV3zeQKqGY)  
- [Relational Model - GeeksforGeeks](https://www.geeksforgeeks.org/relational-model-in-dbms/)  
- *Database System Concepts* – Chapter 2  

---

## 📌 ERD (Entity–Relationship Diagrams)  
- **Entity:** object in the system (e.g., Student, Course).  
- **Attributes:** properties of entities.  
- **Relationships:** associations (e.g., Student → Enrolls → Course).  
- Cardinalities: 1:1, 1:N, N:M.  

**Tools to practice:**  
- Draw.io (free online diagrams)  
- dbdiagram.io (fast ERD drawing)  

**Resources:**  
- [ER Diagrams Tutorial - Lucidchart](https://www.lucidchart.com/pages/er-diagrams)  
- [Chen vs Crow’s Foot Notation](https://vertabelo.com/blog/crow-s-foot-notation/)  
- *Fundamentals of Database Systems* (Elmasri & Navathe) – Chapter 3  

---

## 📌 Relational algebra basics (selection, projection, joins, union, difference)  
- **Selection (σ):** filter rows.  
- **Projection (π):** choose specific columns.  
- **Join (⨝):** combine tables on matching attributes.  
- **Union (∪):** combine rows from two tables.  
- **Difference (−):** subtract one set of rows from another.  

**Resources:**  
- [Relational Algebra Basics - Stanford](https://web.stanford.edu/class/cs345d/lectures/relalg.pdf)  
- [Relational Algebra in DBMS - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)  
- *Database System Concepts* – Chapter 6  

---

## ✅ Next Steps  
- Draw a simple ERD for a **Library System** (Books, Authors, Users, Loans).  
- Convert to relational schema (tables with keys).  
- Normalize to 3NF.  
- Implement schema in SQL.  
