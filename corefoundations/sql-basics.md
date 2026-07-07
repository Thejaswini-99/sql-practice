

SQL :  SQL Commands are instructions used to communicate with the databases

DDL : Data Definition Language ( Create,Alter,Drop,Truncate,Rename)
DML : Data Manipulative Language(Update,Insert,Delete,Modify)
DQL : Data Query Language (Select)
DCL : Data Control Language(Grant,Revoke)
TCL : Transaction Control Langauge(Commit,Rollback,Save)

Creating DATABASES:

CREATE DATABASE tuf_sql  -- cretes a database
USE tuf_sql.             -- it makes all the commands what ever we write goes to this the database by default
CREATE DATABASE IF NOT EXISTS tuf_sql.  --- if not exists it creates this table
SHOW DATABASES.               -- it shows the databases 
DROP DATABASE IF EXISTS tuf_sql.  --- if exists it removes the entire databases


Datatypes:
The kind of data we need to store in the table is 

Examples: int , bigint, varchar, text, date, datetime/timestamp , boolean, decimal


CREATE TABLE IF NOT EXISTS users (
  user_id INT,
  name VARCHAR(30),
  email VARCHAR(50),
  is_active BOOLEAN,
  account_balance DECIMAL(10,2),
  signup_datetime DATETIME,
  last_seen DATETIME
);

SHOW TABLES;

DROP TABLE users;
DROP TABLE IF EXISTS users;

INSERT INTO users (user_id, name, email)
VALUES (1, 'Raj', 'raj@gmail.com');

INSERT INTO users (user_id, name, email)
VALUES
  (2, 'Mark', 'mark@gmail.com'),
  (3, 'Albert', 'albert@gmail.com'),
  (4, 'Peter', 'peter@gmail.com');

  SELECT * FROM users;

  SELECT
  name,
  email AS mail_id
FROM users;


Primary Key:
It is column or a set of colums in table which is never null and that uniquely identifies each rows in the table 

CREATE TABLE users (
  user_id INT PRIMARY KEY,
  name VARCHAR(30),
  email VARCHAR(50)
);


CREATE TABLE users (
  user_id INT,
  name VARCHAR(30),
  email VARCHAR(50),
  PRIMARY KEY (user_id)
);

Forigen Key:
It is also a column in a table which relates to the other table(keeps a relationship with another table) and it is a primary key in another table


CREATE TABLE orders (
  order_id INT Primary key,
  user_id INT References users(user_id)
  order_placed datetime,
  amount decimal
);

CREATE TABLE orders (
  order_id INT Primary key,
  user_id INT References users(user_id)
  order_placed datetime,
  amount decimal

  user_id References users(user_id)
);


Composite Primary Keys: More than one primary keys in the table is called composite primary keys
CREATE TABLE users (
  user_id INT,
  name VARCHAR(30),
  email VARCHAR(50),
  PRIMARY KEY (user_id,email)
);




Constriants in SQL:

AutoIncrement:
It incremnts automatically if last cell data was 0 it will make it to 1 if it 10 it will increment to 11
CREATE TABLE users (
  user_id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(30),
  email VARCHAR(50)
);

UNIQUE: It makes the key unique

CHECK: it is constraint where we will introduce the conditon like age>15 and age<30

NOT NULL:it makes sure that no cell is empty like email can't be empty

DEFUALT: it sets the deafult value to soemthing if no value is entered


CREATE TABLE IF NOT EXISTS users (
  user_id INT Primary Key Auto_increament ,
  name VARCHAR(30),
  email VARCHAR(50) Unique Not Null,
  is_active BOOLEAN Default true,
  account_balance DECIMAL ,
  signup_datetime DATETIME,
  last_seen DATETIME

  check (account_balance> 100)
);

NULL -- no value it doesn't mean zero there could be any value not empty space 
0 -- means 0 does mean nothing it means 0 quantity, 0 
"" -- empty string means it has one empty space.it conatisn no character


how query works interally:
parse : checks for semantic errors
plan : checks which page or from which place data needs to be reterived
execute : Actaull execution of the querry

Indexing in the SQL:

Index:  it is used for the faster data retrivel.An index in a database is a special data structure (often a B-tree or similar) that is built on one or more columns of a table to make searching faster. Instead of scanning every row in the table, the database uses the index to jump directly to the matching rows, just like a book index.


CREATE INDEX idx_user_email ON users(email);
CREATE INDEX idx_name_city ON users(full_name, city);


you drop by drop index indx_user_city from users








