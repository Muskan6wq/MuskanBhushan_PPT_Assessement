
Objective:
Enable internet access for private EC2 instances using NAT Gateway.

Description:
Public and private subnets were created inside a VPC. A NAT Gateway was deployed in the public subnet and route tables were configured so private instances could access the internet.
TASK 10 – VPC 3-Tier Architecture (with Tunneling and NAT Gateway)

1. I created a custom VPC.

2. I created subnets:
   - One Public Subnet
   - Two Private Subnets

3. I attached an Internet Gateway (IGW) to the VPC.

4. I created a Public Route Table:
   - Added route 0.0.0.0/0 → Internet Gateway
   - Associated it with the Public Subnet.

5. I launched one EC2 instance in the Public Subnet.
   - Public IP enabled
   - This instance is used as Bastion Host.

6. I launched EC2 instances in Private Subnets.
   - No public IP assigned
   - These instances are not directly accessible from internet.

7. I configured Security Groups:
   - Public EC2 allowed SSH (22) from my IP.
   - Private EC2 allowed SSH (22) only from Public EC2 security group.

8. I first connected from my Mac to Public EC2 using SSH.

9. From Public EC2, I connected to Private EC2 using private IP
   (SSH tunneling / jump host method).

10. After tunneling was working, I created a NAT Gateway.
    - NAT Gateway created in Public Subnet
    - Elastic IP attached to NAT Gateway.

11. I created a Private Route Table.
    - Added route 0.0.0.0/0 → NAT Gateway
    - Associated this route table with both Private Subnets.

12. This allows Private EC2 instances to access internet
    for updates and downloads, but still blocks inbound traffic.

Architecture Flow:
Mac → Public EC2 (Bastion Host) → Private EC2
Private EC2 → NAT Gateway → Internet

Result:
I successfully implemented a secure 3-tier VPC architecture.
Private EC2 instances are accessed using SSH tunneling and
use NAT Gateway for outbound internet access only.
Result:
Private EC2 instances accessed the internet securely without being publicly exposed.

