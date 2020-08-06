---
title: Elaborare dati (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725039"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="62634-102">Elaborare dati (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="62634-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="62634-103">Quando si importano dati in un modello tabulare, nella modalità cache si acquisisce uno snapshot di tali dati al momento dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="62634-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="62634-104">In alcuni casi, tali dati potrebbero non cambiare mai, pertanto non devono essere aggiornati nel modello.</span><span class="sxs-lookup"><span data-stu-id="62634-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="62634-105">Tuttavia, è più probabile che i dati che si importano cambino regolarmente, pertanto affinché il modello rifletta i dati più recenti delle origini dati, è necessario elaborarli (aggiornarli) e calcolare nuovamente i dati calcolati.</span><span class="sxs-lookup"><span data-stu-id="62634-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="62634-106">Per aggiornare i dati nel modello, è necessario eseguire un'azione di elaborazione in tutte le tabelle, in una singola tabella, in base a una partizione o a una connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="62634-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="62634-107">Durante la creazione del progetto di modello, tutte le azioni di elaborazione devono essere avviate manualmente in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62634-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="62634-108">Dopo la distribuzione di un modello, le operazioni di elaborazione possono essere eseguite tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oppure pianificate utilizzando uno script.</span><span class="sxs-lookup"><span data-stu-id="62634-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="62634-109">Tutte le attività descritte di seguito riguardano le azioni di elaborazione che è possibile eseguire durante la creazione di modelli in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62634-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="62634-110">Per ulteriori informazioni sulle azioni di elaborazione per un modello distribuito, vedere [elaborare database, tabelle o partizioni](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="62634-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="62634-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="62634-111">Related Tasks</span></span>  
  
|<span data-ttu-id="62634-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="62634-112">Topic</span></span>|<span data-ttu-id="62634-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62634-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="62634-114">Elaborare manualmente i dati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="62634-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="62634-115">Viene descritto come elaborare manualmente i dati dell'area di lavoro modello.</span><span class="sxs-lookup"><span data-stu-id="62634-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="62634-116">Risolvere i problemi relativi all'elaborazione dei dati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="62634-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="62634-117">Viene descritto come risolvere i problemi relativi alle operazioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="62634-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
