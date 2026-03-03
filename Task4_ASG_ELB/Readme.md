Objective:
Create a scalable and highly available architecture using Auto Scaling Group and Load Balancer with an AMI.

Description:
An EC2 instance was configured with a web server and website. An AMI (Amazon Machine Image) was created from this instance. This AMI was used in a launch template to create an Auto Scaling Group. An Application Load Balancer distributed traffic across instances.

Steps Overview:
1.⁠ ⁠EC2 instance created and configured with Nginx.
2.⁠ ⁠Website verified on EC2.
3.⁠ ⁠AMI created from the EC2 instance.
4.⁠ ⁠Launch Template created using the AMI.
5.⁠ ⁠Target Group created.
6.⁠ ⁠Application Load Balancer created.
7.⁠ ⁠Auto Scaling Group created using launch template and attached to ALB.

Result:
Web application achieved scalability and high availability.

