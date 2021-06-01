# Deploy a Storage Account for SAP ILM Store

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/path-to-sample/CredScanResult.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fpath-to-sample%2Fazuredeploy.json)
[![Deploy To Azure US Gov](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.svg?sanitize=true)](https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fpath-to-sample%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fpath-to-sample%2Fazuredeploy.json)

This template deploys a SAP ILM Store on a Microsoft Azure Storage Account. The SAP ILM Store is a **description**. For more information about SAP ILM Store, see **link**.

## Overview and deployed resources

The following steps are executed as a part of the solution

+ Deployment of a Microsoft Azure Storage Account
+ Creation of a Custom Role for restricting access to the Microsoft Azure Storage Account
+ Assignment of the Custom Role to a Microsoft Azure Active Directly Application

## Prerequisites

None

## Deployment steps

Click the ![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true) button at the beginning of this document.

For the parameter **"Principal ID of the Azure Active Directory Application"**, run the following command to get the Principal ID. 
Replace `name-of-service-principal` with the name of the Azure Active Directory Application.

**PowerShell:** `(Get-AzADServicePrincipal -DisplayName “name-of-service-principal”).Id`

**Command Line:** `az ad sp list --display-name “name-of-service-principal” --query "[].objectId" --output tsv`

## Notes

The scripts are provided as-is without warranty of any kind, either expressed or implied, including any implied warranties of fitness for a particular purpose, mechantability, or non-infringement.

`Tags: SAP, ILM, Store`
