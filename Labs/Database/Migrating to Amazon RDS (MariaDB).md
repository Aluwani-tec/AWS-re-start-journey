# Migrating to Amazon RDS (MariaDB) - Café Application Lab

## Lab Overview
In this lab, I migrated the café web application from using a local MariaDB database hosted on an EC2 LAMP instance to using a fully managed Amazon RDS (MariaDB) database instance.

The process involved generating application data, creating the required RDS networking components, migrating the database using mysqldump, updating the application configuration via AWS Systems Manager Parameter Store, and validating the migration.

---

## Starting Architecture
- Café web application running on an EC2 LAMP instance in a public subnet
- Local MariaDB database hosted on the same EC2 instance
- CLI Host EC2 instance used for AWS CLI operations

---

## Final Architecture
- Café web application continues to run on EC2
- Database migrated to Amazon RDS (MariaDB)
- RDS deployed in private subnets across two Availability Zones
- Database access restricted using a dedicated security group allowing MySQL traffic only from the application security group

---

## Objectives
- Create an Amazon RDS MariaDB instance using the AWS CLI
- Migrate data from a local MariaDB database to Amazon RDS
- Reconfigure the application to use Amazon RDS
- Validate application functionality and database connectivity
- Review RDS monitoring metrics

---

## Task 1 - Generate Order Data on the Café Website
Orders were placed on the café website to generate data for migration verification.

### Evidence
Café menu used to place orders:
![Cafe Menu](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20cafe%20menu.PNG?raw=true)

Order History recorded before migration:
![Order History](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20order%20history.PNG?raw=true)

---

## Task 2 - Create Amazon RDS Components Using AWS CLI
AWS CLI was used from the CLI Host EC2 instance to create all required RDS infrastructure components.

### EC2 Resources Used
![EC2 Instances](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20ec2.PNG?raw=true)

### Connecting to the CLI Host
![EC2 Connect](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20connect.PNG?raw=true)

### Linux Terminal for AWS CLI Commands
![Linux Terminal](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20linux.PNG?raw=true)

### Database Security Group
A dedicated security group (CafeDatabaseSG) was created to allow inbound MySQL traffic (TCP 3306) only from the café application security group.

![Database Security Group](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Database/images/database%20security.PNG?raw=true)

---

## Task 3 - Migrate Local Database to Amazon RDS
The database migration was performed using standard MariaDB utilities.

### Migration Steps
1. Connect to the CafeInstance
2. Export the local database using mysqldump
3. Restore the database into Amazon RDS using the RDS endpoint
4. Verify migrated data using SQL queries

---

## Task 4 - Update Application Configuration
The café application database connection string was updated in AWS Systems Manager Parameter Store.

### Validation
- Website loaded successfully after configuration update
- Order History count matched pre-migration data
- Application continued to function correctly using Amazon RDS

---

## Task 5 - Monitor the Amazon RDS Instance
The RDS instance was monitored using built-in metrics available in the RDS console.

### Metrics Reviewed
- CPUUtilization
- DatabaseConnections
- FreeStorageSpace
- FreeableMemory
- ReadIOPS
- WriteIOPS

---

## Results and Outcomes
- Amazon RDS MariaDB instance successfully created in private subnets
- Local database migrated without data loss
- Application successfully reconfigured to use Amazon RDS
- Order data verified before and after migration
- Monitoring metrics available and functioning as expected

---

## Challenges Encountered
Some MariaDB engine versions referenced in the lab documentation were not available in the selected AWS region. The issue was resolved by selecting a supported MariaDB engine version available in the region.

---

## Skills Reinforced
- AWS CLI usage for RDS and VPC resource management
- Secure database networking using security groups
- Database migration using mysqldump and restore
- Application configuration using AWS Systems Manager Parameter Store
- Monitoring and validating RDS performance metrics

---
