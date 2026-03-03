TASK 2 – Disk Partitioning (Linux – MBR)


Objective:
Understand how to create, attach, partition, format, and mount an Amazon EBS volume to an EC2 instance using MBR partitioning.

Description:
Amazon EBS (Elastic Block Store) provides block-level storage that can be attached to EC2 instances. In this task, an additional EBS volume was created and attached to an EC2 instance. The volume was then partitioned using MBR, formatted with a file system, and mounted to a directory so it can be used for storage.

Steps Overview:
1.⁠ ⁠EC2 instance was already running.
2.⁠ ⁠A new EBS volume was created.
3.⁠ ⁠The volume was attached to the EC2 instance.
4.⁠ ⁠MBR partition was created using fdisk.
5.⁠ ⁠File system was created.
6.⁠ ⁠Volume was mounted and verified.

Result:
The EBS volume was successfully attached, partitioned using MBR, formatted, and mounted for use.


commnads used:

1. Launch / use Ubuntu EC2
2. EC2 → Volumes → Create volume (gp3, 2 GiB, same AZ)
3. Attach volume to EC2 (/dev/xvdf)
4. SSH into EC2
5. Run lsblk (note new disk, e.g. nvme1n1)
6. Run sudo fdisk /dev/nvme1n1
7. Inside fdisk: n → p → 1 → Enter → Enter → w
8. Run lsblk (verify nvme1n1p1)
9. Run sudo mkfs.ext4 /dev/nvme1n1p1
10. Run sudo mkdir /data
11. Run sudo mount /dev/nvme1n1p1 /data
12. Run df -h
13. Run cd /data && sudo touch testfile.txt
