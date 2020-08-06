---
title: Elaborare partizioni nel database dell'area di lavoro (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3a369705-43fa-4961-9045-32e06fbdde33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4a996e90b30794882535327ea3192d7e72818422
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712440"
---
# <a name="process-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="a4c12-102">Elaborare partizioni nel database dell'area di lavoro (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="a4c12-102">Process Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="a4c12-103">Le partizioni consentono di dividere una tabella in parti logiche.</span><span class="sxs-lookup"><span data-stu-id="a4c12-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="a4c12-104">Ogni partizione può quindi essere elaborata (aggiornata) indipendentemente dalle altre.</span><span class="sxs-lookup"><span data-stu-id="a4c12-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="a4c12-105">Nelle attività di questo argomento viene descritto come elaborare le partizioni nel database dell'area lavoro modello tramite la finestra di dialogo **Elabora partizioni** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4c12-105">The tasks in this topic describe how to process partitions in the model workspace database by using the **Process Partitions** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a4c12-106">Dopo aver distribuito un modello in un'altra istanza di Analysis Services, gli amministratori di database possono creare e gestire partizioni nel modello (distribuito) tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], script o utilizzando un pacchetto di IS.</span><span class="sxs-lookup"><span data-stu-id="a4c12-106">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], by script, or by using an IS package.</span></span> <span data-ttu-id="a4c12-107">Per altre informazioni, vedere [Creare e gestire partizioni di modelli tabulari &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a4c12-107">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="a4c12-108">Per elaborare una partizione</span><span class="sxs-lookup"><span data-stu-id="a4c12-108">To process a partition</span></span>  
  
1.  <span data-ttu-id="a4c12-109">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]fare clic sul menu **Modello** , scegliere **Elabora** (Aggiorna) e quindi fare clic su **Elabora partizioni**.</span><span class="sxs-lookup"><span data-stu-id="a4c12-109">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="a4c12-110">Nella casella di riepilogo **Modalità** selezionare una delle modalità di elaborazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4c12-110">In the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="a4c12-111">Mode</span><span class="sxs-lookup"><span data-stu-id="a4c12-111">Mode</span></span>|<span data-ttu-id="a4c12-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4c12-112">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="a4c12-113">**Elaborazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="a4c12-113">**Process Default**</span></span>|<span data-ttu-id="a4c12-114">Rileva lo stato di elaborazione di un oggetto partizione ed esegue l'elaborazione necessaria per recapitare oggetti partizione non elaborati o elaborati parzialmente in uno stato di elaborazione completa.</span><span class="sxs-lookup"><span data-stu-id="a4c12-114">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="a4c12-115">Vengono caricati i dati per le tabelle vuote e le partizioni; vengono compilate o ricompilate le gerarchie, le colonne calcolate e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="a4c12-115">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="a4c12-116">**Elaborazione completa**</span><span class="sxs-lookup"><span data-stu-id="a4c12-116">**Process Full**</span></span>|<span data-ttu-id="a4c12-117">Elabora un oggetto partizione e tutti gli oggetti in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="a4c12-117">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="a4c12-118">Quando viene eseguita l'elaborazione completa per un oggetto che è stato già elaborato, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vengono eliminati tutti i dati dell'oggetto, quindi quest'ultimo viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="a4c12-118">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="a4c12-119">Questo tipo di elaborazione è necessario quando è stata apportata una modifica strutturale a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4c12-119">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="a4c12-120">**Elaborare i dati**</span><span class="sxs-lookup"><span data-stu-id="a4c12-120">**Process Data**</span></span>|<span data-ttu-id="a4c12-121">Carica i dati in una partizione o in una tabella senza ricompilare le gerarchie o le relazioni oppure ricalcolare le colonne calcolate e le misure.</span><span class="sxs-lookup"><span data-stu-id="a4c12-121">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="a4c12-122">**Elaborazione pulizia**</span><span class="sxs-lookup"><span data-stu-id="a4c12-122">**Process Clear**</span></span>|<span data-ttu-id="a4c12-123">Rimuove tutti i dati da una partizione.</span><span class="sxs-lookup"><span data-stu-id="a4c12-123">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="a4c12-124">**Elaborazione aggiunta**</span><span class="sxs-lookup"><span data-stu-id="a4c12-124">**Process Add**</span></span>|<span data-ttu-id="a4c12-125">Aggiornare in modo incrementale la partizione con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="a4c12-125">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="a4c12-126">Nella colonna della casella di controllo **Elabora** selezionare le partizioni che si desidera elaborare con la modalità scelta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4c12-126">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c12-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4c12-127">See Also</span></span>  
 <span data-ttu-id="a4c12-128">[Partizioni &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a4c12-128">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a4c12-129">Creare e gestire partizioni nel database dell'area di lavoro &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="a4c12-129">Create and Manage Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](workspace-database-ssas-tabular.md)  
  
  
