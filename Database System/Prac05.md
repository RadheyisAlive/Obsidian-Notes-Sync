To complete Practical 5 for your database systems course, here’s what needs to be done step-by-step:

### Task 1: Theory-Based Questions

1. **Question 1:**
    - **Relations:** `Actors(actor_name, address, age)` and `Performs(movie_name, star, date)`
    - **Query Requirement:** List actors who have been a main star and the movies they starred in.
    - **Appropriate Join:** Use an `INNER JOIN` on `Actors.actor_name` = `Performs.star`.
2. **Question 2:**
    - **Relations:** `Properties(address, lot, type)` and `Offers(customer, address, date, agent)`
    - **Query Requirement:** List address and type of properties along with offer dates. Include properties with no offers (show date as NULL).
    - **Appropriate Join:** Use a `LEFT OUTER JOIN` on `Properties.address` = `Offers.address`.
3. **Question 3:**
    - **Relations:** `Cruises(shipname, origin, destination, departure, duration, cost)` and `Ships(shipname, line, cabins, rating)`
    - **Query Requirement:** List cruises with origin, destination, cost, and ship rating.
    - **Appropriate Join:** Use an `INNER JOIN` on `Cruises.shipname` = `Ships.shipname`.

### Task 2: Creating and Populating Tables

1. **Database Setup:**
    - Create a new database named `company`:
        
        ```SQL
        sql
        Copy code
        CREATE DATABASE company;
        USE company;
        
        ```
        
2. **Run SQL Scripts:**
    - Use `rebuild.sql` to create and populate tables:
        
        ```SQL
        sql
        Copy code
        SOURCE /path/to/rebuild.sql;
        
        ```
        
3. **Verify Table Creation:**
    - Check if the tables `Emp`, `Dept`, `Proj`, and `Pworks` exist and have data:
        
        ```SQL
        sql
        Copy code
        SHOW TABLES;
        SELECT * FROM Emp;
        SELECT * FROM Dept;
        SELECT * FROM Proj;
        SELECT * FROM Pworks;
        
        ```
        

### Task 3: Writing SQL Queries

1. **Query 1:** Display the last name, job, and salary of employees responsible for projects with names containing 'Design'.
    
    ```SQL
    sql
    Copy code
    SELECT e.lastname, e.job, e.salary, p.projname
    FROM Emp e
    JOIN Proj p ON e.empno = p.respemp
    WHERE p.projname LIKE '%Design%';
    
    ```
    
2. **Query 2:** Display the first name, last name, job, managing department number, and department name for each department manager.
    
    ```SQL
    sql
    Copy code
    SELECT e.firstname, e.lastname, e.job, d.deptno AS ManagingDeptNo, d.deptname AS ManagingDeptName
    FROM Emp e
    JOIN Dept d ON e.empno = d.mgrno;
    
    ```
    
3. **Query 3:** Show department number, department name, manager’s first name, last name, and job for each department.
    
    ```SQL
    sql
    Copy code
    SELECT d.deptno, d.deptname, e.firstname, e.lastname, e.job
    FROM Dept d
    JOIN Emp e ON d.mgrno = e.empno;
    
    ```
    
4. **Query 4:** Display last name, job, and education level of employees with at least the education level of the ‘Pres’ job.
    
    ```SQL
    sql
    Copy code
    SELECT e.lastname, e.job, e.edlevel
    FROM Emp e
    WHERE e.edlevel >= (SELECT edlevel FROM Emp WHERE job = 'Pres');
    
    ```
    
5. **Query 5:** Show minimum salary, maximum salary, and the number of employees in each job category.
    
    ```SQL
    sql
    Copy code
    SELECT job, MIN(salary) AS MinSalary, MAX(salary) AS MaxSalary, COUNT(*) AS EmployeeCount
    FROM Emp
    GROUP BY job;
    
    ```
    
6. **Query 6:** Find average salary of employees for work departments with more than 5 employees.
    
    ```SQL
    sql
    Copy code
    SELECT workdept, AVG(salary) AS AvgSalary, COUNT(*) AS EmployeeCount
    FROM Emp
    GROUP BY workdept
    HAVING COUNT(*) > 5;
    
    ```
    
7. **Query 7:** Display empno, lastname, salary, and total weekly hours for employees working on projects.
    
    ```SQL
    sql
    Copy code
    SELECT e.empno, e.lastname, e.salary, SUM(pw.hours) AS TotalHrs
    FROM Emp e
    JOIN Pworks pw ON e.empno = pw.empno
    GROUP BY e.empno, e.lastname, e.salary;
    
    ```
    
8. **Query 8:** Show empno, lastname, salary, total weekly hours on projects, and project count for each employee.
    
    ```SQL
    sql
    Copy code
    SELECT e.empno, e.lastname, e.salary, SUM(pw.hours) AS TotalHrs, COUNT(pw.projno) AS ProjectCount
    FROM Emp e
    LEFT JOIN Pworks pw ON e.empno = pw.empno
    GROUP BY e.empno, e.lastname, e.salary;
    
    ```
    
9. **Query 9:** Sort the results of Query 8 by `TotalHrs` in descending order.
    
    ```SQL
    sql
    Copy code
    SELECT e.empno, e.lastname, e.salary, SUM(pw.hours) AS TotalHrs, COUNT(pw.projno) AS ProjectCount
    FROM Emp e
    LEFT JOIN Pworks pw ON e.empno = pw.empno
    GROUP BY e.empno, e.lastname, e.salary
    ORDER BY TotalHrs DESC;
    
    ```
    
10. **Query 10:** List project number and name with sub-projects.
    
    ```SQL
    sql
    Copy code
    SELECT p.projno, p.projname, sp.projno AS SubProjNo, sp.projname AS SubProjName
    FROM Proj p
    LEFT JOIN Proj sp ON p.projno = sp.majproj;
    
    ```
    
11. **Query 11:** List projects with sub-projects only.
    
    ```SQL
    sql
    Copy code
    SELECT p.projno, p.projname, sp.projno AS SubProjNo, sp.projname AS SubProjName
    FROM Proj p
    JOIN Proj sp ON p.projno = sp.majproj;
    
    ```
    

### Final Submission

1. **Create a folder** `**Prac05**` and place the following files:
    - `Prac05Task1.txt` (answers for Task 1)
    - `Prac05Commands.sql` (all Task 3 queries)
    - `Prac05Workings.out` (MySQL command results)
2. **Zip and submit:**
    - Zip the `Prac05` directory:
        
        ```Shell
        bash
        Copy code
        zip -r Prac05_<your student ID> Prac05
        
        ```
        
    - Upload the zip file to Blackboard under ‘Assessments/In Class Practical Submissions’.

  

use a suitable join query to show , for each student, the student ID, first name, last name , the total number of hours spend on community activities, and the number of activities they work on. Use appropriate column headings. Results should be shown in descending order of total hours spend by student on community work. If a student is not working on any activity, the total number of hours spend on activities should be shown as ‘NULL’

  
  
write a subquery to show the student number of the leader of the activities where the estimated cose of activity is lower than the average extimated cost of all activities.  

  

  

write a subquery to show the student number, first name of the student who are leading the activities that have less estimated cost than the average estimated cost of activities.