---
title: Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637962"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="207c0-102">Creare un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="207c0-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="207c0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]usare lo strumento MDSModelDeploy per creare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="207c0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="207c0-104">A seconda dei comandi specificati, il pacchetto può contenere:</span><span class="sxs-lookup"><span data-stu-id="207c0-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="207c0-105">Solo oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="207c0-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="207c0-106">Dati e oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="207c0-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="207c0-107">Per distribuire un pacchetto contenente solo oggetti modello, è possibile utilizzare la Distribuzione guidata modello nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="207c0-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="207c0-108">Per altre informazioni, vedere [Creare un pacchetto di distribuzione di modelli tramite la procedura guidata](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="207c0-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="207c0-109">Questa versione dello strumento MDSModelDeploy non può usare più di gigabyte (GB) di memoria.</span><span class="sxs-lookup"><span data-stu-id="207c0-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="207c0-110">Quando si creano o si distribuiscono modelli di grandi dimensioni utilizzando **gli oggetti modello e** l'opzione dati, è possibile che si verifichino errori di "memoria insufficiente" o "flusso troppo lungo".</span><span class="sxs-lookup"><span data-stu-id="207c0-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="207c0-111">Per risolvere questo problema, utilizzare la gestione temporanea MDS per distribuire i dati. in alternativa, eseguire l'aggiornamento a MDS 2016 o versione successiva, che include la versione aggiornata dello strumento MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="207c0-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="207c0-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="207c0-112">Prerequisites</span></span>  
 <span data-ttu-id="207c0-113">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="207c0-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="207c0-114">Di seguito sono riportate le autorizzazioni di base necessarie per eseguire lo strumento MDSModelDeploy:</span><span class="sxs-lookup"><span data-stu-id="207c0-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="207c0-115">Stessa autorizzazione di Windows di Gestione configurazione MDS (amministratore di Windows)</span><span class="sxs-lookup"><span data-stu-id="207c0-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="207c0-116">Autorizzazione DBA per il database MDS.</span><span class="sxs-lookup"><span data-stu-id="207c0-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="207c0-117">Di seguito sono riportate le autorizzazioni necessarie per creare il pacchetto tramite lo strumento MDSModelDeploy:</span><span class="sxs-lookup"><span data-stu-id="207c0-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="207c0-118">Autorizzazione dell'amministratore di modelli di MDS per il modello di dati</span><span class="sxs-lookup"><span data-stu-id="207c0-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="207c0-119">Autorizzazione per la funzione Gestione integrazione di MDS.</span><span class="sxs-lookup"><span data-stu-id="207c0-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="207c0-120">Di seguito sono riportate le autorizzazioni necessarie per distribuire un modello tramite lo strumento MDSModelDeploy:</span><span class="sxs-lookup"><span data-stu-id="207c0-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="207c0-121">Autorizzazione per la funzione Esplora di MDS</span><span class="sxs-lookup"><span data-stu-id="207c0-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="207c0-122">Autorizzazione per la funzione Gestione integrazione di MDS</span><span class="sxs-lookup"><span data-stu-id="207c0-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="207c0-123">Autorizzazione per la funzione Amministrazione sistema di MDS.</span><span class="sxs-lookup"><span data-stu-id="207c0-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="207c0-124">Di seguito sono riportate le autorizzazioni necessarie per elencare i modelli tramite lo strumento MDSModelDeploy:</span><span class="sxs-lookup"><span data-stu-id="207c0-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="207c0-125">Autorizzazione per la funzione Esplora di MDS</span><span class="sxs-lookup"><span data-stu-id="207c0-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="207c0-126">Autorizzazione dell'amministratore di modelli di MDS sul modello di dati per visualizzare il modello nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="207c0-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="207c0-127">È necessario che sia disponibile un modello affinché sia possibile crearne un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="207c0-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="207c0-128">Per altre informazioni, vedere [Creare un modello &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="207c0-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="207c0-129">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="207c0-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="207c0-130">Per creare un pacchetto di distribuzione modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="207c0-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="207c0-131">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="207c0-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="207c0-132">Spostarsi sul percorso di MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="207c0-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="207c0-133">Se MDS è stato installato nel percorso predefinito, il file si trova in *unità*: \Programmi\microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="207c0-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="207c0-134">Se MDS non è stato installato nel percorso predefinito, cercare MDSModelDeploy.exe nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="207c0-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="207c0-135">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="207c0-135">Optional.</span></span> <span data-ttu-id="207c0-136">Visualizzare le opzioni e la Guida.</span><span class="sxs-lookup"><span data-stu-id="207c0-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="207c0-137">Per visualizzare tutte le opzioni disponibili, digitare `MDSModelDeploy` e premere Invio.</span><span class="sxs-lookup"><span data-stu-id="207c0-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="207c0-138">Per visualizzare la Guida per un'opzione, digitare quanto segue, dove *OptionName* è il nome dell'opzione: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="207c0-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="207c0-139">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="207c0-139">Optional.</span></span> <span data-ttu-id="207c0-140">Se sono disponibili più applicazioni Web, determinare il nome del servizio in cui verrà eseguita la distribuzione digitando questo comando e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="207c0-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="207c0-141">Verrà restituito un elenco di valori, ad esempio `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="207c0-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="207c0-142">Il primo valore di questo elenco, in questo caso `MDS1`, è necessario per distribuire il modello.</span><span class="sxs-lookup"><span data-stu-id="207c0-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="207c0-143">Per creare un pacchetto contenente oggetti modello e dati, digitare quanto segue, dove *ModelName*, *VersionName*, *ServiceName*e *PackageName* sono rispettivamente i nomi del modello, della versione, del servizio e del file di output con estensione pkg:</span><span class="sxs-lookup"><span data-stu-id="207c0-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="207c0-144">Se non si vuole includere dati, non usare le opzioni `-version` e `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="207c0-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="207c0-145">Premi INVIO.</span><span class="sxs-lookup"><span data-stu-id="207c0-145">Press Enter.</span></span> <span data-ttu-id="207c0-146">Al termine della creazione del pacchetto, verrà visualizzato un messaggio "Operazione MDSModelDeploy completata".</span><span class="sxs-lookup"><span data-stu-id="207c0-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="207c0-147">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="207c0-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="207c0-148">Distribuire un pacchetto di distribuzione di modelli tramite MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="207c0-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="207c0-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="207c0-149">See Also</span></span>  
 <span data-ttu-id="207c0-150">[Opzioni di distribuzione del modello &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="207c0-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="207c0-151">Distribuzione di modelli &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="207c0-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
