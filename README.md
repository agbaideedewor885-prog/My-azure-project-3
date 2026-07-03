🚀 Azure Virtual Machine Deployment Using ARM Template

📌 Project Overview

This project demonstrates the deployment of a Linux Virtual Machine (VM) in Microsoft Azure using an Azure Resource Manager (ARM) template.

It showcases Infrastructure as Code (IaC) by automating the provisioning of cloud resources through a reusable JSON template. The deployment includes a complete setup of compute, networking, and security components.

---

🏗️ Architecture Components

The ARM template provisions the following Azure resources:

- Virtual Machine (Ubuntu 22.04)
- Virtual Network (VNet)
- Subnet
- Network Interface (NIC)
- Public IP Address
- Network Security Group (NSG)

---

🧱 ARM Template Structure

The template is organized into the following key sections:

- Parameters: Dynamic inputs such as VM name, location, and admin credentials
- Variables: Reusable values for naming and configurations
- Resources: All Azure services deployed
- Outputs: Useful deployment results such as the Public IP address

---

⚙️ Deployment Process

Step 1: Create a Resource Group

az group create --name myResourceGroup --location "East US"

Step 2: Deploy the ARM Template

az deployment group create \
  --resource-group myResourceGroup \
  --template-file template.json \
  --parameters adminPassword=YourStrongPassword123!

---

🌐 Networking Configuration

The deployment includes:

- Virtual Network: Address space "10.0.0.0/16"
- Subnet: "10.0.1.0/24"
- Public IP: Enables external access
- Network Interface: Connects the VM to the network

---

🔐 Security Configuration

Network Security Group (NSG)

- Allows inbound SSH traffic (Port 22)
- Blocks all other inbound traffic by default

Authentication

- Uses username and password authentication
- Can be enhanced using SSH key authentication for improved security

Multi-Factor Authentication (MFA)

To enable MFA in Azure:

1. Go to Azure Portal
2. Navigate to Azure Active Directory
3. Select Users → Per-user MFA
4. Enable MFA for your account

---

💰 Budget & Cost Management

To manage cloud spending and avoid unexpected charges:

1. Go to Cost Management + Billing
2. Select Budgets
3. Click Add
4. Configure:
   - Budget: $200
   - Alert threshold: 75% ($150)
5. Enable email notifications

---

🧪 Validation & Troubleshooting

Validate Deployment Template

az deployment group validate \
  --resource-group myResourceGroup \
  --template-file template.json

Common Errors

- Incorrect parameter values
- Missing resource dependencies
- JSON syntax errors

---

🔗 Connecting to the Virtual Machine

After deployment, retrieve the Public IP address and connect via SSH:

ssh azureuser@<PUBLIC-IP>

---

📸 Screenshots (Required for Submission)

Include the following screenshots in a "/screenshots" folder:

- Azure Portal Dashboard
- Resource Group Overview
- Successful Deployment
- Virtual Machine Running Status
- Budget Configuration

---

🎯 Key Learning Outcomes

- Understanding ARM template structure
- Deploying infrastructure using code (IaC)
- Configuring Azure networking components
- Applying security best practices
- Managing cloud costs effectively

---

📌 Conclusion

This project demonstrates how to automate Azure infrastructure deployment using ARM templates. It highlights best practices in cloud provisioning, security, and cost management, making it suitable for real-world cloud engineering scenarios.

---

👤 Author

Name: Edewor Abel
Program: 3MTT Cloud Computing Track
