---
title: Aggiungere un filtro (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726511"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="8f8d2-102">Aggiungere un filtro (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8f8d2-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8f8d2-103">Aggiungere un filtro a un set di dati, un'area dati o un gruppo per includere o escludere valori specifici nei calcoli o nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="8f8d2-104">In fase di esecuzione, i filtri vengono applicati prima al set di dati, poi all'area dati e infine al gruppo procedendo dall'alto verso il basso per le gerarchie di gruppi.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="8f8d2-105">In una tabella, una matrice o un elenco i filtri per gruppi di righe, gruppi di colonne e gruppi adiacenti vengono applicati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="8f8d2-106">Anche in un grafico i filtri per gruppi di categorie e gruppi di serie vengono applicati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="8f8d2-107">Per aggiungere un filtro è necessario specificare una o più equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="8f8d2-108">Un'equazione di filtro è costituita da un'espressione che identifica i dati da filtrare, da un operatore e dal valore con il quale eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="8f8d2-109">I dati filtrati e il valore devono essere dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="8f8d2-110">L'applicazione di filtri ai valori aggregati di un set di dati o un'area dati non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="8f8d2-111">Per filtrare punti dati in un grafico è possibile impostare un filtro in un gruppo di categorie o in un gruppo di serie.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="8f8d2-112">Per impostazione predefinita, il grafico usa la funzione predefinita Sum per aggregare valori che fanno parte dello stesso gruppo in un singolo punto dati nella serie.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="8f8d2-113">Se si modifica la funzione di aggregazione di una serie, è necessario modificarla anche nell'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="8f8d2-114">Per altre informazioni sul filtro dei set di dati condivisi e incorporati, vedere [Aggiungere un filtro a un set di dati &#40;Generatore report e SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="8f8d2-115">Per impostare un filtro su un'area dati</span><span class="sxs-lookup"><span data-stu-id="8f8d2-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="8f8d2-116">Aprire un report in visualizzazione **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="8f8d2-117">Selezionare l'area dati nell'area di progettazione, quindi fare clic con il pulsante destro del mouse su _\<data region>_ **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="8f8d2-118">Per un misuratore, selezionare **Proprietà pannello del misuratore**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="8f8d2-119">Verrà visualizzata la finestra di _\<data region>_ dialogo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f8d2-120">In un'area dati Tablix fare clic con il pulsante destro del mouse sulla cella d'angolo oppure sull'handle di una riga o colonna e quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="8f8d2-121">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-121">Click **Filters**.</span></span> <span data-ttu-id="8f8d2-122">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="8f8d2-123">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="8f8d2-124">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-124">Click **Add**.</span></span> <span data-ttu-id="8f8d2-125">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="8f8d2-126">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="8f8d2-127">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="8f8d2-128">Nella casella a discesa selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="8f8d2-129">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="8f8d2-130">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="8f8d2-131">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="8f8d2-132">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="8f8d2-133">Per impostare un filtro su un gruppo di righe o di colonne Tablix</span><span class="sxs-lookup"><span data-stu-id="8f8d2-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="8f8d2-134">Aprire un report in visualizzazione **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="8f8d2-135">Fare clic con il pulsante destro del mouse sulla tabella, sulla matrice o sull'area dati dell'elenco nell'area di progettazione per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="8f8d2-136">Nel riquadro di raggruppamento vengono visualizzati i gruppi per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="8f8d2-137">Nel riquadro Raggruppamento fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Modifica gruppo**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="8f8d2-138">Verrà visualizzata la finestra di dialogo **Gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="8f8d2-139">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-139">Click **Filters**.</span></span> <span data-ttu-id="8f8d2-140">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="8f8d2-141">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="8f8d2-142">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-142">Click **Add**.</span></span> <span data-ttu-id="8f8d2-143">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="8f8d2-144">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="8f8d2-145">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="8f8d2-146">Nella casella a discesa selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="8f8d2-147">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="8f8d2-148">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="8f8d2-149">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="8f8d2-150">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="8f8d2-151">Per impostare un filtro su un gruppo di categorie Grafico</span><span class="sxs-lookup"><span data-stu-id="8f8d2-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="8f8d2-152">Aprire un report in visualizzazione **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="8f8d2-153">Nell'area di progettazione fare due volte clic sul grafico per visualizzare le aree di rilascio dei campi dati, serie e categoria.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="8f8d2-154">Fare clic con il pulsante destro del mouse su un campo contenuto nell'area di rilascio del campo categoria e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="8f8d2-155">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-155">Click **Filters**.</span></span> <span data-ttu-id="8f8d2-156">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="8f8d2-157">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="8f8d2-158">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-158">Click **Add**.</span></span> <span data-ttu-id="8f8d2-159">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="8f8d2-160">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="8f8d2-161">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="8f8d2-162">Nella casella a discesa selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="8f8d2-163">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="8f8d2-164">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="8f8d2-165">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="8f8d2-166">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="8f8d2-167">Per impostare un filtro su un gruppo di serie Grafico</span><span class="sxs-lookup"><span data-stu-id="8f8d2-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="8f8d2-168">Aprire un report in visualizzazione **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="8f8d2-169">Nell'area di progettazione fare due volte clic sul grafico per visualizzare le aree di rilascio dei campi dati, serie e categoria.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="8f8d2-170">Fare clic con il pulsante destro del mouse su un campo contenuto nell'area di rilascio del campo serie e scegliere **Proprietà gruppo serie**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="8f8d2-171">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-171">Click **Filters**.</span></span> <span data-ttu-id="8f8d2-172">Verrà visualizzato l'elenco corrente di equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="8f8d2-173">Per impostazione predefinita, l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="8f8d2-174">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-174">Click **Add**.</span></span> <span data-ttu-id="8f8d2-175">Verrà visualizzata una nuova equazione di filtro vuota.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="8f8d2-176">Nella casella **Espressione**digitare o selezionare l'espressione per il campo da filtrare.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="8f8d2-177">Per modificare l'espressione, fare clic sul pulsante dell'espressione (*fx*).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="8f8d2-178">Nella casella a discesa selezionare il tipo di dati corrispondente a quello dell'espressione creata nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="8f8d2-179">Nella casella **Operatore** selezionare l'operatore che si desidera utilizzare con il filtro per confrontare i valori nelle caselle **Espressione** e **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8f8d2-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="8f8d2-180">L'operatore scelto determina il numero di valori che verranno utilizzati nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="8f8d2-181">Nella casella **Valore** digitare l'espressione o il valore in base al quale viene valutato il valore nella colonna **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="8f8d2-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="8f8d2-182">Per esempi di equazioni di filtro, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d2-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f8d2-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f8d2-183">See Also</span></span>  
 <span data-ttu-id="8f8d2-184">[Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="8f8d2-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="8f8d2-185">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f8d2-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f8d2-186">[Misuratori &#40;Generatore report e SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f8d2-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f8d2-187">[Elenca &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f8d2-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8f8d2-188">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8d2-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
