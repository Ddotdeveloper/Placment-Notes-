- Left Table is Parent Table 
- Right Table is Child Table Contains the Forign Key(Primary Key of Right Table )
- Fk is the primary key of the right table and fk for the left table 
- For applying join there must be relation or we can say a commen attribute must be there 

>[!note] 
> In joins kya hota haii hame 2 tables ko mix karke ek combined table chaiye rahti haii ek dum and unhe join karne ke bad hame sare tuples toh dono ke nhi chaiye hoge hum kuch specific hi chaiye hoge toh uske ke phir diff type ke join use hote haii smje

***
### Inner Join
- Return the resultant table that has the matching value from both the table 
- Basically the ==commen tuples on both sides on particular key== 
- The `INNER JOIN` keyword selects records that have matching values in both tables.
#### Problem Statement (Type of Query )
Write an SQL query to retrieve a ==list of all employees who belong to a department, along with their corresponding department names==. ==Only include employees who have a valid department assignment== (i.e., those whose department_id matches a department in the departments table). Exclude any employees without a department (e.g., those with NULL department_id).
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

### Left Join 
- In this Left table pura aata haii and also voh part bhi 
#### Problem Statement (Type of Query )
Q1. Write an SQL query to retrieve ==a list of all employees== and their corresponding department names. If an ==employee does not belong to any department (i.e., their department_id is NULL), show NULL for the department name.==)
- In this scenario, we will use a **LEFT JOIN** because we want to keep all the rows from the employees table, even if some employees don’t belong to a department
```sql
SELECT 
    employees.name, 
    departments.department_name
FROM 
    employees
LEFT JOIN 
    departments 
ON 
    employees.department_id = departments.department_id;
    -- isme hame employee ka sare chaiye tha and not ki department vala sara chaiye that's why it is used as the left join
```
### Right Joins 
- Is similar to left join just the dir is opposite 
### Minus Left
![[Pasted image 20241003212207.png]]

- So here we can implement this with the help of joins so first we do the left join and then Appy the `where` for the Table b ki `Fk` ko Null kardo 
- (fk) is here which is commen coloumn in both tables so it is used 
```sql
SELECT e.employee_id, e.name
FROM employees e
LEFT JOIN managers m ON e.employee_id = m.employee_id
WHERE m.employee_id IS NULL;
-- m is table b here e is table a 
```
#### Problem Statement Query 
- Give us those employees who don’t have any title. 
- Table a employee and Table b is title 
### Full Join
In this join the `union` of the left join and the right join table 
#### Problem statement 
- Write an SQL query to retrieve a list of all projects and the employees assigned to them. ==Ensure that projects with no assigned employees and employees without a project== (i.e., those with NULL project IDs) ==are also included in the result==.
