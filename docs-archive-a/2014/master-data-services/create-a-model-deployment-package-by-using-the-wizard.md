---
title: Creare un pacchetto di distribuzione di modelli tramite la procedura guidata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637400"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="9633d-102">Creare un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="9633d-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="9633d-103">Utilizzare Distribuzione guidata modello [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per creare un pacchetto contenente solo oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="9633d-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="9633d-104">Se è necessario includere dati nel pacchetto, vedere [Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="9633d-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9633d-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9633d-105">Prerequisites</span></span>  
 <span data-ttu-id="9633d-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="9633d-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9633d-107">Nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] è necessario avere l'autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="9633d-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9633d-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="9633d-108">You must be a model administrator.</span></span> <span data-ttu-id="9633d-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9633d-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9633d-110">È necessario che sia disponibile un modello affinché sia possibile crearne un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9633d-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="9633d-111">Per altre informazioni, vedere [Creare un modello &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9633d-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="9633d-112">Per creare un pacchetto di distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="9633d-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="9633d-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="9633d-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9633d-114">Nella barra dei menu della pagina **Vista modelli** scegliere **Sistema** , quindi fare clic su **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="9633d-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="9633d-115">In **Distribuzione guidata modello**fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="9633d-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="9633d-116">Nella pagina **Crea pacchetto** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="9633d-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="9633d-117">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9633d-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9633d-118">Fare clic su **Download**.</span><span class="sxs-lookup"><span data-stu-id="9633d-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="9633d-119">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9633d-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="9633d-120">Fare clic su **Chiudi** per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9633d-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9633d-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9633d-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="9633d-122">Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="9633d-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="9633d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9633d-123">See Also</span></span>  
 [<span data-ttu-id="9633d-124">Distribuzione di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9633d-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
