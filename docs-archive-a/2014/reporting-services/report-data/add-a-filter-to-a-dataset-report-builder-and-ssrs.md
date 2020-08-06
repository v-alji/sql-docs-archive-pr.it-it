---
title: Aggiungere un filtro a un set di dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623847"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="82a6d-102">Aggiungere un filtro a un set di dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="82a6d-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="82a6d-103">Aggiungere un filtro a un set di dati per limitare i dati di un report dopo averli recuperati da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="82a6d-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="82a6d-104">Quando si aggiunge un filtro a un set di dati, tutte le parti di report o aree dati utilizzano solo dati che soddisfano le condizioni del filtro.</span><span class="sxs-lookup"><span data-stu-id="82a6d-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="82a6d-105">Per i set di dati condivisi, un filtro applicato a tutti gli elementi dipendenti deve essere parte della definizione del set di dati condiviso sul server di report.</span><span class="sxs-lookup"><span data-stu-id="82a6d-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="82a6d-106">Un report o una parte di report contenente un'istanza di un set di dati condiviso può creare un filtro aggiuntivo che si applica solo all'istanza.</span><span class="sxs-lookup"><span data-stu-id="82a6d-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="82a6d-107">Per aggiungere un filtro, è necessario specificare una o più condizioni rappresentate da equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="82a6d-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="82a6d-108">Un'equazione di filtro è costituita da un'espressione che identifica i dati da filtrare, da un operatore e dal valore con il quale eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="82a6d-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="82a6d-109">I dati filtrati e il valore devono essere dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="82a6d-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="82a6d-110">L'applicazione di filtri ai valori aggregati di un set di dati non è supportata.</span><span class="sxs-lookup"><span data-stu-id="82a6d-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="82a6d-111">Per aggiungere un filtro a un set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="82a6d-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="82a6d-112">Aprire un set di dati condiviso in modalità set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="82a6d-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="82a6d-113">Nel gruppo **Set di dati condivisi** della scheda **Home** scegliere Set di dati.</span><span class="sxs-lookup"><span data-stu-id="82a6d-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="82a6d-114">Verrà visualizzata la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="82a6d-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="82a6d-115">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-115">Click **Filters**.</span></span> <span data-ttu-id="82a6d-116">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="82a6d-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="82a6d-117">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="82a6d-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="82a6d-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-118">Click **Add**.</span></span> <span data-ttu-id="82a6d-119">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="82a6d-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="82a6d-120">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="82a6d-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="82a6d-121">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="82a6d-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="82a6d-122">Nella casella di riepilogo selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="82a6d-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="82a6d-123">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="82a6d-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="82a6d-124">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="82a6d-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="82a6d-125">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="82a6d-126">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="82a6d-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="82a6d-127">Per aggiungere un filtro a un set di dati incorporato o a un'istanza del set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="82a6d-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="82a6d-128">Aprire un report in modalità di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="82a6d-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="82a6d-129">Fare clic con il pulsante destro del mouse su un set di dati nel riquadro **Dati report** e scegliere **Proprietà set di dati**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="82a6d-130">Verrà visualizzata la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="82a6d-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="82a6d-131">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-131">Click **Filters**.</span></span> <span data-ttu-id="82a6d-132">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="82a6d-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="82a6d-133">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="82a6d-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="82a6d-134">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-134">Click **Add**.</span></span> <span data-ttu-id="82a6d-135">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="82a6d-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="82a6d-136">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="82a6d-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="82a6d-137">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="82a6d-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="82a6d-138">Nella casella a discesa selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="82a6d-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="82a6d-139">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="82a6d-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="82a6d-140">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="82a6d-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="82a6d-141">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="82a6d-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="82a6d-142">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="82a6d-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82a6d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82a6d-143">See Also</span></span>  
 <span data-ttu-id="82a6d-144">[Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="82a6d-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="82a6d-145">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="82a6d-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="82a6d-146">Aggiungere un filtro &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82a6d-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
