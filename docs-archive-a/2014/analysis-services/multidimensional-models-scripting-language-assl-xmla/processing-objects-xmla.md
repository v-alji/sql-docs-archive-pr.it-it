---
title: Elaborazione di oggetti (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723187"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="43a29-102">Elaborazione di oggetti (XMLA)</span><span class="sxs-lookup"><span data-stu-id="43a29-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="43a29-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] l'elaborazione è il passaggio o la serie di passaggi che trasformano i dati in informazioni per l'analisi aziendale.</span><span class="sxs-lookup"><span data-stu-id="43a29-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="43a29-104">L'elaborazione varia a seconda del tipo di oggetto, ma rappresenta sempre una fase della trasformazione dei dati in informazioni.</span><span class="sxs-lookup"><span data-stu-id="43a29-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="43a29-105">Per elaborare un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oggetto, è possibile usare il comando [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="43a29-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="43a29-106">In un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] il comando `Process` può elaborare gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="43a29-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="43a29-107">Cubi</span><span class="sxs-lookup"><span data-stu-id="43a29-107">Cubes</span></span>  
  
-   <span data-ttu-id="43a29-108">Database</span><span class="sxs-lookup"><span data-stu-id="43a29-108">Databases</span></span>  
  
-   <span data-ttu-id="43a29-109">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="43a29-109">Dimensions</span></span>  
  
-   <span data-ttu-id="43a29-110">Gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="43a29-110">Measure groups</span></span>  
  
-   <span data-ttu-id="43a29-111">Modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="43a29-111">Mining models</span></span>  
  
-   <span data-ttu-id="43a29-112">Strutture di data mining</span><span class="sxs-lookup"><span data-stu-id="43a29-112">Mining structures</span></span>  
  
-   <span data-ttu-id="43a29-113">Partizioni</span><span class="sxs-lookup"><span data-stu-id="43a29-113">Partitions</span></span>  
  
 <span data-ttu-id="43a29-114">Per controllare l'elaborazione di oggetti, al comando `Process` sono associate varie proprietà che possono essere impostate.</span><span class="sxs-lookup"><span data-stu-id="43a29-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="43a29-115">Il comando `Process` dispone di proprietà che controllano la quantità dell'elaborazione e gli oggetti che verranno elaborati e indicano se utilizzare associazioni out-of-line nonché le modalità di gestione degli errori e delle tabelle writeback.</span><span class="sxs-lookup"><span data-stu-id="43a29-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="43a29-116">Impostazione delle opzioni di elaborazione</span><span class="sxs-lookup"><span data-stu-id="43a29-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="43a29-117">La proprietà [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) del `Process` comando specifica l'opzione di elaborazione da utilizzare durante l'elaborazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="43a29-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="43a29-118">Per altre informazioni sulle opzioni di elaborazione, vedere [Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="43a29-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="43a29-119">Nella tabella seguente sono elencate le costanti per la proprietà `Type` e sono indicati i vari oggetti che possono essere elaborati utilizzando ciascuna costante.</span><span class="sxs-lookup"><span data-stu-id="43a29-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="43a29-120">Valore della proprietà `Type`</span><span class="sxs-lookup"><span data-stu-id="43a29-120">`Type` value</span></span>|<span data-ttu-id="43a29-121">Oggetti applicabili</span><span class="sxs-lookup"><span data-stu-id="43a29-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="43a29-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="43a29-122">*ProcessFull*</span></span>|<span data-ttu-id="43a29-123">Cubo, database, dimensione, gruppo di misure, modello di data mining, struttura di data mining, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="43a29-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="43a29-124">*ProcessAdd*</span></span>|<span data-ttu-id="43a29-125">Dimensione, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-125">Dimension, partition</span></span>|  
|<span data-ttu-id="43a29-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="43a29-126">*ProcessUpdate*</span></span>|<span data-ttu-id="43a29-127">Dimension</span><span class="sxs-lookup"><span data-stu-id="43a29-127">Dimension</span></span>|  
|<span data-ttu-id="43a29-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="43a29-128">*ProcessIndexes*</span></span>|<span data-ttu-id="43a29-129">Dimensione, cubo, gruppo di misure, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="43a29-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="43a29-130">*ProcessData*</span></span>|<span data-ttu-id="43a29-131">Dimensione, cubo, gruppo di misure, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="43a29-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="43a29-132">*ProcessDefault*</span></span>|<span data-ttu-id="43a29-133">Cubo, database, dimensione, gruppo di misure, modello di data mining, struttura di data mining, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="43a29-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="43a29-134">*ProcessClear*</span></span>|<span data-ttu-id="43a29-135">Cubo, database, dimensione, gruppo di misure, modello di data mining, struttura di data mining, partizione</span><span class="sxs-lookup"><span data-stu-id="43a29-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="43a29-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="43a29-136">*ProcessStructure*</span></span>|<span data-ttu-id="43a29-137">Cubo, struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="43a29-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="43a29-138">*ProcessClearStructureOnly*</span><span class="sxs-lookup"><span data-stu-id="43a29-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="43a29-139">Struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="43a29-139">Mining structure</span></span>|  
|<span data-ttu-id="43a29-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="43a29-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="43a29-141">Cubo</span><span class="sxs-lookup"><span data-stu-id="43a29-141">Cube</span></span>|  
  
 <span data-ttu-id="43a29-142">Per ulteriori informazioni sull'elaborazione di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oggetti, vedere elaborazione di oggetti del [modello multidimensionale](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="43a29-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="43a29-143">Specifica degli oggetti da elaborare</span><span class="sxs-lookup"><span data-stu-id="43a29-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="43a29-144">La proprietà [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Process` comando contiene l'identificatore di oggetto dell'oggetto da elaborare.</span><span class="sxs-lookup"><span data-stu-id="43a29-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="43a29-145">In un comando `Process` è possibile specificare solo un oggetto, ma l'elaborazione di un oggetto determina anche l'elaborazione di qualsiasi oggetto figlio.</span><span class="sxs-lookup"><span data-stu-id="43a29-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="43a29-146">L'elaborazione di un gruppo di misure in un cubo, ad esempio, determina l'elaborazione di tutte le partizioni di tale gruppo, mentre l'elaborazione di un database determina l'elaborazione di tutti gli oggetti, quali cubi, dimensioni e strutture di data mining, contenuti nel database.</span><span class="sxs-lookup"><span data-stu-id="43a29-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="43a29-147">Se si imposta l'attributo `ProcessAffectedObjects` del comando `Process` su true, viene elaborato qualsiasi oggetto correlato interessato dall'elaborazione di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="43a29-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="43a29-148">Se, ad esempio, una dimensione viene aggiornata in modo incrementale tramite l'opzione di elaborazione *ProcessUpdate* nel `Process` comando, qualsiasi partizione le cui aggregazioni vengono invalidate a causa dei membri aggiunti o eliminati viene elaborata anche da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se `ProcessAffectedObjects` è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="43a29-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="43a29-149">In questo caso, un unico comando `Process` può elaborare più oggetti in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ma in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vengono determinati gli ulteriori oggetti da elaborare oltre all'oggetto specificato nel comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="43a29-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="43a29-150">È possibile tuttavia elaborare più oggetti contemporaneamente, ad esempio dimensioni, tramite più comandi `Process` in un comando `Batch`.</span><span class="sxs-lookup"><span data-stu-id="43a29-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="43a29-151">Le operazioni batch consentono di controllare a livello più dettagliato l'elaborazione in serie o parallela di oggetti in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] rispetto all'utilizzo dell'attributo `ProcessAffectedObjects` e consentono di ottimizzare l'approccio all'elaborazione per i database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="43a29-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="43a29-152">Per ulteriori informazioni sull'esecuzione di operazioni batch, vedere [esecuzione di operazioni batch &#40;&#41;XMLA ](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="43a29-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="43a29-153">Specifica di associazioni out-of-line</span><span class="sxs-lookup"><span data-stu-id="43a29-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="43a29-154">Se il `Process` comando non è contenuto da un `Batch` comando, è possibile specificare le associazioni out-of-line nelle proprietà [bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)e [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) del `Process` comando per gli oggetti da elaborare.</span><span class="sxs-lookup"><span data-stu-id="43a29-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="43a29-155">Le associazioni out-of-line sono riferimenti a origini dati, viste origine dati e altri oggetti in cui l'associazione è presente solo durante l'esecuzione del comando `Process`. Tali associazioni sostituiscono qualsiasi associazione esistente associata agli oggetti elaborati.</span><span class="sxs-lookup"><span data-stu-id="43a29-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="43a29-156">Se non è specificata alcuna associazione out-of-line, vengono utilizzate le associazioni attualmente associate agli oggetti da elaborare.</span><span class="sxs-lookup"><span data-stu-id="43a29-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="43a29-157">Le associazioni out-of-line vengono utilizzate nelle seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="43a29-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="43a29-158">Elaborazione incrementale di una partizione in cui è necessario specificare una tabella dei fatti alternativa o un filtro sulla tabella dei fatti esistente per garantire che le righe non vengono contate due volte.</span><span class="sxs-lookup"><span data-stu-id="43a29-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="43a29-159">Utilizzo di un'attività flusso di dati in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per fornire dati durante l'elaborazione di una dimensione, un modello di data mining o una partizione.</span><span class="sxs-lookup"><span data-stu-id="43a29-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="43a29-160">Le associazioni out-of-line vengono descritte come parte del linguaggio ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="43a29-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="43a29-161">Per ulteriori informazioni sulle associazioni out-of-line in ASSL, vedere [origini dati e associazioni &#40;SSAS multidimensionale&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="43a29-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="43a29-162">Aggiornamento incrementale di partizioni</span><span class="sxs-lookup"><span data-stu-id="43a29-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="43a29-163">Per eseguire l'aggiornamento incrementale di una partizione già elaborata, è necessario utilizzare un'associazione out-of-line poiché l'associazione specificata per la partizione fa riferimento a dati della tabella dei fatti già aggregati all'interno della partizione.</span><span class="sxs-lookup"><span data-stu-id="43a29-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="43a29-164">Se si esegue l'aggiornamento incrementale di una partizione già elaborata tramite il comando `Process`, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vengono effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43a29-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="43a29-165">Creazione di una partizione temporanea con una struttura identica a quella della partizione da aggiornare in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="43a29-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="43a29-166">Elaborazione della partizione temporanea tramite l'associazione out-of-line specificata nel comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="43a29-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="43a29-167">Unione della partizione temporanea con la partizione esistente selezionata.</span><span class="sxs-lookup"><span data-stu-id="43a29-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="43a29-168">Per ulteriori informazioni sull'Unione di partizioni mediante XML for Analysis (XMLA), vedere [Unione di partizioni &#40;&#41;XMLA ](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="43a29-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="43a29-169">Gestione degli errori di elaborazione</span><span class="sxs-lookup"><span data-stu-id="43a29-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="43a29-170">La proprietà [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) del `Process` comando consente di specificare come gestire gli errori rilevati durante l'elaborazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="43a29-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="43a29-171">Ad esempio durante l'elaborazione di una dimensione in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] viene rilevato un valore duplicato nella colonna chiave dell'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="43a29-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="43a29-172">Poiché le chiavi dell'attributo devono essere univoche, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] elimina i record duplicati.</span><span class="sxs-lookup"><span data-stu-id="43a29-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="43a29-173">In base alla proprietà di [duplicazione](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) di `ErrorConfiguration` , è [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] possibile:</span><span class="sxs-lookup"><span data-stu-id="43a29-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="43a29-174">Continuazione dell'elaborazione della dimensione poiché il messaggio viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="43a29-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="43a29-175">Restituzione di un messaggio che indica che in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è stata rilevata una chiave duplicata e continuazione dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="43a29-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="43a29-176">Le condizioni analoghe per cui `ErrorConfiguration` specifica opzioni durante un comando `Process` sono numerose.</span><span class="sxs-lookup"><span data-stu-id="43a29-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="43a29-177">Gestione di tabelle writeback</span><span class="sxs-lookup"><span data-stu-id="43a29-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="43a29-178">Se il comando `Process` rileva una partizione abilitata per la scrittura oppure un cubo o un gruppo di misure per tale partizione la cui elaborazione non è ancora stata completata, è possibile che per tale partizione non esista una tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="43a29-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="43a29-179">La proprietà [WriteBackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) del `Process` comando determina se [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve creare una tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="43a29-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="43a29-180">Esempi</span><span class="sxs-lookup"><span data-stu-id="43a29-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="43a29-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43a29-181">Description</span></span>  
 <span data-ttu-id="43a29-182">Nell'esempio seguente viene elaborato completamente il database di esempio [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43a29-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="43a29-183">Codice</span><span class="sxs-lookup"><span data-stu-id="43a29-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="43a29-184">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43a29-184">Description</span></span>  
 <span data-ttu-id="43a29-185">Nell'esempio seguente viene elaborata in modo incrementale la partizione **Internet_Sales_2004** nel gruppo di misure **Internet Sales** del cubo **Adventure Works DW** del [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] database di esempio [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43a29-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="43a29-186">Il `Process` comando aggiunge le aggregazioni per le date di ordine successive al 31 dicembre 2006 alla partizione utilizzando un'associazione di query out-of-line nella `Bindings` proprietà del `Process` comando per recuperare le righe della tabella dei fatti da cui generare le aggregazioni da aggiungere alla partizione.</span><span class="sxs-lookup"><span data-stu-id="43a29-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="43a29-187">Codice</span><span class="sxs-lookup"><span data-stu-id="43a29-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
