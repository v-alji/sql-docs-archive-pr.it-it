---
title: Ridistribuzione di pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- redeploying packages [Integration Services]
- deploying packages [Integration Services], redeploying
ms.assetid: 86806efb-8cf4-4f9d-9824-1152cb4c495c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c5286d406d96f62fc74eb619f7e7a6064fde2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713271"
---
# <a name="redeployment-of-packages"></a><span data-ttu-id="b523e-102">Ridistribuzione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="b523e-102">Redeployment of Packages</span></span>
  <span data-ttu-id="b523e-103">Dopo la distribuzione di un progetto, potrebbe essere necessario aggiornare o estendere la funzionalità dei pacchetti e ridistribuire quindi il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="b523e-103">After a project is deployed, you may need to update or extend package functionality and then redeploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the updated packages.</span></span> <span data-ttu-id="b523e-104">Durante il processo di ridistribuzione di pacchetti, è consigliabile analizzare le proprietà di configurazione incluse nell'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b523e-104">As part of the process of redeploying packages, you should review the configuration properties that are included in the deployment utility.</span></span> <span data-ttu-id="b523e-105">Potrebbe ad esempio essere utile non consentire alcuna modifica di configurazione dopo la ridistribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b523e-105">For example, you may not want to allow configuration changes after the package is redeployed.</span></span>  
  
## <a name="process-for-redeployment"></a><span data-ttu-id="b523e-106">Ridistribuzione</span><span class="sxs-lookup"><span data-stu-id="b523e-106">Process for Redeployment</span></span>  
 <span data-ttu-id="b523e-107">Dopo avere completato l'aggiornamento di pacchetti, è necessario ricompilare il progetto, copiare la cartella di distribuzione nel computer di destinazione e rieseguire l'Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b523e-107">After you finish updating the packages, you rebuild the project, copy the deployment folder to the target computer, and then rerun the Package Installation Wizard.</span></span>  
  
 <span data-ttu-id="b523e-108">Se si aggiornano solo alcuni pacchetti di un progetto, potrebbe risultare utile ridistribuire solo i pacchetti aggiornati anziché l'intero progetto.</span><span class="sxs-lookup"><span data-stu-id="b523e-108">If you update only a few packages in the project, you may not want to redeploy the entire project.</span></span> <span data-ttu-id="b523e-109">Per distribuire solo alcuni pacchetti, è possibile creare un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , aggiungervi i pacchetti aggiornati e quindi compilare e distribuire il progetto.</span><span class="sxs-lookup"><span data-stu-id="b523e-109">To deploy only a few packages, you can create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add the updated packages to the new project, and then build and deploy the project.</span></span> <span data-ttu-id="b523e-110">Quando il pacchetto viene aggiunto a un altro progetto, le configurazioni di pacchetto vengono copiate automaticamente insieme al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b523e-110">Package configurations are automatically copied with the package when you add the package to a different project.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b523e-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b523e-111">Related Tasks</span></span>  
 [<span data-ttu-id="b523e-112">Distribuzione di pacchetti con l'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b523e-112">Deploy Packages by Using the Deployment Utility</span></span>](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)  
  
  
