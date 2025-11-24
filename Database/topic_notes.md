# Database Detailed Notes 

This file summarizes both the RDS (relational database) and DynamoDB (NoSQL) assignments, as well as hands-on SQL practice done in the EC2 environment.

---

# Databases in Practice (Amazon RDS)
**Image:** Databases in Practice

### What this assignment teaches
- How to launch a managed relational database using Amazon RDS  
- How Multi-AZ deployment works  
- How read replicas improve performance  
- How RDS handles backups and failover  

### Key Points
- **Multi-AZ** = high availability (primary DB + standby)  
- **Read replica** = improves performance for read-heavy apps  
- RDS automates:
  - Backups  
  - Patching  
  - Monitoring  
  - Failover  
- You can launch RDS using engines like MySQL, MariaDB, PostgreSQL, etc.

### Why it matters
RDS removes the heavy admin work (backups, failover, patching), allowing engineers to focus on application logic.

---

# First NoSQL Database (DynamoDB)
**Image:** First NoSQL Database

### What this assignment teaches
- How to create a NoSQL table in DynamoDB  
- How to add items (records) with flexible schema  
- How to query DynamoDB tables  
- How to work with partition keys  

### Key Points
- **DynamoDB is schema-flexible** → items do not require the same attributes  
- **Partition key** = required primary identifier  
- Designed for massive scale  
- Ideal for:
  - IoT
  - Analytics
  - Gaming
  - Real-time apps

### Why it matters
NoSQL databases are extremely fast, scalable, and perfect for applications with large and unstructured data.

---

# Hands-On SQL Practice (MySQL on EC2)
**Images:** Terminal screenshots

### What this assignment teaches
- How to connect to a MySQL database from an EC2 instance  
- How to create databases and tables  
- How to insert data  
- How to run SELECT queries  
- How to use INNER JOIN to combine data  

### Commands Used

#### Create the database
```sql
CREATE DATABASE restart_lab;
USE restart_lab;
```

#### Create the RESTART table
```sql
CREATE TABLE RESTART (
  StudentID INT PRIMARY KEY,
  StudentName VARCHAR(100),
  RestartCity VARCHAR(100),
  GraduationDate DATETIME
);
```

#### Insert multiple records
```sql
INSERT INTO RESTART VALUES
(1, 'Olivia', 'Limpopo', '2025-06-30 10:00:00'),
(2, 'Aisha', 'Johannesburg', '2025-05-29 09:30:00'),
(3, 'Tebogo', 'Pretoria', '2025-04-15 11:00:00'),
(4, 'Sipho', 'Cape Town', '2025-07-01 13:00:00'),
(5, 'Zanele', 'Durban', '2025-03-20 08:45:00'),
(6, 'Musa', 'Polokwane', '2025-08-22 14:00:00'),
(7, 'Neo', 'Bloemfontein', '2025-05-29 15:00:00'),
(8, 'Lerato', 'Tzaneen', '2025-05-15 10:30:00'),
(9, 'Karabo', 'Soweto', '2025-07-25 09:45:00'),
(10, 'Kabelo', 'Mokopane', '2025-08-05 16:00:00');
```

#### Query the table
```sql
SELECT * FROM RESTART;
```

---

# Creating a second table: CLOUD_PRACTITIONER
```sql
CREATE TABLE CLOUD_PRACTITIONER (
  StudentID INT,
  CertificationDate DATETIME
);
```

### Insert records
```sql
INSERT INTO CLOUD_PRACTITIONER VALUES
(1, '2025-07-01 08:00:00'),
(3, '2025-07-09 09:00:00'),
(5, '2025-07-15 10:30:00'),
(7, '2025-07-20 11:15:00'),
(9, '2025-07-25 14:00:00');
```

### Query the table
```sql
SELECT * FROM CLOUD_PRACTITIONER;
```

---

# Using INNER JOIN
Combine the data from both tables:

```sql
SELECT
  RESTART.StudentID,
  RESTART.StudentName,
  CLOUD_PRACTITIONER.CertificationDate
FROM RESTART
INNER JOIN CLOUD_PRACTITIONER
  ON RESTART.StudentID = CLOUD_PRACTITIONER.StudentID;
```

### What this teaches
- INNER JOIN returns only matching data  
- Useful when:
  - Combining user info + certifications  
  - Merging orders + customers  
  - Linking products + categories  

---

# Summary of Database Module
- **RDS Assignment:** Multi-AZ, read replicas, backups  
- **DynamoDB Assignment:** NoSQL, flexible schema, fast scaling  
- **SQL Practice:** Creating tables, inserting data, JOIN operations  
- You completed both the cloud architecture AND hands-on database tasks  

---

