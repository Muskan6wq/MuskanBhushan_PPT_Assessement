Objective:
Allow EC2 instance to access S3 securely using IAM Role.

Description:
An IAM role with S3 permissions was created and attached to an EC2 instance. The EC2 instance accessed S3 without using access keys.
TASK 9 – Access S3 from Ubuntu using IAM Role and Policies

1. I went to IAM service in AWS Console.

2. I clicked on Roles and created a new IAM role.
   - Trusted entity type: AWS service
   - Service: EC2
   - Attached policy: AmazonS3ReadOnlyAccess
   - Role name: Task9-role

3. I created the role successfully.

4. Then I went to EC2 service.

5. I selected my Ubuntu EC2 instance.

6. I clicked:
   Actions → Security → Modify IAM role

7. I attached the IAM role:
   Task9-role

8. I connected to the Ubuntu EC2 instance using SSH.

9. I installed AWS CLI v2 manually on Ubuntu.

10. I verified AWS CLI installation:
    aws --version

11. I verified IAM role attachment using:
    aws sts get-caller-identity

12. The output showed assumed role Task9-role,
    which confirmed that IAM role was working.

13. I created an S3 bucket:
    - Bucket name: buc-1-aws

14. From Ubuntu EC2, I tested S3 access using:
    aws s3 ls

15. The bucket buc-1-aws was visible from Ubuntu EC2,
    which confirms EC2 can access S3 using IAM role.

Result:
EC2 instance successfully accessed S3 using IAM Role (Task9-role).
No access keys were used.
S3 bucket buc-1-aws was visible from Ubuntu instance.

Result:
Secure and keyless access to S3 achieved.
