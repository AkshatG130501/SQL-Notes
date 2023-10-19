#
1. Data already present , REPLACE
2. Data not present, INSERT
#

# REPLACE

    REPLACE INTO Customer(id,city)
        VALUES(1251,'NYC');
    
    REPLACE INTO Customer SET id = 1300, cname = 'Max', city = 'NYC';

    REPLACE INTO Customer(id,cname,city)
        SELECT id,cname,city
        FROM Customer WHERE id = 500;


#

REPLACE Vs UPDATE

1. If row is not present , REPLACE will add(insert) a new row while UPDATE will do nothing.
 