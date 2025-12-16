# Lab: Launch, Monitor, and Secure an Amazon EC2 Web Server

## Lab Scope
- Launch an EC2 instance
- Monitor instance health and status
- Secure the web server using security groups

---

## Services Used
- Amazon EC2
- Amazon VPC (Lab VPC)
- Security Groups
- Amazon CloudWatch

---

## Task 1: Launch an EC2 Web Server

### Objective
Launch an Amazon EC2 instance and deploy a simple Apache web server using User Data.

### Steps
1. Open AWS Management Console
2. Navigate to EC2 → Launch instance
3. Configure instance:
   - Name: Web Server
   - AMI: Amazon Linux 2023
   - Instance type: t3.micro
   - Key pair: Proceed without a key pair
4. Network settings:
   - VPC: Lab VPC
   - Security group name: Web Server security group
   - Description: Security group for my web server
   - Remove default SSH inbound rule
5. Advanced details:
   - Termination protection: Enable
   - User Data:

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
