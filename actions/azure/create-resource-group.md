# Create Resource Group Action

## Description
Creates a new resource group in Azure.

## Syntax
```
Azure.CreateResourceGroup AzureClient: `` GroupName: `` Location: `` ResourceGroup=> ResourceGroup
```

## Parameters
- AzureClient (Required): The client used to connect to Azure
- GroupName (Required): The name of the resource group
- Location (Required): The location where the new disk will be created

## Output
- ResourceGroup: Azure resource group object

## Exceptions
- Resource group already exists
- Failed to create resource group