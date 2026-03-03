Objective:
Create and use a managed relational database.

Description:
An RDS MySQL instance was created. Database and tables were created and accessed using a SQL client.


RDS Name: db-1
Master Username: MuskanDB
Database Name: Task16DB

Objective:
To create a MySQL database using Amazon RDS and connect it using SQL Workbench to run basic SQL queries.

What I did step by step:

1. I went to AWS Console → RDS → Create database.
2. I selected Standard create and chose MySQL engine.
3. I selected Free tier template.
4. I gave DB instance identifier name:
   db-1
5. I set master username as:
   MuskanDB
6. I created and saved the master password.
7. I selected db.t3.micro instance class.
8. In connectivity section, I selected Default VPC.
9. I enabled Publicly accessible = YES.
10. I created/used a security group and added inbound rule:
    Type: MySQL/Aurora
    Port: 3306
    Source: My IP
11. I created the database and waited until status became "Available".
12. I copied the RDS endpoint from Connectivity section.
13. I opened MySQL Workbench.
14. I entered:
    Hostname: RDS endpoint
    Port: 3306
    Username: MuskanDB
    Password: my RDS password
15. I tested the connection and successfully connected.

Queries I executed:

CREATE DATABASE Task16DB;
USE Task16DB;

CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(50)
);

INSERT INTO users (name, email)
VALUES ('Muskan', 'muskan@example.com');

SELECT * FROM users;

Result:
The RDS database was successfully created and connected.
The Task16DB database was created.
The users table was created successfully.
Data was inserted and SELECT query showed the inserted record.

Services Used:
- Amazon RDS (MySQL)
- MySQL Workbench
- Security Groups

Proof:
- Screenshot of RDS status (Available)
- Screenshot of inbound rule (Port 3306 allowed)
- Screenshot of SQL query output
Result:
Managed database service used successfully.
