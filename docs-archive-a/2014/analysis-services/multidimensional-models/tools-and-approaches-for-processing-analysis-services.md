---
title: Strumenti e approcci per l'elaborazione (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629057"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="d4c42-102">Strumenti e approcci per l'elaborazione (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d4c42-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="d4c42-103">L'elaborazione è un'operazione durante la quale tramite Analysis Services viene effettuata una query su un'origine dati relazionale e gli oggetti di Analysis Services vengono popolati utilizzando i dati ottenuti.</span><span class="sxs-lookup"><span data-stu-id="d4c42-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="d4c42-104">Un amministratore di sistema di Analysis Services può eseguire e monitorare l'elaborazione degli oggetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilizzando i seguenti approcci:</span><span class="sxs-lookup"><span data-stu-id="d4c42-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="d4c42-105">Eseguire l'analisi di impatto per comprendere le dipendenze tra oggetti e l'ambito delle operazioni</span><span class="sxs-lookup"><span data-stu-id="d4c42-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="d4c42-106">Elaborare oggetti singoli in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c42-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="d4c42-107">Elaborare oggetti singoli o più oggetti in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c42-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="d4c42-108">Eseguire l'analisi di impatto per esaminare un elenco di oggetti correlati che resteranno non elaborati in conseguenza dell'azione corrente</span><span class="sxs-lookup"><span data-stu-id="d4c42-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="d4c42-109">Generare ed eseguire uno script in una finestra Query XMLA di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per elaborare oggetti singoli o più oggetti</span><span class="sxs-lookup"><span data-stu-id="d4c42-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="d4c42-110">Utilizzare cmdlet di PowerShell per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c42-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="d4c42-111">Utilizzare flussi di controllo e attività nei pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c42-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="d4c42-112">Monitorare l'elaborazione con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d4c42-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="d4c42-113">Programmare una soluzione personalizzata utilizzando AMO.</span><span class="sxs-lookup"><span data-stu-id="d4c42-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="d4c42-114">Per altre informazioni, vedere [Programmazione di oggetti OLAP in AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="d4c42-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="d4c42-115">L'elaborazione è un'operazione estremamente configurabile, controllata da un set di opzioni che determinano se si verifica un'elaborazione completa o incrementale a livello di oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4c42-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="d4c42-116">Per altre informazioni sulle opzioni di elaborazione e gli oggetti, vedere [Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) ed [Elaborazione di oggetti di Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4c42-117">In questo argomento vengono descritti gli strumenti e gli approcci per l'elaborazione di modelli multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="d4c42-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="d4c42-118">Per ulteriori informazioni sull'elaborazione di modelli tabulari, vedere elaborare i dati del [database, della tabella o della partizione](../tabular-models/process-database-table-or-partition-analysis-services.md) ed [elaborare i dati &#40;SSAS tabulare&#41;](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="d4c42-119">Gestione di oggetti in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4c42-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d4c42-120">Avviare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e connettersi ad Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d4c42-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="d4c42-121">Fare clic con il pulsante destro del mouse sull'oggetto di Analysis Services che si vuole elaborare, quindi scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="d4c42-122">È possibile elaborare dati a uno qualsiasi dei livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4c42-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="d4c42-123">Database</span><span class="sxs-lookup"><span data-stu-id="d4c42-123">Databases</span></span>  
  
    -   <span data-ttu-id="d4c42-124">Cubi</span><span class="sxs-lookup"><span data-stu-id="d4c42-124">Cubes</span></span>  
  
    -   <span data-ttu-id="d4c42-125">Gruppi di misure o singole partizioni nel gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="d4c42-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="d4c42-126">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="d4c42-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="d4c42-127">Modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="d4c42-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="d4c42-128">Strutture di data mining</span><span class="sxs-lookup"><span data-stu-id="d4c42-128">Mining Structures</span></span>  
  
     <span data-ttu-id="d4c42-129">Gli oggetti di Analysis Services sono gerarchici.</span><span class="sxs-lookup"><span data-stu-id="d4c42-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="d4c42-130">Se si sceglie database, l'elaborazione può essere effettuata per tutti gli oggetti contenuti nel database.</span><span class="sxs-lookup"><span data-stu-id="d4c42-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="d4c42-131">L'effettiva esecuzione dell'elaborazione dipende dall'opzione di elaborazione selezionata e dallo stato dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4c42-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="d4c42-132">In particolare, se un oggetto non è elaborato, l'elaborazione del relativo oggetto padre comporterà l'elaborazione di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4c42-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="d4c42-133">Per altre informazioni sulle dipendenze tra oggetti, vedere [Elaborazione di oggetti di Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="d4c42-134">Nella finestra di dialogo **Elabora** , in **Opzioni elaborazione**usare il valore predefinito fornito o selezionare un'opzione diversa dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="d4c42-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="d4c42-135">Per altre informazioni su ogni opzione, vedere [Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="d4c42-136">Fare clic su **Analisi di impatto** per identificare ed eventualmente elaborare gli oggetti dipendenti sui quali influisce l'elaborazione degli oggetti elencati nella finestra di dialogo Elabora.</span><span class="sxs-lookup"><span data-stu-id="d4c42-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="d4c42-137">Facoltativamente, fare clic su **Modifica impostazioni** per modificare l'ordine di elaborazione, il comportamento di elaborazione in relazione a tipi specifici di errori e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d4c42-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="d4c42-138">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="d4c42-139">Nella finestra di dialogo Stato elaborazione viene visualizzato stato corrente per ogni comando.</span><span class="sxs-lookup"><span data-stu-id="d4c42-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="d4c42-140">Se un messaggio di stato è troncato, è possibile fare clic su **Visualizza dettagli** per leggere l'intero messaggio.</span><span class="sxs-lookup"><span data-stu-id="d4c42-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="d4c42-141">Elaborazione di oggetti in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="d4c42-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="d4c42-142">Avviare [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e aprire un progetto distribuito.</span><span class="sxs-lookup"><span data-stu-id="d4c42-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="d4c42-143">In Esplora soluzioni espandere la cartella **Dimensioni** del progetto distribuito.</span><span class="sxs-lookup"><span data-stu-id="d4c42-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="d4c42-144">Fare clic con il pulsante destro del mouse su una dimensione, quindi scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="d4c42-145">È possibile fare clic con il pulsante destro del mouse su più dimensioni per elaborare più oggetti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d4c42-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="d4c42-146">Per altre informazioni, vedere [Elaborazione batch &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="d4c42-147">Nella finestra di dialogo \*\*\*\* di elaborazione, in **Elenco oggetti** verificare che l’opzione per la colonna **Opzioni elaborazione**sia **Elaborazione completa**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="d4c42-148">In caso contrario, in **Opzioni elaborazione**fare clic sull’opzione e selezionare **Elaborazione completa** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d4c42-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="d4c42-149">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="d4c42-150">Al termine dell'elaborazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="d4c42-151">Eseguire l'analisi di effetto per identificare le dipendenze tra oggetti e l'ambito delle operazioni</span><span class="sxs-lookup"><span data-stu-id="d4c42-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="d4c42-152">Prima di elaborare un oggetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], è possibile analizzare l'effetto sugli oggetti correlati facendo clic su **Analisi di impatto** in una delle finestre di dialogo **Elabora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="d4c42-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="d4c42-153">Fare clic con il pulsante destro del mouse su una dimensione, un cubo, un gruppo di misure o una partizione per aprire una finestra di dialogo **Elabora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="d4c42-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="d4c42-154">Fare clic su **Analisi di impatto**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d4c42-155">esegue l’analisi del modello e indica i requisiti di rielaborazione per gli oggetti correlati a quello che è stato selezionato per l’elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d4c42-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="d4c42-156">Elaborazione di oggetti tramite XMLA</span><span class="sxs-lookup"><span data-stu-id="d4c42-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="d4c42-157">Avviare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e connettersi ad Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d4c42-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="d4c42-158">Fare clic con il pulsante destro del mouse sull'oggetto da elaborare, quindi scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="d4c42-159">Nella finestra di dialogo **Elabora** selezionare l'opzione di elaborazione che si vuole utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d4c42-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="d4c42-160">Modificare eventuali altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d4c42-160">Modify any other settings.</span></span> <span data-ttu-id="d4c42-161">Eseguire l'analisi di impatto per identificare le eventuali modifiche che potrebbe essere necessario apportare.</span><span class="sxs-lookup"><span data-stu-id="d4c42-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="d4c42-162">Fare clic su **Script** nella schermata **Elabora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="d4c42-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="d4c42-163">Verrà generato uno script XMLA e verrà aperta una finestra Query XMLA di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4c42-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="d4c42-164">Chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d4c42-164">Close the dialog box.</span></span> <span data-ttu-id="d4c42-165">Lo script contiene il comando e le opzioni di elaborazione specificati nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d4c42-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="d4c42-166">Facoltativamente, è possibile continuare ad aggiungere allo script se si desidera elaborare oggetti aggiuntivi nello stesso batch.</span><span class="sxs-lookup"><span data-stu-id="d4c42-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="d4c42-167">Per continuare, ripetere i passaggi precedenti, accodando lo script generato in modo da disporre di un solo script per tutte le operazioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d4c42-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="d4c42-168">Per un esempio, vedere [Pianificare attività amministrative SSAS con SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="d4c42-169">Sulla barra dei menu scegliere **Esegui**dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="d4c42-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="d4c42-170">Elaborazione di oggetti tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c42-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="d4c42-171">Avviando questa versione di SQL Server, è possibile utilizzare i cmdlet di PowerShell per Analysis Services per l'elaborazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4c42-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="d4c42-172">È possibile eseguire i cmdlet seguenti in modo interattivo o in script:</span><span class="sxs-lookup"><span data-stu-id="d4c42-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="d4c42-173">Cmdlet Invoke-ProcessCube</span><span class="sxs-lookup"><span data-stu-id="d4c42-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="d4c42-174">Cmdlet Invoke-ProcessDimension</span><span class="sxs-lookup"><span data-stu-id="d4c42-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="d4c42-175">Cmdlet Invoke-ProcessPartition</span><span class="sxs-lookup"><span data-stu-id="d4c42-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="d4c42-176">[cmdlet Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd)che può essere usato per eseguire script XMLA, MDX o DMX che includono comandi di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d4c42-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="d4c42-177">Monitoraggio dell'elaborazione degli oggetti utilizzando SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d4c42-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="d4c42-178">Connettersi a un'istanza di Analysis Services in SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="d4c42-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="d4c42-179">In Selezione eventi fare clic su **Mostra tutti gli eventi** per aggiungere tutti gli eventi all'elenco.</span><span class="sxs-lookup"><span data-stu-id="d4c42-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="d4c42-180">Scegliere gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4c42-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="d4c42-181">**Inizio del comando** e **Fine del comando** per mostrare l'inizio e la fine dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="d4c42-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="d4c42-182">**Errore** per acquisire eventuali errori</span><span class="sxs-lookup"><span data-stu-id="d4c42-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="d4c42-183">**Inizio del report di stato**, **Stato corrente del report di stato**e **Fine del report di stato** per creare un report sullo stato dell'elaborazione e mostrare le query SQL utilizzate per recuperare i dati</span><span class="sxs-lookup"><span data-stu-id="d4c42-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="d4c42-184">**Inizio dell'esecuzione di script MDX** e **Fine dell'esecuzione di script MDX** per mostrare i calcoli del cubo</span><span class="sxs-lookup"><span data-stu-id="d4c42-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="d4c42-185">Facoltativamente, aggiungere eventi di blocco in caso di diagnosi di problemi di prestazioni correlati all'elaborazione</span><span class="sxs-lookup"><span data-stu-id="d4c42-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="d4c42-186">Elaborare oggetti di Analysis Services utilizzando Integration Services</span><span class="sxs-lookup"><span data-stu-id="d4c42-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="d4c42-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]creare un pacchetto in cui viene usata l'attività Elaborazione Analysis Services per popolare automaticamente gli oggetti con nuovi dati quando si eseguono aggiornamenti regolari nel database relazionale di origine.</span><span class="sxs-lookup"><span data-stu-id="d4c42-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="d4c42-188">In **Casella degli strumenti SSIS**fare doppio clic su **Attività Elaborazione Analysis Services** per aggiungerla al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d4c42-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="d4c42-189">Modificare l'attività per specificare una connessione al database, gli oggetti da elaborare e l'opzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d4c42-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="d4c42-190">Per ulteriori informazioni sull'implementazione di questa attività, vedere [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="d4c42-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c42-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4c42-191">See Also</span></span>  
 [<span data-ttu-id="d4c42-192">Elaborazione di oggetti del modello multidimensionale</span><span class="sxs-lookup"><span data-stu-id="d4c42-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
