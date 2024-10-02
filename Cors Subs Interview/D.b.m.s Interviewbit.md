## What is DBMS and what is its utility? Explain RDBMS with examples.
##### What is dbms 
-  [**Database Management System**](https://www.interviewbit.com/blog/components-of-dbms/)**,** is a set of applications or programs that enable users to create and maintain a database
-  performing various operations such as inserting, deleting, updating
-  storage of data more compactly and securely as compared to a file-based system
- overcome problems like data inconsistency, data redundancy, etc
##### What is RDBMS
- store data more efficiently than DBMS. RDBMS stores data in the form of tables as compared to DBMS which stores data as files
- easier to locate specific values in the database
## What is Database 
- A Database is an organized, consistent, and logical collection of data that can easily be updated, accessed, and managed
- A tuple or a row represents a single entry in a table. An attribute or a column represents the basic units of data storage
## Mention the issues with traditional file-based systems that make DBMS a better choice?
- absence of indexing in a traditional file-based system (makes it slow and tedious to work with )
- The other issue is redundancy and inconsistency as files have many duplicate and redundant data (change one of them will not change in the whole database)
- Accessing data is harder(because data is unorganized )
- Another issue is the lack of concurrency control
- Integrity check, data isolation, atomicity, security, etc. are some other issues with traditional file-based systems
## Advantages of DBMS
To Read each point in depth : https://www.interviewbit.com/dbms-interview-questions/?sign_up_medium=ib_article_auth_blocker/#dbms-advantages

[[Advatages of Dbms]]
- **Data Sharing**
- **Integrity constraints:**
- **Controlling redundancy in a database**
- **Provides backup and recovery facility**
- **Data Independence:**
- **Data Security:**

## Explain different languages present in DBMS.

Following are various languages present in DBMS:

- **DDL(Data Definition Language):**  It contains commands which are required to define the database.  
    E.g., CREATE, ALTER, DROP, TRUNCATE, RENAME, etc.
- **DML(Data Manipulation Language):** It contains commands which are required to manipulate the data present in the database.  
    E.g., SELECT, UPDATE, INSERT, DELETE, etc.
- **DCL(Data Control Language):**  It contains commands which are required to deal with the user permissions and controls of the database system.  
    E.g., GRANT and REVOKE.
- **TCL(Transaction Control Language):**  It contains commands which are required to deal with the transaction of the database.  
    E.g., COMMIT, ROLLBACK, and SAVEPOINT.

## What is meant by ACID properties in DBMS?
ACID stands for Atomicity, Consistency, Isolation, and Durability
###### Atomicity 
* This property reflects the concept of either executing the whole query or executing nothing at all
* Paytm ka system hota ha jaise jab tak dono taraf sai verify hota 

**Consistency:** This property ensures that the data remains consistent before and after a transaction in a database.
**Isolation:** This property ensures that each transaction is occurring independently of the others. This implies that the state of an ongoing transaction doesn’t affect the state of another ongoing transaction.
**Durability:** This property ensures that the data is not lost in cases of a system failure or restart and is present in the same state as it was before the system failure or restart.

## Are NULL values in a database the same as that of blank space or zero?
- No, a NULL value is very different from that of zero and blank space as it represents a value that is assigned
- Example: NULL value in “number_of_courses” taken by a student represents that its value is unknown whereas 0 in it means that the student hasn’t taken any courses.

## What is meant by normalization and denormalization?
**Normalization**
-  process of reducing redundancy by organizing the data into multiple tables
- easier to maintain the integrity of the database.
**Denormalization**
- reverse process of normalization as it combines the tables which have been normalized into a single table
- JOIN operation allows us to create a denormalized form of the data by reversing the normalisation

## What is a lock. Explain the major difference between a shared lock and an exclusive lock during a transaction in a database.
**Kinda Like Lock Variable in semaphor**es
- protect a shared piece of data from getting updated by two or more database users
- single database user or session has acquired a lock then no other database user or session can modify that data until the lock is released.
- **Shared Lock:**
  - many transactions may hold a lock on the same data item in a shared lock.
  - a lock on any transaction that is about to perform a write operation
- **Exclusive lock:**
 - a lock on any transaction that is about to perform a write operation
 - doesn’t allow more than one transaction and hence prevents any inconsistency
## Explain the difference between the DELETE and TRUNCATE command in a DBMS.

**DELETE command:** this command is needed to delete rows from a table based on the condition provided by the WHERE clause.
   - It can be rolled back if required.
   - maintains a log to lock the row of the table before deleting it so it is slow 

**TRUNCATE command:** this command is needed to remove complete data from a table in a database. It is like a DELETE command which has no WHERE clause.
   - It can't be rolled back even if required.
   - does not maintain a log hence fast

## Explain the difference between intension and extension in a database.
**Intension:** (Schema)
  - known as database schema is used to define the description of the database
  - specified during the design of the database and mostly remains unchanged.
**Extension:** (Entries)
- Extension on the other hand is the measure of the number of tuples present in the database at any given point in time.
- extension of a database is also referred to as the snapshot of the database

## Explain different types of relationships amongst tables in a DBMS.
- **One to One Relationship:**  This type of relationship is applied when a particular row in table X is linked to a singular row in table Y.
  -> ex : Person and passport
- **One to Many Relationship:** This type of relationship is applied when a single row in table X is related to many rows in table Y.
   -> ex : Customer and Account
- **Many to Many Relationship:** This type of relationship is applied when multiple rows in table X can be linked to multiple rows in table Y.
  -> ex: customer and product 
- **Self Referencing Relationship:** This type of relationship is applied when a particular row in table X is associated with the same table.
  -> ex:  iska smja ni kya bakchodi haii 


## Explain different levels of data abstraction in a DBMS

- **Physical Level:**  
  - it is the lowest level and is managed by DBMS. 
  - This level consists of data storage descriptions 
  - hidden from system admins, developers, and users.
- **Conceptual or Logical level:**  it is the level on which developers and system admins work and it determines what data is stored in the database and what is the relationship between the data points.
- **External or View level:** it is the level that describes only part of the database and hides the details of the table schema and its physical storage from the users. The result of a query is an example of View level data abstraction.  A view is a virtual table created by selecting fields from one or more tables present in the database.