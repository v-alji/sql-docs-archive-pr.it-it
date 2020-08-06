---
title: Creare e distribuire una cache per la trasformazione Ricerca | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623406"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="55593-102">Creazione e distribuzione di una cache per la trasformazione Ricerca</span><span class="sxs-lookup"><span data-stu-id="55593-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="55593-103">È possibile creare e distribuire un file di cache (.caw) per la trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="55593-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="55593-104">Il set di dati di riferimento è archiviato nel file di cache.</span><span class="sxs-lookup"><span data-stu-id="55593-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="55593-105">La trasformazione Ricerca esegue ricerche unendo in join i dati contenuti nelle colonne di input da un'origine dati connessa con le colonne nel set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="55593-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="55593-106">Creare un file di cache utilizzando una Gestione connessione cache e una trasformazione di tipo cache.</span><span class="sxs-lookup"><span data-stu-id="55593-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="55593-107">Per altre informazioni, vedere [Gestione connessione della cache](../../connection-manager/cache-connection-manager.md) e [Trasformazione Cache](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="55593-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="55593-108">Per sapere di più sulla trasformazione Ricerca e i file di cache, vedere [Trasformazione Ricerca](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="55593-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="55593-109">Per creare un file di cache</span><span class="sxs-lookup"><span data-stu-id="55593-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="55593-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="55593-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="55593-111">Nella scheda **Flusso di controllo** , aggiungere un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="55593-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="55593-112">Nella scheda **Flusso di dati** , aggiungere una trasformazione di tipo cache al flusso di dati e quindi connettere la trasformazione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="55593-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="55593-113">Configurare l'origine dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="55593-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="55593-114">Fare doppio clic sulla Trasformazione cache e quindi in **Editor trasformazione cache**, nella pagina **Gestione connessione** fare clic su **Nuova** per creare una nuova gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="55593-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="55593-115">In **Editor gestione connessione della cache**, nella scheda **Generale** configurare la Gestione connessione della cache per salvare la cache selezionando le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="55593-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="55593-116">Selezionare **Usa cache dei file**.</span><span class="sxs-lookup"><span data-stu-id="55593-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="55593-117">In **Nome file**, digitare il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="55593-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="55593-118">Il sistema crea il file quando viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55593-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55593-119">Il livello di protezione del pacchetto non si applica al file di cache.</span><span class="sxs-lookup"><span data-stu-id="55593-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="55593-120">Se il file di cache contiene informazioni riservate, utilizzare un elenco di controllo di accesso (ACL) per limitare l'accesso al percorso o alla cartella nella quale verrà archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="55593-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="55593-121">È consigliabile consentire l'accesso solo a determinati account.</span><span class="sxs-lookup"><span data-stu-id="55593-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="55593-122">Per altre informazioni, vedere [Accesso ai file utilizzati dai pacchetti](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="55593-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="55593-123">Fare clic sulla scheda **Colonne** e quindi specificare quali colonne sono le colonne di indice usando l'opzione **Posizione dell'indice** .</span><span class="sxs-lookup"><span data-stu-id="55593-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="55593-124">Per le colonne non dell'indice, la posizione è 0.</span><span class="sxs-lookup"><span data-stu-id="55593-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="55593-125">Per le colonne di indice, la posizione di indice è un numero sequenziale e positivo.</span><span class="sxs-lookup"><span data-stu-id="55593-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55593-126">Quando la trasformazione Ricerca viene configurata per utilizzare una Gestione connessione cache, è possibile eseguire il mapping solo delle colonne di indice nel set di dati di riferimento alle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="55593-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="55593-127">Inoltre, è necessario eseguire il mapping di tutte le colonne di indice.</span><span class="sxs-lookup"><span data-stu-id="55593-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="55593-128">Per altre informazioni, vedere [Editor gestione connessione cache](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="55593-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="55593-129">Configurare la Trasformazione Cache in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="55593-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="55593-130">Per altre informazioni, vedere [Editor trasformazione cache &#40;pagina Gestione connessioni&#41;](../../cache-transformation-editor-connection-manager-page.md) e [Editor trasformazione cache &#40;pagina Mapping&#41;](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="55593-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="55593-131">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55593-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="55593-132">Per distribuire un file di cache</span><span class="sxs-lookup"><span data-stu-id="55593-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="55593-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="55593-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="55593-134">Facoltativamente, creare una configurazione di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55593-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="55593-135">Per altre informazioni, vedere [Creazione di configurazioni dei pacchetti](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="55593-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="55593-136">Aggiungere il file di cache al progetto eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55593-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="55593-137">In Esplora soluzioni, selezionare il progetto aperto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="55593-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="55593-138">Scegliere **Aggiungi elemento esistente** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="55593-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="55593-139">Selezionare il file di cache e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="55593-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="55593-140">Il file viene visualizzato nella cartella **Varie** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="55593-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="55593-141">Configurare il progetto per creare un'utilità di distribuzione e quindi compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="55593-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="55593-142">Per altre informazioni, vedere [Creazione di un'utilità di distribuzione](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="55593-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="55593-143">Viene creato un file manifesto, \<*project name*>.SSISDeploymentManifest.xml che elenca i vari file nel progetto, i pacchetti e le configurazioni del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55593-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="55593-144">Distribuire il pacchetto nel file system.</span><span class="sxs-lookup"><span data-stu-id="55593-144">Deploy the package to the file system.</span></span> <span data-ttu-id="55593-145">Per altre informazioni, vedere [Distribuzione di pacchetti con l'utilità di distribuzione](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="55593-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55593-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55593-146">See Also</span></span>  
 [<span data-ttu-id="55593-147">Creazione di un'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="55593-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
