---
title: Creare e gestire partizioni nel database dell'area di lavoro (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626914"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="4bacd-102">Creare e gestire partizioni nel database dell'area di lavoro (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="4bacd-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="4bacd-103">Le partizioni consentono di dividere una tabella in parti logiche.</span><span class="sxs-lookup"><span data-stu-id="4bacd-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="4bacd-104">Ogni partizione può quindi essere elaborata (aggiornata) indipendentemente o in parallelo ad altre.</span><span class="sxs-lookup"><span data-stu-id="4bacd-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="4bacd-105">Le partizioni possono consentire di migliorare la scalabilità e la facilità di gestione di database grandi.</span><span class="sxs-lookup"><span data-stu-id="4bacd-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="4bacd-106">Per impostazione predefinita, ogni tabella dispone di una partizione in cui sono incluse tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="4bacd-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="4bacd-107">Nelle attività di questo argomento viene descritto come creare e gestire partizioni nel database dell'area di lavoro modello tramite la finestra di dialogo **Gestione partizioni** in[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bacd-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="4bacd-108">Dopo aver distribuito un modello in un'altra istanza di Analysis Services, gli amministratori di database possono creare e gestire partizioni nel modello (distribuito) utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bacd-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4bacd-109">Per altre informazioni, vedere [Creare e gestire partizioni di modelli tabulari &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="4bacd-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="4bacd-110">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bacd-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="4bacd-111">Per creare una nuova partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="4bacd-112">Per copiare una partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="4bacd-113">Per eliminare una partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="4bacd-114">Non è possibile unire partizioni nel database dell'area di lavoro modello tramite la finestra di dialogo Gestione partizioni.</span><span class="sxs-lookup"><span data-stu-id="4bacd-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="4bacd-115">Le partizioni possono essere unite in un modello distribuito solo utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bacd-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="4bacd-116">Attività</span><span class="sxs-lookup"><span data-stu-id="4bacd-116">Tasks</span></span>  
 <span data-ttu-id="4bacd-117">Per creare e gestire partizioni, usare la finestra di dialogo **Gestione partizioni** .</span><span class="sxs-lookup"><span data-stu-id="4bacd-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="4bacd-118">Per visualizzare la finestra di dialogo **Gestione partizioni** , in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]fare clic sul menu **Tabella** e quindi scegliere **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="4bacd-119">Per creare una nuova partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="4bacd-120">In Progettazione modelli selezionare la tabella per cui si desidera definire una partizione.</span><span class="sxs-lookup"><span data-stu-id="4bacd-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="4bacd-121">Fare clic sul menu **Tabella** , quindi scegliere **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="4bacd-122">Nella casella di riepilogo **Tabella**di **Gestione partizioni** verificare o selezionare la tabella che si vuole partizionare e quindi fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="4bacd-123">In **Nome partizione**digitare un nome per la partizione.</span><span class="sxs-lookup"><span data-stu-id="4bacd-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="4bacd-124">Per impostazione predefinita, il nome della partizione predefinita sarà numerato in modo incrementale per ogni nuova partizione.</span><span class="sxs-lookup"><span data-stu-id="4bacd-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="4bacd-125">È possibile selezionare le righe e le colonne da includere nella partizione utilizzando la modalità Anteprima tabella o una query SQL creata tramite la modalità Editor query.</span><span class="sxs-lookup"><span data-stu-id="4bacd-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="4bacd-126">Per usare la modalità Anteprima tabella (impostazione predefinita), fare clic sul pulsante **Anteprima tabella** in prossimità dell'angolo superiore destro della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="4bacd-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="4bacd-127">Scegliere le colonne che si desidera includere nella partizione selezionando la casella di controllo accanto al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="4bacd-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="4bacd-128">Per filtrare le righe, fare clic con il pulsante destro del mouse su un valore della cella e scegliere **Filtro in base al valore della cella selezionata**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="4bacd-129">Per usare un'istruzione SQL, fare clic sul pulsante **Editor query** in prossimità dell'angolo superiore destro della finestra di anteprima e quindi digitare o incollare un'istruzione della query SQL nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="4bacd-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="4bacd-130">Per convalidare l'istruzione, fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="4bacd-131">Per usare Progettazione query, fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a><span data-ttu-id="4bacd-132">Per copiare una partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="4bacd-133">Nella casella di riepilogo **Tabella**di **Gestione partizioni** verificare o selezionare la tabella contenente la partizione che si vuole copiare.</span><span class="sxs-lookup"><span data-stu-id="4bacd-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="4bacd-134">Dall'elenco **Partizioni** selezionare la partizione che si vuole copiare e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="4bacd-135">In **Nome partizione**digitare un nuovo nome per la partizione.</span><span class="sxs-lookup"><span data-stu-id="4bacd-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="4bacd-136">Per eliminare una partizione</span><span class="sxs-lookup"><span data-stu-id="4bacd-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="4bacd-137">Nella casella di riepilogo **Tabella**di **Gestione partizioni** verificare o selezionare la tabella contenente la partizione che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="4bacd-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="4bacd-138">Nell'elenco **Partizioni** selezionare la partizione che si vuole eliminare e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4bacd-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bacd-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bacd-139">See Also</span></span>  
 <span data-ttu-id="4bacd-140">[Partizioni &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="4bacd-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="4bacd-141">Elaborare partizioni nel database dell'area di lavoro &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="4bacd-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
