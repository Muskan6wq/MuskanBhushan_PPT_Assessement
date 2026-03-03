TASK 5 — VS Code Integration with Azure (Blob Trigger Deployment)

Objective:
Connect Visual Studio Code to Azure, develop a Blob Trigger function locally, and deploy it to Azure. Validate event-driven execution when a file is uploaded to a storage container.

Overview:
In this task, Visual Studio Code was integrated with Azure using Azure extensions. A Blob Trigger Azure Function was created locally, configured with a storage account connection, tested, and deployed to Azure. The function was triggered automatically upon file upload.

Step 1: Login to Azure from VS Code
Installed Azure extensions in VS Code.
Signed in using Azure Account extension.
Verified subscription access inside VS Code.

Step 2: Create Blob Trigger Project
Used command:
Azure Functions: Create New Project.
Selected:
- Language: Python
- Template: Blob Trigger
- Function name: blobprocessor
- Path: upload-container/{name}
- Storage connection: AzureWebJobsStorage

Project files generated:
- host.json
- local.settings.json
- function_app.py
- requirements.txt

Step 3: Configure Storage Connection
Created a Storage Account in Azure.
Created container named:
upload-container
Copied Primary Connection String.
Updated local.settings.json with AzureWebJobsStorage value.

Step 4: Local Testing
Installed Azure Functions Core Tools.
Ran:
func start
Uploaded file to upload-container.
Verified local terminal logs showed blob trigger execution.

Step 5: Create Function App in Azure
From VS Code:
Created new Function App.
Selected:
- Subscription
- Resource Group
- Runtime: Python
- Region
- Storage Account

Azure automatically provisioned required services.

Step 6: Deploy to Azure
Right-clicked project folder.
Selected:
Deploy to Function App.
Deployment completed successfully.

Step 7: Cloud Testing
Uploaded file to Azure Storage container.
Navigated to:
Function App → Monitor → Logs.
Verified function executed successfully.

Architecture Flow:

Local VS Code
→ Azure Authentication
→ Azure Function App
→ Storage Account
→ Blob Container (upload-container)
→ File Upload
→ Blob Trigger Function Executes Automatically

Concepts Demonstrated:
- VS Code and Azure integration
- Event-driven serverless architecture
- Blob Trigger mechanism
- Storage account configuration
- Cloud deployment workflow
- Monitoring and logging

Conclusion:
Task 5 successfully demonstrated end-to-end Azure development workflow, including local project creation, configuration, deployment, and validation of Blob Trigger-based serverless execution in Azure.
