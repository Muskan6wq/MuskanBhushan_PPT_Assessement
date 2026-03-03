TASK 2 — Highly Available VM Infrastructure (Azure)

Objective:
Deploy a highly available virtual machine infrastructure using Availability Set, Availability Zones, Azure Load Balancer, and Azure Monitor.

Overview:
In this task, multiple virtual machines were deployed across fault domains and availability zones to ensure high availability. A public load balancer was configured to distribute traffic between VMs, and Azure Monitor was used to create alerts and monitor health.

Step 1: Resource Group and Virtual Network
Created a Resource Group in a selected Azure region.
Created a Virtual Network with appropriate address space.
Configured required subnets for VM deployment.

Step 2: Deploy VMs in Availability Set
Created an Availability Set.
Deployed 2 virtual machines inside the Availability Set.
This ensures VMs are placed across different fault domains and update domains, protecting against hardware and maintenance failures.

Step 3: Deploy VMs in Availability Zone
Deployed another 2 VMs in different Availability Zones within the same region.
This protects against data center-level failures.

Step 4: Configure Public Load Balancer
Created a Public Azure Load Balancer.
Configured:
- Frontend Public IP
- Backend Pool
- Health Probe (Port 80)
- Load Balancing Rule

Added all VMs to the Backend Pool.
Load Balancer distributes incoming traffic across available VMs.

Step 5: Install Web Server
Installed Apache (or web server) on all VMs.
Modified index pages to differentiate VMs for testing.
Verified traffic was distributed when accessing the Load Balancer Public IP.

Step 6: Enable Azure Monitor
Configured Azure Monitor for VM metrics.
Created an Alert Rule based on CPU utilization threshold.
Configured action group for notifications.

Step 7: Configure Storage and Diagnostics
Created a Storage Account.
Enabled diagnostic logs for monitoring and troubleshooting.

Testing and Validation:
Accessed Load Balancer public IP.
Verified traffic switching between VMs.
Stopped one VM to simulate failure.
Confirmed Load Balancer routed traffic to remaining healthy VMs.

Architecture Flow:

Internet
→ Public Load Balancer
→ Backend Pool (Multiple VMs)
→ Availability Set and Availability Zones
→ Azure Monitor for alerts

Concepts Demonstrated:
- High Availability design
- Fault tolerance
- Availability Set vs Availability Zone
- Load balancing configuration
- Health probes and backend pools
- Monitoring and alerting
- Resilient cloud architecture

Conclusion:
Task 2 successfully implemented a highly available VM architecture in Azure using redundancy, load balancing, and monitoring to ensure continuous application availability even during failures.
