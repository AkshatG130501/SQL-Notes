To Apply JOINS , there should be a common atribute.
#

# INNER JOIN 
Returns a resultant table that has matching values from both the tables or all the tables.

Synatx : 

    SELECT Column_List FROM table1 INNER JOIN table2 ON Codition1 INNER JOIN table3 ON Condition2


Example : 

    SELECT c.*, o.* FROM Cutomer AS c INNER JOIN Order AS o ON c.id = o.cust_id;


# OUTER JOIN

1.  LEFT JOIN 
    
    Returns all records of the left table and the matched records in the right table. If no match is found on the right side it returns NULL 

        SELECT c.*, o.* FROM Cutomer AS c LEFT JOIN Order AS o ON c.id = o.cust_id;


2. RIGHT JOIN 

    Return all records of the right table and the matched records in the left table. If no match is found on the left side it returns NULL 

        SELECT c.*, o.* FROM Cutomer AS c LEFT JOIN Order AS o ON c.id = o.cust_id;


3. FULL JOIN (No such keyword)

    Union of LEFT and RIGHT JOIN

        SELECT c.*, o.* FROM Cutomer AS c LEFT JOIN Order AS o ON c.id = o.cust_id
        UNION
        SELECT c.*, o.* FROM Cutomer AS c RIGHT JOIN Order AS o ON c.id = o.cust_id;


# CROSS JOIN 
Cross join returns Cartesian product of two tables. It means each row in one table is matched with every row in another table (No industrial use).

    SELECT c.*,o.* FROM Customer As c CROSS JOIN Order AS o;


# SELF JOIN 
Used to get output from a particular table when the same table is joined to itself.

    SELECT c.* FROM Customer AS c1 INNER JOIN Customer AS c2 ON c1.id = c2.id;

# Questions 

![](/Images/project.png)


![](/Images/employee.png)


![](/Images/client.png)


Q1. Enlist all the employees ID's , names along with the Project allocated to them.

    SELECT e.id, e.fname, e.lname, p.name FROM Employee AS e INNER JOIN Project AS p ON e.id = p.empID;

Q2. Fetch out all the employee ID's and their contact detail who have been working from Jaipur with the clinets name working in Hyderabad

    SELECT e.id, e.emailID, e.PhoneNo, c.first_name, c.last_name FROM Employee AS e INNER JOIN Client AS c ON e.id = c.empID WHERE e.City = 'Jaipur' AND c.City = 'Hyderabad';

Q3. Fetch out each project allocated to each Employee

    SELECT * FROM Employee as e LEFT JOIN Project as p ON e.id = p.empID;

Q4. List out all the combinations possible for the employee's name and projects that can exist.

    SELECT e.fname, e.lname, p.name FROM Employee AS e CROSS JOIN  FROM Project AS p;

Q5. List out all the projects along with the employee's name and their respective allocated email ID.

    SELECT e.name, e.emailID, p.name FROM Employee AS e RIGHT JOIN FROM Project AS p on e.id = p.empID;

Q6. Can we use JOIN without using the keyword JOIN ?

    Yes, 
    SELECT e.id, e.fname, e.lname, p.name FROM Employee AS e, Project AS p WHERE e.id = p.empID;

