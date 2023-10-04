# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands
# AIM:
To create a manager database and execute DML queries using SQL.

# DML(Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
# List of DML commands:
INSERT: It is used to insert data into a table.
UPDATE: It is used to update existing data within a table.
DELETE: It is used to delete records from a database table.
# Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
# insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
# Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
# QUERY:
```
UPDATE manager SET salary = salary * 1.10;
```
# OUTPUT:
![D1](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/eed9aa48-406b-413c-b4a6-6e4eb8662080)


# Q2) Delete the records from manager table where the salary less than 2750.
# QUERY:
```
DELETE FROM manager WHERE salary < 2750;
```
# OUTPUT:
![D2](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/4cdeb147-110c-45f0-86cd-38b9c66a9008)


# Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in MANAGER table is the monthly salary)
# QUERY:
```
SELECT ename AS "Name", (salary * 12) + NVL(commission, 0) AS "Annual Salary" FROM manager;
```
# OUTPUT:
![D3](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/b3997352-a906-46de-8865-dca069ac0c09)


# Q4) List the names of Clerks from MANAGER table.
# QUERY:
```
SELECT ename FROM manager WHERE designation = 'clerk';
```
# OUTPUT:
![D4](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/c1fa5fd9-0c83-436d-b14c-db064d9417db)


# Q5) List the names of employee who are not Managers.
# QUERY:
```
SELECT ename FROM manager WHERE designation != 'manager';
```
# OUTPUT:
![D5](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/45f6cd8e-0d14-4dda-8cec-8158697f9a20)



# Q6) List the names of employees not eligible for commission.
# QUERY:
```
SELECT ename FROM manager WHERE commission = 0;
```
# OUTPUT:
![D6](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/f67bcebd-a10d-4a8e-8cb4-91ee8a429c74)



# Q7) List employees whose name either start or end with ‘s’.
# QUERY:
```
SELECT ename FROM manager WHERE ename LIKE 'S%' OR ename LIKE '%S';
```
# OUTPUT:
![D7](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/6e1b43de-1923-4401-b6fc-646d6f06f53d)



# Q8) Sort MANAGER table in ascending order by hire-date and list ename, job, deptno and hire-date.
# QUERY:
```
SELECT ename, designation, deptno, Hiredate FROM manager ORDER BY hiredate ASC;
```
# OUTPUT:
![D8](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/0bdb8c52-b566-4d58-a43c-05fd7044bf57)



# Q9) List the Details of Employees who have joined before 30 Sept 81.
# QUERY:
```
SELECT * FROM manager WHERE Hiredate < TO_DATE('30-SEP-81', 'DD-MON-YY');
```
# OUTPUT:
![D9](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/237a1a7f-867a-43d5-b07d-06c45499e58f)



# Q10) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
# QUERY:
```
SELECT ename, deptno, salary FROM manager ORDER BY deptno ASC, salary DESC;
```
# OUTPUT:
![D10](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/2e7ab403-f84f-41ee-9a12-9cf804b60967)


# Q11) List the names of employees not belonging to dept no 30,40 & 10
# QUERY:
```
SELECT ename FROM manager WHERE deptno NOT IN (10, 30, 40);
```
# OUTPUT:
![D11](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/716a965a-a13a-4788-ae26-247a853067a1)



# Q12) Find number of rows in the table MANAGER.
# QUERY:
```
SELECT COUNT(*) AS "Number of Rows" FROM manager;
```
# OUTPUT:
![D12](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/17a78488-ccf8-4032-9149-a486c9909ce1)



# Q13) Find maximum, minimum and average salary in MANAGER table.
# QUERY:
```
SELECT MAX(salary) AS "Maximum Salary", MIN(salary) AS "Minimum Salary", AVG(salary) AS "Average Salary" FROM manager;
```
# OUTPUT:
![D13](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/6ea7e18f-0df6-4fcf-a1f4-dcc40ad59db5)


# Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
# QUERY:
```
SELECT designation, COUNT(*) AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT(*) DESC;
```
# OUTPUT:
![D14](https://github.com/HariviswanathB/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119103855/67126962-7842-46ac-9f75-9055fa584892)

