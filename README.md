# Azure Resource Deployment with ARM Templates

## 🔧 Tools Used
* Azure Resource Manager (ARM): Native infrastructure-as-code service for Azure.

* Azure Portal: For verification and manual testing.

* Azure CLI / PowerShell: To deploy templates via terminal.

* Visual Studio Code: For editing JSON ARM templates.

* Postman or Web Browser: For testing deployed services.

* Git: For source control and versioning of templates.

## 💡 Project Goal
To automate the provisioning of a secure and scalable Azure Web App with an Azure SQL Database using ARM templates, demonstrating Infrastructure as Code (IaC) principles on Microsoft Azure.

## 🔍 Features
Deploys:

* Azure Resource Group

* Azure App Service Plan

* Azure Web App (Node.js / Python / .NET supported)

* Azure SQL Server and SQL Database

* Uses parameters.json for dynamic input

* Supports deployment in different environments (dev, staging, prod)

* Secures database credentials via parameters

* Outputs Web App URL after deployment

* Easy to integrate with Azure DevOps or GitHub Actions later



## 📦 Folder Structure
azure-arm-webapp-sql/
│
├── templates/
│   ├── mainTemplate.json            # Root ARM template
│   ├── parameters/
│   │   ├── dev.parameters.json
│   │   └── prod.parameters.json
│
├── scripts/
│   ├── deploy.ps1                   # PowerShell deployment script
│   └── deploy.sh                    # Bash deployment script
│
├── README.md
├── .gitignore


## 🚀 How to Run
Option 1: Using Azure CLI
az login

az group create --name myResourceGroup --location eastus

az deployment group create \
  --resource-group myResourceGroup \
  --template-file templates/mainTemplate.json \
  --parameters @templates/parameters/dev.parameters.json
  
Option 2: Using PowerShell Script
.\scripts\deploy.ps1 -resourceGroup "myResourceGroup" `
                    -templateFile "templates/mainTemplate.json" `
                    -parametersFile "templates/parameters/dev.parameters.json"
                    
Option 3: Using Bash Script (Linux/macOS)

bash scripts/deploy.sh myResourceGroup eastus templates/mainTemplate.json templates/parameters/dev.parameters.json

## 🧠 Learning Outcome
* Understand the structure of ARM templates: resources, parameters, variables, outputs.

* Automate Azure infrastructure using Infrastructure as Code.

* Learn how to deploy and manage Web Apps and SQL Databases programmatically.

* Parameterize templates for multiple environments (e.g., dev/prod).

* Practice secure handling of sensitive data (e.g., SQL credentials).

* Learn to use Azure CLI and PowerShell for template deployment.

* Prepare for integration with CI/CD pipelines.
