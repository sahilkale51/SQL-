```# SQL - Important EMP Table Queries
# SQL - Create Database EMPLOYEEB3_RAW
CREATE DATABASE EMPLOYEEB3_RAW

-- Create a New DEPT table.
CREATE TABLE DEPT(DEPTNO INT(3) PRIMARY KEY , DNAME VARCHAR(20) NOT NULL, LOC VARCHAR(20) NOT NULL;

-- Create a New SALGRADE table.
CREATE TABLE SALGRADE( LOSAL INT(9) ,HISAL(9),GRADE INT(2));

-- Create a New EMP table.
CREATE TABLE EMP(EMPNO INT (3) PRIMARY KEY, ENAME VARCHAR(20) NOT NULL, JOB VARCHAR(20) NOT NULL, MGR INT(3),HIREDATE DATE NOT NULL, COMM INT(3) ,DEPTNO INT(3) NOT NULL,);


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


# SQL - EMP Table Inserts

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7499','WARD','SALESMAN','7566','1981-02-20',2100,105,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7521','ALLEN','SALESMAN','7698','1981-02-22',1750,88,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7566','JONES','MANAGER','7788','1981-02-02',2975,149,20);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7654','MARTIN','SALESMAN','7698','1981-09-28',1795,88,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7698','BLAKE','MANAGER','7788','1981-01-05',2850,143,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7728','CLARK','MANAGER','7788','1981-06-09',2950,148,10);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7788','KING','PRESIDENT',NULL,'1981-11-17',5200,260,10);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7839','SCOTT','ANALYST','7788','1987-04-19',3000,150,20);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7844','TURNER','SALESMAN','7698','1981-08-09',2000,100,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7876','JAMES','CLERK','7698','1987-03-12',1450,73,30);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7900','ADAMS','CLERK','7566','1987-05-23',1600,80,20);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7902','FORD','ANALYST','7788','1983-12-03',3000,150,20);

-- Insert a new row into the EMP table.
INSERT INTO EMP VALUES('7934','MILLER','CLERK','7782','1982-01-23',1300,40,10);

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


-- Select all columns and rows from the EMP table.
SELECT * FROM EMP;

-- Select distinct job titles from the EMP table.
SELECT DISTINCT JOB FROM EMP;

-- Select all columns and rows for employees with the job 'MANAGER'.
SELECT * FROM EMP WHERE JOB = 'MANAGER';

-- Select all columns and rows for employees hired before January 1, 1981.
SELECT * FROM EMP WHERE HIREDATE < TO_DATE('1981-01-01', 'YYYY-MM-DD');

-- Select employee number, name, and salary from the EMP table.
SELECT EMPNO, ENAME, SAL FROM EMP;

-- Select employee number, name, job, and hire date for employees with the job 'ANALYST'.
SELECT EMPNO, ENAME, JOB, HIREDATE FROM EMP WHERE JOB = 'ANALYST';

-- Select all columns and rows for employees whose commission is greater than their salary.
SELECT * FROM EMP WHERE COMM > SAL;

-- Select employee number, name, job, and hire date for employees hired after June 30, 1981.
SELECT EMPNO, ENAME, JOB, HIREDATE FROM EMP WHERE HIREDATE > TO_DATE('1981-06-30', 'YYYY-MM-DD');

-- Select all columns and rows for employees with the jobs 'CLERK' or 'ANALYST'.
SELECT * FROM EMP WHERE JOB IN ('CLERK', 'ANALYST');

-- Select all columns and rows for employees in departments 10 or 20.
SELECT * FROM EMP WHERE DEPTNO IN (10, 20);

-- Select employee number, name, and salary for employees in department 10.
SELECT EMPNO, ENAME, SAL FROM EMP WHERE DEPTNO = 10;

-- Select all columns and rows for employees hired on May 1, 1981, or December 3, 1981.
SELECT * FROM EMP WHERE HIREDATE IN (TO_DATE('1981-05-01', 'YYYY-MM-DD'), TO_DATE('1981-12-03', 'YYYY-MM-DD'));

-- Select all columns and rows for employees who are clerks in department 30.
SELECT * FROM EMP WHERE JOB = 'CLERK' AND DEPTNO = 30;

-- Select all columns and rows for employees in departments 10 or 30 and hired in 1981.
SELECT * FROM EMP WHERE DEPTNO IN (10, 30) AND EXTRACT(YEAR FROM HIREDATE) = 1981;

-- Select all columns and rows for employees who are not salesmen and were not hired in 1981.
SELECT * FROM EMP WHERE JOB != 'SALESMAN' AND EXTRACT(YEAR FROM HIREDATE) != 1981;

-- Select distinct department numbers for employees hired after December 31, 1983.
SELECT DISTINCT DEPTNO FROM EMP WHERE HIREDATE > TO_DATE('1983-12-31', 'YYYY-MM-DD');

-- Select distinct job titles from the EMP table.
SELECT DISTINCT JOB FROM EMP;

-- Select all columns and rows for employees who are not presidents or managers.
SELECT * FROM EMP WHERE JOB NOT IN ('PRESIDENT', 'MGR');

-- Select all columns and rows for employees with salaries between 1000 and 2500.
SELECT * FROM EMP WHERE SAL BETWEEN 1000 AND 2500;

-- Select all columns and rows for clerks with salaries between 1000 and 2500.
SELECT * FROM EMP WHERE JOB = 'CLERK' AND SAL BETWEEN 1000 AND 2500;

-- Select all columns and rows for employees hired in 1981 with salaries greater than 2500.
SELECT * FROM EMP WHERE EXTRACT(YEAR FROM HIREDATE) = 1981 AND SAL > 2500;

-- Select all columns and rows from the EMP table, ordered by hire date in descending order.
SELECT * FROM EMP ORDER BY HIREDATE DESC;

-- Select all columns and rows from the EMP table, ordered by job title.
SELECT * FROM EMP ORDER BY JOB;

-- Select all columns and rows from the EMP table, ordered by employee name and then by job title.
SELECT * FROM EMP ORDER BY ENAME, JOB;

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

