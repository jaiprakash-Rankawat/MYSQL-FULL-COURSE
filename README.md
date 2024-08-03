# MYSQL-FULL-COURSE
COMPLETE COURSE ABOUT MYSQL 

# 1. CREATE DATABASE 
CREATE DATABASE DATABASENAME;
<h3>Example :</h3>
<ol>
  <li>create database car;</li>
  <li>CREATE DATABASE STUDENTS;</li>
  <ul>
    <li>These both line will create a database. </li>
    <li>Database is not a case sensitive.</li>
</ol>

# 2. DROP DATABASE 
DROP DATABASE DATABASENAME;
<h3>Example :</h3>
<ol>
  <li>drop database car;</li>
</ol>

# 3. SHOW DATABASES
SHOW DATABASES;
<P>Show all databases present in database</P>

# 4. USE DATABASE
USE DATABASE DATABASENAME;
<p>After creating we have to use database.</p>
<h3>Example :</h3>
<ol>
  <li>use database car;</li>
</ol>

# 5. SELECT DATABASE();
<p>Give current working database.</p>
<br>


# Tables In MYSQL

# 1. CREATING TABLE <br>
create table TableName( <br>
  firstName varchar(30), <br>
  lastName varchar(20),<br>
  Age int);<br>

# 2. SHOW ALL TABLES
SHOW TABLES;

# 3. DATA TYPE OF VARIABLE
DESC TABLENAME;

# 4. INSERT DATA INTO TABLE
INSERT INTO TABLENAME(firstName,lastName,Age)  <br>
values("ajay","sharma",45), <br>
("aman","gupta",22), <br>
("rohit","kumawat",26); <br>

# 5. SHOW DATA FROM TABLE
SELECT * FROM TABLENAME; <br>

# 6. DELETE TABLE
DELETE TABLE TABLENAME;

# 7. CREATE TABLE FROM EXISTING TABLE 
CREATE TABLE newTableName as <br>
select column1, column2 from oldTableName <br>
where condition ; <br>

# 8. DELETE DATA FROM TABLE 
TRUNCATE TABLE TABLENAME;

<H1>ALTER TABLE STATEMENTS</H1>
<P>ALTER TABLE statement is used to add, delete, or modify columns in an existing table.</P>

# 1. ADD COLUMN
alter table TableName <BR>
add columnName dataType; <BR>

# 2. DELETE COLUMN 
alter table tableName <br>
drop column columnName; <br>

# 3. CHANGE DATA TYPE
alter table tableName <br>
modify column columnName newDataType ; <br>

# CONSTRAINTS
<OL>
<li>NOT NULL - Ensures that a column cannot have a NULL value</li>
<li>UNIQUE - Ensures that all values in a column are different</li>
<li>PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table</li>
<li>FOREIGN KEY - Prevents actions that would destroy links between tables</li>
<li>CHECK - Ensures that the values in a column satisfies a specific condition<li>
<li>DEFAULT - Sets a default value for a column if no value is specified</li>
<li>CREATE INDEX - Used to create and retrieve data from the database very quickly</li>
</OL>

# EXAMPLES 
CREATE TABLE PRODUCT (
    ID INT PRIMARY KEY, <BR>
    NAME VARCHAR(255) UNIQUE, <BR>
    COMPANY_NAME VARCHAR(255) NOT NULL, <BR>
    WEIGHT DECIMAL(10,2), --DEFAULT  <BR>
    PRICE INT CHECK (PRICE > 3000 AND PRICE < 5000) <BR>
);

# ALTER IS ALSO USED TO CHANGE KEY 
alter table product( <BR>
add unique(company_name);<BR>

# DROP UNIQUE CONSTRAINT 
alter table product
drop index company_name;

# FOREIGN KEY 
CREATE TABLE PRODUCT (
    ID INT PRIMARY KEY, <BR>
    NAME VARCHAR(255) UNIQUE, <BR>
    COMPANY_NAME VARCHAR(255) NOT NULL, <BR>
    WEIGHT DECIMAL(10,2), --DEFAULT  <BR>
    PRICE INT CHECK (PRICE > 3000 AND PRICE < 5000) <BR>
);
<BR> <BR>
CREATE TABLE billing ( <BR>
    id INT, <BR>
    quantity INT NOT NULL, <BR>
    purchase_price DECIMAL(10,2) NOT NULL, <BR>
    date DATE, <BR>
    FOREIGN KEY (id) REFERENCES product(id) <BR>
); <BR><BR><BR>
INSERT INTO billing (id, quantity, purchase_price, date) <BR>
VALUES <BR>
    (1, 10, 2950, '2024-07-15'), <BR>
    (2, 15, 3200, '2024-07-16'), <BR>
    (3, 15, 3150, '2024-07-14'); <BR>

<BR>
INSERT INTO PRODUCT (ID, NAME, COMPANY_NAME, WEIGHT, PRICE) <BR>
VALUES <BR>
(1, "ACE EXTERIOR EMULSION", "ASIAN PAINTS", 20, 3010), <BR>
(2, "JK TRU SHYNE", "JK MAXX PAINTS", 20, 3400), <BR>
(3, "PIXA EXTERIOR EMULSION", "JSW PAINTS", 20, 3500); <BR>

# DEFAULT CONSTRAINT 
CREATE TABLE GAMES ( <BR>
NAME VARCHAR(50) UNIQUE, <BR>
PLAYED VARCHAR(30) DEFAULT 'NOT PLAYED' <BR>
); <BR>
<P>Normally, it is used to show current date (default current_date)</P>


  # CLEAR TERMINAL (BOUNS)
  SYSTEM CLS;
