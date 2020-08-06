---
title: Distribuzione di pacchetti (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, deploying
- deploying packages [Integration Services]
- SQL Server Integration Services packages, deploying
- deploying packages [Integration Services], about deploying packages
- packages [Integration Services], deploying
- SSIS packages, deploying
ms.assetid: 0f5fc7be-e37e-4ecd-ba99-697c8ae3436f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 32627eddf5e7a696decd549e9b87ebb5c3b9d031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629903"
---
# <a name="package-deployment-ssis"></a><span data-ttu-id="29325-102">Distribuzione di pacchetti (SSIS)</span><span class="sxs-lookup"><span data-stu-id="29325-102">Package Deployment (SSIS)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="29325-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include strumenti e procedure guidate per la distribuzione di pacchetti dal computer di sviluppo al server di produzione o ad altri computer.</span><span class="sxs-lookup"><span data-stu-id="29325-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes tools and wizards that make it simple to deploy packages from the development computer to the production server or to other computers.</span></span>  
  
 <span data-ttu-id="29325-104">La procedura per la distribuzione di pacchetti prevede quattro passaggi.</span><span class="sxs-lookup"><span data-stu-id="29325-104">There are four steps in the package deployment process:</span></span>  
  
1.  <span data-ttu-id="29325-105">Il primo passaggio è facoltativo e riguarda la creazione delle configurazioni dei pacchetti che aggiornano le proprietà degli elementi dei pacchetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="29325-105">The first optional step is optional and involves creating package configurations that update properties of package elements at run time.</span></span> <span data-ttu-id="29325-106">Le configurazioni vengono incluse automaticamente durante la distribuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="29325-106">The configurations are automatically included when you deploy the packages.</span></span>  
  
2.  <span data-ttu-id="29325-107">Il secondo passaggio consiste nella compilazione del progetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per creare un'utilità di distribuzione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="29325-107">The second step is to build the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to create a package deployment utility.</span></span> <span data-ttu-id="29325-108">L'utilità di distribuzione per il progetto contiene i pacchetti che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="29325-108">The deployment utility for the project contains the packages that you want to deploy</span></span>  
  
3.  <span data-ttu-id="29325-109">Il terzo passaggio consiste nel copiare nel computer di destinazione la cartella di distribuzione creata in fase di compilazione del progetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29325-109">The third step is to copy the deployment folder that was created when you built the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to the target computer.</span></span>  
  
4.  <span data-ttu-id="29325-110">Il quarto passaggio consiste nell'eseguire nel computer di destinazione l'Installazione guidata pacchetti per installare i pacchetti nel file system o in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29325-110">The fourth step is to run, on the target computer, the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="29325-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="29325-111">Related Tasks</span></span>  
 <span data-ttu-id="29325-112">Per informazioni su come creare un'utilità di distribuzione, vedere [Creazione di un'utilità di distribuzione](../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="29325-112">For information about how to create a deployment utility, see [Create a Deployment Utility](../create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="29325-113">Per informazioni su come distribuire i pacchetti usando l'utilità di distribuzione, vedere [Distribuzione di pacchetti con l'utilità di distribuzione](../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="29325-113">For information about how to deploy packages using the deployment utility, see [Deploy Packages by Using the Deployment Utility](../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="29325-114">Per informazioni su come creare le configurazioni dei pacchetti, vedere [Creazione di configurazioni dei pacchetti](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="29325-114">For information about how to create package configurations, see [Create Package Configurations](../create-package-configurations.md).</span></span>  
  
  
