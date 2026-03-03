Objective:
Launch and configure a basic Azure Virtual Machine.

Description:
An Ubuntu VM was created in Azure and accessed from Mac terminal using username and password authentication.


Task Name:
Launch and Configure a Basic Azure VM

Objective:
To create and configure a basic Ubuntu virtual machine in Microsoft Azure and access it using username and password from a Mac terminal.

Services Used:
- Microsoft Azure
- Azure Virtual Machine
- Resource Group
- SSH (Port 22)

Configuration Details:

Resource Group Name:
basic-vm-rg

Virtual Machine Name:
MyVmTask18

Operating System:
Ubuntu Server 20.04 LTS

VM Size:
Standard B1s

Authentication Method:
Username and Password

Username:
Muskanvm

Network Configuration:
- Public IP enabled
- SSH (Port 22) allowed in inbound rules

Steps Performed:

1. Resource group created in Azure.
2. Virtual machine created inside the resource group.
3. Ubuntu Server selected as the operating system.
4. Standard B1s selected as the VM size.
5. Administrator username and password configured.
6. SSH (Port 22) enabled in networking settings.
7. Virtual machine deployed successfully.
8. Public IP address obtained from Azure portal.
9. Virtual machine accessed from Mac terminal using password-based SSH login.

SSH Command Used:

ssh Muskanvm@<Public-IP>

Result:
Azure virtual machine launched successfully.
Password-based SSH access configured.
VM accessed successfully from Mac terminal and ready for use.

Proof:
- Screenshot of Azure VM overview showing Running status
- Screenshot of terminal showing successful login to VM
Result:
Azure VM launched and configured successfully.
