# CS303_Final_Project_1

The table used in this assignment has many functional and transitive dependencies which need to be addressed in order for the table to be considered normalized. The Employee ID column is the primary key and determines the values of the employee’s first and last name, address, Position, and salary. This means Employee Last Name, Employee First Name, Street Address, Position, and Salary are functionally dependent on the primary key Employee ID. City, State, and Zip code are transitively dependent on the Street Address because they are not dependent on the employee’s primary key and thus violates the rules of second and third normal form. Department and Manager ID are also not dependent on Employee ID so they are transitively dependent on the position. 

The table is not in 3NF and is instead in 1NF because it contains not all non-primary keys are dependent on the primary key and there are transitive dependencies in the same table. In order to normalize the table in the third normal form the current table must be split into separate tables for Employee, Address, City, State, Zip Code, Department, and Position. Each new table will also need primary keys established in them to relate back to the first table and not contain duplicate records. 

CREATE TABLE employee (employeeid INT PRIMARY KEY, employeelastname VARCHAR(45), employeefirstname VARCHAR(45), salary VARCHAR(45)); 

CREATE TABLE address (addressid INT PRIMARY KEY, streetaddress VARCHAR(45));  

CREATE TABLE city (cityid INT PRIMARY KEY, city VARCHAR (45)); 

CREATE TABLE state (stateid INT PRIMARY KEY, state VARCHAR(2)); 

CREATE TABLE zipcode (zipcodeid INT PRIMARY KEY, zipcode INT); 

CREATE TABLE department (departmentid INT PRIMARY KEY, managerid INT); 

CREATE TABLE position (positionid INT PRIMARY KEY, postion VARCHAR(45)); 

Now to fill in the tables with the data from the original database: 

INSERT INTO employee VALUES (1005, ‘Doe’, ‘Janet’, ‘$100,000’), (1010, ‘Eyre’, ‘Jane’, ‘$95,000’), (1011, ‘Bronte’, ‘Charlotte’, ‘$75,000’), (2060, ‘Poe’, ‘Edgar’, ‘$70,000’), (2090, ‘Dickens’, ‘Charles’, ‘$45,000’), (2100, ‘Doyle’, ‘AC’, ‘$60,000’), (3230, ‘Uberville’, ‘Tess’, ‘$50,000’), (3330, ‘Dumas’, ‘Alex’, ‘$35,000’); 

INSERT INTO address VALUES (1, ‘312 Maple Drive’), (2, ‘1200 First Street’), (3, ‘4989 Fleur de Lane’), (4, ‘12 Arcadia Avenue’), (5, ‘687 Gulf View Street’), (6, ‘1209 Pine Tree Lane’), (7, ‘5435 Main Street’), (8, ‘3 Post Drive’); 

INSERT INTO city VALUES (1, ‘Anytown’), (2, ‘Sometown’); 

INSERT INTO state VALUES (1, ‘FL’); 

INSERT INTO zipcode VALUES (1, 32829), (2, 32830), (3, 32831); 

INSERT INTO department VALUES (1, ‘Board of Directors’, 1000), (2, ‘Administration’, 1005), (3, ‘Information Technology’, 1015), (4, ‘Sales’, 1021); 

INSERT INTO position VALUES (1, ‘President’), (2, 'Vice President’), (3, ‘Programmer I’), (4, ‘Programmer II’), (5, ‘Sales Representative’); 
