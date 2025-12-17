# 3D E-Commerce Cloud Architecture


## Project Type
Cloud Architecture Design (AWS)

![3D E-Commerce Architecture](https://raw.githubusercontent.com/Aluwani-tec/AWS-re-start-journey/main/Projects/3D%20E-Commerce%20Architecture/images/3D1.PNG)


## Team Members
- Thato  
- Ndzalo  
- Aluwani  
- Xoliswa  

---

## Project Overview
The Praesignis 3D E-Commerce Platform is designed to support a new form of online shopping where customers can view and interact with high-quality 3D product models.

These 3D assets are significantly larger and more complex than traditional images, requiring a cloud-based architecture that delivers:
- Global performance
- Low latency
- High availability
- Strong security
- Scalability during traffic spikes

The architecture reflects real-world industry practices and applies core concepts from the AWS Cloud Practitioner curriculum. To ensure reliability and fault tolerance, the solution is deployed across multiple AWS Availability Zones.

---

## Architecture Summary
User traffic begins at Amazon Route 53, which manages DNS routing and performs health checks to ensure users are always directed to healthy endpoints.

Traffic is then protected by AWS Web Application Firewall (WAF) and AWS Shield, providing defense against common web attacks and denial-of-service events.

Static content such as:
- 3D product models
- Textures
- Images

is delivered via Amazon CloudFront. CloudFront caches content at edge locations worldwide, reducing latency and improving user experience. The original assets are stored securely in Amazon S3.

Dynamic requests that require backend processing are routed through an Application Load Balancer (ALB) to Amazon EC2 instances distributed across two Availability Zones. These EC2 instances handle:
- Product data retrieval
- User session management
- Order processing

The compute layer is managed using an Auto Scaling Group to dynamically adjust capacity based on demand.

Relational data is stored in Amazon RDS configured with Multi-AZ deployment. This enables automatic failover if the primary database instance becomes unavailable.

System monitoring and operational visibility are provided by Amazon CloudWatch, while AWS Trusted Advisor offers recommendations related to:
- Cost optimization
- Security
- Performance
- Fault tolerance

---

## AWS Services Used
- Amazon Route 53
- AWS WAF
- AWS Shield
- Amazon CloudFront
- Amazon S3
- Application Load Balancer
- Amazon EC2
- EC2 Auto Scaling
- Amazon RDS (Multi-AZ)
- Amazon CloudWatch
- AWS Trusted Advisor
- AWS IAM
- VPC, subnets, and security groups

---

## How the Architecture Meets Requirements

### High Availability
- Multi-AZ deployment for Amazon RDS
- EC2 instances distributed across multiple Availability Zones
- Route 53 health checks and traffic routing

### Scalability
- EC2 Auto Scaling adjusts compute capacity automatically
- Amazon S3 supports virtually unlimited storage
- CloudFront handles global content delivery at scale

### Performance
- CloudFront caching reduces latency for static assets
- Application Load Balancer distributes traffic evenly
- Optimized backend compute layer for 3D processing

### Security
- AWS WAF and Shield provide perimeter protection
- IAM enforces least-privilege access control
- Databases deployed in private subnets
- Security groups restrict network access

### Cost Efficiency
- Auto Scaling prevents over-provisioning
- S3 provides cost-effective object storage
- Trusted Advisor offers cost optimization insights

---

## Design Trade-Offs and Challenges
- Amazon EC2 was chosen over serverless services due to the need for consistent compute power for heavy 3D processing workloads.
- Amazon RDS was selected instead of DynamoDB because the application requires structured relational data and strong transactional consistency.
- Multi-AZ deployments increase cost but were intentionally chosen to ensure reliability and fault tolerance.
- Performance is dependent on optimized 3D assets to prevent excessive load times for users.

---

## Team Contributions
- Xoliswa: Designed the overall architecture layout and Availability Zone distribution
- Thato: Documented AWS services and architectural decisions
- Aluwani: Contributed to architecture structure and security design
- Ndzalo: Analyzed alternative architectures, trade-offs, and challenges

---

## Conclusion
The Praesignis 3D E-Commerce Cloud Architecture Project demonstrates a complete, production-style cloud solution capable of delivering interactive 3D shopping experiences at scale.

The design is resilient, secure, scalable, and aligned with modern AWS best practices and real-world industry standards.

