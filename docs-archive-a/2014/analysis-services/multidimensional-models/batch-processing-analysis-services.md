---
title: Elaborazione batch (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624407"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="76b59-102">Elaborazione batch (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="76b59-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="76b59-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]è possibile utilizzare il comando Batch per inviare al server più comandi di elaborazione in una sola richiesta.</span><span class="sxs-lookup"><span data-stu-id="76b59-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="76b59-104">Tramite l'elaborazione batch è possibile determinare gli oggetti da elaborare e l'ordine di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="76b59-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="76b59-105">Un batch può inoltre essere eseguito come una serie di processi autonomi o come una transazione nella quale l'esito negativo di un processo causa il rollback dell'intero batch.</span><span class="sxs-lookup"><span data-stu-id="76b59-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="76b59-106">L'elaborazione batch consente di aumentare al massimo la disponibilità dei dati consolidando e riducendo la quantità di tempo necessaria per eseguire il commit delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="76b59-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="76b59-107">Quando una dimensione viene elaborata completamente, qualsiasi partizione in cui viene utilizzata tale dimensione viene contrassegnata come non elaborata</span><span class="sxs-lookup"><span data-stu-id="76b59-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="76b59-108">e, di conseguenza, i cubi contenenti le partizioni non elaborate non sono disponibili per l'esplorazione.</span><span class="sxs-lookup"><span data-stu-id="76b59-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="76b59-109">È possibile ottenere questo risultato con un processo di elaborazione batch elaborando le dimensioni insieme alle partizioni interessate.</span><span class="sxs-lookup"><span data-stu-id="76b59-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="76b59-110">L'esecuzione del processo di elaborazione batch come transazione consente di verificare che tutti gli oggetti inclusi nella transazione rimangano disponibili per l'esecuzione di query fino al completamento dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="76b59-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="76b59-111">Durante il commit delle modifiche da parte della transazione, vengono applicati blocchi agli oggetti interessati, rendendoli temporaneamente non disponibili; tuttavia il tempo necessario per eseguire il commit delle modifiche è inferiore rispetto a quello per elaborare singolarmente gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="76b59-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="76b59-112">Nelle procedure di questo argomento vengono illustrati i passaggi per l'elaborazione completa di dimensioni e partizioni.</span><span class="sxs-lookup"><span data-stu-id="76b59-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="76b59-113">L'elaborazione batch può includere anche altre opzioni di elaborazione, ad esempio l'elaborazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="76b59-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="76b59-114">Per il corretto funzionamento di queste procedure, è consigliabile utilizzare un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esistente contenente almeno due dimensioni e una partizione.</span><span class="sxs-lookup"><span data-stu-id="76b59-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="76b59-115">Questo argomento include le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76b59-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="76b59-116">Elaborazione batch in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="76b59-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="76b59-117">Elaborazione batch con XMLA in Management Studio</span><span class="sxs-lookup"><span data-stu-id="76b59-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a> <span data-ttu-id="76b59-118">Elaborazione batch in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="76b59-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="76b59-119">Prima di poter elaborare gli oggetti in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], è necessario distribuire il progetto contenente gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="76b59-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="76b59-120">Per altre informazioni, vedere [Distribuire progetti di Analysis Services &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="76b59-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="76b59-121">Aprire [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76b59-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="76b59-122">Aprire un progetto che è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="76b59-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="76b59-123">In Esplora soluzioni espandere la cartella **Dimensioni** del progetto distribuito.</span><span class="sxs-lookup"><span data-stu-id="76b59-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="76b59-124">Tenendo premuto il tasto CTRL, fare clic su ogni dimensione elencata in **Dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="76b59-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="76b59-125">Fare clic con il pulsante destro del mouse sulle dimensioni selezionate, quindi scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="76b59-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="76b59-126">Tenendo premuto il tasto CTRL, fare clic su ogni dimensione elencata in **Elenco oggetti**.</span><span class="sxs-lookup"><span data-stu-id="76b59-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="76b59-127">Fare clic con il pulsante destro del mouse sulle dimensioni selezionate, quindi scegliere **Elaborazione completa**.</span><span class="sxs-lookup"><span data-stu-id="76b59-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="76b59-128">Per personalizzare il processo batch, fare clic su **Cambia impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="76b59-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="76b59-129">In **Opzioni di elaborazione**contrassegnare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76b59-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="76b59-130">**Ordine di elaborazione** è impostato su **Sequenziale**e **Modalità transazione** è impostato su **Una sola transazione**.</span><span class="sxs-lookup"><span data-stu-id="76b59-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="76b59-131">**Opzione tabella writeback** è impostato su **Use existing**(Usa esistente).</span><span class="sxs-lookup"><span data-stu-id="76b59-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="76b59-132">In **Oggetti interessati**selezionare la casella di controllo **Elabora oggetti interessati** .</span><span class="sxs-lookup"><span data-stu-id="76b59-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="76b59-133">Fare clic sulla scheda **errori chiave dimensione** . Verificare che l'opzione **Usa configurazione errori predefinita** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="76b59-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="76b59-134">Fare clic su **OK** per chiudere la schermata **Cambia impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="76b59-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="76b59-135">Fare clic su **Esegui** nella schermata **Elabora oggetti** per avviare il processo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="76b59-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="76b59-136">Quando nella casella **Stato** viene visualizzato **Elaborazione completata correttamente**, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="76b59-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="76b59-137">Fare clic su **Chiudi** nella schermata **Elabora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="76b59-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="76b59-138">Elaborazione batch con XMLA in Management Studio</span><span class="sxs-lookup"><span data-stu-id="76b59-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="76b59-139">È possibile creare uno script XMLA che esegue l'elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="76b59-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="76b59-140">Iniziare generando uno script XMLA in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per ogni oggetto, quindi combinarli in una sola query XMLA da eseguire in modo interattivo o in un'attività pianificata.</span><span class="sxs-lookup"><span data-stu-id="76b59-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="76b59-141">Per istruzioni dettagliate, vedere l' **esempio 2** in [Pianificare attività amministrative SSAS con SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span><span class="sxs-lookup"><span data-stu-id="76b59-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76b59-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76b59-142">See Also</span></span>  
 [<span data-ttu-id="76b59-143">Elaborazione di oggetti del modello multidimensionale</span><span class="sxs-lookup"><span data-stu-id="76b59-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
