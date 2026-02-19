# EXPERIMENT:-03
QUERIES

01 . Names with Exactly 5 Characters (A___N)
```sql
SELECT ENAME, JOB, DEPTNO,ENAME
FROM EMPLOYEE
WHERE ENAME LIKE 'A___N';
--------------------------------------
+----------+--------+-------+
| JOB      | DEPTNO | ENAME |
+----------+--------+-------+
| SALESMAN |     30 | ALLEN |
+----------+--------+-------+
```
02 . Salary of employee in descending order of dept 30
```sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE
WHERE DEPTNO = 30
ORDER BY SAL DESC;
----------------------------------------
+--------+----------+------+
| ENAME  | JOB      | SAL  |
+--------+----------+------+
| BLAKE  | MANAGER  | 2850 |
| ALLEN  | SALESMAN | 1600 |
| TURNER | SALESMAN | 1500 |
| WARD   | SALESMAN | 1250 |
| MARTIN | SALESMAN | 1250 |
| JAMES  | CLERK    |  950 |
+--------+----------+------+
```
03 . List of employee name start with S
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE 'S%';
-------------------------------
+-------+
| ENAME |
+-------+
| SMITH |
| SCOTT |
+-------+
```
04 . Name ends with S
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '%S';
---------------------------------------
+-------+
| ENAME |
+-------+
| JONES |
| ADAMS |
| JAMES |
+-------+
```
05 . Display the names of employees working in department number 10, 20, or 40 OR employees working as CLERK, SALESMAN, or ANALYST
```sql 
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO IN (10, 20, 40)
   OR JOB IN ('CLERK', 'SALESMAN', 'ANALYST');
   ------------------------------------
   +--------+
| ENAME  |
+--------+
| SMITH  |
| ALLEN  |
| WARD   |
| JONES  |
| MARTIN |
| CLARK  |
| SCOTT  |
| KING   |
| TURNER |
| ADAMS  |
| JAMES  |
| FORD   |
| MILLER |
+--------+
```
06 . Display employee number and names for employees who earn commission
```sql
SELECT EMPNO, ENAME
FROM EMPLOYEE
WHERE COMM IS NOT NULL
AND COMM > 0;
-----------------------------
+-------+--------+
| EMPNO | ENAME  |
+-------+--------+
|  7499 | ALLEN  |
|  7521 | WARD   |
|  7654 | MARTIN |
+-------+--------+
```
07 . Display employee number and total salary for each employee
```sql
SELECT EMPNO, (SAL + IFNULL(COMM, 0)) AS TOTAL_SALARY
FROM EMPLOYEE;
-------------------------------------
+-------+--------------+
| EMPNO | TOTAL_SALARY |
+-------+--------------+
|  7369 |          800 |
|  7499 |         1900 |
|  7521 |         1550 |
|  7566 |         2975 |
|  7654 |         2650 |
|  7698 |         2850 |
|  7782 |         2450 |
|  7788 |         3000 |
|  7839 |         5000 |
|  7844 |         1500 |
|  7876 |         1100 |
|  7900 |          950 |
|  7902 |         3000 |
|  7934 |         1300 |
+-------+--------------+
```
08 . Display employee number and annual salary for each employee
```sql
SELECT EMPNO, (SAL * 12) AS ANNUAL_SALARY
FROM EMPLOYEE;
-------------------------------------
+-------+---------------+
| EMPNO | ANNUAL_SALARY |
+-------+---------------+
|  7369 |          9600 |
|  7499 |         19200 |
|  7521 |         15000 |
|  7566 |         35700 |
|  7654 |         15000 |
|  7698 |         34200 |
|  7782 |         29400 |
|  7788 |         36000 |
|  7839 |         60000 |
|  7844 |         18000 |
|  7876 |         13200 |
|  7900 |         11400 |
|  7902 |         36000 |
|  7934 |         15600 |
+-------+---------------+
```
09 . Display the names of all employees working as CLERK and drawing a salary more than 3000
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB = 'CLERK'
AND SAL > 3000;
----------------------------------------
Empty set
```
10 . Display the names of employees who are working as
CLERK, SALESMAN, or ANALYST and drawing a salary more than 3000
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB IN ('CLERK', 'SALESMAN', 'ANALYST')
AND SAL > 3000;
-----------------------------------
Empty set
```