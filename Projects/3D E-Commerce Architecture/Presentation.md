# 3D E-Commerce Cloud Architecture

This repository presents a cloud architecture designed to support a
3D e-commerce platform where users can view and interact with
high-quality 3D product models.

Unlike traditional image-based e-commerce systems, 3D platforms handle
much larger and more complex files. This architecture was designed to
deliver those assets efficiently while maintaining performance,
availability, security, and cost control at scale.

## Project Context

The platform supports a new style of online shopping that relies on
interactive 3D assets rather than static images. Because these assets
are significantly heavier, the system needed to provide:

- Global performance with low latency
- High availability and fault tolerance
- Scalable compute resources
- Strong security controls
- Cost-efficient storage and delivery

To meet these requirements, the solution follows cloud architecture
best practices and is deployed across multiple Availability Zones.

## Architecture Overview

User traffic begins at Amazon Route 53, which manages DNS routing and
performs health checks to ensure traffic is directed only to healthy
endpoints.

Requests are filtered through AWS WAF and protected by AWS Shield to
defend against common web attacks and denial-of-service attempts.

Static content such as 3D models, textures, and images is delivered
through Amazon CloudFront, with Amazon S3 acting as the origin storage.
This allows large assets to be cached at edge locations worldwide,
significantly improving load times for users.

Requests that require backend processing are forwarded by an
Application Load Balancer to EC2 instances deployed across two
Availability Zones. These instances handle tasks such as retrieving
product data, managing user sessions, and processing transactions.
Compute capacity is managed using an Auto Scaling Group.

Relational data is stored in Amazon RDS using a Multi-AZ configuration,
allowing automatic failover if the primary database becomes
unavailable. Monitoring and optimisation are supported through Amazon
CloudWatch and Trusted Advisor.

## Meeting the Core Requirements

### Availability
High availability is achieved through Multi-AZ database deployment,
EC2 Auto Scaling, load balancing, and Route 53 health checks.

### Scalability
Scalability is supported through elastic compute resources, object
storage in Amazon S3, and global content delivery via CloudFront.

### Performance
Performance is improved using CloudFront edge caching and balanced
backend traffic distribution.

### Security
Security is enforced through layered controls including AWS WAF,
AWS Shield, IAM policies, private subnets, and security groups.

### Cost Optimisation
Cost efficiency is supported through Auto Scaling, S3 storage tiers,
and continuous recommendations from Trusted Advisor.

## Design Decisions and Challenges

EC2 instances were selected instead of serverless services due to the
continuous and compute-intensive nature of 3D asset processing.

Amazon RDS was chosen over NoSQL alternatives to support structured,
relational data and strong transactional consistency.

Multi-AZ deployments increase infrastructure cost but provide higher
resilience and reliability, which is critical for a platform delivering
rich interactive content.

An additional challenge was ensuring that 3D assets were optimised
enough to maintain fast user experiences without compromising visual
quality.

## Key Outcomes and Lessons Learned

### Outcomes
- A resilient and scalable architecture suitable for 3D workloads
- Clear separation between static content delivery and backend processing
- Strong security integrated across all layers of the system

### Lessons Learned
- Performance considerations must be built into the design from the start
- High availability always introduces cost trade-offs
- Cloud architecture requires balancing technical, business, and user needs

## Conclusion

This project demonstrates a complete cloud-based architecture capable
of delivering interactive 3D content to users around the world.

The design is scalable, secure, resilient, and aligned with modern
industry practices, reflecting real-world considerations involved in
building high-performance cloud platforms.

