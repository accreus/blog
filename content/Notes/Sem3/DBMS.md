> * [[Notes/Sem3/index|index]]
---
# Briefing on Database Management Systems

## 1. Fundamentals of Database Management Systems

### 1.1. Core Definitions

|   |   |
|---|---|
|Term|Definition|
|**Data**|Raw, unorganized facts that need to be processed. For example, a person's name, age, or weight.|
|**Information**|Data that has been processed, organized, or structured in a given context to make it useful.|
|**Database**|A collection of logically inter-related data, such as a student database in a university.|
|**DBMS**|A collection of inter-related data and a set of programs to manipulate that data. It is software for creating and managing databases (e.g., MS SQL Server, Oracle, MySQL).|
|**Metadata**|Data about data. This includes information like table names, column names, data types, and user access privileges.|
|**Data Dictionary**|An information repository that contains metadata, often as part of the system catalog.|
|**Record (Tuple)**|A collection of logically related fields, representing a single horizontal entry in a table.|
|**Field (Data Item)**|A character or group of characters with a specific meaning, represented by a value in the database.|

### 1.2. Advantages of DBMS over File Processing Systems

A DBMS is designed to overcome the significant limitations of traditional file-based data management.

|   |   |
|---|---|
|Disadvantage of File Systems|Corresponding DBMS Advantage|
|**Data Redundancy**|**Minimal Data Redundancy:** Centralized storage avoids unnecessary duplication of data, saving memory and reducing extra processing.|
|**Data Inconsistency**|**Improved Data Consistency:** By reducing redundancy, DBMS eliminates inconsistencies that arise when the same data is updated in only one of several locations.|
|**Difficulty in Accessing Data**|**Efficient Data Access:** DBMS provides query languages (like SQL) to retrieve required data conveniently, eliminating the need for custom programs for each new query.|
|**Limited Data Sharing / Data Isolation**|**Shared Data:** Data is no longer scattered in various files with different formats. All authorized users and applications can easily share the database.|
|**Integrity Problems**|**Enhanced Data Integrity:** DBMS provides mechanisms to enforce constraints (rules, e.g., account balance cannot be negative), ensuring data is correct and consistent.|
|**Atomicity Problems**|**Guaranteed Atomicity:** Any operation on the database (a transaction) is treated as an atomic unit—it is either executed 100% or 0%, preventing inconsistent states from partial operations.|
|**Concurrent Access Anomalies**|**Controlled Concurrent Access:** DBMS supervises simultaneous access by multiple users, preventing anomalies and ensuring better system performance and faster response.|
|**Security Problems**|**Improved Data Security:** DBMS offers robust security mechanisms to control access, allowing users to access only the data they are authorized for.|
|**No Backup/Recovery**|**Backup and Recovery Services:** Provides facilities to backup and restore the database in the event of system failures.|

### 1.3. Database System Architecture

#### 1.3.1. ANSI SPARC Three-Level Architecture

This architecture promotes data independence by separating the database into three levels of abstraction.

- **Internal Level (Physical Level):** The lowest level, describing _how_ data is physically stored on storage devices. It deals with file structures, pages, blocks, and indexes. It is defined by the internal schema.
- **Conceptual Level (Logical Level):** The middle level, describing _what_ data is stored in the database and the relationships among that data. It hides the complexities of physical storage. It is defined by the conceptual schema, and DBAs primarily work at this level.
- **External Level (View Level):** The highest level, describing only the part of the database that a particular end-user requires. A single database can have multiple external views for different users. It is defined by external schemas.

The process of transforming requests and results between these levels is called **mapping**.

#### 1.3.2. Data Independence

Data independence is the ability to modify a schema at one level without affecting the schema at the next higher level.

- **Physical Data Independence:** The ability to modify the internal (physical) schema without changing the conceptual schema. This allows for performance improvements at the physical level (e.g., changing storage devices or hashing algorithms) without impacting applications.
- **Logical Data Independence:** The ability to modify the conceptual (logical) schema without requiring changes in external schemas or application programs. This allows the logical structure of the database to evolve.

#### 1.3.3. Three-Tier Architecture

This is the most widely used client-server architecture, separating the system into three logical tiers:

1. **Database (Data) Tier:** This tier houses the database, its query processing languages, and all stored relations and constraints.
2. **Application (Middle) Tier:** This tier contains the application server and the business logic. It acts as an intermediary, accessing the database on behalf of the user and presenting an abstracted view to the presentation tier.
3. **User (Presentation) Tier:** This is the end-user's interface (e.g., a web browser or client application). Users at this tier are unaware of the underlying database structure.

#### 1.3.4. Components of a DBMS

A DBMS is composed of two primary functional units:

1. **Query Processor Units:** These components handle the execution of DDL and DML statements. They include:
    - **DDL Interpreter:** Interprets DDL statements and records the definitions in the data dictionary.
    - **DML Compiler:** Translates DML statements into low-level instructions for the query evaluation engine.
    - **Query Evaluation Engine:** Executes the low-level instructions generated by the DML compiler.
2. **Storage Manager Units:** This provides the interface between the low-level data stored on disk and the application programs and queries. It includes:
    - **Authorization and Integrity Manager:** Enforces security and integrity constraints.
    - **Transaction Manager:** Ensures database consistency and handles atomicity and durability.
    - **File Manager:** Manages the allocation of space on disk storage.
    - **Buffer Manager:** Fetches data from disk storage into main memory and decides what data to cache.

These components interact with the physical disk storage, which contains the Data Files, Data Dictionary, Indices, and Statistical Data.

### 1.4. Database Users and Administrator

#### 1.4.1. Types of Database Users

- **Naive Users (End Users):** Unsophisticated users with little to no knowledge of the database system. They interact with the system through pre-written application programs with user-friendly interfaces (e.g., a bank clerk using a banking application).
- **Application Programmers:** Professionals who write application programs using tools like Java or PHP to interact with the database.
- **Sophisticated Users:** Users who interact with the system without writing programs, instead forming their requests using a database query language like SQL (e.g., analysts).
- **Specialized Users (DBA):** Users who write specialized database applications that do not fit the traditional data-processing framework, such as the Database Administrator.

#### 1.4.2. Role of the Database Administrator (DBA)

The DBA is the person who controls the design and use of the database. Key responsibilities include:

- **Schema Definition:** Defines the logical schema of the database.
- **Storage Structure and Access Method Definition:** Decides how data is represented and accessed.
- **Defining Security and Integrity Constraints:** Establishes rules to protect data and ensure its correctness.
- **Granting Authorization for Data Access:** Determines which users have access to which parts of the database.
- **Monitoring Performance and Responding to Changes:** Tunes the database for optimal performance.
- **Backup and Recovery:** Manages backup and recovery procedures.

## 2. The Entity-Relationship (E-R) Model

The E-R model is a high-level, conceptual data model that provides a graphical representation of entities, their attributes, and the relationships between them.

### 2.1. Core Concepts

|   |   |   |
|---|---|---|
|Concept|Description|Symbol|
|**Entity**|A real-world object or thing that is distinguishable from other objects (e.g., `Student`, `Course`).|Rectangle|
|**Entity Set**|A set of entities of the same type that share the same properties.|Rectangle|
|**Attribute**|A property or detail that describes an entity (e.g., `RollNo` for a `Student`).|Oval|
|**Relationship**|An association or connection between two or more entities (e.g., a `Student` _enrolls in_ a `Course`).|Diamond|

### 2.2. Types of Attributes

|   |   |   |   |
|---|---|---|---|
|Attribute Type|Description|Example|Symbol|
|**Simple**|Cannot be divided into subparts.|`CPI`, `Age`|Single Oval|
|**Composite**|Can be divided into subparts.|`Name` (First Name, Middle Name, Last Name)|Oval connected to smaller ovals|
|**Single-valued**|Can have only one value for a particular entity.|`RollNo`|Single Oval|
|**Multi-valued**|Can have more than one value for a particular entity.|`MobileNo`|Double Oval|
|**Stored**|An attribute whose value is stored directly in the database.|`BirthDate`|Single Oval|
|**Derived**|An attribute whose value can be calculated from other stored attributes.|`Age` (derived from `BirthDate`)|Dashed Oval|
|**Descriptive**|An attribute of a relationship set.|`Issue_Date` for the `Issue` relationship|Oval connected to the relationship diamond|

### 2.3. Constraints in the E-R Model

#### 2.3.1. Mapping Cardinalities

This defines the number of entities in one set that can be associated with the number of entities in another set via a relationship.

- **One-to-One (1:1):** An entity in set A is associated with at most one entity in set B, and vice-versa.
- **One-to-Many (1:N):** An entity in set A is associated with any number of entities in set B, but an entity in B is associated with at most one entity in A.
- **Many-to-One (N:1):** An entity in set A is associated with at most one entity in B, but an entity in B is associated with any number of entities in A.
- **Many-to-Many (N:N):** An entity in set A is associated with any number of entities in B, and vice-versa.

#### 2.3.2. Participation Constraints

This specifies whether the existence of an entity depends on its being related to another entity via the relationship.

- **Total Participation:** Every entity in the entity set must participate in at least one relationship instance. This is indicated by a **double line** connecting the entity set to the relationship.
- **Partial Participation:** Some entities in the entity set may not participate in any relationship instance. This is indicated by a **single line**.

### 2.4. Advanced E-R Concepts

- **Weak Entity Set:** An entity set that does not have a sufficient set of attributes to form a primary key. Its existence depends on a strong (identifying) entity set.
    - It is represented by a **double rectangle**.
    - The identifying relationship is represented by a **double diamond**.
    - The primary key of a weak entity set is formed by the primary key of the strong entity set plus the weak entity set's **discriminator** (or partial key), which is underlined with a dashed line.
- **Specialization and Generalization:** These concepts are used to model superclass/subclass relationships.
    - **Specialization:** A top-down process of creating subclasses from a superclass based on distinguishing characteristics.
    - **Generalization:** A bottom-up process of creating a higher-level superclass from several entity sets that share common features.
    - **Constraints on Specialization/Generalization:**
        - **Disjoint vs. Overlapping:** `Disjoint` means a superclass entity can be a member of at most one subclass. `Overlapping` means it can be a member of more than one.
        - **Total vs. Partial:** `Total` means every superclass entity must belong to a subclass. `Partial` means it is optional.
- **Aggregation:** A mechanism to treat a relationship as a higher-level entity, allowing it to participate in other relationships. This is used when there is a need to express a relationship among relationships.

## 3. The Relational Model and Relational Algebra

### 3.1. Structure of Relational Databases

The relational model organizes data in two-dimensional tables called **relations**.

- **Relation (Table):** A set of tuples (rows).
- **Attribute (Column):** A named column of a relation. The number of attributes is the **degree** of the relation.
- **Tuple (Row/Record):** A single row in a relation. The number of tuples is the **cardinality** of the relation.
- **Domain:** A set of permissible values for one or more attributes.
- **Schema:** The logical structure of the database (e.g., `Student(RollNo, Name, Branch)`).
- **Instance:** The actual data in the database at a specific point in time.

### 3.2. Keys

Keys are crucial for uniquely identifying records and establishing relationships.

|   |   |
|---|---|
|Key Type|Description|
|**Super Key**|A set of one or more attributes that, taken collectively, uniquely identify a tuple within a relation.|
|**Candidate Key**|A minimal super key, i.e., a super key for which no proper subset is also a super key.|
|**Primary Key**|A candidate key chosen by the database designer to uniquely identify tuples. It cannot contain NULL values.|
|**Alternate Key**|A candidate key that is not chosen as the primary key.|
|**Foreign Key**|A set of attributes in one relation whose values are derived from the primary key of another relation, thus creating a link.|

### 3.3. Relational Algebra

Relational algebra is a procedural query language that forms the theoretical basis for relational databases and SQL.

|   |   |   |
|---|---|---|
|Operator|Symbol|Description & Example|
|**Selection**|σ|Selects tuples that satisfy a given predicate. `σ_Dept='CE' (Student)`|
|**Projection**|∏|Selects certain attributes (columns) from a relation and discards the others. Removes duplicate tuples. `∏_Name, Branch (Student)`|
|**Union**|U|Produces a relation containing all tuples that appear in either or both of two relations. Relations must be union-compatible. `∏_Name (Employee) U ∏_Name (Customer)`|
|**Set Difference**|−|Produces a relation containing tuples that are in the first relation but not in the second. `∏_Name (Employee) − ∏_Name (Customer)`|
|**Intersection**|∩|Produces a relation containing tuples that appear in both of two relations. `∏_Name (Employee) ∩ ∏_Name (Customer)`|
|**Cartesian Product**|X|Combines each tuple of the first relation with each tuple of the second relation. `Student X Result`|
|**Natural Join**|⋈|Combines tuples from two relations based on common attributes with the same name. It performs a Cartesian product, selects matching tuples, and eliminates duplicate columns. `Student ⋈ Result`|
|**Outer Join**||An extension of the join operation that avoids loss of information. It includes tuples that do not have matching values in the other relation, padding with NULLs. Types include **Left**, **Right**, and **Full** Outer Join.|
|**Division**|÷|Finds tuples in one relation that are associated with all tuples of another relation.|
|**Rename**|ρ|Renames a relation or its attributes.|
|**Aggregate**|G|Applies functions like `SUM`, `AVG`, `MAX`, `MIN`, `COUNT` to a set of tuples. `G_sum(CPI) (Student)`|

## 4. SQL - Structured Query Language

SQL is the standard language for managing and querying data in a relational database.

### 4.1. SQL Command Categories

|   |   |   |
|---|---|---|
|Category|Name|Purpose & Commands|
|**DDL**|Data Definition Language|To define and manage the database structure. **CREATE**, **ALTER**, **DROP**, **TRUNCATE**.|
|**DML**|Data Manipulation Language|To manage data within database objects. **INSERT**, **UPDATE**, **DELETE**.|
|**DQL**|Data Query Language|To retrieve data from the database. **SELECT**.|
|**DCL**|Data Control Language|To control access rights and permissions. **GRANT**, **REVOKE**.|
|**TCL**|Transaction Control Language|To manage transactions in the database. **COMMIT**, **ROLLBACK**, **SAVEPOINT**.|

### 4.2. Integrity Constraints in SQL

Constraints are rules enforced on data columns to ensure accuracy and reliability.

- **NOT NULL:** Ensures that a column cannot have a NULL value.
- **UNIQUE:** Ensures that all values in a column are different. Allows multiple NULLs.
- **PRIMARY KEY:** A combination of NOT NULL and UNIQUE. Uniquely identifies each row in a table. A table can have only one primary key.
- **FOREIGN KEY:** Also known as a referential integrity constraint. It is a key used to link two tables together, ensuring that a value in the child table's foreign key column exists in the parent table's primary key column.
- **CHECK:** Limits the value range that can be placed in a column by defining a business rule. `CHECK (SPI >= 0 AND SPI <= 10)`.

### 4.3. SQL Joins

Joins are used to combine rows from two or more tables based on a related column.

- **INNER JOIN:** Returns records that have matching values in both tables.
- **LEFT OUTER JOIN:** Returns all records from the left table, and the matched records from the right table. The result is NULL from the right side if there is no match.
- **RIGHT OUTER JOIN:** Returns all records from the right table, and the matched records from the left table. The result is NULL from the left side if there is no match.
- **FULL OUTER JOIN:** Returns all records when there is a match in either the left or the right table. It combines the results of both LEFT and RIGHT joins.
- **CROSS JOIN:** Returns the Cartesian product of the sets of records from the two joined tables.
- **SELF JOIN:** A table is joined with itself, often to query hierarchical data.

### 4.4. Views

A view is a virtual table based on the result-set of an SQL statement. It contains rows and columns, just like a real table, but does not store data physically.

- **Simple View:** Created on a single base table. DML operations are generally allowed.
- **Complex View:** Created on multiple tables. DML operations are generally restricted.
- **Materialized View:** Stores data physically and is updated periodically. It is used to improve performance for complex queries and aggregations.

## 5. Relational Database Design

### 5.1. Functional Dependencies (FDs)

A functional dependency `X → Y` holds if the values of attribute set X uniquely determine the values of attribute set Y.

- **Full FD:** An attribute Y is fully functionally dependent on X if it is dependent on X but not on any proper subset of X.
- **Partial FD:** A non-key attribute is dependent on a proper subset of a composite primary key.
- **Transitive FD:** A non-key attribute is dependent on another non-key attribute. `A → B` and `B → C` implies `A → C`.
- **Armstrong's Axioms:** A set of inference rules used to find all FDs logically implied by a given set of FDs. The primary rules are Reflexivity, Augmentation, and Transitivity.

### 5.2. Anomalies in Database Design

Poorly designed databases suffer from anomalies due to data redundancy.

- **Insertion Anomaly:** Inability to insert a record for one entity without data for another unrelated entity.
- **Deletion Anomaly:** Unintentional loss of data when a record is deleted.
- **Update/Modification Anomaly:** Inconsistency caused by updating only some of the redundant copies of a piece of data.

### 5.3. Normalization

Normalization is the process of organizing columns and tables in a relational database to minimize data redundancy and eliminate anomalies.

- **First Normal Form (1NF):** The table is in 1NF if all its attributes contain atomic (indivisible) values. There should be no repeating groups or multi-valued attributes.
- **Second Normal Form (2NF):** The table must be in 1NF and every non-key attribute must be fully functionally dependent on the entire primary key. This eliminates partial dependencies.
- **Third Normal Form (3NF):** The table must be in 2NF and every non-key attribute must be non-transitively dependent on the primary key. This eliminates transitive dependencies.
- **Boyce-Codd Normal Form (BCNF):** A stricter version of 3NF. A table is in BCNF if for every non-trivial functional dependency `X → Y`, X is a super key.
- **Higher Normal Forms (4NF, 5NF):** Address more complex dependencies like multi-valued dependencies (4NF) and join dependencies (5NF).

### 5.4. Decomposition

Decomposition is the process of breaking down a single relation into two or more smaller relations to achieve normalization.

- **Lossless Decomposition:** A decomposition is lossless if the natural join of the decomposed relations results in the original relation without creating any spurious tuples. This is a critical property.
- **Dependency Preserving Decomposition:** A decomposition is dependency-preserving if all the original functional dependencies can be enforced by checking constraints on the individual decomposed tables.

## 6. Query Processing and Optimization

**Query processing** is the sequence of activities involved in extracting data from a database. The steps include parsing, validation, optimization, and execution.

- **Query Optimization:** The process of selecting the most efficient query evaluation plan from among many alternatives. The cost of a query is typically measured by the number of disk I/O operations.
- **Evaluation Methods:**
    - **Materialization:** Each operation in a query plan is fully executed, and its result is stored in a temporary relation on disk, which is then used by the next operation.
    - **Pipelining:** The results of one operation are passed directly to the next operation in memory, without creating temporary disk files. This significantly reduces I/O costs.

## 7. Transaction Management

### 7.1. ACID Properties

A transaction is a logical unit of work that must exhibit four properties, known as ACID properties, to ensure database integrity.

1. **Atomicity:** A transaction is an "all or nothing" proposition. It either completes in its entirety or is rolled back as if it never occurred.
2. **Consistency:** A transaction must transform the database from one consistent state to another.
3. **Isolation:** Transactions execute independently of one another. The intermediate state of a transaction is not visible to other transactions until it has been committed.
4. **Durability:** Once a transaction is committed, its effects are permanent and will survive any subsequent system failures.

### 7.2. Concurrency Control

Concurrency control is the management of simultaneous operations on the database without them interfering with one another.

- **Concurrency Problems:**
    - **Lost Update:** The updates of one transaction are overwritten by another concurrent transaction.
    - **Dirty Read:** A transaction reads data that has been modified by another transaction that has not yet committed.
    - **Inconsistent Analysis:** A transaction reads several values, but a second transaction updates some of them during the execution of the first.
- **Lock-Based Protocols:** A lock is a mechanism to control access to a data item.
    - **Shared (S) Lock:** Allows reading but not writing. Multiple transactions can hold an S lock simultaneously.
    - **Exclusive (X) Lock:** Allows both reading and writing. Only one transaction can hold an X lock at a time.
    - **Two-Phase Locking (2PL):** A protocol that ensures serializability by dividing a transaction into a **growing phase** (locks can be acquired but not released) and a **shrinking phase** (locks can be released but not acquired).

### 7.3. Deadlock

A deadlock is a condition where two or more transactions are waiting for each other to release locks, resulting in a standstill.

- **Detection:** Can be detected using a **wait-for graph**, where a cycle indicates a deadlock.
- **Prevention:** Can be prevented using schemes like **wait-die** (an older transaction waits for a younger one) or **wound-wait** (an older transaction forces a younger one to roll back).

### 7.4. Recovery System

The recovery system ensures that the database can be restored to a consistent state after a failure.

- **Log-Based Recovery:** All modifications are recorded in a log file.
    - **Deferred Modification:** Updates are not written to the database until after a transaction commits. Requires `REDO`.
    - **Immediate Modification:** Updates are written to the database immediately. Requires both `UNDO` and `REDO`.
- **Checkpoints:** A mechanism to reduce the amount of log that needs to be scanned during recovery. At a checkpoint, all modified buffer blocks are written to disk.

## 8. Database Security

Database security refers to the protection of data from unauthorized users and malicious attacks.

- **Authentication vs. Authorization:**
    - **Authentication:** Verifying the identity of a user (verifying _who you are_).
    - **Authorization:** Granting a user permission to perform certain actions (verifying _what you are allowed to do_).
- **Access Control Models:**
    - **Discretionary Access Control (DAC):** The owner of an object can grant privileges to other users. Implemented in SQL via `GRANT` and `REVOKE` commands.
    - **Mandatory Access Control (MAC):** A system-wide policy where subjects (users) and objects (data) are assigned security levels. Access is granted based on comparing these levels.
    - **Role-Based Access Control (RBAC):** Access is granted based on a user's role within an organization.
- **Data Encryption:** The process of encoding data into a ciphertext that can only be read if decrypted.
    - **Symmetric Key:** The same key is used for encryption and decryption.
    - **Asymmetric Key:** Different public and private keys are used.
- **SQL Injection:** A common attack vector where malicious SQL code is inserted into input fields to manipulate the backend database.
- **Intrusion Detection System (IDS):** A system that monitors network or system activities for malicious actions or policy violations.

## 9. Advanced SQL and PL/SQL

### 9.1. Stored Procedures

A stored procedure is a group of pre-compiled PL/SQL or SQL statements stored in the database that performs a specific task.

- **Advantages:** Improved security (users can be granted permission to execute the procedure without having direct access to the tables), faster execution (pre-compiled), and code sharing/reusability.

### 9.2. Database Triggers

A trigger is a PL/SQL block that is automatically executed (fired) in response to a specific DML (INSERT, UPDATE, DELETE) or DDL (CREATE, ALTER, DROP) event on a table or view.

- **Types:**
    - **DML Triggers:** Fired by DML statements.
        - **AFTER Trigger:** Executes after the triggering statement.
        - **INSTEAD OF Trigger:** Executes instead of the triggering statement (used for views).
    - **DDL Triggers:** Fired by DDL statements.
    - **Logon Triggers:** Fired when a user session is established.

### 9.3. Cursors

A cursor is a pointer to a temporary work area created in system memory when an SQL statement is executed. It is used to traverse the set of rows returned by a query, processing them one at a time.

- **Implicit Cursors:** Automatically created by the database for every DML statement and single-row SELECT statement.
- **Explicit Cursors:** User-defined cursors for queries that return multiple rows. The process involves: **DECLARE**, **OPEN**, **FETCH**, **CLOSE**, and **DEALLOCATE**.