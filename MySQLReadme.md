# Basic commands

CREATE => Creates a new table, view, or stored procedure. Ex.:

CREATE TABLE employees (employee_id INT PRIMARY KEY, first_name VARCHAR(50), last_name VARCHAR(50), hire_date DATE); => Creates a new "employees" table with the specified columns and data types.

ALTER => Modifies the structure of a table or view. Ex.:

ALTER TABLE customers ADD COLUMN email VARCHAR(100); => Adds a new "email" column to the "customers" table.

SELECT => Retrieves data from one or more tables. Ex.:

SELECT * FROM customers WHERE age > 30; => Retrieves all columns from the "customers" table where the "age" column is greater than 30.

INSERT => Inserts new data into a table. Ex.:

INSERT INTO orders (order_id, customer_id, order_date) VALUES (1, 101, '2023-04-26'); => Inserts a new row into the "orders" table with the specified values for the "order_id", "customer_id", and "order_date" columns.

UPDATE => Updates existing data in a table. Ex.:

UPDATE products SET price = 9.99 WHERE product_id = 5; => Updates the "price" column in the "products" table to 9.99 for the row where the "product_id" is 5.

DELETE => Deletes data from a table. Ex.:

DELETE FROM customers WHERE customer_id = 101; => Deletes the row from the "customers" table where the "customer_id" is 101.

DROP => Deletes a table, view, or stored procedure. Ex.:

DROP VIEW order_summary; => Deletes the "order_summary" view.

GRANT => Grants privileges to a MySQL user account. Ex.:

GRANT SELECT, INSERT, UPDATE ON orders TO 'user1'@'localhost'; => Grants the "user1" MySQL user account SELECT, INSERT, and UPDATE privileges on the "orders" table.

REVOKE => Revokes privileges from a MySQL user account. Ex.:

REVOKE DELETE ON products FROM 'user2'@'localhost'; => Revokes the "user2" MySQL user account's DELETE privilege on the "products" table.

SHOW => Displays information about databases, tables, or views. Ex.:

SHOW DATABASES; => Displays a list of all databases in the MySQL server.

DESCRIBE => Describes the structure of a table. Ex.:

DESCRIBE customers; => Displays the structure of the "customers" table.

USE => Specifies the database to use. Ex.:

USE sales_database; => Specifies that the "sales_database" database should be used.

SET => Sets MySQL system variables. Ex.:

SET GLOBAL max_connections = 1000; => Sets the maximum number of allowed connections to 1000.

EXPLAIN => Displays information about how MySQL executes a query. Ex.:

EXPLAIN SELECT * FROM orders WHERE order_id = 100; => Displays information about how MySQL executes the query to retrieve all columns from the "orders" table where the "order_id" is 100.

FLUSH => Flushes tables or logs. Ex.:

FLUSH TABLES; => Flushes all tables in the MySQL server's cache.

# INNER and OUTER commands

1. INNER JOIN:

Assuming we have two tables named "customers" and "orders", with a common column "customer_id", the following MySQL command will join the two tables using an INNER JOIN and return only the rows where there is a match on the customer_id column:

```
SELECT *
FROM customers
INNER JOIN orders
ON customers.customer_id = orders.customer_id;
```

This command will return only the rows where there is a match on the customer_id column, meaning that only the customers who have placed an order will be returned.

2. LEFT OUTER JOIN:

Assuming we have the same "customers" and "orders" tables as above, the following MySQL command will join the two tables using a LEFT OUTER JOIN and return all rows from the customers table along with matching rows from the orders table. If there is no match in the orders table, the result will contain NULL values for the orders columns:

```
SELECT *
FROM customers
LEFT OUTER JOIN orders
ON customers.customer_id = orders.customer_id;
```

This command will return all rows from the customers table, even if there is no match in the orders table. If there is a match, the result will contain columns from both tables, but if there is no match, the result will contain NULL values for the orders columns.

3. RIGHT OUTER JOIN:

Assuming we have the same "customers" and "orders" tables as above, the following MySQL command will join the two tables using a RIGHT OUTER JOIN and return all rows from the orders table along with matching rows from the customers table. If there is no match in the customers table, the result will contain NULL values for the customers columns:

```
SELECT *
FROM customers
RIGHT OUTER JOIN orders
ON customers.customer_id = orders.customer_id;
```

This command will return all rows from the orders table, even if there is no match in the customers table. If there is a match, the result will contain columns from both tables, but if there is no match, the result will contain NULL values for the customers columns.
