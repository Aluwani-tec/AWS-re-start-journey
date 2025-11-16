# Compute Module — Detailed Notes (AWS re/Start)

These notes summarize the four CloudQuest assignments related to the Compute module.

---

## 1️⃣ Cloud Computing Essentials
**Image:** Cloud Computing Essentials

### What this assignment teaches
- How to enable static website hosting on Amazon S3
- How to configure bucket policy for public access
- Basic understanding of S3 as a storage & hosting service

### Key Points
- S3 can host static websites (HTML/CSS/JS)
- Enable "Static Website Hosting" inside bucket properties
- Public access requires a bucket policy that allows `s3:GetObject`
- You can rename index.html depending on requirements (e.g., waves.html)

### Why it matters
Static website hosting on S3 is cost-effective, scalable, and serverless. 
It removes the need for EC2 servers for simple websites.

---

## 2️⃣ Cloud Economics
**Image:** Cloud Economics

### What this assignment teaches
- How traditional IT differs from cloud elasticity
- How demand affects resource usage
- How to estimate EC2 pricing

### Key Points
- Traditional IT = upfront cost + unused capacity
- Cloud = pay-as-you-go + resources match demand automatically
- Auto Scaling adjusts capacity based on customer demand
- Instance types (e.g., t2.micro, t3.medium) influence cost
- You can generate pricing estimates using AWS Cost Calculator

### Why it matters
Understanding cloud pricing helps optimize cost and avoid over-provisioning.

---

## 3️⃣ Cloud First Steps
**Image:** Cloud First Steps

### What this assignment teaches
- How to launch your first EC2 instance
- How to deploy instances across multiple Availability Zones
- How to automate tasks using a user-data script

### Key Points
- EC2 = virtual server running in the cloud
- Regions contain multiple Availability Zones for high availability
- Launching instances in different AZs improves reliability
- User-data scripts run at the first boot (install packages, write files, etc.)

### Why it matters
This assignment builds foundational EC2 knowledge used across all cloud workloads.

---

## 4️⃣ Computing Solutions
**Image:** Computing Solutions

### What this assignment teaches
- How to select the correct EC2 instance type
- How to scale up for better performance
- How to connect using EC2 Instance Connect
- How to view EC2 instance metadata (instance ID, region, public IP)

### Key Points
- Scaling up means choosing a larger instance (e.g., m4.large)
- Instance metadata shows system information through `http://169.254.169.254`
- EC2 Instance Connect is a browser-based SSH alternative
- AWS Systems Manager integrates with EC2 for management tasks

### Why it matters
Choosing the correct compute resources improves performance and user experience.

---

## ✔️ Summary of All Assignments
- **Cloud Computing Essentials** → S3 website hosting basics  
- **Cloud Economics** → cloud pricing + cost optimization  
- **Cloud First Steps** → EC2 basics + user-data + AZs  
- **Computing Solutions** → instance types + scaling + metadata  

---

