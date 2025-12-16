# EC2 Web Server Lab


### LAB OVERVIEW

This lab demonstrates the core operational steps required
to deploy and secure an Amazon EC2 web server:

- Launch an EC2 instance using User Data
- Monitor instance health and visibility
- Secure inbound access using security groups


### SERVICES USED

- Amazon EC2
- Amazon VPC (Lab VPC)
- Security Groups
- Amazon CloudWatch (Basic Monitoring)


### 1. LAUNCH EC2 INSTANCE

Objective:
Launch an EC2 instance configured as a web server with
termination protection enabled.

Configuration:
- Instance Name         : Web Server
- AMI                   : Amazon Linux 2023
- Instance Type         : t3.micro
- VPC                   : Lab VPC
- Key Pair              : None
- Termination Protection: Enabled
- SSH Access            : Removed
- Storage               : Default (8 GiB)

Launch Confirmation:
![EC2 Instant Launch](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/Compute%20EC2%20Instant%20Launch.PNG?raw=true)

Instance Running State:
![EC2 Running](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/Compute%20EC2%20view%20instances%20and%20running.PNG?raw=true)

EC2 Dashboard View:
![EC2 Dashboard](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/Compute%20EC2.PNG?raw=true)

Outcome:
- EC2 instance launched successfully
- Apache installed automatically
- Instance reached Running state

### 2. MONITOR EC2 INSTANCE
   
Objective:
Verify instance health and operational visibility.

Monitoring Actions:
- Checked instance state
- Verified status checks
- Reviewed CloudWatch metrics
- Captured instance screenshot

Instance Screenshot:
![EC2 Instance Screenshot](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/EC2%20Monitor%20and%20trouble%20shoot%20screenshot.jpg?raw=true)

Health Validation:
- Instance State        : Running
- System Reachability   : Passed
- Instance Reachability : Passed (2/2 checks)

Outcome:
- Instance healthy and operational
- No system or hardware errors detected

### 3. SECURE THE WEB SERVER

Objective:
Control inbound traffic using security groups.

Initial Access Test:
- Accessed Public IPv4 address
- Result: Connection failed
- Reason: HTTP (port 80) not allowed inbound

Initial Failure Evidence:
![Web Not Opening](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/EC2%20web%20not%20opening.PNG?raw=true)

Security Group Update:
Inbound Rule Added:
- Type   : HTTP
- Port   : 80
- Source : Anywhere (IPv4)

Inbound Rule Evidence:
![Inbound Rules](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/EC2%20Inbound%20Rules%20from%20security%20groups.PNG?raw=true)

Final Access Test:
- Refreshed browser using Public IPv4
- Result: Web page loaded successfully

Success Evidence:
![Web Port 80 Open](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/EC2%20Web%20port%2080%20open.PNG?raw=true)


### CHALLENGES

- Web server unreachable before allowing HTTP traffic
- Required understanding of security group behavior
- Waited for status checks before testing access


### WINS

- Automated web server deployment using User Data
- Correct application of security groups as a firewall
- Successful monitoring and validation

### LESSONS LEARNED

- EC2 instances require explicit inbound rules to be accessible
- Security groups are critical for network access control
- Monitoring confirms readiness before troubleshooting
- User Data enables repeatable and consistent deployments
