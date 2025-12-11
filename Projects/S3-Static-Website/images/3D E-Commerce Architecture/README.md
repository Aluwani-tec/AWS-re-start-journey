# Interactive 3D Commerce – Cloud Architecture (Group Work)

This folder documents our group’s cloud architecture design for a modern 3D-commerce platform.  
The goal was to build an online shopping environment capable of delivering large, interactive 3D models with high performance, strong security, and global reach.

This was a group activity completed by:
Thato, Ndzalo, Aluwani, and Xoliswa.

---

## 1. Architecture Overview

The platform supports a new shopping experience where users inspect 3D product files.  
These files are significantly larger than normal images, so the system needed to deliver:

- Low-latency access
- High availability
- Secure public-facing endpoints
- Automatic scaling when traffic spikes
- Efficient global delivery for heavy assets

The architecture uses key AWS services taught in the Praesignis Cloud Practitioner Programme and reflects real industry design patterns.

---

## 2. Architecture Diagram

The architecture below illustrates how user requests flow through Route 53, CloudFront, WAF, the Application Load Balancer, EC2 Auto Scaling Group, and the Multi-AZ RDS backend.  
It also shows how static 3D assets such as textures and models are delivered from S3 at high speed through CloudFront edge locations.

![Architecture Diagram](./images/architecture.png)
