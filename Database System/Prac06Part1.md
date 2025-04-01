### Task 1: Sub-queries to Retrieve Data

1. **Use a select statement with a subquery to display the names of all departments that are responsible for at least one project that has already started.**
    
    ```SQL
    sql
    Copy code
    SELECT deptname
    FROM Dept
    WHERE deptid IN (
        SELECT deptid
        FROM Proj
        WHERE startdate IS NOT NULL
    );
    
    ```
    
2. **Find the name, start date, and duration in months of projects that have the earliest end date.**
    
    ```SQL
    SELECT pname, startdate, TIMESTAMPDIFF(MONTH, startdate, enddate) AS duration
    FROM Proj
    WHERE enddate = (SELECT MIN(enddate) FROM Proj);
    
    ```
    
3. **Produce a list of all female employees whose education level is higher than the average education level of all employees in their departments. Display employee number, first name, last name, and gender.**
    
    ```SQL
    SELECT empno, firstname, lastname, gender
    FROM Emp
    WHERE gender = 'F'
    AND edlevel > (SELECT AVG(edlevel) FROM Emp e WHERE e.deptid = Emp.deptid);
    ```
    
4. **Find the lastname, job, and salary of employees who do not work on any project.**
    
    ```SQL
    SELECT lastname, job, salary
    FROM Emp
    WHERE empno NOT IN (SELECT empno FROM Pworks);
    
    ```
    
5. **List all employees who have a higher education level than all designers. Display the first name, last name, and edlevel of the employee. Assume that designers are indicated by job = ‘Designer’.**
    
    ```SQL
    sql
    Copy code
    SELECT firstname, lastname, edlevel
    FROM Emp
    WHERE edlevel > ALL (
        SELECT edlevel
        FROM Emp
        WHERE job = 'Designer'
    );
    
    ```
    
6. **Get the names of departments that are currently responsible for only one project each.**
    
    ```SQL
    sql
    Copy code
    SELECT deptname
    FROM Dept
    WHERE deptid IN (
        SELECT deptid
        FROM Proj
        GROUP BY deptid
        HAVING COUNT(*) = 1
    );
    
    ```
    
7. **In the PROJ table, a row with a null value in the MAJPROJ column indicates that the project represented by that row is not a sub-project of any other. Display the project number, name, and end date of all projects along with a remark of ‘Sub-project’ if the MAJPROJ value is not null and ‘Not a sub-project’ otherwise. Order the result by project end date.**
    
    ```SQL
    sql
    Copy code
    SELECT projno, projname, enddate,
    CASE
        WHEN majproj IS NULL THEN 'Not a sub-project'
        ELSE 'Sub-project'
    END AS remark
    FROM Proj
    ORDER BY enddate;
    
    ```
    

### Task 2: Table Modifications with Sub-queries

1. **Create a new database “NewCompany” and use it as the database for all activities in this task.**
    
    ```SQL
    sql
    Copy code
    CREATE DATABASE NewCompany;
    USE NewCompany;
    
    ```
    
2. **Create the Emp and Dept tables on the NewCompany database using the create_tables.sql script. Then populate the two tables Emp and Dept using insemp.sql and insdept.sql files. Look at the table structure and the data and be familiar with the tables.**
    
    ```SQL
    sql
    Copy code
    -- Assuming the create_tables.sql script has the required commands.
    SOURCE create_tables.sql;
    SOURCE insemp.sql;
    SOURCE insdept.sql;
    
    ```
    
3. **Create the table Emp2 from table Emp, using a statement of the form: The select_expression should select the appropriate table, and the results are stored in Emp2, instead of being displayed and discarded. The employee name in Emp2 should be in the format <lastname>,<first initial>. For example, Eileen Henderson becomes Henderson,E. Note also that the table contains the age of the employee, not the birthdate, so you will need to calculate that.**
    
    ```SQL
    sql
    Copy code
    CREATE TABLE Emp2 AS
    SELECT empno AS eid,
           CONCAT(lastname, ',', LEFT(firstname, 1)) AS ename,
           YEAR(CURDATE()) - YEAR(birthdate) AS age,
           gender,
           salary
    FROM Emp;
    
    ```
    
4. **Make eid the primary key of Emp2, by using an ALTER TABLE statement of the form:**
    
    ```SQL
    ALTER TABLE Emp2 ADD PRIMARY KEY (eid);
    ```
    
5. **Create the table Dept2 in your database using the following statement:**
    
    ```SQL
    CREATE TABLE Dept2 (
        did CHAR(3),
        dname VARCHAR(36),
        budget DECIMAL(12,2),
        managerid CHAR(6),
        PRIMARY KEY(did),
        FOREIGN KEY (managerid) REFERENCES Emp2 (eid)
    );
    
    ```
    
6. **Insert data into Dept2 from the Emp and Dept tables of Practical 2. Take the budget of each department as 20% more than the total salary of all employees in the department. Use an insert statement of the same form as above. Note the renaming of some attributes.**
    
    ```SQL
    sql
    Copy code
    INSERT INTO Dept2 (did, dname, budget, managerid)
    SELECT d.deptid, d.deptname, (1.2 * SUM(e.salary)), d.managerid
    FROM Dept d
    JOIN Emp e ON d.deptid = e.deptid
    GROUP BY d.deptid;
    
    ```
    
7. **Use a CREATE TABLE statement with a subquery to create the table Works2, assuming that the percentage of time each employee works in his/her workdept is 100.**
    
    ```SQL
    sql
    Copy code
    CREATE TABLE Work2 AS
    SELECT empno AS eid,
           deptid AS did,
           100 AS pct_time
    FROM Emp;
    
    ```
    
8. **Add an attribute called ‘since’ of TIMESTAMP type to Works2 table, using an ALTER TABLE statement. Give CURRENT_TIMESTAMP as the default value for this attribute. Display the rows of the table to check the changes.**
    
    ```SQL
    sql
    Copy code
    ALTER TABLE Work2
    ADD COLUMN since TIMESTAMP DEFAULT CURRENT_TIMESTAMP;
    
    ```
    
9. **Delete all managers of departments from the Works2 table.**
    
    ```SQL
    sql
    Copy code
    DELETE FROM Work2
    WHERE eid IN (SELECT managerid FROM Dept);
    
    ```
    
10. **Update the since column of Work2 with the hiredate of each employee from the EMP table.**

```SQL
sql
Copy code
UPDATE Work2 w
SET since = (SELECT hiredate FROM Emp e WHERE e.empno = w.eid);

```

1. **Define (eid, did) as the primary key of Works2, using ALTER TABLE in the form:**

```SQL
sql
Copy code
ALTER TABLE Work2 ADD PRIMARY KEY (eid, did);

```

This complete version includes both the questions and the corresponding SQL queries. Let me know if you need further assistance!