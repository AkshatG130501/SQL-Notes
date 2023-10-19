# ALTER OPERATIONS

    CREATE TABLE Account(
        id INT PRIMARY KEY,
        name VARCHAR(255) UNIQUE,
        balance 
    )

# ADD

    Adding a new column in the table:

        ALTER TABLE Account ADD interest FLOAT NOT NULL DEAFULT 0;

# MODIFY

    Modify :

        ALTER TABLE Account MODIFY interest DOUBLE NOT NULL DEAFULT 0;

    -- DESC Account ;    // To describe the table

# CHANGE COLUMN

    Rename Column : 

        ALTER TABLE Account CHANGE COLUMN interest saving_interest FLOAT NOT NULL DEFAULT 0;
        (Necessary : To specify the datatype with change colum command)
    

# DROP COLUMN 

    ALTER TABLE Account DROP COLUMN saving_interest;

# RENAME TABLE

    ALTER TABLE Account RENAME TO Account_Details;



