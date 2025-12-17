# 3D E-Commerce Cloud Architecture

This project showcases a cloud architecture designed to support a
high-performance 3D e-commerce platform where users interact with
immersive 3D product models.

The architecture addresses the unique challenges of 3D commerce,
including large asset sizes, global delivery, scalability, security,
and cost control.

## What the Architecture Solves

3D product assets are significantly heavier than traditional images.
This solution was designed to ensure:

- Low-latency global content delivery
- High availability and fault tolerance
- Scalable backend compute capacity
- Strong security from edge to database
- Cost-efficient storage and optimisation

## Architecture Highlights

- **Route 53** for DNS routing and health checks  
- **AWS WAF and AWS Shield** for edge security and DDoS protection  
- **CloudFront + S3** for global delivery of large 3D assets  
- **Application Load Balancer** distributing traffic across EC2 instances  
- **Auto Scaling Group** for elastic compute capacity  
- **Amazon RDS (Multi-AZ)** for highly available relational data  
- **CloudWatch and Trusted Advisor** for monitoring and optimisation  

## Key Design Decisions

- EC2 instances were chosen over serverless services due to continuous
  and compute-intensive 3D processing requirements.
- A relational database was selected to support structured data and
  transactional consistency.
- Multi-AZ deployments were prioritised to ensure reliability, even
  with increased cost.

## Key Takeaways

- Performance must be designed in from the start for 3D workloads
- High availability always involves cost trade-offs
- Cloud architecture is about balancing user experience, reliability,
  and operational efficiency

## Summary

This project demonstrates a production-oriented cloud architecture
capable of delivering rich 3D e-commerce experiences at scale.
It reflects practical decision-making, real-world trade-offs, and
modern cloud engineering best practices.
