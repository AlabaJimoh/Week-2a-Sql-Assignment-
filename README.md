# Week-2a-Sql-Assignment-
-- Create the 'payments' table (assuming it doesn't exist)
CREATE TABLE IF NOT EXISTS payments (
    checkNumber VARCHAR(50), -- Assuming a reasonable length
    paymentDate DATE,
    amount DECIMAL(10, 2) -- Assuming a currency amount
);

-- Create the 'orders' table (assuming it doesn't exist)
CREATE TABLE IF NOT EXISTS orders (
    orderNumber INT, -- Assuming an integer order number
    orderDate DATE,
    requiredDate DATE,
    status VARCHAR(50) -- Assuming a reasonable length for status
);

-- Create the 'employees' table (assuming it doesn't exist)
CREATE TABLE IF NOT EXISTS employees (
    employeeNumber INT,
    firstName VARCHAR(50), -- Assuming a reasonable length
    lastName VARCHAR(50), -- Assuming a reasonable length
    email VARCHAR(100), -- Assuming a reasonable length
    jobTitle VARCHAR(50) -- Assuming a reasonable length
);

-- Create the 'offices' table (assuming it doesn't exist)
CREATE TABLE IF NOT EXISTS offices (
    officeCode VARCHAR(10) -- Assuming a reasonable length
    -- Add other columns as needed for your specific schema
);

-- Create the 'products' table (assuming it doesn't exist)
CREATE TABLE IF NOT EXISTS products (
    productCode VARCHAR(15), -- Assuming a reasonable length
    productName VARCHAR(75), -- Assuming a reasonable length
    quantityInStock INT,
    buyPrice DECIMAL(10, 2) -- Assuming a currency amount
);

-- Query 1: Retrieve checkNumber, paymentDate, and amount from the payments table
SELECT
    checkNumber,
    paymentDate,
    amount
FROM
    payments;

-- Query 2: Retrieve orderDate, requiredDate, and status of 'In Process' orders, sorted by orderDate descending
SELECT
    orderDate,
    requiredDate,
    status
FROM
    orders
WHERE
    status = 'In Process'
ORDER BY
    orderDate DESC;

-- Query 3: Display firstName, lastName, and email of 'Sales Rep' employees, sorted by employeeNumber descending
SELECT
    firstName,
    lastName,
    email
FROM
    employees
WHERE
    jobTitle = 'Sales Rep'
ORDER BY
    employeeNumber DESC;

-- Query 4: Retrieve all columns and records from the offices table
SELECT
    *
FROM
    offices;

-- Query 5: Fetch productName and quantityInStock from the products table, sorted by buyPrice ascending, limit to 5 records
SELECT
    productName,
    quantityInStock
FROM
    products
ORDER BY
    buyPrice ASC
LIMIT 5;
