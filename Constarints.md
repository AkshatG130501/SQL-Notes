# PRIMARY KEY 
    1. Not NULL
    2. Unique
    3. Only one P.K

    Good Practice : keep P.K INT


    Two ways to decalre P.K : 

    1. id INT PRIMARY KEY,
    
    2. id INT, 
       PRIMARY KEY(id)


# FROEIGN KEY
(Refers to P.K of other table)

Customer(
    id INT PRIMARY KEY,
    cname VARCHAR(255),
    Address VARCHAR(255),
)

Order(
    order_id INT PRIMARY KEY,
    delivery_date DATE,
    cust_id INT,
    FOREIGN KEY (cust_id) REFERENCES Customer(id)
)

Order -> referencing table  ,   customer -> referenced table


# UNIQUE

    we want in the DB each name to be unique:

            CREATE TABLE Customer(
                id INT NOT NULL AUTO_INCREMENT,
                name VARCHAR(255) UNIQUE,
            )
            ensures each name entered will be unique(checks if it doesn't exist before in DB)


# CHECK

    CREATE TABLE Account(
        id INT PRIMARY KEY,
        name VARCHAR(255) UNIQUE,
        balance INT,
        CONSTRAINT acc_chk_bal CHECK(balance>1000)
    )


# DEFAULT 
    CREATE TABLE Account(
        name VARCHAR(255),
        balance INT NOT NULL DEFAULT 0,
    )

    INSERT INTO Account 
    VALUES('Akshat')

    by default balance value will be set to 0 (we didn't specify its value)


// An attribute can be both F.K and P.K in a table