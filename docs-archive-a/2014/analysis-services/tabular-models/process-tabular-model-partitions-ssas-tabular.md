---
title: Elaborare partizioni di modelli tabulari (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712435"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="84c09-102">Elaborare partizioni di modelli tabulari (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="84c09-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="84c09-103">Le partizioni consentono di dividere una tabella in parti logiche.</span><span class="sxs-lookup"><span data-stu-id="84c09-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="84c09-104">Ogni partizione può quindi essere elaborata (aggiornata) indipendentemente dalle altre.</span><span class="sxs-lookup"><span data-stu-id="84c09-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="84c09-105">Nelle attività di questo argomento viene descritto come elaborare le partizioni in un database modello tramite la finestra di dialogo **Elabora partizioni** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84c09-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="84c09-106">Per elaborare una partizione</span><span class="sxs-lookup"><span data-stu-id="84c09-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="84c09-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla tabella contenente le partizioni che si desidera elaborare, quindi scegliere **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="84c09-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="84c09-108">Nella finestra di dialogo **Partizioni** fare clic sul pulsante Elabora in **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="84c09-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="84c09-109">Nella casella di riepilogo **modalità** della finestra di dialogo **Elabora partizione/i** selezionare una delle modalità di elaborazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="84c09-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="84c09-110">Mode</span><span class="sxs-lookup"><span data-stu-id="84c09-110">Mode</span></span>|<span data-ttu-id="84c09-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84c09-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="84c09-112">**Elaborazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="84c09-112">**Process Default**</span></span>|<span data-ttu-id="84c09-113">Rileva lo stato di elaborazione di un oggetto partizione ed esegue l'elaborazione necessaria per recapitare oggetti partizione non elaborati o elaborati parzialmente in uno stato di elaborazione completa.</span><span class="sxs-lookup"><span data-stu-id="84c09-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="84c09-114">Vengono caricati i dati per le tabelle vuote e le partizioni; vengono compilate o ricompilate le gerarchie, le colonne calcolate e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="84c09-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="84c09-115">**Elaborazione completa**</span><span class="sxs-lookup"><span data-stu-id="84c09-115">**Process Full**</span></span>|<span data-ttu-id="84c09-116">Elabora un oggetto partizione e tutti gli oggetti in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="84c09-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="84c09-117">Quando viene eseguita l'elaborazione completa per un oggetto che è stato già elaborato, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vengono eliminati tutti i dati dell'oggetto, quindi quest'ultimo viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="84c09-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="84c09-118">Questo tipo di elaborazione è necessario quando è stata apportata una modifica strutturale a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="84c09-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="84c09-119">**Elaborare i dati**</span><span class="sxs-lookup"><span data-stu-id="84c09-119">**Process Data**</span></span>|<span data-ttu-id="84c09-120">Carica i dati in una partizione o in una tabella senza ricompilare le gerarchie o le relazioni oppure ricalcolare le colonne calcolate e le misure.</span><span class="sxs-lookup"><span data-stu-id="84c09-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="84c09-121">**Elaborazione pulizia**</span><span class="sxs-lookup"><span data-stu-id="84c09-121">**Process Clear**</span></span>|<span data-ttu-id="84c09-122">Rimuove tutti i dati da una partizione.</span><span class="sxs-lookup"><span data-stu-id="84c09-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="84c09-123">**Elaborazione aggiunta**</span><span class="sxs-lookup"><span data-stu-id="84c09-123">**Process Add**</span></span>|<span data-ttu-id="84c09-124">Aggiornare in modo incrementale la partizione con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="84c09-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="84c09-125">Nella colonna della casella di controllo **Elabora** selezionare le partizioni che si desidera elaborare con la modalità scelta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c09-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c09-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84c09-126">See Also</span></span>  
 <span data-ttu-id="84c09-127">[Partizioni di modelli tabulari &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="84c09-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="84c09-128">Creare e gestire partizioni di modelli tabulari &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="84c09-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
