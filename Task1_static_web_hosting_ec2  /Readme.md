# Task 1 – Static Website Hosting in EC2 (Ubuntu + Nginx)

## Objective
To deploy and host a static HTML website on an Amazon EC2 Ubuntu instance using the Nginx web server.

---

## Tools & Services Used
- Amazon EC2
- Ubuntu 22.04
- Nginx Web Server
- SSH
- Linux commands (wget, unzip, mv)

---

## Steps Performed

### 1. EC2 Instance Setup
- Launched an Ubuntu 22.04 EC2 instance.
- Configured Security Group to allow:
  - SSH (Port 22)
  - HTTP (Port 80)

---

### 2. SSH Connection
- Connected to the EC2 instance using an SSH key pair.

---

### 3. Nginx Installation
- Updated system packages.
- Installed Nginx web server to host the website.

---

### 4. Web Root Directory
- Navigated to the Nginx default web root directory:
  /var/www/html

---

### 5. Website Download
- Downloaded a static HTML website template using wget.

---

### 6. Website Extraction
- Renamed the downloaded file to .zip format.
- Extracted website contents using unzip.

---

### 7. Website Deployment
- Moved website files (index.html, CSS, JS, images) into /var/www/html.
- Removed the default Nginx page.

---

### 8. Permission Configuration
- Updated ownership and permissions so Nginx could access the website files.

---

### 9. Nginx Restart
- Restarted the Nginx service to apply changes.

---

### 10. Verification
- Accessed the website using the EC2 public IP address.
- Verified that the static website loaded successfully.

---

## Outcome
The static HTML website was successfully hosted on an EC2 Ubuntu instance using Nginx and is accessible via the public IP.

---

## Key Learnings
- EC2 instance creation and management
- SSH connectivity
- Linux file and permission management
- Nginx web server configuration
- Static website hosting on AWS

---

## Conclusion
This task demonstrates how to deploy a static website on AWS EC2 using Nginx, providing hands-on experience with cloud infrastructure and Linux fundamentals.

---

Status: Task Completed Successfully
