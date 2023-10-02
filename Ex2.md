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
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
update manager set salary=salary+(salary*0.10);

### OUTPUT:

![1](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/c70cc3e9-214c-4d0d-9157-f814d8afb9b4)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
delete from manager where salary<2750;

### OUTPUT:
![2](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/3c6766bb-f67f-4ed6-bfe9-1f7a359dd86f)



### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
select ename as "Name",salary*12 as "Annual salary" from manager;

### OUTPUT:
![3](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/69fe0d04-9f63-49bf-a378-d03b12c247e0)


### Q4)	List the names of Clerks from emp table.


### QUERY:
select ename from manager where designation='clerk';

### OUTPUT:
![4](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/f724c631-946f-4aed-95a4-a9564b18e4c8)


### Q5)	List the names of employee who are not Managers.


### QUERY:

select ename from manager where designation <> 'manager';
### OUTPUT:

![5](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/975786e1-ebfc-4839-a4ea-68f9f81e21bb)

### Q6)	List the names of employees not eligible for commission.


### QUERY:
select ename from manager where commission=0;

### OUTPUT:
![6](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/14c9c27a-6311-44ae-a24f-c2a08535c475)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
select ename from manager where ename like '%s' or ename like 's%';

### OUTPUT:
![7](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/5980ccdf-6f7a-4bcb-94dc-5d5665d316ca)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;

### OUTPUT:
![8](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/fa153693-af5a-49e3-b31b-d26d25956ecf)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');

### OUTPUT:
![9](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/5e079889-651b-4f46-bc97-a22f027d85d7)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;

### OUTPUT:
![10](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/bc9048f7-f6a9-4afb-bdad-1df33bd323aa)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
select ename from manager where deptno not in (30,40,10);

### OUTPUT:
![11](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/68c17a65-63fd-4bc6-b749-5e62932c0d20)


### Q12) Find number of rows in the table EMP

### QUERY:

select count(*) from manager;
### OUTPUT:
![12](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/16603de8-eb6a-479b-9587-79793fcfffbb)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
### MAXIMUM :
select max(salary) from manager;

### OUTPUT:
![13](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/82e47a5f-a0bd-4846-88ba-95721f776725)
### MINIMUM :
select min(salary) from manager;
### OUTPUT:

![14](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/f0a5520c-bfa3-4174-af5a-27afbfd58924)
### AVERAGE :
select avg(salary) from manager;
## OUTPUT:
![15](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/7bf9ad52-bff6-4cbb-b764-172ce74f89c1)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

### OUTPUT:
![16](https://github.com/AdhithiyanK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121029258/3280b4f2-1d4f-41ac-aac4-b633b21240c0)

