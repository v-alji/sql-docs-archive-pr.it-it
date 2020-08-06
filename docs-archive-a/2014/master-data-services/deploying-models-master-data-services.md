---
title: Distribuzione di modelli (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638442"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="eb35f-102">Distribuzione di modelli (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eb35f-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="eb35f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]un pacchetto è un file XML contenente una struttura di modello distribuibile e, facoltativamente, i dati del modello.</span><span class="sxs-lookup"><span data-stu-id="eb35f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="eb35f-104">Utilizzare i pacchetti del modello per spostare le copie di modelli da un ambiente MDS a un altro o per creare nuovi modelli nell'ambiente MDS esistente.</span><span class="sxs-lookup"><span data-stu-id="eb35f-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb35f-105">I pacchetti possono essere distribuiti solo nella versione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzata per crearli.</span><span class="sxs-lookup"><span data-stu-id="eb35f-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="eb35f-106">Pertanto non è possibile distribuire pacchetti creati in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] a [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="eb35f-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="eb35f-107">Strumenti per la distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="eb35f-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="eb35f-108">Per utilizzare i pacchetti di modello sono disponibili tre strumenti, a seconda delle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="eb35f-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="eb35f-109">**Strumento MDSModelDeploy**: per creare e distribuire oggetti modello e dati, usare lo strumento MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="eb35f-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="eb35f-110">Se durante l'installazione di MDS è stato selezionato il percorso predefinito, questo strumento si trova in *unità*: \Programmi\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="eb35f-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="eb35f-111">**Distribuzione guidata modello**: per creare e distribuire solo pacchetti della struttura del modello, usare la procedura guidata nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb35f-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="eb35f-112">Non è possibile utilizzare questa procedura guidata per distribuire dati.</span><span class="sxs-lookup"><span data-stu-id="eb35f-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="eb35f-113">**Editor pacchetti di modelli**: per modificare un pacchetto di modelli, usare ModelPackageEditor.exe che avvia la procedura guidata Editor pacchetti di modelli.</span><span class="sxs-lookup"><span data-stu-id="eb35f-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="eb35f-114">Questa procedura guidata viene utilizzata per modificare un pacchetto creato dallo strumento MDSModelDeploy o dalla Distribuzione guidata modello.</span><span class="sxs-lookup"><span data-stu-id="eb35f-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="eb35f-115">Se durante l'installazione di MDS è stato selezionato il percorso predefinito, questo strumento si trova in *unità*: \Programmi\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="eb35f-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb35f-116">È possibile utilizzare MDSDeployModel per creare un nuovo modello, creare un clone di un modello oppure aggiornare un modello esistente e i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="eb35f-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="eb35f-117">Se si utilizza lo strumento MDSModelDeploy per aggiornare un modello esistente e i relativi dati e nel pacchetto non è contenuto alcun attributo, entità o membro disponibile nel modello di destinazione, questi elementi non saranno eliminati dal modello tramite MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="eb35f-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="eb35f-118">Contenuto dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="eb35f-118">What Packages Contain</span></span>  
 <span data-ttu-id="eb35f-119">Un pacchetto del modello è un file XML salvato con estensione pkg.</span><span class="sxs-lookup"><span data-stu-id="eb35f-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="eb35f-120">Quando si crea un pacchetto di distribuzione, è possibile decidere se includere o meno dati.</span><span class="sxs-lookup"><span data-stu-id="eb35f-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="eb35f-121">Se si decide di includere dati, è necessario selezionare una versione dei dati da includere.</span><span class="sxs-lookup"><span data-stu-id="eb35f-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="eb35f-122">Tutti gli oggetti modello vengono inclusi in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="eb35f-122">All model objects are included in a package.</span></span> <span data-ttu-id="eb35f-123">Questi oggetti sono:</span><span class="sxs-lookup"><span data-stu-id="eb35f-123">These objects are:</span></span>  
  
-   <span data-ttu-id="eb35f-124">Entità</span><span class="sxs-lookup"><span data-stu-id="eb35f-124">Entities</span></span>  
  
-   <span data-ttu-id="eb35f-125">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb35f-125">Attributes</span></span>  
  
-   <span data-ttu-id="eb35f-126">Gruppi di attributi</span><span class="sxs-lookup"><span data-stu-id="eb35f-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="eb35f-127">Gerarchie</span><span class="sxs-lookup"><span data-stu-id="eb35f-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="eb35f-128">Raccolte</span><span class="sxs-lookup"><span data-stu-id="eb35f-128">Collections</span></span>  
  
-   <span data-ttu-id="eb35f-129">Regole business</span><span class="sxs-lookup"><span data-stu-id="eb35f-129">Business rules</span></span>  
  
-   <span data-ttu-id="eb35f-130">Flag versione</span><span class="sxs-lookup"><span data-stu-id="eb35f-130">Version flags</span></span>  
  
-   <span data-ttu-id="eb35f-131">Viste sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="eb35f-131">Subscription views</span></span>  
  
 <span data-ttu-id="eb35f-132">Non sono inclusi i metadati definiti dall'utente, gli attributi file e le autorizzazioni di utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="eb35f-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="eb35f-133">Dopo avere distribuito un modello, è necessario aggiornare questi elementi manualmente.</span><span class="sxs-lookup"><span data-stu-id="eb35f-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="eb35f-134">Pacchetti di esempio</span><span class="sxs-lookup"><span data-stu-id="eb35f-134">Sample Packages</span></span>  
 <span data-ttu-id="eb35f-135">I file di pacchetto di esempio sono inclusi nell'installazione di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb35f-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="eb35f-136">Questi file di pacchetto si trovano nella directory Master Data Services\Samples\Packages in cui è stato installato [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb35f-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="eb35f-137">Quando si distribuiscono questi pacchetti di esempio tramite lo strumento MDSModelDeploy, i modelli di esempio vengono creati e popolati con dati.</span><span class="sxs-lookup"><span data-stu-id="eb35f-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="eb35f-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="eb35f-138">Related Tasks</span></span>  
  
|<span data-ttu-id="eb35f-139">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="eb35f-139">Task Description</span></span>|<span data-ttu-id="eb35f-140">Argomento</span><span class="sxs-lookup"><span data-stu-id="eb35f-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="eb35f-141">Creare un nuovo pacchetto di distribuzione di oggetti modello e/o dati tramite lo strumento MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="eb35f-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="eb35f-142">Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="eb35f-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="eb35f-143">Creare un nuovo pacchetto di distribuzione solo di oggetti modello utilizzando la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="eb35f-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="eb35f-144">Creare un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="eb35f-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="eb35f-145">Distribuite un pacchetto di oggetti modello e/o dati tramite lo strumento MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="eb35f-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="eb35f-146">Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="eb35f-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="eb35f-147">Distribuire un pacchetto solo di oggetti modello utilizzando la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="eb35f-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="eb35f-148">Distribuire un pacchetto di distribuzione di modelli tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="eb35f-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="eb35f-149">Modificare un pacchetto di distribuzione del modello per distribuire parti selezionate di un modello, anziché l'intero modello.</span><span class="sxs-lookup"><span data-stu-id="eb35f-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="eb35f-150">Modificare un pacchetto di distribuzione di modelli</span><span class="sxs-lookup"><span data-stu-id="eb35f-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="eb35f-151">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="eb35f-151">Related Content</span></span>  
  
-   [<span data-ttu-id="eb35f-152">Opzioni di distribuzione dei modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eb35f-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
