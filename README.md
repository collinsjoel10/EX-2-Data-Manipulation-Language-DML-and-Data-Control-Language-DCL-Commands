# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
![1](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/06234599-9be0-4e72-bdbe-b1169beb3c5f)

## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
![2](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/8eb63d65-57aa-47e9-b8d7-c58e31622704)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```update manager set salary=salary+(salary*0.10);```
### OUTPUT:   
![3](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/f4f41ee4-14b9-40b4-aadc-69b42685a243)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```delete from manager where salary < 2750;```

### OUTPUT:   
![4](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/1777297d-b2ed-40a0-b454-6dd62e245148)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
``` select ename as "Name", salary * 12 as "Annual Salary" from manager;```

### OUTPUT:
![5](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/3eab237a-7805-4d63-9db5-e20b44698236)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```select ename from manager where designation = 'clerk';```

### OUTPUT:
![6](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/2d2aba03-5d0e-472d-986a-33ba8ddd3b81)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```select ename from manager where designation <> 'manager';```

### OUTPUT:
![7](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/be3f7586-7291-4e10-946b-271576fc45dd)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```select ename from manager where commission is null or commission = 0;```

### OUTPUT:
![8](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/fa2f987e-8fcc-4279-a46f-fd1c10d5208a)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
``` select ename from manager where ename like 'S%' or ename like '%S';```

### OUTPUT:
![9](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/194e79f5-9ef2-4f87-9653-acecdba3d154)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```select ename, designation, deptno, hiredate from manager order by hiredate asc;```

### OUTPUT:
![10](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/aaf3c688-f70a-4e70-aef0-0495b462cd8e)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```select * from manager where hiredate < date'1981-09-30';```

### OUTPUT:
![11](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/b30277f1-105f-402b-8d2b-44f37d05cce0)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```select ename, deptno, salary from manager order by deptno asc, salary desc;```

### OUTPUT:
![12](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/9b4f7365-5839-47ed-88cb-74e02098ce48)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
``` select ename from manager where deptno not in (30, 40, 10);```

### OUTPUT:
![13](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/fdb56029-5db2-4d78-b6e5-4d46618a29e6)

### Q13) Find number of rows in the table EMP

### QUERY:
```select count(*) as total_rows from manager;```

### OUTPUT:
![14](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/d6c5d526-640c-40ea-9988-9af187f6b689)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```select max(salary) as max_salary, min(salary) as min_salary, avg(salary) as avg_salary from manager;```

### OUTPUT:
![15](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/7547aa73-85c6-4853-9ded-2358e4aec21a)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```select designation, count(*) as number_of_employees from manager group by designation order by number_of_employees
desc;
```
### OUTPUT:
![16](https://github.com/ASHWINKUMAR2903/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119407186/47799369-49c5-444b-b68e-2fe54416e97d)
## RESULT:
The Data Manipulation Language (DML) and Data Control Language (DCL) Commands have been executed successfully.
