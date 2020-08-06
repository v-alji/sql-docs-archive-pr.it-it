---
title: Elaborare manualmente i dati (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635837"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="c8fa6-102">Elaborare manualmente i dati (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c8fa6-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="c8fa6-103">In questo argomento viene illustrato come elaborare manualmente i dati dell'area di lavoro in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8fa6-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c8fa6-104">Quando si crea un modello tabulare in cui vengono utilizzati dati esterni, è possibile aggiornare manualmente i dati tramite il comando Elabora.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="c8fa6-105">È possibile elaborare una sola tabella, tutte le tabelle nel modello o una o più partizioni.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="c8fa6-106">Ogni volta che si elaborano i dati, potrebbe anche essere necessario ricalcolarli.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="c8fa6-107">Per elaborazione dei dati si intende il recupero dei dati più recenti dalle origini esterne.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="c8fa6-108">Con ricalcolo si intende l'aggiornamento del risultato di qualsiasi formula in cui vengono utilizzati i dati.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="c8fa6-109">Sezioni dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="c8fa6-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="c8fa6-110">Elaborare manualmente i dati</span><span class="sxs-lookup"><span data-stu-id="c8fa6-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="c8fa6-111">Stato elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="c8fa6-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="c8fa6-112">Elaborare manualmente i dati</span><span class="sxs-lookup"><span data-stu-id="c8fa6-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="c8fa6-113">Per elaborare i dati per una sola tabella o tutte le tabelle in un modello</span><span class="sxs-lookup"><span data-stu-id="c8fa6-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="c8fa6-114">In Progettazione modelli fare clic sulla tabella che si desidera elaborare.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="c8fa6-115">Nel menu **Modello** fare clic su **Elabora**, quindi su **Elabora** o **Elabora tutto**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="c8fa6-116">Per elaborare i dati di tutte le tabelle utilizzando la stessa connessione</span><span class="sxs-lookup"><span data-stu-id="c8fa6-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="c8fa6-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]fare clic sul menu **Modello** , quindi scegliere **Connessioni esistenti**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="c8fa6-118">Nella finestra di dialogo **Connessioni esistenti** selezionare una connessione, quindi fare clic su **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="c8fa6-119">Per elaborare i dati di una o più partizioni</span><span class="sxs-lookup"><span data-stu-id="c8fa6-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="c8fa6-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Elabora** dal menu **Modello**, quindi fare clic su **Elabora partizioni**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="c8fa6-121">In **Modalità** della finestra di dialogo **Elabora partizioni**selezionare una delle modalità di elaborazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8fa6-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="c8fa6-122">Mode</span><span class="sxs-lookup"><span data-stu-id="c8fa6-122">Mode</span></span>|<span data-ttu-id="c8fa6-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8fa6-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="c8fa6-124">**Elaborazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-124">**Process Default**</span></span>|<span data-ttu-id="c8fa6-125">Rileva lo stato di elaborazione di un oggetto partizione ed esegue l'elaborazione necessaria per recapitare oggetti partizione non elaborati o elaborati parzialmente in uno stato di elaborazione completa.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="c8fa6-126">Vengono caricati i dati per le tabelle vuote e le partizioni; vengono compilate o ricompilate le gerarchie, le colonne calcolate e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="c8fa6-127">**Elaborazione completa**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-127">**Process Full**</span></span>|<span data-ttu-id="c8fa6-128">Elabora un oggetto partizione e tutti gli oggetti in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="c8fa6-129">Quando viene eseguita l'elaborazione completa per un oggetto che è stato già elaborato, in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] vengono eliminati tutti i dati dell'oggetto, quindi quest'ultimo viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="c8fa6-130">Questo tipo di elaborazione è necessario quando è stata apportata una modifica strutturale a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="c8fa6-131">**Elaborare i dati**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-131">**Process Data**</span></span>|<span data-ttu-id="c8fa6-132">Carica i dati in una partizione o in una tabella senza ricompilare le gerarchie o le relazioni oppure ricalcolare le colonne calcolate e le misure.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="c8fa6-133">**Elaborazione pulizia**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-133">**Process Clear**</span></span>|<span data-ttu-id="c8fa6-134">Rimuove tutti i dati da una partizione.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="c8fa6-135">**Elaborazione aggiunta**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-135">**Process Add**</span></span>|<span data-ttu-id="c8fa6-136">Aggiornare in modo incrementale la partizione con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="c8fa6-137">Nell'elenco delle partizioni selezionare le partizioni da elaborare, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a><span data-ttu-id="c8fa6-138">Stato elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="c8fa6-138">Data Process Progress</span></span>  
 <span data-ttu-id="c8fa6-139">La finestra di dialogo **Stato elaborazione dati** consente di monitorare l'elaborazione di dati importati nel modello da un'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="c8fa6-140">Per accedere a questa finestra di dialogo, scegliere **Elabora partizioni** , **Elabora tabella**o **Elabora tutto** dal menu **Modello**.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="c8fa6-141">**Status**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-141">**Status**</span></span>  
 <span data-ttu-id="c8fa6-142">Viene indicato se l'operazione di elaborazione ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="c8fa6-143">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-143">**Details**</span></span>  
 <span data-ttu-id="c8fa6-144">Vengono elencate le tabelle e le visualizzazioni importate, il numero di righe importato e viene fornito un collegamento a un report di qualsiasi problema.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="c8fa6-145">**Arresta aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="c8fa6-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="c8fa6-146">Fare clic per arrestare l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-146">Click to halt the process operation.</span></span> <span data-ttu-id="c8fa6-147">Questa opzione è utile se l'operazione è troppo lunga o se si sono verificati troppi errori.</span><span class="sxs-lookup"><span data-stu-id="c8fa6-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fa6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8fa6-148">See Also</span></span>  
 <span data-ttu-id="c8fa6-149">[Elaborare dati &#40;SSAS tabulare&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c8fa6-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c8fa6-150">Risolvere i problemi relativi all'elaborazione dei dati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c8fa6-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
