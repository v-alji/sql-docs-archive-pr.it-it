---
title: Completamento procedura guidata (creazione guidata partizione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625752"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="77436-102">Completamento procedura guidata (Creazione guidata partizione)</span><span class="sxs-lookup"><span data-stu-id="77436-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="77436-103">Usare la pagina **Completamento procedura guidata** per assegnare un nome alla partizione, definire la progettazione delle aggregazioni per la partizione ed eventualmente distribuire ed elaborare la partizione dopo aver completato la Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="77436-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="77436-104">Options</span></span>  
 <span data-ttu-id="77436-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="77436-105">**Name**</span></span>  
 <span data-ttu-id="77436-106">Consente di digitare un nome per la nuova partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-106">Type the name for the new partition.</span></span> <span data-ttu-id="77436-107">Se si sta lavorando con più tabelle, immettere il prefisso che verrà utilizzato con il nome della tabella per creare il nome di ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="77436-108">**Opzioni di aggregazione**</span><span class="sxs-lookup"><span data-stu-id="77436-108">**Aggregation options**</span></span>  
 <span data-ttu-id="77436-109">Consente di specificare l'opzione di aggregazione per la partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="77436-110">Nella tabella seguente vengono elencate le opzioni di aggregazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="77436-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="77436-111">Opzione</span><span class="sxs-lookup"><span data-stu-id="77436-111">Option</span></span>|<span data-ttu-id="77436-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77436-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="77436-113">**Progetta le aggregazioni per la partizione adesso**</span><span class="sxs-lookup"><span data-stu-id="77436-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="77436-114">Le aggregazioni per la nuova partizione vengono progettate al termine della creazione della nuova partizione da parte della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="77436-115">La selezione di questa opzione determina l'avvio della Progettazione guidata aggregazioni dopo aver scelto **Fine** nella Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="77436-116">Per altre informazioni sulla Progettazione guidata aggregazioni, vedere [Guida sensibile al contesto della Progettazione guidata aggregazioni](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="77436-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="77436-117">**Configura le aggregazioni in seguito**</span><span class="sxs-lookup"><span data-stu-id="77436-117">**Design the aggregations later**</span></span>|<span data-ttu-id="77436-118">La partizione viene creata senza che vengano subito progettate le aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="77436-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="77436-119">**Copia la progettazione delle aggregazioni da una partizione esistente**</span><span class="sxs-lookup"><span data-stu-id="77436-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="77436-120">La progettazione delle aggregazioni viene copiata nella nuova partizione da una partizione esistente nel gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="77436-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="77436-121">La selezione di questa opzione rende disponibile l'opzione **Copia da** .</span><span class="sxs-lookup"><span data-stu-id="77436-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="77436-122">Usare l'opzione **Copia da** per selezionare la partizione da cui copiare la progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="77436-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="77436-123">Si noti che le partizioni che possono essere unite in futuro devono avere la stessa struttura di tabella e la stessa progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="77436-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="77436-124">Per unire la nuova partizione a una partizione esistente nel gruppo di misure, è consigliabile copiare la progettazione delle aggregazioni della partizione esistente nella nuova partizione.</span><span class="sxs-lookup"><span data-stu-id="77436-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="77436-125">**Distribuisci ed elabora adesso**</span><span class="sxs-lookup"><span data-stu-id="77436-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="77436-126">Consente di distribuire ed elaborare la partizione nell'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] specificata nella pagina **Posizioni di elaborazione e archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="77436-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="77436-127">Dopo aver scelto **Fine** in questa pagina, la partizione viene distribuita ed elaborata.</span><span class="sxs-lookup"><span data-stu-id="77436-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77436-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77436-128">See Also</span></span>  
 [<span data-ttu-id="77436-129">Partizioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="77436-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
