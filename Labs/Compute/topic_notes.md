# Compute Module Lab Notes

## Scenario: Computing Solutions

The school wants to upgrade its **class scheduling system**, which is currently running on an Amazon EC2 instance.  
The system is experiencing performance limitations, so the goal is to **increase computing power and memory capacity**.

**Task Requirement:**  
Change the EC2 instance to a **larger instance type** and verify that the system continues running correctly.

---

## 1. Lab Objective

The objective of this lab was to:

- Review the existing EC2 instance hosting the scheduling system
- Confirm the current instance size and configuration
- Access the instance to validate metadata
- Inspect application logs before and after the change
- Compare available EC2 instance types
- Upgrade the instance to a larger type
- Verify that the upgrade was successful

---

## 2. Initial EC2 Instance Review (Baseline)

**Screenshot:**  
![EC2 Instance Overview](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/computing%20simulearn.PNG?raw=true)

### Steps performed

1. Logged into the **AWS Management Console**.
2. Set the **Region** to: US East (N. Virginia) us-east-1
3. 3. Opened the **EC2** service.
4. Clicked **Instances** from the left navigation menu.
5. Selected the instance named: AWS Computing Solutions

   
### Baseline configuration observed

- Instance state: **Running**
- Instance type: **t3.micro**
- Availability Zone: **us-east-1a**
- Private IP address: **10.10.0.10**
- Status checks: **Passed**

This screenshot represents the **starting point** before increasing compute and memory capacity.

---

## 3. Accessing Instance Metadata (Inside the Server)

**Screenshot:**  
![Instance Metadata](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/computing%20simulearn1.PNG?raw=true)

### Steps performed

1. With the instance selected, clicked: Connect → EC2 Instance Connect
2. 2. Used the default user (`ec2-user`) and opened the browser terminal.
3. Navigated to the application directory:

bash : cd sample_app
ls

4. The application displayed instance metadata.
Metadata confirmed
Instance Type: t3.micro
Instance ID: i-060c05b5b153b83b1
Availability Zone: us-east-1a
Private IP: 10.10.0.10
This confirmed that the scheduling system was running on a small instance size, which justified the need for an upgrade.

### 4. Reviewing Application Logs (Before Upgrade)
**Screenshot:**
 ![Instance Metadata](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/computing%20simulearn1.PNG?raw=true)

 ### Steps performed

From inside the instance, ran:
tail -f aws_compute_solutions.log


Observed live log output while the application was running.

### Observations

- The application was actively receiving HTTP requests.
- Log entries included:
- Instance metadata
- Request paths
- Response codes (e.g. 404 for unsupported paths)
- Some protocol warnings appeared (e.g. HTTP version not supported).

### Why this step mattered

This step ensured the application was healthy before resizing and provided a baseline for comparison after the upgrade.

   ### 5. Comparing EC2 Instance Types (Upgrade Decision)
   **Screenshot:**
   ![Instance Metadata](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/computing%20simulearn3.PNG?raw=true)

### Steps performed

In the EC2 console, opened: Instance types
Compared the following instance types:
- t3.large
- c5.large
- r5.large
  
### Comparison results
 | Instance Type | vCPUs | Memory | Use Case |
|--------------|-------|--------|----------|
| t3.large     | 2     | 8 GiB  | General-purpose workloads |
| c5.large     | 2     | 4 GiB  | Compute-intensive tasks |
| r5.large     | 2     | 16 GiB | Memory-intensive applications |

### Decision

Because the scheduling system required more memory and better performance, a larger general-purpose instance was selected for the upgrade.

### 6. Changing the Instance Type (Upgrade Execution)

**Screenshot:**
![Instance comparison table](https://github.com/Aluwani-tec/AWS-re-start-journey/blob/main/Labs/Compute/images/computing%20simulearn4.PNG?raw=true)

## Steps performed

1.Selected the AWS Computing Solutions instance.
2. Stopped the instance: Instance state → Stop instance
3. Modified the instance type: Actions → Instance settings → Modify instance type
4. Selected: m4.large
5. Saved the change.
6. Restarted the instance.
7. Waited for status checks to pass.

### 7. Verifying the Upgrade

1. Reconnected using EC2 Instance Connect.
2. Navigated back to the application folder: cd sample_app
                                             tail -f aws_compute_solutions.log


3. Confirmed that:
   - The instance was running successfully
   - Logs now reflected the new instance type
   - The application continued functioning without errors

This confirmed the upgrade was successful and the scheduling system now had greater compute and memory capacity.

### 8. Challenges Encountered

- Attempted to modify instance type while it was running (not allowed).
- Initial concern about log warnings that were actually normal traffic noise.
- Understanding which instance family best matched the workload.

All issues were resolved by following AWS best practices.

### 9. Key Learning Outcomes

- How to safely upgrade an EC2 instance for better performance.
- Why instances must be stopped before resizing.
- How to validate changes using logs and metadata.
- How to choose instance types based on workload needs.
- How compute and memory directly impact application performance.

### 10. Conclusion

The task of upgrading the EC2 instance was completed successfully.
The school’s scheduling system now runs on a larger instance type, providing improved performance and memory capacity while maintaining application stability.

This lab demonstrated real-world EC2 upgrade procedures aligned with AWS operational standards.
