---
description: Deploy a managed cluster with Azure Container Service (AKS) with Helm
page_type: sample
products:
- azure
- azure-resource-manager
urlFragment: aks-helm
languages:
- json
- bicep
---
# Azure Container Service (AKS) with Helm

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/CredScanResult.svg)

![Bicep Version](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks-helm/BicepVersion.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.kubernetes%2Faks-helm%2Fazuredeploy.json)
[![Deploy To Azure US Gov](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.svg?sanitize=true)](https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.kubernetes%2Faks-helm%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.kubernetes%2Faks-helm%2Fazuredeploy.json)

## Deployment

This template deploys an **AKS cluster**. To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-rm-template) article.

For information about how to deploy an AKS cluster using Azure CLI, see the [quickstart](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough) article.


## Deploy the Bicep file

1. Run the ssh-keygen command. The following example creates an SSH key pair using RSA encryption and a bit length of 4096:
Console

```ps
ssh-keygen -t rsa -b 4096
```

2. Deploy the Bicep file using either Azure CLI or Azure PowerShell.

```ps
az group create --name myResourceGroup --location eastus
az deployment group create --resource-group myResourceGroup --template-file main.bicep --parameters clusterName=<cluster-name> dnsPrefix=<dns-previs> linuxAdminUsername=<linux-admin-username> sshRSAPublicKey='<ssh-key> _artifactsLocation='https://raw.githubusercontent.com/ricardona/bicep-firsts-steps-intro/master/quickstarts/microsoft.kubernetes/aks-helm/'
```

Provide the following values in the commands:

- Cluster name: Enter a unique name for the AKS cluster, such as `myAKSCluster`.
- DNS prefix: Enter a unique DNS prefix for your cluster, such as `myakscluster`.
- Linux Admin Username: Enter a username to connect using SSH, such as `azureuser`.
- SSH RSA Public Key: Copy and paste the public part of your SSH key pair (by default, the contents of ~/.ssh/id_rsa.pub).
- Artifacts location: For the artifacts location, they need to accessible from an internet http location. Either anonymously or secured with a token in its query string. This can be from a github repo or from an azure storage account.

It takes a few minutes to create the AKS cluster. Wait for the cluster to be successfully deployed before you move on to the next step.

## References

[What is Bicep?] (https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview?tabs=bicep)

[Original templates from Azure Quickstart Templates]
(https://github.com/kabeer81/azure-quickstart-templates)

[Quickstart: Deploy an Azure Kubernetes Service (AKS) cluster using Bicep] (https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-bicep?toc=%2Fazure%2Fazure-resource-manager%2Fbicep%2Ftoc.json&tabs=azure-cli%2CCLI)

[Fundamentals of Bicep] (https://learn.microsoft.com/en-us/training/paths/fundamentals-bicep/)

