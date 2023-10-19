# Creating a DB named temp
    CREATE DATABASE temp;
    use temp;

# Creating a table and inserting data in it

    CREATE TABLE Student(
        Id INT PRIMARY KEY,
        Name VARCHAR(255),
    );

    INSERT INTO Student VALUES(1,"Akshat");

    SELECT * FROM Student;
    
