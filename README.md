🚀 Azure Virtual Machine Deployment using ARM Template

📌 Project Overview

This project demonstrates how to deploy a Linux Virtual Machine (VM) in Microsoft Azure using an Azure Resource Manager (ARM) template. The deployment includes complete infrastructure setup such as networking, security, and compute resources.

The goal is to showcase Infrastructure as Code (IaC) by automating resource deployment using a reusable JSON template.

---

🏗️ Architecture Components

The ARM template deploys the following resources:

- Virtual Machine (Ubuntu 22.04)
- Virtual Network (VNet)
- Subnet
- Network Interface (NIC)
- Public IP Address
- Network Security Group (NSG)

---

🧱 ARM Template Structure

The template is structured into the following sections:

- Parameters: Dynamic inputs such as VM name, location, and admin credentials
- Variables: Reusable values for resource naming and configuration
- Resources: Azure services to be deployed
- Outputs: Returns useful information such as Public IP address

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
- Public IP: Enables internet access
- NIC: Connects VM to the network

---

🔐 Security Configuration

Network Security Group (NSG)

- Allows inbound SSH traffic on port 22
- Blocks all other inbound traffic by default

Authentication

- Uses username and password
- Can be enhanced with SSH key authentication for better security

Multi-Factor Authentication (MFA)

To enable MFA on Azure:

1. Go to Azure Portal
2. Search for Azure Active Directory
3. Select Users → Per-user MFA
4. Enable MFA for your account

---

💰 Budget & Cost Management

To avoid unexpected charges, a budget can be configured:

1. Go to Cost Management + Billing
2. Select Budgets
3. Click Add
4. Set:
   - Budget amount: $200
   - Alert threshold: 75% ($150)
5. Configure email alerts

---

🧪 Validation & Troubleshooting

Validate Template

az deployment group validate \
  --resource-group myResourceGroup \
  --template-file template.json

Common Errors

- Incorrect parameter values
- Missing dependencies
- JSON syntax issues

---

🔗 Connecting to the Virtual Machine

After deployment, retrieve the Public IP and connect:

ssh azureuser@<PUBLIC-IP>

---

📸 Screenshots (Add Yours Here)

Include the following screenshots for submission:

- Azure Portal Dashboard
- Resource Group Overview
- Successful Deployment
- VM Running Status
- Budget Configuration

Key Learning Outcomes

- Understanding ARM template structure
- Deploying infrastructure using code
- Configuring networking in Azure
- Applying security best practices
- Managing cloud costs effectively

Conclusion

This project demonstrates how to automate Azure infrastructure deployment using ARM templates. It highlights best practices in cloud provisioning, security, and cost management, making it suitable for real-world cloud engineering scenarios.

---

👤 Author

Name: Your Name Edewor Abel 
Program: 3MTT Cloud Computing Track
