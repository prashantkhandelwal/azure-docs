---
title: Set up the Azure Service Fabric Mesh CLI | Microsoft Docs
description: Learn how to set up the Azure Service Fabric Mesh CLI.
services: service-fabric-mesh
keywords:  
author: tylermsft
ms.author: twhitney
ms.date: 07/26/2018
ms.topic: get-started-article
ms.service: service-fabric-mesh
manager: timlt  
#Customer intent: As a developer, I need to prepare install the prerequisites to enable deployment to service fabric mesh.
---

# Set up the Service Fabric Mesh CLI
Service Fabric Mesh CLI is required to deploy and manage resources in Service Fabric Mesh. 

For the preview, Azure Service Fabric Mesh CLI is written as an extension to Azure CLI. You can install it in the Azure Cloud Shell or a local installation of Azure CLI. 

[!INCLUDE [cloud-shell-try-it.md](../../includes/cloud-shell-try-it.md)] 

If you choose to install and use the CLI locally, you must install the Azure CLI version 2.0.35 or later. Run `az --version` to find the version. To install or upgrade to the latest version of the CLI, see [Install Azure CLI 2.0][azure-cli-install].

Remove any previous install of the Azure Service Fabric Mesh CLI module.

```azurecli-interactive
az extension remove --name mesh
```

Install the Azure Service Fabric Mesh CLI extension module using following command. 

```azurecli-interactive
az extension add --source https://meshcli.blob.core.windows.net/cli/mesh-0.9.1-py2.py3-none-any.whl
```

You can also set up your [Windows development environment](service-fabric-mesh-howto-setup-developer-environment-sdk.md).

[azure-cli-install]: /cli/azure/install-azure-cli