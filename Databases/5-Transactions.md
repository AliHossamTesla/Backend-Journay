# 5. Transactions & Concurrency  

This note covers **transactions, concurrency, and recovery mechanisms** — the foundation for reliable DB operations.  

---

## 📌 ACID properties  
- **Atomicity** → all or nothing.  
- **Consistency** → DB moves from one valid state to another.  
- **Isolation** → transactions appear independent.  
- **Durability** → committed data survives crashes.  

**Resources:**  
- [ACID Explained - IBM](https://www.ibm.com/docs/en/db2/11.5?topic=concepts-acid-properties)  
- [ACID Transactions (YouTube)](https://www.youtube.com/watch?v=5ZjhNTM8XU8)  
- *Database System Concepts* – Chapter 16  

---

## 📌 Concurrency problems: dirty reads, lost updates, phantom reads  
- **Dirty read:** read uncommitted changes from another transaction.  
- **Lost update:** two transactions overwrite each other.  
- **Non-repeatable read:** same query returns different results within one transaction.  
- **Phantom read:** new rows appear/disappear in repeated queries.  

**Resources:**  
- [Concurrency Problems - GFG](https://www.geeksforgeeks.org/concurrency-control-in-dbms/)  
- [Transaction Anomalies (YouTube)](https://www.youtube.com/watch?v=LoF3RZ9P5J0)  

---

## 📌 Isolation levels (RU, RC, RR, Serializable)  
- **Read Uncommitted (RU):** allows dirty reads.  
- **Read Committed (RC):** prevents dirty reads.  
- **Repeatable Read (RR):** prevents dirty + non-repeatable reads.  
- **Serializable:** strictest, full isolation, but can reduce concurrency.  

**Resources:**  
- [Postgres Isolation Levels](https://www.postgresql.org/docs/current/transaction-iso.html)  
- [SQL Server Isolation Levels (conceptual)](https://learn.microsoft.com/en-us/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
- [Isolation Levels Explained (YouTube)](https://www.youtube.com/watch?v=2dQv6uK_mgE)  

---

## 📌 Locking: row-level, table-level, shared vs exclusive locks  
- **Row-level locks:** fine-grained, higher concurrency.  
- **Table-level locks:** coarser, simpler but reduces concurrency.  
- **Shared (S) lock:** multiple transactions can read.  
- **Exclusive (X) lock:** only one transaction can write.  

**Resources:**  
- [Postgres Locking Guide](https://www.postgresql.org/docs/current/explicit-locking.html)  
- [Lock Types - GFG](https://www.geeksforgeeks.org/locking-in-dbms/)  

---

## 📌 Deadlocks & prevention  
- **Deadlock:** two transactions wait for each other’s locks.  
- **Prevention techniques:**  
  - Ordering resource access.  
  - Timeout detection.  
  - Wait-Die / Wound-Wait schemes.  

**Resources:**  
- [Deadlocks in DBMS - GFG](https://www.geeksforgeeks.org/deadlock-in-dbms/)  
- [Deadlocks Explained (YouTube)](https://www.youtube.com/watch?v=YXlM5I_FTKA)  

---

## 📌 WAL (Write-Ahead Logging) & recovery  
- **WAL principle:** log changes **before** applying them to the database.  
- Enables crash recovery → replay committed transactions, undo incomplete ones.  
- Core to Postgres & InnoDB durability.  

**Resources:**  
- [Postgres WAL Docs](https://www.postgresql.org/docs/current/wal-intro.html)  
- [WAL in DBMS - GFG](https://www.geeksforgeeks.org/write-ahead-logging-in-dbms/)  
- [Crash Recovery & WAL (YouTube)](https://www.youtube.com/watch?v=nbYl4TOJWe8)  

---

## ✅ Next Steps  
1. On your **Library System DB**:  
   - Run two concurrent transactions (Postgres `psql` sessions).  
   - Test anomalies: dirty read, lost update.  
   - Switch isolation levels (`SET TRANSACTION ISOLATION LEVEL`).  
2. Use `EXPLAIN` + `pg_locks` in Postgres to inspect locks.  
3. Enable WAL logs in Postgres and simulate crash recovery with `pg_resetwal`.  
4. In **Spring Boot + JPA**:  
   - Use `@Transactional(isolation = Isolation.REPEATABLE_READ)` and test concurrency.  
   - Observe differences between isolation levels in practice.  
