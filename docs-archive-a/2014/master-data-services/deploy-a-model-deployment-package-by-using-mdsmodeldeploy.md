---
title: Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635092"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="df8db-102">Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="df8db-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="df8db-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]utilizzare lo strumento MDSModelDeploy per distribuire un pacchetto contenente:</span><span class="sxs-lookup"><span data-stu-id="df8db-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="df8db-104">Solo oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="df8db-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="df8db-105">Dati e oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="df8db-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="df8db-106">Per distribuire un pacchetto contenente solo oggetti modello, è possibile utilizzare la Distribuzione guidata modello nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df8db-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="df8db-107">Per altre informazioni, vedere [Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df8db-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="df8db-108">I pacchetti possono essere distribuiti solo nella versione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzata per crearli.</span><span class="sxs-lookup"><span data-stu-id="df8db-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="df8db-109">Pertanto non è possibile distribuire pacchetti creati in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] a [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="df8db-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df8db-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="df8db-110">Prerequisites</span></span>  
 <span data-ttu-id="df8db-111">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="df8db-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="df8db-112">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Amministrazione sistema** nell'ambiente [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="df8db-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="df8db-113">È necessario che sia già disponibile un pacchetto di distribuzione di modelli.</span><span class="sxs-lookup"><span data-stu-id="df8db-113">A model deployment package must exist.</span></span> <span data-ttu-id="df8db-114">Per altre informazioni, vedere  [Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="df8db-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="df8db-115">È necessario essere un amministratore nell'ambiente in cui viene distribuito il modello.</span><span class="sxs-lookup"><span data-stu-id="df8db-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="df8db-116">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="df8db-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="df8db-117">Se si aggiorna un modello con i dati, la versione in cui si esegue la distribuzione non può essere **bloccata** o sottoposta a **commit**.</span><span class="sxs-lookup"><span data-stu-id="df8db-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="df8db-118">Per distribuire un pacchetto di distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="df8db-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="df8db-119">Determinare se si distribuisce un nuovo modello, un clone di un modello o si aggiorna un modello clonato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="df8db-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="df8db-120">Per altre informazioni, vedere [Opzioni di distribuzione dei modelli &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="df8db-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="df8db-121">Aprire un prompt dei comandi e spostarsi su MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="df8db-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="df8db-122">Se MDS è installato nel percorso predefinito, lo strumento è disponibile in *unità*: \Programmi\microsoft SQL Server\120\Master data Services\Configuration\MDSModelDeploy.exe</span><span class="sxs-lookup"><span data-stu-id="df8db-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="df8db-123">Se MDS non è stato installato nel percorso predefinito, cercare MDSModelDeploy.exe nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="df8db-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="df8db-124">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df8db-124">Optional.</span></span> <span data-ttu-id="df8db-125">Visualizzare le opzioni e la Guida.</span><span class="sxs-lookup"><span data-stu-id="df8db-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="df8db-126">Per visualizzare tutte le opzioni disponibili, digitare `MDSModelDeploy` e premere Invio.</span><span class="sxs-lookup"><span data-stu-id="df8db-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="df8db-127">Per visualizzare la Guida per un'opzione, digitare quanto segue, dove *OptionName* è il nome dell'opzione: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="df8db-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="df8db-128">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df8db-128">Optional.</span></span> <span data-ttu-id="df8db-129">Se sono disponibili più applicazioni Web, determinare il nome del servizio in cui verrà eseguita la distribuzione digitando questo comando e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="df8db-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="df8db-130">Verrà restituito un elenco di valori, ad esempio `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="df8db-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="df8db-131">Il primo valore di questo elenco, in questo caso `MDS1`, è necessario per distribuire il modello.</span><span class="sxs-lookup"><span data-stu-id="df8db-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="df8db-132">A seconda del fatto che si crei, si cloni o si aggiorni un modello, al prompt dei comandi digitare quanto segue e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="df8db-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="df8db-133">Per creare un nuovo modello:</span><span class="sxs-lookup"><span data-stu-id="df8db-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="df8db-134">Per creare un clone di un modello:</span><span class="sxs-lookup"><span data-stu-id="df8db-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="df8db-135">Per aggiornare un modello esistente e i relativi dati:</span><span class="sxs-lookup"><span data-stu-id="df8db-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="df8db-136">Se si utilizza lo strumento MDSModelDeploy per aggiornare un modello esistente e i relativi dati e nel pacchetto non è contenuto alcun attributo, entità o membro disponibile nel modello di destinazione, questi elementi non saranno eliminati dal modello tramite MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="df8db-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="df8db-137">Dove *PackageName* è il nome del file di pacchetto (con estensione pkg), *ModelName* è il nome del nuovo modello, *VersionName* è il nome della versione e *ServiceName* è il nome del servizio del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="df8db-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="df8db-138">Assicurarsi che i nomi della versione e del modello corrispondano esattamente ai nomi, rispettando la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="df8db-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="df8db-139">Al termine della distribuzione del pacchetto, verrà visualizzato un messaggio "Operazione MDSModelDeploy completata".</span><span class="sxs-lookup"><span data-stu-id="df8db-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="df8db-140">**Note:**</span><span class="sxs-lookup"><span data-stu-id="df8db-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="df8db-141">Se una vista sottoscrizioni nel pacchetto ha lo stesso nome di una vista sottoscrizioni in un modello esistente, la vista viene creata come *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="df8db-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="df8db-142">Se questo nome è già in uso, la vista della sottoscrizione non viene creata.</span><span class="sxs-lookup"><span data-stu-id="df8db-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="df8db-143">Il processo di distribuzione si svolge in quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="df8db-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="df8db-144">Creazione degli oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="df8db-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="df8db-145">Creazione delle regole business.</span><span class="sxs-lookup"><span data-stu-id="df8db-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="df8db-146">Creazione delle viste sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="df8db-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="df8db-147">Popolamento dei dati master.</span><span class="sxs-lookup"><span data-stu-id="df8db-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="df8db-148">Quando si crea un nuovo modello o se ne clona uno esistente, se si verifica un errore durante un qualsiasi passaggio del processo, il modello viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="df8db-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="df8db-149">Quando si aggiorna un modello, se si verifica un errore durante i primi tre passaggi, l'operazione viene interrotta; tuttavia il rollback delle modifiche già effettuate non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="df8db-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="df8db-150">Se si verifica un errore durante il quarto passaggio, viene eseguito l'aggiornamento dei membri che è possibile aggiornare.</span><span class="sxs-lookup"><span data-stu-id="df8db-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="df8db-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="df8db-151">Next Steps</span></span>  
 <span data-ttu-id="df8db-152">I metadati definiti dall'utente, gli attributi di file e le autorizzazioni utente e gruppo non sono inclusi nei pacchetti di distribuzione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="df8db-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="df8db-153">Dopo avere distribuito un modello, è necessario aggiornare questi elementi manualmente.</span><span class="sxs-lookup"><span data-stu-id="df8db-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="df8db-154">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="df8db-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="df8db-155">Aggiungere metadati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="df8db-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="df8db-156">Assegnare autorizzazioni per oggetti modello &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="df8db-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="df8db-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df8db-157">See Also</span></span>  
 [<span data-ttu-id="df8db-158">Distribuzione di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="df8db-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
