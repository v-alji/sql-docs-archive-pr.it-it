---
title: Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721532"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="bd709-102">Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="bd709-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="bd709-103">Utilizzare Distribuzione guidata modello [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per distribuire pacchetti contenenti solo oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="bd709-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="bd709-104">Se è necessario distribuire un pacchetto con i dati, vedere [Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="bd709-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd709-105">I pacchetti possono essere distribuiti solo nella versione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzata per crearli.</span><span class="sxs-lookup"><span data-stu-id="bd709-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="bd709-106">Pertanto non è possibile distribuire pacchetti creati in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] a [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd709-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bd709-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bd709-107">Prerequisites</span></span>  
 <span data-ttu-id="bd709-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd709-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bd709-109">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Amministrazione sistema** nell'ambiente [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bd709-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="bd709-110">È necessario che sia già disponibile un pacchetto di distribuzione di modelli.</span><span class="sxs-lookup"><span data-stu-id="bd709-110">A model deployment package must exist.</span></span> <span data-ttu-id="bd709-111">Per altre informazioni, vedere [Creare un pacchetto di distribuzione di modelli tramite la procedura guidata](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bd709-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="bd709-112">È necessario essere un amministratore nell'ambiente in cui viene distribuito il modello.</span><span class="sxs-lookup"><span data-stu-id="bd709-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="bd709-113">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd709-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="bd709-114">Per distribuire un pacchetto di distribuzione di modelli di soli oggetti modello</span><span class="sxs-lookup"><span data-stu-id="bd709-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="bd709-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="bd709-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bd709-116">Nella barra dei menu della pagina **Vista modelli** scegliere **Sistema** , quindi fare clic su **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="bd709-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="bd709-117">Su **Distribuzione guidata modello**, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="bd709-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="bd709-118">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="bd709-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="bd709-119">Individuare il pacchetto di distribuzione (file con estensione pkg) e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="bd709-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="bd709-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd709-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="bd709-121">Dopo aver caricato il pacchetto, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd709-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="bd709-122">Se il modello è già presente, è possibile aggiornarlo selezionando **Aggiorna il modello esistente**.</span><span class="sxs-lookup"><span data-stu-id="bd709-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="bd709-123">Per creare un nuovo modello, selezionare **Crea un nuovo modello** e, dopo aver fatto clic su **Avanti** , è possibile digitare un nome per il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="bd709-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="bd709-124">Fare clic su **Fine** per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bd709-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="bd709-125">**Note:**</span><span class="sxs-lookup"><span data-stu-id="bd709-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="bd709-126">Se una vista sottoscrizioni nel pacchetto ha lo stesso nome di una vista sottoscrizioni in un modello esistente, la vista viene creata come *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="bd709-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="bd709-127">Se questo nome è già in uso, la vista della sottoscrizione non viene creata.</span><span class="sxs-lookup"><span data-stu-id="bd709-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="bd709-128">Il processo di distribuzione si svolge in quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="bd709-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="bd709-129">Creazione degli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="bd709-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="bd709-130">Creazione delle viste sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="bd709-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="bd709-131">Creazione delle regole business.</span><span class="sxs-lookup"><span data-stu-id="bd709-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="bd709-132">Popolamento dei dati master.</span><span class="sxs-lookup"><span data-stu-id="bd709-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="bd709-133">Quando si crea un nuovo modello o se ne clona uno esistente, se si verifica un errore durante un qualsiasi passaggio del processo, il modello viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="bd709-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="bd709-134">Quando si aggiorna un modello, se si verifica un errore durante uno dei primi tre passaggi, l'operazione viene interrotta; tuttavia il rollback delle modifiche già effettuate non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="bd709-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="bd709-135">Se si verifica un errore durante il quarto passaggio, viene eseguito l'aggiornamento dei membri che è possibile aggiornare.</span><span class="sxs-lookup"><span data-stu-id="bd709-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bd709-136">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bd709-136">Next Steps</span></span>  
 <span data-ttu-id="bd709-137">I metadati definiti dall'utente, gli attributi di file e le autorizzazioni utente e gruppo non sono inclusi nei pacchetti di distribuzione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="bd709-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="bd709-138">Dopo avere distribuito un modello, è necessario aggiornare questi elementi manualmente.</span><span class="sxs-lookup"><span data-stu-id="bd709-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="bd709-139">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="bd709-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="bd709-140">Aggiungere metadati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd709-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="bd709-141">Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd709-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd709-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd709-142">See Also</span></span>  
 [<span data-ttu-id="bd709-143">Distribuzione di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd709-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
