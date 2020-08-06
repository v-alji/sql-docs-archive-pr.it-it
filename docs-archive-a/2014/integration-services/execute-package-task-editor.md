---
title: Editor attività Esegui pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629499"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="1fe2b-102">Editor attività Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="1fe2b-103">Utilizzare l'editor attività Esegui pacchetto per configurare la relativa attività.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="1fe2b-104">L'attività Esegui pacchetto permette di estendere le funzionalità aziendali di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] consentendo ai pacchetti di eseguire altri pacchetti nell'ambito di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="1fe2b-105">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="1fe2b-106">Aprire l'editor attività Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="1fe2b-107">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="1fe2b-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="1fe2b-108">Impostare le opzioni nella pagina Pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="1fe2b-109">Impostare le opzioni nella pagina Associazioni di parametro</span><span class="sxs-lookup"><span data-stu-id="1fe2b-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="1fe2b-110">Aprire l'editor attività Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="1fe2b-111">Aprire un progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] contenente un'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="1fe2b-112">Fare clic con il pulsante destro del mouse sull'attività disponibile in Progettazione SSIS, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="1fe2b-113">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="1fe2b-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="1fe2b-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-114">**Name**</span></span>  
 <span data-ttu-id="1fe2b-115">Specificare un nome univoco per l'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="1fe2b-116">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fe2b-117">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="1fe2b-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-118">**Description**</span></span>  
 <span data-ttu-id="1fe2b-119">Digitare una descrizione dell'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="1fe2b-120">Impostare le opzioni nella pagina Pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="1fe2b-121">**ReferenceType**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-121">**ReferenceType**</span></span>  
 <span data-ttu-id="1fe2b-122">Selezionare **Riferimento al progetto** per pacchetti figlio inclusi nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="1fe2b-123">Selezionare **Riferimento esterno** per pacchetti figlio posizionati esternamente al pacchetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fe2b-124">L'opzione **ReferenceType** è di sola lettura e viene impostata su **Riferimento esterno** se il progetto in cui è contenuto il pacchetto non è stato convertito nel modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="1fe2b-125">Per altre informazioni sulla conversione, vedere [Distribuire progetti nel server Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="1fe2b-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="1fe2b-126">**Password**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-126">**Password**</span></span>  
 <span data-ttu-id="1fe2b-127">Se il pacchetto figlio è protetto con password, specificare la password del pacchetto figlio oppure fare clic sul pulsante con i puntini di sospensione (...) per creare una nuova password per il pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="1fe2b-128">Specificare se il pacchetto figlio viene eseguito nel processo del pacchetto padre o in un processo a parte.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="1fe2b-129">Per impostazione predefinita, la proprietà ExecuteOutOfProcess dell'attività Esegui pacchetto è impostata su `False` e il pacchetto figlio viene eseguito nello stesso processo del pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="1fe2b-130">Se si imposta questa proprietà su `true`, il pacchetto figlio viene eseguito in un processo separato.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="1fe2b-131">In questo modo è possibile che l'avvio del pacchetto figlio sia rallentato.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="1fe2b-132">Inoltre, se la proprietà viene impostata su `true`, non è possibile eseguire il debug del pacchetto in un'installazione di soli strumenti, ma è necessario installare il prodotto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fe2b-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="1fe2b-133">Per altre informazioni, vedere [Installazione di Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="1fe2b-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="1fe2b-134">Opzioni dinamiche relative a ReferenceType</span><span class="sxs-lookup"><span data-stu-id="1fe2b-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="1fe2b-135">ReferenceType = Riferimento esterno</span><span class="sxs-lookup"><span data-stu-id="1fe2b-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="1fe2b-136">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-136">**Location**</span></span>  
 <span data-ttu-id="1fe2b-137">Selezionare il percorso del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-137">Select the location of the child package.</span></span> <span data-ttu-id="1fe2b-138">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1fe2b-139">valore</span><span class="sxs-lookup"><span data-stu-id="1fe2b-139">Value</span></span>|<span data-ttu-id="1fe2b-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe2b-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1fe2b-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-141">**SQL Server**</span></span>|<span data-ttu-id="1fe2b-142">Impostare il percorso su un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fe2b-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="1fe2b-143">**File system**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-143">**File system**</span></span>|<span data-ttu-id="1fe2b-144">Impostare il percorso sul file system.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="1fe2b-145">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-145">**Connection**</span></span>  
 <span data-ttu-id="1fe2b-146">Selezionare il tipo di posizione di archiviazione del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="1fe2b-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="1fe2b-148">Viene visualizzato il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="1fe2b-149">ReferenceType = Riferimento al progetto</span><span class="sxs-lookup"><span data-stu-id="1fe2b-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="1fe2b-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="1fe2b-151">Selezionare un pacchetto contenuto nel progetto affinché sia considerato il pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="1fe2b-152">Opzioni dinamiche relative al percorso</span><span class="sxs-lookup"><span data-stu-id="1fe2b-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="1fe2b-153">Percorso = SQL Server</span><span class="sxs-lookup"><span data-stu-id="1fe2b-153">Location = SQL Server</span></span>  
 <span data-ttu-id="1fe2b-154">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-154">**Connection**</span></span>  
 <span data-ttu-id="1fe2b-155">Selezionare una gestione connessione OLE DB nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="1fe2b-156">**Argomenti correlati:** [Gestione connessione OLE DB](connection-manager/ole-db-connection-manager.md), [Configura gestione connessione OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="1fe2b-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="1fe2b-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-157">**PackageName**</span></span>  
 <span data-ttu-id="1fe2b-158">Digitare il nome del pacchetto figlio oppure fare clic sul pulsante con i puntini di sospensione (...) e quindi individuare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="1fe2b-159">Percorso = File system</span><span class="sxs-lookup"><span data-stu-id="1fe2b-159">Location = File system</span></span>  
 <span data-ttu-id="1fe2b-160">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-160">**Connection**</span></span>  
 <span data-ttu-id="1fe2b-161">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="1fe2b-162">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="1fe2b-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="1fe2b-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="1fe2b-164">Viene visualizzato il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="1fe2b-165">Impostare le opzioni nella pagina Associazioni di parametro</span><span class="sxs-lookup"><span data-stu-id="1fe2b-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="1fe2b-166">È possibile passare i valori del pacchetto padre o del progetto al pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="1fe2b-167">Il progetto deve utilizzare il modello di distribuzione del progetto e il pacchetto figlio deve essere contenuto nello stesso progetto in cui è contenuto il pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="1fe2b-168">Per informazioni sulla conversione dei progetti nel modello di distribuzione del progetto, vedere [Distribuire progetti nel server Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="1fe2b-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="1fe2b-169">**Parametro del pacchetto figlio**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-169">**Child package parameter**</span></span>  
 <span data-ttu-id="1fe2b-170">Immettere o selezionare un nome per il parametro del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="1fe2b-171">**Parametro o variabile di associazione**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="1fe2b-172">Selezionare il parametro o la variabile contenente il valore che si desidera passare al pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="1fe2b-173">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-173">**Add**</span></span>  
 <span data-ttu-id="1fe2b-174">Fare clic su questa opzione per eseguire il mapping di un parametro o una variabile a un parametro del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="1fe2b-175">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-175">**Remove**</span></span>  
 <span data-ttu-id="1fe2b-176">Fare clic su questa opzione per rimuovere un mapping tra un parametro o una variabile e un parametro del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="1fe2b-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
