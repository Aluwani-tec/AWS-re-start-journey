# Database Module 


These notes explain **step by step** what tasks were completed in the Database lab,
what actions were taken, and what was learned from each activity.

---

## 1. Lab Objectives

The objectives of this lab were to:

- Understand the difference between relational and NoSQL databases
- Work with managed databases using Amazon RDS
- Understand DynamoDB concepts and use cases
- Perform hands-on SQL operations inside an EC2 instance
- Create databases, tables, and queries using MySQL/MariaDB
- Combine data using JOIN operations

---

## 2. Databases in Practice - Amazon RDS (Conceptual)

Amazon RDS was studied to understand how AWS manages relational databases
without requiring manual server administration.

### Key Concepts Learned
- RDS supports engines such as MySQL, MariaDB, PostgreSQL, and others
- Multi-AZ deployments improve availability by maintaining a standby replica
- Read replicas are used to improve performance for read-heavy workloads
- AWS automatically handles backups, patching, and failover

### Why This Matters
Using RDS allows engineers to focus on application development rather than
database maintenance and infrastructure management.

---

## 3. First NoSQL Database - DynamoDB (Conceptual)

DynamoDB was reviewed to understand NoSQL database design.

### Key Concepts Learned
- Schema-flexible design (items do not need identical attributes)
- Partition key is required to uniquely identify items
- Designed for massive scale and low latency
- Ideal for real-time and high-traffic applications

### Typical Use Cases
- IoT platforms
- Gaming leaderboards
- Analytics workloads
- Real-time web and mobile applications

---

## 4. Hands-On SQL Practice – MySQL/MariaDB on EC2

This section involved **direct interaction with a database engine**
running on an EC2 instance.

---

### Step 1 – Connecting to the Database Engine

After connecting to the EC2 instance using **EC2 Instance Connect**,
I accessed the MariaDB/MySQL service using the root user.

This confirmed that the database service was running correctly
and ready to accept SQL commands.

---

### Step 2 – Viewing Existing Databases

I checked the databases already present on the system
to understand the initial environment.

This displayed system databases such as:
- information_schema
- mysql
- performance_schema

### Step 3 – Creating a New Database

I created a new database to store lab data.
CREATE DATABASE world;
USE world;
This step confirmed that I had permission to create and manage databases.

Step 4 – Creating Tables

I created a table named country with structured columns
to store geographical and demographic data.

This required defining:

- Data types
- Primary key
- Default values
- Nullable and non-nullable fields
**Screenshot:** Creating database tables
  
![MySQL create tables](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/mysql_create_tables.PNG?raw=true)

### Step 5 - Verifying Tables and Columns
After table creation, I verified the structure of the table
  SHOW TABLES;
  SHOW COLUMNS FROM world.country;
This confirmed that all fields were created correctly
with the expected data types and constraints.

### Step 6 - Creating Additional Tables

To simulate a realistic relational database scenario,
I created additional tables for learners and certifications.

Example structure:

| Table Name           | Purpose                                  | Key Columns                         | Notes |
|----------------------|------------------------------------------|--------------------------------------|-------|
| RESTART              | Stores learner information               | StudentID (PK), StudentName, City    | Primary table holding core learner data |
| CLOUD_PRACTITIONER   | Stores certification completion records  | StudentID, CertificationDate         | Linked to RESTART using StudentID |

### Table 7 – Sample Data Inserted into Tables

| StudentID | StudentName | City          | GraduationDate        | CertificationDate |
|-----------|-------------|---------------|-----------------------|-------------------|
| 1         | Olivia      | Limpopo       | 2025-06-30 10:00:00   | 2025-07-01 08:00:00 |
| 3         | Tebogo      | Pretoria      | 2025-04-15 11:00:00   | 2025-07-09 09:00:00 |
| 5         | Zanele      | Durban        | 2025-03-20 08:45:00   | 2025-07-15 10:30:00 |
| 7         | Neo         | Bloemfontein  | 2025-05-29 15:00:00   | 2025-07-20 11:15:00 |
| 9         | Karabo      | Soweto        | 2025-07-25 09:45:00   | 2025-07-25 14:00:00 |

### Step 8 - Querying Data Using INNER JOIN

To combine related data from different tables,
I used an INNER JOIN.

| Element                  | Description |
|--------------------------|-------------|
| JOIN Type                | INNER JOIN |
| Join Condition           | RESTART.StudentID = CLOUD_PRACTITIONER.StudentID |
| Data Returned            | Only records where StudentID exists in both tables |
| Columns Displayed        | StudentID, StudentName, CertificationDate |
| Purpose                  | Combine learner information with certification status |
| Real-World Use Case      | Linking users with completed certifications |

This returned only records that existed in both tables.

**Screenshot:** SELECT query with INNER JOIN

