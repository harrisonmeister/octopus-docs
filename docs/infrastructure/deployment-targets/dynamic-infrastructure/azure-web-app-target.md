---
title: Create Azure Web App target command
description: Cmdlet for creating an Azure Web App target
position: 20
---

## Azure Web App
Command: **_New-OctopusAzureWebAppTarget_**

| Parameter                           | Value                                         |
| ----------------------------------- | --------------------------------------------- |
| `-name`                             | name for the Octopus deployment target        |
| `-azureWebApp`                      | Name of the Azure Web App                     |
| `-azureWebAppSlot`                  | Name of the Azure Web App Slot                |
| `-azureResourceGroupName`           | Name of the Azure Resource Group              |
| `-octopusAccountIdOrName`           | Name or Id of the Account Resource in Octopus |
| `-octopusRoles`                     | Comma separated list of Roles to assign       |
| `-updateIfExisting`                 | Will update an existing Web App target with the same name, create if it doesn't exist |
| `-octopusDefaultWorkerPoolIdOrName` | Name or Id of the Worker Pool for the deployment target to use. (Optional). Added in 2020.6.0. |

### Examples


```powershell
# Using default options
New-OctopusAzureWebAppTarget -name "My Azure Web Application" `
                             -azureWebApp "WebApp1" `
                             -azureResourceGroupName "WebApp1-ResourceGroup"  `
                             -octopusAccountIdOrName "Dev Azure Account" `
                             -octopusRoles "AzureWebApp" `
                             -updateIfExisting

# Specifying a default worker pool for the target
New-OctopusAzureWebAppTarget -name "My Azure Web Application" `
                             -azureWebApp "WebApp1" `
                             -azureResourceGroupName "WebApp1-ResourceGroup"  `
                             -octopusAccountIdOrName "Dev Azure Account" `
                             -octopusRoles "AzureWebApp" `
                             -octopusDefaultWorkerPoolIdOrName "Worker Pool with Azure Access" `
                             -updateIfExisting
```

!include <create-deployment-targets-hint>