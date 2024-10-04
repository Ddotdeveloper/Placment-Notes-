### Alising (AS)
First Name is changed to the Worker Name in the Table 
```SQL
 SELECT FIRST_NAME AS Worker_Name from WORKER;
```
### UPPER and Substring 
In This first we get the data in by the select keyword and then give some change to it
- It is part of post processing 
```sql
SELECT UPPER(FIRST_NAME) FROM WORKER;
select substring(first_name,1,3) from worker;
```
### DISTINCT  AND GROUP BY (WITHOUT THE AGG FUN)
What distinct do is it makes the parituclar coloum and give the distinct values of that coloum and also if we appy Group by without agg fun it gives the same result 
```sql
SELECT distinct DEPARTMENT FROM WORKER;
-- by the group by
SELECT DEPARTMENT  FROM WORKER GROUP BY DEPARTMENT;
```

### INSTR
The INSTR() function is used to find the position of a substring within a string.
```SQL
SELECT INSTR('Hello World', 'World') AS Position;
SELECT INSTR(FIRST_NAME,'b') as pos_of_b_in_amitabh  FROM WORKER WHERE first_name = 'Amitabh';

```

### LTRIM AND RTRIM 
- Remove white spaces 
```sql
SELECT LTRIM('   Hello World') AS TrimmedString;
SELECT LTRIM('Hello World   ') AS TrimmedString;
SELECT LTRIM(first_name) AS TrimmedString;
SELECT LTRIM(first_name) AS TrimmedString;
```
### LENGTH 
- do not give the count give the length of characters 
```sql
Select distinct department,LENGTH(DEPARTMENT) AS LENOF FROM WORKER;
```
### Replace  And Concat 
- it is used to replace a substring to another substring
- used to replace all occurrences of a specified substring within a string with another substring // imp 
```sql
SELECT REPLACE('Hello World', 'World', 'Universe') AS NewString;
SELECT REPLACE(FIRST_NAME,'a','A') from worker;
SELECT CONCAT(FIRST_NAME,' ',LAST_NAME) AS COMP_NAME FROM WORKER;
```
### ORDER BY 
- By Default by the ascending order 
- for desc we have to mention 
Genric syntax
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC], ...;
-- example 
SELECT FIRST_NAME FROM WORKER ORDER BY FIRST_NAME ASC ; 
select * from worker order by first_name, department DESC;
```
#### in case of conflict 
1. The rows are **first** sorted by the first_name in ascending order.
2. If two or more rows have the **same** first_name, then these rows will be further sorted by the department in **descending order**.

### In operator 

• The IN operator checks if a value exists in a given list of values.
• The list can be a set of literal values, a subquery, or a combination of both.
• NOT IN can be used to exclude rows with certain values.
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column IN (value1, value2, ...);
-- ex 1
SELECT * 
FROM employees
WHERE department IN ('HR', 'IT', 'Finance');
-- ex 2
select * from worker where first_name IN ('Vipul', 'Satish');
```

### String Matching in SQL
#### % 
The wildcard character % is used with the LIKE operator to represent zero, one, or multiple characters.
```sql
select * from worker where department LIKE 'Admin%';
select * from worker where first_name LIKE '%a%';
select * from worker where first_name LIKE '_____h';
```
### WHERE 
- WHERE clause in SQL is used to ==filter records based on specified conditions==. 
- • Conditions in the WHERE clause ==can involve comparisons== (using operators like =, >, <, >=, <=, <>), logical operators (AND, OR, NOT), and pattern matching (LIKE).
• The ==IN operator== can also be used within a WHERE clause to specify multiple values.

### Between 
- check between the tow values for numeric 
- Can be used in various cases 
   - salary Price range 
   - date values and time values 
   - string values 
```sql 
SELECT * 
FROM employees
WHERE salary BETWEEN 50000 AND 80000;
SELECT * 
FROM employees
WHERE first_name BETWEEN 'A' AND 'M';
SELECT * 
FROM orders
WHERE order_date BETWEEN '2023-01-01' AND '2023-06-30';
```

### Extract The Year and Month 
- Here we extract year and month from the joining date 
```sql
Select * from worker where year(joining_date) = 2014 and month(joining_date) = 02;

```
***
### Agg functions 
- Are commanly used with group by 
- List of imp functions 
   1. **COUNT()**: Returns the number of rows that meet a specified condition.
   2. **SUM()**: Calculates the total sum of a numeric column.
   3. **AVG()**: Computes the average value of a numeric column.
   4. **MIN()**: Finds the smallest value in a set.
  5. **MAX()**: Determines the largest value in a set.
  6. **GROUP_CONCAT()**: Concatenates non-NULL values from a group (specific to MySQL).
```sql
SELECT 
    department,
    COUNT(*) AS total_employees,
    SUM(salary) AS total_salary,
    AVG(salary) AS average_salary,
    MIN(salary) AS lowest_salary,
    MAX(salary) AS highest_salary,
    GROUP_CONCAT(first_name) AS employees
FROM 
    employees
GROUP BY 
    department
HAVING 
    COUNT(*) > 10;
```
![[Pasted image 20241002174008.png]] imp result of above code 
- imse yeh hora ki har ek deparment mai agg function lag raha 
- according to code it going to  the each department and for each deparment we are applying the agg function find values like avg count and min and max and getting the names 
***
### Joins 
#### Inner join 
- Give the commen between the table 1 and table 2 
Syntax :
~~~sql
SELECT 
    employees.name, 
    departments.department_name
FROM 
    employees
INNER JOIN 
    departments 
ON 
    employees.department_id = departments.department_id;
~~~
[[Joins in Sql]] For the details 
*** 
### Diff Between Where and Having 
##### WHERE Clause**
• **Purpose**: Used to filter rows ==**before** any grouping or aggregation== takes place.
• **Works on**: Individual rows of a table.
• **Used with**: ==Any non-aggregated column== (e.g., columns containing data such as salary, age, etc.).
• **Cannot** be used with aggregate functions like SUM(), COUNT(), AVG(), etc.
**Example**:
```sql
SELECT first_name, department, salary
FROM worker
WHERE salary > 50000; 
-- 
```
##### Having 
• **Purpose**: Used to filter the results **after** aggregation has occurred (i.e., after GROUP BY).
• **Works on**: The results of aggregate functions like SUM(), COUNT(), etc., or on the grouped data.
• **Used with**: Aggregate functions or columns in the GROUP BY clause.
```sql
SELECT department, SUM(salary)
FROM worker
GROUP BY department
HAVING SUM(salary) > 500000;  -- Filters based on aggregated total salary for each department
```

### Mod (Modulous)
- to find the reminder 
```sql
-- for the even rows 
select * from worker where mod(worker_id,2) = 0;
select * from worker where mod(worker_id,2) <> 0;
-- for the odd rows 
-- or 
select * from worker where mod(worker_id,2) != 0;
```

### To clone some table 
```sql
CREATE TABLE worker_clone LIKE worker; -- copy the schema 
-- insert the worker entreis in worker clone
INSERT INTO worker_clone select * from worker;
select * from worker_clone;
```
