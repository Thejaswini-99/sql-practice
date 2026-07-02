what is Database?
        DataBase is a organised collection of Data 
        Ex: Employee , Student 


Table: Table is structured collection of data which contains rows and colums
        Ex: Employee table which contains emp name, emp mail,emp phone number 


Row: It is also know as a record where it contains the complete entry in the table 
Example:
id	name	email	city
1	Rahul Mehta	rahul.mehta@mail.com	Mumbai


Column: It is also known as field represents one specific attribute or property of the data stored in the table.All the columns will be same for the reocrd in the table there might be data miss in the tbale
Example (same Customers table):
name - column that stores the name of each customer
email - column that stores the email of each customer

SQL: Structured Querry Language.It is a langugae which is used to communicate with the DB.It helps you to find,store,update,delete data in the db


RDBMS & NOSQL DBMS

Relational db store the data in strict tables and connect those tables using some shared piece of information.

Example:
A Students table.
An Attendance table.
A Fees table.
All of these are connected through a common identifier, like a student ID or an email address. That connection is called the relation.
MYSQL,POSTGRESQL


NOSQL DBMS store the data in no reistirct manner they were built for flexibilty and store the data in different forms like Key-Value pairs, Json format,Graph Structues.NOSQL often stores related data in the form of a documents
Examples: MongoDB, Cassandra, Redis.


RDBMS priortizes structre and correctness it suites more for banking,accounting
NOSQL proitizes speed and flexibility it suites for live chats,media feeds 

OLTP: Online Transaction Processing. --- for day to day activites like fetch,update,delete
OLAP: Online Analysis Processing. -- like for doing analysi like fetching the data from millions of users

Transactional DB: It is a not a single querry it is bundle oprations that belong together like dedcuct the money from the students wallet and upadte the finances table and update the students table to show the status table as fees paid






