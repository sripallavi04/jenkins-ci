Step-by-Step Instructions
Step 1: Prepare Your Azure Environment
Create an Azure Account:

If you don’t have an Azure account, create one at Azure.
Azure Portal:

Log in to the Azure Portal.
Create a Resource Group:

Navigate to "Resource groups" and click "Create".
Provide a name for the resource group and select a region.
Click "Review + create" and then "Create".
Step 2: Create a Virtual Machine (VM)
Create VM:

Search for "Virtual machines" and click "Create".
Select "Azure virtual machine".
Basic Settings:

Select the resource group you created.
Provide a name for the VM (e.g., jenkins-server).
Choose your region (same as the resource group).
Select an appropriate size (e.g., Standard_DS1_v2).
Administrator Account:

Set the authentication type to password or SSH public key.
Enter the username and password or SSH public key.
Inbound Port Rules:

Allow HTTP, HTTPS, and SSH (port 22).
Create and Review:

Click "Review + create" and then "Create".
Step 3: Connect to the VM
Retrieve Public IP:

Once the VM is running, go to the "Overview" tab.
Note down the public IP address of the VM.
SSH into VM:

Open a terminal on your local machine.
Use the following command to SSH into your VM:
ssh <username>@<public-ip-address>
Step 4: Install Jenkins
Update System Packages:

Run the package manager to update the system packages.
Install Java:

Jenkins requires Java to run; install OpenJDK.
Add Jenkins Repository:

Add the Jenkins repository.
Install Jenkins:

Use the package manager to install Jenkins.
Start Jenkins:

Start the Jenkins service.
Ensure Jenkins is enabled to start on boot.
Step 5: Configure Jenkins
Initial Setup:

Open a web browser and navigate to http://<your-vm-public-ip>:8080.
Retrieve the initial admin password from the Jenkins log file on the VM.
Complete the setup wizard by installing the recommended plugins.
Create Admin User:

Create a new admin user with a secure password.
Security Configuration:

Set up security settings, including role-based access control if needed.
Step 6: Optimize and Secure Jenkins
Install Essential Plugins:

Install necessary plugins based on your project requirements (e.g., Git, Docker, Pipeline).
Configure SSL/TLS:

For production, set up SSL/TLS for Jenkins using a reverse proxy such as Nginx.
Obtain SSL certificates (e.g., from Let's Encrypt).
Performance Tuning:

Adjust Java options for optimal memory usage.
Configure log rotation to manage disk space.
Monitoring and Alerts:

Set up Azure Monitor and Jenkins plugins for system and job monitoring.
Step 7: Backup and Recovery
Backup Jenkins Home:

Regularly backup the JENKINS_HOME directory.
Use Azure Blob Storage or another backup solution.
Automate Backups:

Schedule automated backup tasks within Jenkins or using Azure Automation.
Conclusion
By following these steps, you will have a comprehensive guide to setting up and optimizing a Jenkins server on Azure. This setup will support competitive programming requirements and ensure a robust CI/CD environment.

Example of azurejenkins-setup.md
# Azure Jenkins Server Setup

## Introduction
This document provides a step-by-step guide to setting up a Jenkins server on Azure, optimized for handling competitive programming test cases.

## Step 1: Prepare Your Azure Environment

1. Create an Azure Account
2. Log in to the [Azure Portal](https://portal.azure.com/)
3. Create a Resource Group

## Step 2: Create a Virtual Machine (VM)

1. Create VM
2. Basic Settings
3. Administrator Account
4. Inbound Port Rules
5. Create and Review

## Step 3: Connect to the VM

1. Retrieve Public IP
2. SSH into VM

## Step 4: Install Jenkins

1. Update System Packages
2. Install Java
3. Add Jenkins Repository
4. Install Jenkins
5. Start Jenkins

## Step 5: Configure Jenkins

1. Initial Setup
2. Create Admin User
3. Security Configuration

## Step 6: Optimize and Secure Jenkins

1. Install Essential Plugins
2. Configure SSL/TLS
3. Performance Tuning
4. Monitoring and Alerts

## Step 7: Backup and Recovery

1. Backup Jenkins Home
2. Automate Backups