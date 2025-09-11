# 2. Database Design  

This note covers the **principles of designing relational schemas**.  
Goal: move from ERD → well-structured tables → ready for SQL + JPA.  

---

## 📌 Normalization (1NF → 3NF → BCNF)  
- **1NF:** eliminate repeating groups; atomic values only.  
- **2NF:** 1NF + remove partial dependency (on part of a composite key).  
- **3NF:** 2NF + remove transitive dependency (non-key depending on another non-key).  
- **BCNF:** stricter than 3NF — every determinant must be a candidate key.  

**Resources:**  
- [Normalization in DBMS - GeeksforGeeks](https://www.geeksforgeeks.org/normal-forms-in-dbms/)  
- [1NF, 2NF, 3NF explained (YouTube)](https://www.youtube.com/watch?v=UrYLYV7WSHM)  
- *Database System Concepts* – Chapter 19 (Design Theory)  

---

## 📌 Denormalization & trade-offs  
- **Denormalization:** intentionally merging tables or adding redundancy to improve performance.  
- Trade-offs:  
  - ✅ Faster reads (fewer joins).  
  - ❌ Harder writes (data duplication, risk of inconsistency).  
- Common in data warehousing & reporting systems.  

**Resources:**  
- [When to Denormalize a Database - Vertabelo](https://vertabelo.com/blog/when-to-denormalize-a-database/)  
- [Normalization vs Denormalization (YouTube)](https://www.youtube.com/watch?v=-qNSXK7s7_w)  

---

## 📌 Keys: primary, foreign, candidate, composite  
- **Primary key (PK):** uniquely identifies a row.  
- **Candidate key:** attribute(s) that can serve as PK.  
- **Foreign key (FK):** establishes relationships across tables.  
- **Composite key:** key made of multiple columns.  

**Resources:**  
- [Keys in DBMS - GFG](https://www.geeksforgeeks.org/types-of-keys-in-relational-model-candidate-super-primary-alternate-and-foreign/)  
- [Database Keys Explained (YouTube)](https://www.youtube.com/watch?v=VJZ9B6rSBlA)  
- *Concise Guide to Databases* – Chapter 2 (covers keys & constraints concisely)  

---

## 📌 Constraints: NOT NULL, UNIQUE, CHECK, FK  
- **NOT NULL:** column cannot store NULL values.  
- **UNIQUE:** all values must be distinct.  
- **CHECK:** enforce condition at row level.  
- **FOREIGN KEY:** maintains referential integrity.  

**Resources:**  
- [SQL Constraints - W3Schools](https://www.w3schools.com/sql/sql_constraints.asp)  
- [SQL Constraints Explained (YouTube)](https://www.youtube.com/watch?v=PBwO1lQH_2I)  
- *SQL Antipatterns* (Bill Karwin) – great for learning what NOT to do.  

---

## 📌 Schema design for real-world systems  
- Translate **requirements → ERD → normalized schema**.  
- Consider:  
  - Data integrity.  
  - Query patterns.  
  - Future scaling (OLTP vs OLAP).  
- Document assumptions + constraints.  

**Resources:**  
- [Database Design Basics - Microsoft Docs](https://learn.microsoft.com/en-us/office/troubleshoot/access/database-design-basics)  
- [Real-World Database Design Example (YouTube)](https://www.youtube.com/watch?v=ztHopE5Wnpc)  
- *Designing Data-Intensive Applications* – Chapter 2 (data models & query languages)  

---

## ✅ Next Steps  
- Take your **Library System ERD** from topic 1.  
- Normalize it to **3NF**.  
- Add **constraints + keys**.  
- Write the full **SQL schema (DDL)**.  
- Implement with **Spring Boot + JPA annotations** (`@Entity`, `@Id`, `@ManyToOne`, etc.).  
