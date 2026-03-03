TASK 3 — IAM + RBAC + Least Privilege (AWS + Azure)

Objective:
Implement role-based access control using least privilege principles in both AWS IAM and Azure RBAC. The goal was to allow required actions while restricting sensitive operations.

────────────────────────────────
AWS PART — IAM + Least Privilege
────────────────────────────────

Overview:
An IAM user was created with full EC2 access but restricted S3 delete permissions. This demonstrated how AWS policies enforce access control and how explicit deny overrides allow permissions.

Step 1: Create IAM User
Logged in as root user.
Navigated to IAM → Users → Create User.
Created user named Task3User.
Enabled AWS Management Console access and set password.

Step 2: Attach EC2 Full Access Policy
Selected “Attach policies directly.”
Attached:
AmazonEC2FullAccess
This allowed full EC2 management.

Step 3: Create Custom Deny Policy for S3 Delete
Navigated to IAM → Policies → Create Policy → JSON.
Created policy:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "s3:DeleteObject",
      "Resource": "*"
    }
  ]
}

Named it:
DenyS3Delete

Step 4: Attach S3 Access and Deny Policy
Attached:
AmazonS3FullAccess
DenyS3Delete

Because explicit Deny overrides Allow:
User could access S3 but could not delete objects.

Step 5: Testing AWS Permissions

EC2 Test:
Logged in as Task3User.
Successfully launched EC2 instance.
Result: EC2 access allowed.

S3 Upload Test:
User could list buckets and upload files.
Result: S3 access allowed.

S3 Delete Test:
User attempted to delete object.
Received “Access Denied.”
Result: Delete blocked due to explicit deny.

AWS Concepts Demonstrated:
- IAM Users
- Managed Policies
- Custom Policies
- Explicit Deny overrides Allow
- Principle of Least Privilege

────────────────────────────────
AZURE PART — RBAC + Least Privilege
────────────────────────────────

Overview:
Implemented Azure Role-Based Access Control (RBAC) using Microsoft Entra ID (Azure AD). A user was assigned limited roles at different scopes to demonstrate controlled access.

Step 1: Create Azure User
Logged in to Azure Portal.
Navigated to Microsoft Entra ID → Users → Create New User.
Created user named Task3UserAzure.

Step 2: Assign Reader Role at Resource Group Level
Navigated to:
Resource Group → Access Control (IAM) → Add Role Assignment.
Selected role:
Reader
Assigned to Task3UserAzure.

Reader role allows:
- View resources
- Cannot create, modify, or delete

Step 3: Assign Contributor Role on Specific VM Only
Navigated to:
Specific Virtual Machine → Access Control (IAM) → Add Role Assignment.
Selected role:
Contributor
Assigned to Task3UserAzure.

Contributor role allows:
- Create
- Modify
- Delete resources
But only at assigned scope (that single VM).

Step 4: Testing Azure Permissions

Resource Group Level:
User logged in.
Could view all resources.
Could NOT create new VM at resource group level.
Result: Reader restriction working.

Specific VM Level:
User could start, stop, and manage assigned VM.
Result: Contributor working at scoped level.

Other Resources:
User could NOT modify other VMs.
Result: Scoped RBAC working correctly.

Azure Concepts Demonstrated:
- Microsoft Entra ID Users
- Role Assignments
- Scope-based access control
- Resource Group level roles
- Resource-specific roles
- Least Privilege implementation

────────────────────────────────
Final Outcome

AWS:
User had full EC2 access but restricted S3 delete operation.

Azure:
User had read-only access at resource group level and full control only on a specific VM.

Both platforms successfully demonstrated:
- Role-Based Access Control (RBAC)
- Policy-based permission management
- Scoped access
- Explicit restriction of sensitive actions
- Principle of Least Privilege

Conclusion:
Task 3 successfully implemented IAM and RBAC in AWS and Azure. Access was granted only where required and restricted where necessary, proving effective enforcement of least privilege security practices across both cloud platforms.
