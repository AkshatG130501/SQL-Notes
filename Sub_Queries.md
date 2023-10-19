# Sub Queries
Q1 ( Q2 ) 

Q1-> Outer Query

Q2 -> Inner Query

Generally Outer Query depends on Inner Query.

# Correlated SubQuery

Q. Find 3rd oldest Employee

    SELECT * FROM Employee e1
    WHERE 3 = (
        SELECT COUNT(e2.Age)
        FROM Employee e2
        WHERE e2.Age >= e1.Age
    );

