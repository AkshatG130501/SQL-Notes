# DQL 

    Syntax : SELECT <set of column names> FROM <table_name>

    Order of execution is from left to right => first FROM executes then SELECT

    SELECT * FROM Worker;   // Lists the complete worker table
    
    SELECT First_Name , Salary FROM Worker; // Returns the first_name and salary column  


# Q. Can we use SELECT without FROM ?   
Ans.    Using dual tables (dummy tables created by MySQL without reffering to user-defined     tables).

    SELECT 44 + 11;     // returns 55
    SELECT now();       // gives server time
    SELECT ucase('aksHat');     // AKSHAT



# WHERE
(Applying condition)

    SELECT * FROM Worker WHERE Salary > 800000;
    SELECT * FROM Worker WHERE Department = 'HR';


# BETWEEN
    SELECT * FROM Worker WHERE Salary BETWEEN 80000 AND 100000;   
    (80000 and 100000 are inclusive)


# IN
(Reduces OR conditons)
    Q : all worker data who work in HR or ADMIN Department

    SELECT * FROM Worker WHERE Department = 'HR' OR Department = 'ADMIN';

    Better way :
    SELECT * FROM Worker WHERE Department IN ('HR', 'ADMIN') ;


# NOT
    SELECT * FROM Worker WHERE Department NOT IN ('HR', 'ADMIN') ;


# NULL 
    INSERT INTO Customer VALUES(1252, 'Akshat', 'Rajasthan', 'M', NULL);

    SELECT * FROM Customer WHERE pincode is NULL;   // Above entry gets printed


# WILDCARDS
    %  -> Any no. of characters
    _  -> Single character

    print all workers whose name have 'i'
    SELECT * FROM Worker WHERE First_name LIKE '%i%';

    print all workers whose name have i as second letter
    SELECT * FROM Worker WHERE First_name LIKE '_i%';

