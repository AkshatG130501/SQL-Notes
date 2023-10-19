# DML 

# UPDATE

    UPDATE Customer SET Address = 'Mumbai', Gender = 'M' WHERE id = 122;

    Update Multiple rows together : 

        SET SQL_SAFE_UPDATES = 0;    (SQl does not allow updating all data together in safe mode)
        UPDATE Customer SET pincode = 3303030;
    
        UPDATE Customer SET pincode = pincode + 1;
    

# DELETE

    DELETE FROM Customer WHERE id = 121;

    
# Referential Constraints Overcome Methods 

    -> ON DELETE CASCASDE
    -> ON DELETE SET NULL

    CREATE TABLE Customer(
        id INT NOT NULL,
        name VARCHAR(50),
        address VARCHAR(100),
    )

    CREATE TABLE Order_id(
        order_id INT AUTO_INCREMENT PRIMARY KEY,
        cust_id INT,
        FOREIGN  KEY(cust_id) REFERENCES Customer(id) ON DELETE CASCADE
    )

    DELETE FROM Customer WHERE id = 1;

