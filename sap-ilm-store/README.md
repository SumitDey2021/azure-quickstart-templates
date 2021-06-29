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

This template deploys a Microsoft Storage Account which can be integrated with a SAP Information Lifecycle Magagement (ILM) Store. A ILM Store is a component which fulfills the requirements of SAP ILM compliant storage systems. One can store archive files in a storage media using WebDAV interface standards while making use of SAP ILM Retention Management rules. For more information about SAP ILM Store, refer to the [SAP Help Portal](https://help.sap.com/viewer/7ce8e5dc89d7407e8baa9de7b775f31f/703%20SP27/en-US).

## Overview and deployed resources

The following steps are executed as a part of the solution:

+ Deployment of a Microsoft Azure Storage Account
+ Creation of a Custom Role for restricting access to the Microsoft Azure Storage Account
+ Assignment of the Custom Role to a Microsoft Azure Active Directory Application

## Prerequisites

For the parameter **"Principal ID of the Azure Active Directory Application"**, run the following command to get the Principal ID. 
Replace `name-of-service-principal` with the name of the Azure Active Directory Application that you intend to enable for SAP ILM access to the Microsoft Azure Storage Account.

**PowerShell:** `(Get-AzADServicePrincipal -DisplayName "name-of-service-principal").Id`

**Command Line:** `az ad sp list --display-name "name-of-service-principal" --query "[].objectId" --output tsv`

**Note:** While most of the parameters have a default value, please make sure that you provide a new and unique value for the parameters **"Custom Role name for the Role Definition"** and **"Name of the Storage Account"**.

## Deployment steps

Click the [![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://github.com/SumitDeySAP/azure-quickstart-templates/tree/patch-1/sap-ilm-store#deploy-a-storage-account-for-sap-ilm-store) button at the beginning of this document.

## Error Handling

For deployment errors raised with Azure Resource Manager, please refer to the Microsoft Documentation [Troubleshoot common Azure deployment errors with Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/common-deployment-errors).

Some of the errors are listed below:

**Error code:** `StorageAccountAlreadyTaken`

**Error Description:** `The storage account named <<value>> is already taken`

**Deployment phase:** Preflight validation

**Description:** It is likely that the Storage Account name that you have currently chosen for the parameter "Name of the Storage Account" is already in use. 

**Solution:** Please select a new unique value for this parameter and try again.


**Error code:** `RoleScopeBeingRemovedContainsAssignments`

**Error Description:** `Role assignments found under scope '/subscriptions/<<value>>/resourcegroups/<<value>>' which is being removed. Removing this scope from the role will orphan these assignments. Delete these **assignments before removing the scope`

**Deployment phase:** Deployment

**Description:** It is likely that the name of the Custom Role that you have currently chosen for the parameter "Custom Role name for the Role Definition" is already in use.

**Solution:** Please select a new unique value for this parameter and try again.



**Error code:** `InvalidPrincipalId`

**Error Description:** `A valid principal ID must be provided for role assignment`

**Deployment phase:** Deployment

**Description:** It is likely that the Principal Id provided for the parameter "Principal ID of the Azure Active Directory Application" is either empty or incorrect.

**Solution:** Please refer to the Prerequisites section above to determine the correct value for this parameter.



## Notes

The scripts are provided as-is without warranty of any kind, either expressed or implied, including any implied warranties of fitness for a particular purpose, mechantability, or non-infringement.


`Tags: SAP, Information Lifecycle Magagement, ILM, Store`
