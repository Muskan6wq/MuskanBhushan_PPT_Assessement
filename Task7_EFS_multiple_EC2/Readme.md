Objective:
Establish secure connection between EC2 instances and transfer files.

Description:
SSH was used to securely connect to EC2 instances. SCP was used to transfer files between local machine and EC2.
TASK 7 – Create EFS and Connect to Multiple Ubuntu Instances

1. I created 2 Ubuntu EC2 instances in the same VPC.

2. I went to the EFS service and created a new file system.
   - Selected the same VPC
   - Mount targets were created automatically
   - Attached security group allowing NFS access

3. In the EFS security group, I added an inbound rule:
   - Type: NFS
   - Port: 2049
   - Source: EC2 security group

4. I connected to the first Ubuntu EC2 instance using SSH.

5. Installed NFS client:
   sudo apt update
   sudo apt install nfs-common -y

6. Created mount directory:
   sudo mkdir -p /Mymount

7. Mounted the EFS:
   sudo mount -t nfs4 fs-xxxx.efs.eu-north-1.amazonaws.com:/ /Mymount

8. Verified mount using:
   df -h

9. Created a test file:
   cd /Mymount
   sudo touch a.txt

10. Then I connected to the second Ubuntu EC2 instance.

11. Installed NFS client again:
    sudo apt update
    sudo apt install nfs-common -y

12. Created mount directory:
    sudo mkdir -p /Mymount

13. Mounted the same EFS on second instance:
    sudo mount -t nfs4 fs-xxxx.efs.eu-north-1.amazonaws.com:/ /Mymount

14. Verified shared storage:
    ls /Mymount

15. I could see the file a.txt in the second instance.
    This confirms EFS is shared across multiple EC2 instances.

Result:
EFS was successfully mounted on multiple Ubuntu EC2 instances and shared file access was verified.

Result:
Secure access and file transfer were successfully performed.

