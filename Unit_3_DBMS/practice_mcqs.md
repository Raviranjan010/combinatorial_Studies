# Unit III: DBMS - Graded MCQ Bank

This practice bank contains 130 high-probability Multiple Choice Questions (MCQs) graded by difficulty: **30 Easy**, **50 Medium**, and **50 Hard** questions. Use this bank to test your knowledge of SQL, normalization, index structures, transactions, recovery, and NoSQL systems.

---

## 🟢 Part 1: Easy Level MCQs (1–30)

#### Q1. DBMS stands for:
- A) Data Backup Management System
- B) Database Management System
- C) Data Management Server
- D) Database Memory System
- **Answer: ✅ B**
- **Explanation**: A Database Management System (DBMS) is software designed to store, retrieve, update, and manage database records.

#### Q2. A row in a table is called:
- A) Attribute
- B) Field
- C) Tuple
- D) Domain
- **Answer: ✅ C**
- **Explanation**: In relational database theory (Codd's rules), a table row is formally called a **tuple**.

#### Q3. A column in a table is called:
- A) Attribute
- B) Relation
- C) Tuple
- D) Schema
- **Answer: ✅ A**
- **Explanation**: A column represents a field of the record, formally referred to as an **attribute**.

#### Q4. SQL stands for:
- A) Structured Query Language
- B) Sequential Query Language
- C) System Query Language
- D) Server Query Language
- **Answer: ✅ A**
- **Explanation**: SQL (Structured Query Language) is the standard language used to interact with Relational Database Management Systems.

#### Q5. Which command retrieves data?
- A) INSERT
- B) UPDATE
- C) DELETE
- D) SELECT
- **Answer: ✅ D**
- **Explanation**: The `SELECT` command is a Data Query Language (DQL) command used to retrieve records from database tables.

#### Q6. Which key uniquely identifies a record?
- A) Foreign Key
- B) Composite Key
- C) Primary Key
- D) Alternate Key
- **Answer: ✅ C**
- **Explanation**: A **Primary Key** uniquely identifies each row in a table and cannot contain `NULL` values.

#### Q7. Which SQL clause filters rows?
- A) GROUP BY
- B) WHERE
- C) ORDER BY
- D) HAVING
- **Answer: ✅ B**
- **Explanation**: The `WHERE` clause is used to filter records before any groupings are made.

#### Q8. Which normal form removes repeating groups?
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF
- **Answer: ✅ A**
- **Explanation**: First Normal Form (1NF) requires that all attribute values be atomic (no multi-valued cells or repeating groups).

#### Q9. ACID property "A" stands for:
- A) Accuracy
- B) Atomicity
- C) Access
- D) Availability
- **Answer: ✅ B**
- **Explanation**: Atomicity ensures that all operations in a transaction execute successfully, or none do (All-or-Nothing).

#### Q10. MongoDB is a:
- A) Relational DB
- B) Document DB
- C) Graph DB
- D) Key DB
- **Answer: ✅ B**
- **Explanation**: MongoDB is a popular NoSQL database that stores data in flexible, JSON-like BSON documents.

#### Q11. Which command is used to add data into a table?
- A) SELECT
- B) INSERT
- C) CREATE
- D) ALTER
- **Answer: ✅ B**
- **Explanation**: The `INSERT` command is a DML command used to append new rows/records to a table.

#### Q12. Which SQL command is used to remove all records but keep the table structure?
- A) DROP
- B) DELETE
- C) TRUNCATE
- D) REMOVE
- **Answer: ✅ C**
- **Explanation**: `TRUNCATE` is a DDL command that clears all records by deallocating data pages. It is faster than `DELETE` and cannot be filtered with `WHERE`.

#### Q13. Which key creates a relationship between tables?
- A) Primary Key
- B) Alternate Key
- C) Foreign Key
- D) Candidate Key
- **Answer: ✅ C**
- **Explanation**: A **Foreign Key** in a table points to the primary key of another table, establishing a referential link between them.

#### Q14. How many primary keys can a table have?
- A) Many
- B) Two
- C) One
- D) Zero
- **Answer: ✅ C**
- **Explanation**: A table can have **only one** primary key to uniquely identify records, although that primary key can be composite (contain multiple columns).

#### Q15. Which SQL clause is used for sorting?
- A) HAVING
- B) ORDER BY
- C) GROUP BY
- D) WHERE
- **Answer: ✅ B**
- **Explanation**: The `ORDER BY` clause sorts query results in ascending (`ASC`) or descending (`DESC`) order.

#### Q16. Which aggregate function counts rows?
- A) SUM()
- B) AVG()
- C) COUNT()
- D) MAX()
- **Answer: ✅ C**
- **Explanation**: The `COUNT()` function returns the number of rows that match specified criteria.

#### Q17. Which aggregate function returns the highest value?
- A) MAX()
- B) MIN()
- C) AVG()
- D) COUNT()
- **Answer: ✅ A**
- **Explanation**: The `MAX()` function returns the maximum value in a set of values.

#### Q18. A table is also called:
- A) Tuple
- B) Relation
- C) Domain
- D) Attribute
- **Answer: ✅ B**
- **Explanation**: In relational algebra, a table is formally referred to as a **relation**.

#### Q19. Number of columns in a table is called:
- A) Cardinality
- B) Degree
- C) Relation
- D) Schema
- **Answer: ✅ B**
- **Explanation**: The number of columns/attributes in a table represents its **Degree**.

#### Q20. Number of rows in a table is called:
- A) Degree
- B) Domain
- C) Cardinality
- D) Relation
- **Answer: ✅ C**
- **Explanation**: The total number of rows/records currently stored in a table is its **Cardinality**.

#### Q21. Which join returns matching records only?
- A) LEFT JOIN
- B) RIGHT JOIN
- C) FULL JOIN
- D) INNER JOIN
- **Answer: ✅ D**
- **Explanation**: An `INNER JOIN` returns rows from both tables only when there is a matching key match in both tables.

#### Q22. Which SQL statement creates a table?
- A) INSERT
- B) CREATE
- C) UPDATE
- D) SELECT
- **Answer: ✅ B**
- **Explanation**: The DDL command `CREATE TABLE` is used to establish a new table structure.

#### Q23. Which language category contains the CREATE command?
- A) DML
- B) DCL
- C) DDL
- D) TCL
- **Answer: ✅ C**
- **Explanation**: `CREATE` is a Data Definition Language (DDL) command because it defines/modifies the database schema.

#### Q24. Which language category contains the INSERT command?
- A) DML
- B) DDL
- C) TCL
- D) DCL
- **Answer: ✅ A**
- **Explanation**: `INSERT` modifies row values, categorizing it as a Data Manipulation Language (DML) command.

#### Q25. Which property ensures committed data remains permanent?
- A) Consistency
- B) Isolation
- C) Durability
- D) Atomicity
- **Answer: ✅ C**
- **Explanation**: Durability guarantees that committed transaction changes are written to non-volatile storage and survive power failures or crashes.

#### Q26. Redis is a:
- A) Graph Database
- B) Key-Value Database
- C) Relational Database
- D) Object Database
- **Answer: ✅ B**
- **Explanation**: Redis is an in-memory, open-source Key-Value store commonly used as a database, cache, and message broker.

#### Q27. Which normal form removes transitive dependency?
- A) 1NF
- B) 2NF
- C) 3NF
- D) 4NF
- **Answer: ✅ C**
- **Explanation**: Third Normal Form (3NF) removes transitive functional dependencies (where a non-key attribute determines another non-key attribute).

#### Q28. Which command permanently saves transaction changes?
- A) ROLLBACK
- B) COMMIT
- C) SAVEPOINT
- D) GRANT
- **Answer: ✅ B**
- **Explanation**: The `COMMIT` command signals the successful completion of a transaction and persists all changes to disk.

#### Q29. Which command undoes uncommitted changes?
- A) COMMIT
- B) DELETE
- C) ROLLBACK
- D) DROP
- **Answer: ✅ C**
- **Explanation**: The `ROLLBACK` command reverts the database state back to the start of the transaction or to a defined savepoint.

#### Q30. Which database type is best suited for relationship networks?
- A) Document DB
- B) Key-Value DB
- C) Graph DB
- D) Relational DB
- **Answer: ✅ C**
- **Explanation**: Graph databases (like Neo4j) store entities as nodes and relationships as edges, making them highly optimized for traversing complex networks.

#### Q31. Which key constraint is required for the functioning of the foreign key in a relational database?
- A) Unique key
- B) Primary key
- C) Candidate key
- D) Super key
- **Answer: ✅ B**
- **Explanation**: Foreign keys assert relationship structures across tables by directly pointing to an explicitly mapped primary key index field in the source table.

#### Q32. Given the basic ER and relational models, which of the following statements is incorrect?
- A) An entity relation can have a composite primary key.
- B) In a row of a relational table, an attribute can have more than one value.
- C) A table can have multiple foreign keys.
- D) Relational models represent data as relations (tables).
- **Answer: ✅ B**
- **Explanation**: A core condition of the 1st Normal Form (1NF) in standard table sets is that every row-attribute value domain context must be fully atomic (no multi-valued or repeating attributes).

#### Q33. The DBMS acts as an interface between _______ and _______ of an enterprise class system.
- A) Hardware and Operating System
- B) Database Application and the Database
- C) Web Server and the Client
- D) Query Compiler and the Storage Engine
- **Answer: ✅ B**
- **Explanation**: The DBMS sits between user database applications and the physical stored database files, abstracting data access and management details.

#### Q34. Which of the following commands is correct to delete the values in the relation "Teaches"?
- A) DROP TABLE Teaches;
- B) REMOVE TABLE Teaches;
- C) DELETE FROM Teaches;
- D) ALTER TABLE Teaches DROP VALUES;
- **Answer: ✅ C**
- **Explanation**: The `DELETE FROM table_name;` query flushes internal row records out while maintaining table properties. `DROP` destroys the table schema entirely.

#### Q35. What happens if a piece of data is stored in two places in the database?
- A) Query execution speed is doubled.
- B) Storage space is wasted and changing data in one spot will cause data inconsistency.
- C) ACID properties are automatically satisfied.
- D) The database becomes read-only.
- **Answer: ✅ B**
- **Explanation**: Redundant data storage wastes disk space and introduces the risk of data inconsistency, where updates to one copy are not synchronized with the other.

---

## 🟡 Part 2: Medium Level MCQs (1–50)

#### Q1. Which key is selected from candidate keys to uniquely identify records?
- A) Foreign Key
- B) Composite Key
- C) Primary Key
- D) Alternate Key
- **Answer: ✅ C**
- **Explanation**: A primary key is the candidate key officially chosen by the database architect to uniquely identify table rows.

#### Q2. A candidate key not chosen as primary key is called:
- A) Composite Key
- B) Alternate Key
- C) Foreign Key
- D) Super Key
- **Answer: ✅ B**
- **Explanation**: Alternate keys are candidate keys that were not selected to serve as the primary key.

#### Q3. Which join returns all records from the left table and matching records from the right table?
- A) INNER JOIN
- B) RIGHT JOIN
- C) LEFT JOIN
- D) FULL JOIN
- **Answer: ✅ C**
- **Explanation**: A `LEFT JOIN` (or LEFT OUTER JOIN) returns all records from the left table, filling unmatched right columns with `NULL`.

#### Q4. Which SQL clause is used with aggregate functions?
- A) WHERE
- B) GROUP BY
- C) ORDER BY
- D) ALTER
- **Answer: ✅ B**
- **Explanation**: The `GROUP BY` clause divides table rows into groups to perform computations (like count, sum, average) on each group.

#### Q5. Which SQL clause filters grouped records?
- A) WHERE
- B) HAVING
- C) ORDER BY
- D) DISTINCT
- **Answer: ✅ B**
- **Explanation**: `HAVING` filters group records computed by aggregate functions. `WHERE` filters individual rows *before* grouping occurs.

#### Q6. Which command modifies table structure?
- A) UPDATE
- B) ALTER
- C) INSERT
- D) SELECT
- **Answer: ✅ B**
- **Explanation**: The `ALTER` (e.g., `ALTER TABLE`) command is a DDL command used to add, modify, or drop columns in a table.

#### Q7. Which of the following is not an aggregate function?
- A) AVG()
- B) COUNT()
- C) MAX()
- D) DISTINCT
- **Answer: ✅ D**
- **Explanation**: `DISTINCT` is a keyword used to filter out duplicate rows. `AVG`, `COUNT`, and `MAX` are aggregate mathematical functions.

#### Q8. A super key may contain:
- A) Only one attribute
- B) Extra attributes beyond uniqueness
- C) No attribute
- D) Foreign key only
- **Answer: ✅ B**
- **Explanation**: A super key is any set of attributes that uniquely identifies a row. It can contain extra attributes that are not strictly necessary for uniqueness.

#### Q9. Which normal form removes partial dependency?
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF
- **Answer: ✅ B**
- **Explanation**: Second Normal Form (2NF) requires a relation to be in 1NF and have no partial dependencies (no non-key attribute can depend on a subset of a composite primary key).

#### Q10. BCNF is stricter than:
- A) 1NF
- B) 2NF
- C) 3NF
- D) 4NF
- **Answer: ✅ C**
- **Explanation**: BCNF (Boyce-Codd Normal Form) is a stricter version of 3NF. It eliminates the 3NF exception that allows the right-hand side of an FD to be a prime attribute.

#### Q11. Which transaction state comes immediately after the Active state?
- A) Aborted
- B) Failed
- C) Partially Committed
- D) Committed
- **Answer: ✅ C**
- **Explanation**: After executing the last statement, a transaction enters the "Partially Committed" state, where changes are written to memory buffers but not yet committed to non-volatile disk.

#### Q12. Which ACID property prevents interference among transactions?
- A) Consistency
- B) Isolation
- C) Atomicity
- D) Durability
- **Answer: ✅ B**
- **Explanation**: Isolation guarantees that concurrent transaction executions run independently without viewing intermediate uncommitted data.

#### Q13. Which concurrency problem occurs when uncommitted data is read?
- A) Lost Update
- B) Phantom Read
- C) Dirty Read
- D) Deadlock
- **Answer: ✅ C**
- **Explanation**: A dirty read (Write-Read conflict) occurs when transaction $T_1$ reads data written by $T_2$ that has not yet committed. If $T_2$ aborts, $T_1$ has read invalid data.

#### Q14. Deadlock occurs when:
- A) Database crashes
- B) Transactions wait indefinitely for each other
- C) Table is deleted
- D) Index is corrupted
- **Answer: ✅ B**
- **Explanation**: Deadlock is a state where two or more transactions are blocked waiting for locks held by each other, forming a dependency cycle.

#### Q15. The result of a CROSS JOIN is:
- A) Matching rows only
- B) Cartesian Product
- C) Union
- D) Intersection
- **Answer: ✅ B**
- **Explanation**: A `CROSS JOIN` pairs every row from the first table with every row from the second table, representing the Cartesian Product.

#### Q16. If table A has 5 rows and table B has 4 rows, a CROSS JOIN returns:
- A) 5
- B) 9
- C) 20
- D) 25
- **Answer: ✅ C**
- **Explanation**: Cartesian product row count $= |A| \times |B| = 5 \times 4 = 20$.

#### Q17. An index primarily improves:
- A) Storage Space
- B) Query Performance
- C) Security
- D) Backup
- **Answer: ✅ B**
- **Explanation**: Indexes trade storage space and write performance to dramatically speed up data retrieval querying times.

#### Q18. Which index determines the physical order of data?
- A) Secondary Index
- B) Clustered Index
- C) Hash Index
- D) Dense Index
- **Answer: ✅ B**
- **Explanation**: A clustered index sorts and stores data rows physically on disk according to the index key columns.

#### Q19. Which SQL command removes both table structure and data?
- A) DELETE
- B) TRUNCATE
- C) DROP
- D) UPDATE
- **Answer: ✅ C**
- **Explanation**: The `DROP TABLE` command completely deletes the table data, indexes, and schema from the database catalog.

#### Q20. Which SQL statement grants user permissions?
- A) REVOKE
- B) GRANT
- C) COMMIT
- D) SAVEPOINT
- **Answer: ✅ B**
- **Explanation**: `GRANT` is a DCL command used to assign security privileges and access permissions to database users.

#### Q21. Which NoSQL database is column-family based?
- A) MongoDB
- B) Redis
- C) Cassandra
- D) Neo4j
- **Answer: ✅ C**
- **Explanation**: Apache Cassandra is a highly scalable, distributed Column-Family (Wide-Column) store.

#### Q22. Which NoSQL database stores JSON-like documents?
- A) Redis
- B) Neo4j
- C) MongoDB
- D) HBase
- **Answer: ✅ C**
- **Explanation**: MongoDB is a document store that saves data in BSON format, which is binary JSON.

#### Q23. Replication mainly improves:
- A) Query Syntax
- B) Availability
- C) Degree
- D) Cardinality
- **Answer: ✅ B**
- **Explanation**: By maintaining copies of data across multiple physical servers, replication ensures that the system remains available even if a node crashes.

#### Q24. Horizontal partitioning of data is called:
- A) Replication
- B) Clustering
- C) Sharding
- D) Fragmentation
- **Answer: ✅ C**
- **Explanation**: Sharding partitions a table horizontally, storing subsets of rows across separate database servers to scale load.

#### Q25. Which Big Data characteristic refers to the speed of data generation?
- A) Variety
- B) Value
- C) Volume
- D) Velocity
- **Answer: ✅ D**
- **Explanation**: Velocity is the speed at which new data is generated, collected, and processed.

#### Q26. Which SQL function returns the average value?
- A) COUNT()
- B) SUM()
- C) AVG()
- D) MAX()
- **Answer: ✅ C**
- **Explanation**: The aggregate function `AVG()` returns the mathematical mean of numerical column values.

#### Q27. Which clause removes duplicate rows from query results?
- A) GROUP BY
- B) DISTINCT
- C) HAVING
- D) UNIQUE
- **Answer: ✅ B**
- **Explanation**: Adding `DISTINCT` right after `SELECT` filters out duplicate rows from the final query result set.

#### Q28. Which operator is used for pattern matching in SQL?
- A) IN
- B) BETWEEN
- C) LIKE
- D) EXISTS
- **Answer: ✅ C**
- **Explanation**: The `LIKE` operator is used inside the `WHERE` clause to perform string pattern matching using wildcards.

#### Q29. Which wildcard represents multiple characters in SQL?
- A) _
- B) *
- C) %
- D) #
- **Answer: ✅ C**
- **Explanation**: In standard SQL, the percent sign (`%`) matches zero, one, or multiple characters.

#### Q30. Which wildcard represents exactly one character?
- A) %
- B) _
- C) *
- D) ?
- **Answer: ✅ B**
- **Explanation**: The underscore (`_`) wildcard matches exactly one character in SQL pattern matching.

#### Q31. Which command removes specific rows from a table?
- A) DROP
- B) DELETE
- C) TRUNCATE
- D) ALTER
- **Answer: ✅ B**
- **Explanation**: `DELETE` is a DML command that removes rows matching a specified `WHERE` condition.

#### Q32. Which JOIN returns all records from both tables?
- A) INNER JOIN
- B) LEFT JOIN
- C) RIGHT JOIN
- D) FULL OUTER JOIN
- **Answer: ✅ D**
- **Explanation**: A `FULL OUTER JOIN` returns all records from both left and right tables, mapping unmatched columns to `NULL`.

#### Q33. Which key can uniquely identify a row but is not necessarily selected as the primary key?
- A) Candidate Key
- B) Foreign Key
- C) Composite Key
- D) Surrogate Key
- **Answer: ✅ A**
- **Explanation**: A Candidate Key is any minimal super key that uniquely identifies records. One is selected as the Primary Key; the rest are Alternate Keys.

#### Q34. A table with 8 columns and 200 rows has:
- A) Degree = 200, Cardinality = 8
- B) Degree = 8, Cardinality = 200
- B) Degree = 8, Cardinality = 200
- D) Degree = 8, Cardinality = 25
- **Answer: ✅ B**
- **Explanation**: Degree is columns (8), Cardinality is rows (200).

#### Q35. Which dependency causes violation of 3NF?
- A) Functional Dependency
- B) Partial Dependency
- C) Transitive Dependency
- D) Multivalued Dependency
- **Answer: ✅ C**
- **Explanation**: Transitive dependencies (where non-key attribute $A \to B \to C$) are prohibited in 3NF.

#### Q36. Which normal form ensures every determinant is a candidate key?
- A) 2NF
- B) 3NF
- C) BCNF
- D) 4NF
- **Answer: ✅ C**
- **Explanation**: A relation is in BCNF (Boyce-Codd Normal Form) if for every functional dependency $X \to Y$, the determinant $X$ is a super key.

#### Q37. Which transaction state indicates successful completion?
- A) Active
- B) Failed
- C) Aborted
- D) Committed
- **Answer: ✅ D**
- **Explanation**: A transaction enters the "Committed" state after successfully saving all updates to non-volatile disk.

#### Q38. Which command creates a point to which a transaction can roll back?
- A) GRANT
- B) SAVEPOINT
- C) COMMIT
- D) REVOKE
- **Answer: ✅ B**
- **Explanation**: `SAVEPOINT` creates sub-transaction markers that allow partial rollbacks.

#### Q39. Which ACID property ensures all constraints remain valid?
- A) Consistency
- B) Isolation
- C) Durability
- D) Atomicity
- **Answer: ✅ A**
- **Explanation**: Consistency ensures database transactions transition the database from one valid state to another, maintaining all schema constraints.

#### Q40. Which issue occurs when one transaction overwrites another transaction's update?
- A) Dirty Read
- B) Phantom Read
- C) Lost Update
- D) Deadlock
- **Answer: ✅ C**
- **Explanation**: A lost update occurs when transaction $T_2$ overwrites updates made by uncommitted transaction $T_1$ (Write-Write conflict).

#### Q41. Which indexing technique stores an index entry for every search key value?
- A) Sparse Index
- B) Dense Index
- C) Clustered Index
- D) Composite Index
- **Answer: ✅ B**
- **Explanation**: A dense index maintains a index entry mapping for every record key value in the table file.

#### Q42. Which indexing technique contains entries for only some search key values?
- A) Dense Index
- B) Sparse Index
- C) Secondary Index
- D) Unique Index
- **Answer: ✅ B**
- **Explanation**: A sparse index stores pointer mappings for only select keys (usually representing blocks/pages of data).

#### Q43. Which NoSQL database is best suited for social network relationships?
- A) MongoDB
- B) Cassandra
- C) Redis
- D) Neo4j
- **Answer: ✅ D**
- **Explanation**: Graph databases like Neo4j use node-edge properties that are highly optimized for searching network paths.

#### Q44. Which Big Data characteristic refers to different forms of data?
- A) Velocity
- B) Value
- C) Variety
- D) Veracity
- **Answer: ✅ C**
- **Explanation**: Variety represents the diverse formats of Big Data (structured, semi-structured, and unstructured data).

#### Q45. Which Big Data characteristic refers to the trustworthiness of data?
- A) Variety
- B) Veracity
- C) Volume
- D) Velocity
- **Answer: ✅ B**
- **Explanation**: Veracity refers to the quality, cleanliness, and accuracy of data.

#### Q46. Which architecture keeps one main database and several replica databases?
- A) Sharding
- B) Peer-to-Peer
- C) Master-Slave Replication
- D) Federation
- **Answer: ✅ C**
- **Explanation**: In Master-Slave replication, one master handles writes and distributes updates to slaves which handle reads.

#### Q47. Query optimization mainly aims to:
- A) Increase redundancy
- B) Reduce execution cost
- C) Increase storage
- D) Increase normalization
- **Answer: ✅ B**
- **Explanation**: Optimization processes select query execution paths that minimize hardware cost (Disk I/O, CPU, RAM).

#### Q48. Which SQL subquery returns TRUE if at least one row exists?
- A) ALL
- B) ANY
- C) EXISTS
- D) UNIQUE
- **Answer: ✅ C**
- **Explanation**: The `EXISTS` operator returns true if the nested subquery returns one or more matching rows.

#### Q49. Which operation combines rows from two tables based on related columns?
- A) UNION
- B) JOIN
- C) INTERSECT
- D) DIFFERENCE
- **Answer: ✅ B**
- **Explanation**: A `JOIN` combines column fields from multiple tables using matching key values.

#### Q50. Which SQL operator checks membership in a set?
- A) LIKE
- B) BETWEEN
- C) IN
- D) EXISTS
- **Answer: ✅ C**
- **Explanation**: The `IN` operator filters rows matching values listed in a specified set or returned by a subquery.

---

## 🔴 Part 3: Hard Level MCQs (1–50)

#### Q1. A relation $R(A, B, C)$ has functional dependencies $A \to B$ and $B \to C$. Then $A \to C$ is derived using:
- A) Reflexivity Rule
- B) Augmentation Rule
- C) Transitivity Rule
- D) Decomposition Rule
- **Answer: ✅ C**
- **Explanation**: According to Armstrong's transitivity rule, if $A \to B$ and $B \to C$ hold, then $A \to C$ must hold.

#### Q2. Which normal form specifically removes transitive dependencies?
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF
- **Answer: ✅ C**
- **Explanation**: 3NF prohibits transitive dependencies (where a non-prime attribute determines another non-prime attribute).

#### Q3. A relation is in BCNF if:
- A) Every non-key attribute depends on the primary key
- B) Every determinant is a candidate key
- C) No multivalued dependency exists
- D) No partial dependency exists
- **Answer: ✅ B**
- **Explanation**: In BCNF, for every non-trivial functional dependency $X \to Y$, the left-side determinant $X$ must be a super key.

#### Q4. For a relation $R(A, B, C, D)$ with FD: $(A, B) \to C$. Attribute $C$ depends on only $A$. This violates:
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF
- **Answer: ✅ B**
- **Explanation**: If $C$ depends on $A$ (a subset of composite key $\{A, B\}$), this represents a **partial dependency**, violating 2NF.

#### Q5. If a transaction has committed successfully, which operation cannot undo it?
- A) SAVEPOINT
- B) ROLLBACK
- C) DELETE
- D) UPDATE
- **Answer: ✅ B**
- **Explanation**: A transaction's `COMMIT` is permanent (durable). You cannot run `ROLLBACK` to undo it; you can only execute new compensating transactions (`UPDATE` or `DELETE`).

#### Q6. Which concurrency control technique locks data items during transaction execution?
- A) Timestamp Ordering
- B) Lock-Based Protocol
- C) Validation Protocol
- D) Hashing
- **Answer: ✅ B**
- **Explanation**: Lock-based protocols enforce isolation by forcing transactions to acquire read/write locks before editing records.

#### Q7. Two-phase locking (2PL) guarantees:
- A) Durability
- B) Consistency
- C) Conflict Serializability
- D) Atomicity
- **Answer: ✅ C**
- **Explanation**: 2PL guarantees that any concurrent execution schedule is conflict-serializable (cycle-free precedence graph).

#### Q8. The schedule equivalent to serial execution is called:
- A) Recoverable Schedule
- B) Serializable Schedule
- C) Cascading Schedule
- D) Deadlock Schedule
- **Answer: ✅ B**
- **Explanation**: A schedule is serializable if its net database state effect is identical to running transactions sequentially.

#### Q9. Which ACID property is most directly maintained by locking mechanisms?
- A) Atomicity
- B) Isolation
- C) Durability
- D) Consistency
- **Answer: ✅ B**
- **Explanation**: Locking mechanisms isolate executing transactions, preventing them from interfering with each other.

#### Q10. In a B+ Tree, actual records are stored in:
- A) Root Node
- B) Internal Nodes
- C) Leaf Nodes
- D) Parent Nodes
- **Answer: ✅ C**
- **Explanation**: Unlike B-Trees, B+ Trees store all actual record data pointers exclusively in the leaf nodes.

#### Q11. Which index structure is most commonly used in DBMS?
- A) Linked List
- B) Stack
- C) Queue
- D) B+ Tree
- **Answer: ✅ D**
- **Explanation**: B+ Trees support highly efficient key searches ($O(\log N)$) and block-based sequential range scans.

#### Q12. A clustered index allows:
- A) Multiple physical orderings
- B) One physical ordering of records
- C) No ordering
- D) Random ordering only
- **Answer: ✅ B**
- **Explanation**: A clustered index sorts table rows physically on disk, meaning only one clustered index can exist per table.

#### Q13. Suppose Table A has 100 rows and Table B has 50 rows. A CROSS JOIN returns:
- A) 100
- B) 500
- C) 5000
- D) 150
- **Answer: ✅ C**
- **Explanation**: Total rows $= |A| \times |B| = 100 \times 50 = 5000$.

#### Q14. Which SQL clause is executed first logically?
- A) SELECT
- B) ORDER BY
- C) FROM
- D) HAVING
- **Answer: ✅ C**
- **Explanation**: The DBMS must first fetch the table source (`FROM`), then filter rows (`WHERE`), group them (`GROUP BY`), filter groups (`HAVING`), select columns (`SELECT`), and finally sort (`ORDER BY`).

#### Q15. Which SQL clause is executed after GROUP BY?
- A) SELECT
- B) HAVING
- C) FROM
- D) WHERE
- **Answer: ✅ B**
- **Explanation**: Logically, the `HAVING` clause filters the aggregated groups right after the `GROUP BY` clause evaluates.

#### Q16. Which join is used to find unmatched rows between tables?
- A) INNER JOIN
- B) LEFT/RIGHT OUTER JOIN
- C) CROSS JOIN
- D) SELF JOIN
- **Answer: ✅ B**
- **Explanation**: Outer Joins keep unmatched rows, filling missing columns with `NULL`, which allows identifying unmatched keys.

#### Q17. The CAP theorem states that distributed systems can guarantee at most:
- A) One property
- B) Two properties simultaneously
- C) All three properties
- D) Four properties
- **Answer: ✅ B**
- **Explanation**: CAP theorem states that distributed databases can guarantee at most two of: Consistency, Availability, and Partition Tolerance.

#### Q18. CAP theorem properties are:
- A) Consistency, Availability, Partition Tolerance
- B) Consistency, Atomicity, Performance
- C) Availability, Atomicity, Durability
- D) Consistency, Parallelism, Throughput
- **Answer: ✅ A**
- **Explanation**: CAP stands for Consistency, Availability, and Partition Tolerance.

#### Q19. The BASE model is commonly associated with:
- A) SQL Databases
- B) NoSQL Databases
- C) File Systems
- D) Data Warehouses
- **Answer: ✅ B**
- **Explanation**: NoSQL databases prioritize horizontal scaling by trading strict ACID consistency for the flexible BASE model.

#### Q20. Which NoSQL database category stores data as nodes and edges?
- A) Column Family
- B) Document
- C) Graph
- D) Key-Value
- **Answer: ✅ C**
- **Explanation**: Graph databases represent relationships directly as node and edge entities.

#### Q21. Horizontal scaling means:
- A) Increasing RAM on one server
- B) Increasing CPU on one server
- C) Adding more servers
- D) Increasing cache only
- **Answer: ✅ C**
- **Explanation**: Horizontal scaling (scaling out) involves adding more machine nodes to a database cluster. Scaling up hardware on a single node is vertical scaling.

#### Q22. Sharding primarily improves:
- A) Availability
- B) Scalability
- C) Security
- D) Consistency
- **Answer: ✅ B**
- **Explanation**: Sharding distributes tables across nodes, allowing writes and storage capacity to scale horizontally.

#### Q23. Replication primarily improves:
- A) Availability
- B) Cardinality
- C) Degree
- D) Normalization
- **Answer: ✅ A**
- **Explanation**: Replication maintains backup copies of database shards to guarantee uptime (Availability) during node failures.

#### Q24. A deadlock occurs when:
- A) One transaction aborts
- B) Multiple transactions permanently wait for resources held by each other
- C) Database is normalized
- D) Table is indexed
- **Answer: ✅ B**
- **Explanation**: Deadlock represents a cyclic wait condition among transactions requesting locked resources.

#### Q25. Which recovery technique uses transaction logs?
- A) Checkpointing only
- B) Logging and Recovery Management
- C) Indexing
- D) Hashing
- **Answer: ✅ B**
- **Explanation**: Log-based recovery mechanisms parse transaction log records (REDO/UNDO) to restore database consistency after crashes.

#### Q26. Let relation $R(A, B, C, D, E)$ have functional dependencies $A \to BC$, $CD \to E$, $B \to D$, and $E \to A$. What is the attribute closure of $\{B, C\}$, denoted as $\{B, C\}^+$?
- A) $\{B, C, D\}$
- B) $\{A, B, C, D, E\}$
- C) $\{B, C\}$
- D) $\{B, C, D, E\}$
- **Answer: ✅ B**
- **Explanation**:
  - Start with closure $X^{(0)} = \{B, C\}$.
  - Apply $B \to D \implies X^{(1)} = \{B, C, D\}$.
  - Apply $CD \to E$ (since both $C, D$ are in the set) $\implies X^{(2)} = \{B, C, D, E\}$.
  - Apply $E \to A \implies X^{(3)} = \{A, B, C, D, E\}$.
  - Therefore, $\{B, C\}^+ = \{A, B, C, D, E\}$.

#### Q27. Let a relation schema $R(A, B, C, D, E)$ contain $n=5$ attributes. If the Candidate Keys of $R$ are $\{A, B\}$ and $\{C, D\}$, what is the total number of possible Super Keys?
- A) 12
- B) 16
- C) 14
- D) 10
- **Answer: ✅ C**
- **Explanation**:
  - Using the Principle of Inclusion-Exclusion (PIE):
  - Super keys containing $\{A, B\}$ (size 2): $2^{5-2} = 2^3 = 8$.
  - Super keys containing $\{C, D\}$ (size 2): $2^{5-2} = 2^3 = 8$.
  - Super keys containing both (the union $\{A, B, C, D\}$ has size 4): $2^{5-4} = 2^1 = 2$.
  - Total Super Keys = $8 + 8 - 2 = 14$.

#### Q28. Decomposing relation $R(A, B, C, D)$ with functional dependencies $A \to B, B \to C, C \to D$ into $R_1(A, B)$, $R_2(B, C)$, and $R_3(C, D)$ is:
- A) Lossless and dependency-preserving
- B) Lossy and dependency-preserving
- C) Lossless and non-dependency-preserving
- D) Lossy and non-dependency-preserving
- **Answer: ✅ A**
- **Explanation**:
  - **Lossless Check:** Joining $R_1(A, B)$ and $R_2(B, C)$ on common attribute $B$ is lossless since $B \to C$ holds, yielding $R_{12}(A, B, C)$. Joining $R_{12}$ with $R_3(C, D)$ on $C$ is lossless since $C \to D$ holds. The join is lossless.
  - **Dependency Preservation:** $A \to B$ can be checked in $R_1$, $B \to C$ in $R_2$, and $C \to D$ in $R_3$. All dependencies are preserved.

#### Q29. Consider the concurrent schedule $S: R_1(A), R_2(A), W_1(A), W_2(A), C_1, C_2$. Construct the precedence graph. Is the schedule conflict serializable?
- A) Yes, equivalent to serial order $T_1 \to T_2$
- B) Yes, equivalent to serial order $T_2 \to T_1$
- C) No, it is not conflict serializable
- D) Yes, it is view serializable but not conflict serializable
- **Answer: ✅ C**
- **Explanation**:
  - Conflict 1: $R_2(A) \to W_1(A)$ in different transactions creates edge $T_2 \to T_1$.
  - Conflict 2: $W_1(A) \to W_2(A)$ in different transactions creates edge $T_1 \to T_2$.
  - The precedence graph contains a cycle ($T_1 \leftrightarrow T_2$), making the schedule **not** conflict serializable.

#### Q30. Which of the following locking protocols guarantees conflict serializability and is also completely free from cascading rollbacks?
- A) Basic Two-Phase Locking (2PL)
- B) Strict Two-Phase Locking (Strict 2PL)
- C) Conservative Two-Phase Locking
- D) All of the above
- **Answer: ✅ B**
- **Explanation**:
  Strict 2PL prevents cascading rollbacks by requiring that all exclusive (write) locks be held until commit/abort, ensuring that no other transaction can read uncommitted dirty modifications.

#### Q31. Suppose a database disk block size is 4096 bytes. A search key is 12 bytes long, and a child block pointer is 8 bytes long. In a B+ Tree, what is the maximum order $p$ (number of pointers) of an internal node?
- A) 204
- B) 205
- C) 341
- D) 512
- **Answer: ✅ B**
- **Explanation**:
  - An internal node of order $p$ contains $p$ block pointers and $p-1$ keys.
  - Formula: $p \times 8 + (p - 1) \times 12 \le 4096$
  - $8p + 12p - 12 \le 4096 \implies 20p \le 4108 \implies p \le 205.4$.
  - Thus, the maximum order $p$ is 205.

#### Q32. Under the Timestamp Ordering protocol, what does Thomas' Write Rule allow?
- A) Reads from uncommitted transactions.
- B) Overwriting obsolete write operations by younger transactions without aborting the older transaction.
- C) Deferring all write operations until commit.
- D) Automatic deadlock resolution using locks.
- **Answer: ✅ B**
- **Explanation**:
  Thomas' Write Rule states that if $T$ issues `Write(X)` and $TS(T) < \text{Write-TS}(X)$, the write is ignored (treated as obsolete) because it is overwritten by a younger transaction anyway. This avoids unnecessary aborts.

#### Q33. Which of the following relational algebra expressions is equivalent to the SQL query:
`SELECT name FROM Student WHERE dept = 'CS' AND GPA > 3.5;`
- A) $\pi_{name}(\sigma_{dept = 'CS'}(\sigma_{GPA > 3.5}(Student)))$
- B) $\sigma_{name}(\pi_{dept = 'CS' \land GPA > 3.5}(Student))$
- C) $\pi_{name}(\sigma_{dept = 'CS' \lor GPA > 3.5}(Student))$
- D) $\sigma_{name}(\sigma_{dept = 'CS'}(Student)) \times \sigma_{name}(\sigma_{GPA > 3.5}(Student))$
- **Answer: ✅ A**
- **Explanation**:
  - Nested selections $\sigma_{dept = 'CS'}(\sigma_{GPA > 3.5}(Student))$ filter rows matching both conditions (logical AND).
  - The projection $\pi_{name}$ restricts the final output to the `name` column.

#### Q34. Consider the concurrent schedule $S: W_1(A), R_2(A), W_2(B), C_2, A_1$ (where $A_1$ is the abort of $T_1$). What happens to transaction $T_2$?
- A) $T_2$ is unaffected because it committed.
- B) $T_2$ must be rolled back, causing an unrecoverable schedule error because it read uncommitted data and committed before the writer committed/aborted.
- C) $T_2$ is committed, and $T_1$ will restore $A$ to its old value, creating a data inconsistency.
- D) The DBMS will reject $T_1$'s abort command.
- **Answer: ✅ B**
- **Explanation**:
  - $T_2$ read uncommitted data written by $T_1$ ($R_2(A)$). Since $T_2$ committed ($C_2$) *before* $T_1$ aborted ($A_1$), the schedule is **unrecoverable**.
  - In theory, $T_2$ must be rolled back, but since it committed, this violates durability. The recovery manager must prevent such schedules.

#### Q35. Shared (S) and Exclusive (X) lock request compatibility is defined by which relationship?
- A) S is compatible with S, S is compatible with X
- B) S is compatible with S, S is incompatible with X, X is incompatible with X
- C) S is incompatible with S, X is compatible with X
- D) All lock combinations are compatible
- **Answer: ✅ B**
- **Explanation**:
  - Shared locks are compatible (multiple reads allowed).
  - Exclusive locks are incompatible with other locks (only one writer, blocking all readers/writers).

#### Q36. Which of the following statements is true regarding View Serializability?
- A) Every view serializable schedule is also conflict serializable.
- B) Every conflict serializable schedule is also view serializable.
- C) Conflict serializability and view serializability are completely identical.
- D) View serializability can be tested in polynomial time ($O(N^2)$).
- **Answer: ✅ B**
- **Explanation**:
  Conflict serializability is a stricter, polynomial-time checkable subset of View Serializability. Thus, all conflict-serializable schedules are view-serializable, but not vice versa.

#### Q37. In a B+ Tree index, when a leaf node of maximum capacity $M$ overflows during insertion, what is the standard split procedure?
- A) The node splits, and the middle key is copied to the parent node while remaining in the leaf node.
- B) The node splits, and the middle key is moved (deleted from leaf) to the parent node.
- C) The overflow key is stored in a separate overflow block linked via pointers.
- D) The entire tree is rebuilt.
- **Answer: ✅ A**
- **Explanation**:
  In a B+ Tree, leaf nodes must contain all search key values. Thus, when split, the split boundary key is **copied** (duplicated) to the parent to act as a search guide, while still residing in the leaf.

#### Q40. Let table Employee have 10,000 blocks and a clustered B+ tree index on ID. A search query `SELECT * FROM Employee WHERE ID = 500;` is executed. What is the approximate number of disk block access reads needed?
- A) 10,000 reads
- B) 5,000 reads
- C) $\log_2(10,000) \approx 14$ reads
- D) $\log_B(10,000) \approx 3$ to $4$ reads (where $B$ is B+ tree fan-out)
- **Answer: ✅ D**
- **Explanation**:
  A B+ tree has a high fan-out (e.g., $B \ge 100$). The height of a tree with 10,000 leaves is $\approx 3$ levels. Finding the record requires reading only 3 to 4 blocks from disk. A linear scan would take 10,000 reads.

#### Q41. In query optimization heuristics, why is "Push Selection ($\sigma$) Down" considered a major optimization?
- A) It removes columns from the query result early.
- B) It reduces the number of tuples in intermediate relations, making subsequent operations (like Joins) run much faster on smaller datasets.
- C) It automatically creates indexes on the tables.
- D) It bypasses lock acquisition.
- **Answer: ✅ B**
- **Explanation**:
  Applying selection ($\sigma$) early filters out irrelevant rows, significantly reducing the size of intermediate relations before they are joined or sorted.

#### Q42. In a distributed database system, what are the two phases of the Two-Phase Commit (2PC) protocol?
- A) Growing Phase and Shrinking Phase
- B) Prepare Phase and Commit Phase
- C) Lock Phase and Unlock Phase
- D) Active Phase and Aborted Phase
- **Answer: ✅ B**
- **Explanation**:
  2PC guarantees distributed atomicity:
  1. Prepare Phase: Coordinator votes nodes to see if they can commit.
  2. Commit Phase: If all vote yes, commit is executed; if any node votes no, abort is executed.

#### Q43. A transaction schedule is defined as strict if:
- A) Transactions hold all locks until commit.
- B) It prevents dirty reads only.
- C) No transaction can write to a data item until all transactions that previously wrote to it have committed or aborted.
- D) It does not allow concurrent execution.
- **Answer: ✅ C**
- **Explanation**:
  A schedule is strict if it prevents both dirty reads and dirty writes. This requires that if $T_1$ writes $X$, no other transaction can read or write $X$ until $T_1$ commits or aborts.

#### Q44. Which of the following is NOT a primary inference rule (Armstrong's Axiom)?
- A) Reflexivity (If $Y \subseteq X$, then $X \to Y$)
- B) Augmentation (If $X \to Y$, then $XZ \to YZ$)
- C) Transitivity (If $X \to Y$ and $Y \to Z$, then $X \to Z$)
- D) Pseudotransitivity (If $X \to Y$ and $WY \to Z$, then $WX \to Z$)
- **Answer: ✅ D**
- **Explanation**:
  The three primary Armstrong's axioms are Reflexivity, Augmentation, and Transitivity. Pseudotransitivity is a secondary rule derived from them.

#### Q45. Suppose relation $R(A, B, C)$ has FDs $AB \to C$ and $C \to A$. Candidate keys are $\{A, B\}$ and $\{B, C\}$. Decomposing $R$ into BCNF results in $R_1(C, A)$ and $R_2(C, B)$. Which of the following is true?
- A) The decomposition is lossy.
- B) The dependency $AB \to C$ is lost because its attributes are split across tables.
- C) Both dependencies are preserved.
- D) The decomposition is in 3NF but not BCNF.
- **Answer: ✅ B**
- **Explanation**:
  - $R_1 \cap R_2 = \{C\}$. Since $C \to A$ holds in $R_1$, $C$ is a key of $R_1$, making the decomposition lossless.
  - However, $AB \to C$ cannot be checked in either $R_1(C, A)$ or $R_2(C, B)$ independently. Thus, it is lost.

#### Q46. Which of the following is true about Wound-Wait and Wait-Die deadlock prevention schemes?
- A) Wound-Wait allows younger transactions to wound older ones.
- B) Both protocols prevent deadlocks by ensuring transactions only wait in a single direction of age seniority.
- C) Wait-Die is a preemptive scheme.
- D) Both protocols suffer from starvation of older transactions.
- **Answer: ✅ B**
- **Explanation**:
  Both protocols prevent cycles by using timestamps to enforce a strict waiting order (old waits for young, or young waits for old). Wait-Die is non-preemptive (younger dies), while Wound-Wait is preemptive (older wounds younger).

#### Q47. A system crashes. The recovery log contains:
`<T1, Start>`, `<T1, Commit>`
`<T2, Start>`
`<Checkpoint [T2]>`
`<T3, Start>`
`<System Crash>`
Which transactions must be REDOed and which must be UNDOed during recovery?
- A) REDO T1, REDO T2, UNDO T3
- B) UNDO T2, UNDO T3 (Ignore T1)
- C) REDO T1, UNDO T2, UNDO T3
- D) REDO T3, UNDO T2
- **Answer: ✅ B**
- **Explanation**:
  - $T_1$ committed before the checkpoint, so its changes are safe on disk.
  - $T_2$ was active at checkpoint and never committed. It must be **UNDOed**.
  - $T_3$ started after checkpoint and did not commit. It must be **UNDOed**.

#### Q48. If a database designer increases the index block size from 4KB to 16KB, what is the effect on the B+ Tree index?
- A) Tree height increases, query time slows down.
- B) Node fan-out increases, tree height decreases, reducing disk block reads.
- C) Tree becomes unbalanced.
- D) Storage overhead doubles.
- **Answer: ✅ B**
- **Explanation**:
  A larger block size allows each node to store more keys and pointers (higher fan-out). This packs more structure per node, flattening the tree and reducing the number of disk accesses required to traverse to leaf nodes.

#### Q49. In cost-based query optimization, which cost factor dominates the estimation?
- A) CPU instruction execution speed.
- B) Memory access latency.
- C) The number of disk page transfers (Disk I/O).
- D) Network data transmission rate.
- **Answer: ✅ C**
- **Explanation**:
  Disk access is several orders of magnitude slower than RAM or CPU execution. Therefore, the cost estimator focuses primarily on minimizing the number of disk block read/write operations (Disk I/O).

#### Q50. Why are NoSQL databases easier to scale horizontally compared to relational databases?
- A) NoSQL databases do not support strings.
- B) NoSQL databases avoid joint-table operations and strict ACID transactions, allowing data to be partitioned (sharded) independently across servers without coordinate locks.
- C) NoSQL databases run only in the cloud.
- D) NoSQL databases use faster network protocols.
- **Answer: ✅ B**
- **Explanation**:
  Relational databases enforce strict ACID transactions across tables. Enforcing this across multiple servers requires complex distributed locks (like 2PC), which bottleneck horizontal scaling. NoSQL databases relax these constraints, allowing shards to scale independently.
