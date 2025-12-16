# EC2 Web Server Lab
# Scope: Launch | Monitor | Secure

--------------------------------------------------
LAB OVERVIEW
--------------------------------------------------
This lab demonstrates the core operational steps required
to deploy and protect an Amazon EC2 web server:

- Launch an EC2 instance using User Data
- Monitor instance health and visibility
- Secure inbound access using security groups

--------------------------------------------------
SERVICES USED
--------------------------------------------------
- Amazon EC2
- Amazon VPC (Lab VPC)
- Security Groups
- Amazon CloudWatch (Basic Monitoring)

--------------------------------------------------
1. LAUNCH EC2 INSTANCE
--------------------------------------------------
Objective:
Launch an EC2 instance configured as a web server with
termination protection enabled.

Configuration:
- Instance Name        : Web Server
- AMI                  : Amazon Linux 2023
- Instance Type        : t3.micro
- VPC                  : Lab VPC
- Key Pair             : None (not required)
- Termination Protection: Enabled
- SSH Access           : Removed
- Storage              : Default (8 GiB)

User Data Script:
--------------------------------------------------
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
--------------------------------------------------

Outcome:
- EC2 instance launched successfully
- Apache installed automatically
- Instance reached Running state

--------------------------------------------------
2. MONITOR EC2 INSTANCE
--------------------------------------------------
Objective:
Verify instance health and operational status.

Monitoring Actions:
- Checked instance state
- Verified status checks
- Reviewed CloudWatch metrics
- Captured instance screenshot

Health Validation:
- Instance State        : Running
- System Reachability   : Passed
- Instance Reachability : Passed (2/2 checks)

Outcome:
- Instance healthy and operational
- No system or hardware errors detected

--------------------------------------------------
3. SECURE THE WEB SERVER
--------------------------------------------------
Objective:
Control inbound traffic using security groups.

Initial Test:
- Accessed Public IPv4 address
- Result: Connection failed
- Reason: Port 80 not allowed inbound

Security Group Update:
Inbound Rule Added:
- Type   : HTTP
- Port   : 80
- Source : Anywhere (IPv4)

Final Test:
- Refreshed browser using Public IPv4
- Result: Web page displayed successfully

Web Page Output:
--------------------------------------------------
Hello From Your Web Server!
--------------------------------------------------

--------------------------------------------------
CHALLENGES
--------------------------------------------------
- Web server unreachable before allowing HTTP traffic
- Required understanding of security group behavior
- Waited for status checks to pass before testing

--------------------------------------------------
WINS
--------------------------------------------------
- Automated web server deployment using User Data
- Correct use of security groups as a firewall
- Successful monitoring and validation

--------------------------------------------------
LESSONS LEARNED
--------------------------------------------------
- Running instances are not accessible without correct security rules
- Security groups explicitly control inbound traffic
- Monitoring confirms instance readiness before troubleshooting
- User Data enables consistent, repeatable deployments
