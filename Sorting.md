# ORDER BY

    Sort workers according to salary :

    1. Ascending :
        SELECT * FROM Worker ORDER BY Salary;
    2. Descending :
        SELECT * FROM Worker ORDER BY Salary DESC;
    

# DISTINCT

    If we have multiple departments in a table , we need distinct departments :
        
        SELECT DISTINCT Department FROM Worker;  

    // HR, Admin, Account


# GROUP BY
(Used with aggregation functions (COUNT, SUM, AVG, MIN) )
=>  Without aggregation function GROUP BY works as DISTINCT
    
    Find no. of employees working in each department :

        SELECT Department, COUNT(Department) FROM Worker GROUP BY Department;
    
    Find avg. salary per department : 

        SELECT Department, AVG(Salary) FROM Worker GROUP BY Department;

        SELECT Department, MIN(Salary) FROM Worker GROUP BY Department;

        SELECT Department, MAX(Salary) FROM Worker GROUP BY Department;

        SELECT Department, SUM(Salary) FROM Worker GROUP BY Department;


# GROUP BY HAVING

    Find department count , having more than two workers :

        SELECT Department, COUNT(Department) FROM Worker GROUP BY Department HAVING COUNT(Department) > 2;
    
 Q. WHERE vs  HAVING ? 
        WHERE -> Filtering on table
        HAVING -> Filtering after aggregate function is applied(on groups)

