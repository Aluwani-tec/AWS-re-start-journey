# 3D Architecture Showcase

This folder documents a cloud architecture solution designed during the AWS re/Start Programme as part of a group-based practical assignment facilitated by Praesignis.

The architecture demonstrates how AWS services can be combined to support a modern 3D e-commerce platform that delivers high-quality interactive 3D product models to users globally.

---

## Project Overview

The Praesignis 3D E-Commerce platform supports a new form of online shopping where customers interact with large and complex 3D product assets.


![3D E-Commerce Architecture](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Projects/3D%20E-Commerce%20Architecture/3D1.PNG?raw=true)

Because 3D models are significantly heavier than traditional images, the system required:
- High availability  
- Low latency global access  
- Strong security controls  
- Scalable compute capacity  
- Cost-efficient storage and delivery  

The solution was designed using AWS best practices and is deployed across multiple Availability Zones to ensure reliability and fault tolerance.

---

## Architecture Summary

User traffic begins at **Amazon Route 53**, which handles DNS routing and health checks to ensure users are directed only to healthy endpoints.

Traffic then passes through **AWS WAF** and **AWS Shield**, providing protection against common web exploits and distributed denial-of-service (DDoS) attacks.

Static content such as 3D models, textures, and images is delivered using **Amazon CloudFront**, with **Amazon S3** acting as the origin storage. This allows global caching of large assets and significantly improves performance for end users.

Requests that require backend processing are routed through an **Application Load Balancer (ALB)** to **EC2 instances** deployed across two Availability Zones. These instances are managed using an **Auto Scaling Group** to adjust capacity based on demand.

Relational data is stored in **Amazon RDS (Multi-AZ)**, enabling automatic failover and high availability. Monitoring and optimisation are supported through **Amazon CloudWatch** and **AWS Trusted Advisor**.

---

## Key Design Principles

- **High Availability**  
  Achieved through Multi-AZ RDS deployment, EC2 Auto Scaling, and Route 53 health checks.

- **Scalability**  
  Supported by Amazon S3, CloudFront global distribution, and elastic EC2 capacity.

- **Performance**  
  Improved using CloudFront edge caching and load-balanced backend traffic.

- **Security**  
  Enforced through AWS WAF, AWS Shield, IAM, private subnets, and security groups.

- **Cost Efficiency**  
  Enabled by Auto Scaling, S3 storage tiers, and Trusted Advisor recommendations.

---

## Design Decisions and Trade-Offs

- EC2 instances were selected instead of serverless services due to the heavy and continuous compute requirements of 3D content processing.
- Amazon RDS was chosen over DynamoDB to support structured relational data and transactional consistency.
- Multi-AZ deployment increases cost but provides enterprise-grade reliability and resilience.

---

## Team Contributions

This project was completed as group work with the following contributions:

- Xoliswa – Architecture layout and Availability Zone distribution  
- Thato – Documentation of service roles and justifications  
- Aluwani – Architecture structure and security design  
- Ndzalo – Analysis of trade-offs, alternatives, and challenges  

---

## Conclusion

This architecture represents a realistic AWS-based solution for delivering high-quality 3D e-commerce experiences. The design aligns with modern cloud engineering practices and demonstrates practical understanding of scalability, security, performance, and availability within AWS.

