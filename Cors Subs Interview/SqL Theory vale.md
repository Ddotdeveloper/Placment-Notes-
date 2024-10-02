### Pattern Matching 
- no clue as to what that word should be.
- uses wildcards to match a string pattern, rather than writing the exact word
- LIKE operator
- % not fixed length after that  and _ exact spaces before this 
// Examples 
```sql
SELECT * FROM students WHERE first_name LIKE 'K%' // first letter is K 
SELECT * FROM students WHERE first_name NOT LIKE '%Q%' // contanin Q in string 
SELECT * FROM students WHERE first_name LIKE '__K%' // 3rd letter is K 
// Paricular length if you want to find 
SELECT * FROM students WHERE first_name LIKE '___%'// Length of string is greater or equal to 3 
```

### How to create empty tables with the same structure as another table?
-  in this schema is copied to the copy table but not the data 
	```sql
CREATE TABLE Students_copy AS SELECT * FROM Students WHERE 1 = 2;
```
- Give me some wrong condition after the where so that nothing is copied 

### Recursive Stored Procedure?
- stored procedure that calls itself until a boundary condition is reached, is called a recursive stored procedure
- deploy the same set of code several times
- Some SQL programming languages limit the recursion depth to prevent stack overflow 
- [[Sql Codes]] of the Recursive Code 

### Stored Procedure?
 - Subroutine available to applications that access a relational database management system (RDBMS)
 - The sole disadvantage of stored procedure is that it can be executed nowhere except in the database and occupies more memory in the database server.
  - It also provides a sense of security and functionality as users who can't access the data directly can be granted access via stored procedures.
   
  ```sql
    
DELIMITER $$ CREATE PROCEDURE FetchAllStudents() BEGIN SELECT * FROM myDB.students; END $$ DELIMITER

```
![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/001/024/original/Stored_Procedure.jpg?1631032812)
- Here you can see acess through the stored procedure 
