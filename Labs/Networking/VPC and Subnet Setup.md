# Amazon VPC Fundamentals

## Lab Overview
This lab focuses on building foundational knowledge of Amazon Virtual Private Cloud (VPC). The objective is to understand how AWS networking components are created, configured, and connected to form a secure and isolated virtual network environment. The lab emphasizes correct VPC design practices that support scalability, security, and future expansion.

---

## Step 1: Creating a Custom VPC
A new VPC was created to establish a logically isolated network within AWS. Instead of using the default VPC, a custom IPv4 CIDR block was defined to allow full control over IP addressing and subnet allocation.

Key configuration choices:
- IPv4 CIDR block set to `10.0.0.0/16` to provide a large private address space
- No IPv6 CIDR block assigned
- Default tenancy selected

This step establishes the network boundary that all future AWS resources will operate within.

![Create VPC](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Networking/images/create%20VPC.PNG?raw=true)

---

## Step 2: Verifying VPC Configuration
After creation, the VPC configuration was reviewed to confirm that it was successfully provisioned with the correct CIDR block and naming. The VPC was named **Lab VPC** to clearly identify it within the AWS account.

This verification step ensures the VPC is non-default and properly configured for custom networking.

![Lab VPC Details](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Networking/images/lab%20VPC.PNG?raw=true)

---

## Step 3: Enabling DNS Resolution and DNS Hostnames
DNS resolution and DNS hostnames were enabled at the VPC level. This configuration allows EC2 instances launched in the VPC to:
- Resolve domain names using AWS-provided DNS
- Automatically receive DNS hostnames when assigned public IP addresses

This step is critical for enabling communication with AWS services and external endpoints.

![DNS VPC Settings](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Networking/images/DNS%20VPC.PNG?raw=true)

---

## Step 4: Creating a Public Subnet
A public subnet was created within the Lab VPC to host resources that require internet connectivity.

Subnet configuration:
- Subnet name: **Public Subnet**
- Availability Zone: First available AZ in the region
- IPv4 CIDR block: `10.0.0.0/24`

This subnet represents a smaller, controlled portion of the VPC address space designed for public-facing resources such as bastion hosts or web servers.

![Subnet VPC](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Networking/images/Subnet%20VPC.PNG?raw=true)

---

## Step 5: Enabling Auto-Assign Public IPv4 Addresses
The public subnet was configured to automatically assign public IPv4 addresses to instances launched within it. This ensures that EC2 instances placed in this subnet can be reached from the internet once routing is configured.

This step distinguishes the subnet as *public-ready* and prepares it for internet-facing workloads.

![Subnet Settings VPC](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Networking/images/Subnet%20settings%20VPC.PNG?raw=true)

---

## Architecture Summary
- Custom VPC with CIDR block `10.0.0.0/16`
- DNS resolution and DNS hostnames enabled
- Public subnet created using `10.0.0.0/24`
- Public subnet configured for automatic public IP assignment

This foundational setup forms the basis for more advanced networking components such as internet gateways, NAT gateways, route tables, and private subnets.

---

## Key AWS Concepts Reinforced
- Custom VPC design
- CIDR-based IP planning
- Subnet segmentation
- DNS functionality within AWS
- Public subnet configuration principles

---

## Outcome
The lab successfully demonstrates the initial stages of AWS network architecture design. A custom VPC and public subnet were created and configured according to AWS best practices, providing a solid foundation for deploying and securing cloud resources.

