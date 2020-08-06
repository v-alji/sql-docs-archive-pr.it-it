---
title: Ordinamento dei dati in un'area dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723379"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="bc3aa-102">Ordinamento dei dati in un'area dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bc3aa-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bc3aa-103">Per modificare l'ordinamento dei dati in un'area dati quando si esegue un report per la prima volta, è necessario impostare l'espressione di ordinamento nel gruppo o nell'area dati.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="bc3aa-104">Per impostazione predefinita, l'espressione di ordinamento per un gruppo viene impostata automaticamente su un valore identico a quello dell'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="bc3aa-105">In un'area dati Tablix impostare l'espressione di ordinamento per l'area dati o per ogni gruppo, incluso il gruppo di dettagli.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="bc3aa-106">Se in un'area dati Tablix è disponibile un solo gruppo di dettagli, è possibile definire un'espressione di ordinamento nella query, nell'area dati o nel gruppo di dettagli e ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="bc3aa-107">In un'area dati del grafico impostare l'espressione di ordinamento per i gruppi Categoria e Serie in modo da controllare l'ordinamento per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="bc3aa-108">L'ordine dei colori in una legenda del grafico viene determinato dall'espressione di ordinamento per i punti dati nel gruppo Categoria.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="bc3aa-109">In un'area dati del misuratore in genere non è necessario ordinare i dati, in quanto nel misuratore viene visualizzato un solo valore relativo a un intervallo.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="bc3aa-110">Se è necessario ordinare i dati in un misuratore, definire innanzitutto un gruppo e quindi impostare l'espressione di ordinamento per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="bc3aa-111">Per altre informazioni, vedere [Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc3aa-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="bc3aa-112">Per un'area dati Tablix è inoltre possibile aggiungere un pulsante di ordinamento interattivo nella parte superiore di un'intestazione di colonna, in modo da consentire all'utente di modificare l'ordinamento di gruppi o righe di dettagli.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="bc3aa-113">Per altre informazioni, vedere [Ordinamento interattivo &#40;Generatore report e SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc3aa-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="bc3aa-114">Per ordinare i dati in un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="bc3aa-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="bc3aa-115">Nell'area di progettazione fare clic con il pulsante destro del mouse sull'handle di riga, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="bc3aa-116">Fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bc3aa-117">Per ogni espressione di ordinamento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bc3aa-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bc3aa-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bc3aa-119">Digitare o selezionare un'espressione in base alla quale ordinare i dati.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="bc3aa-120">Nell'elenco a discesa della colonna **Ordine** scegliere la direzione di ordinamento per ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bc3aa-121">L'opzione**A-Z** consente di disporre l'espressione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bc3aa-122">L'opzione**Z-A** consente di disporre l'espressione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="bc3aa-123">Per ordinare i valori di un gruppo, incluso il gruppo di dettagli, per una Tablix</span><span class="sxs-lookup"><span data-stu-id="bc3aa-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="bc3aa-124">Nell'area di progettazione fare clic nell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="bc3aa-125">Nel riquadro di raggruppamento vengono visualizzati i gruppi di righe e di colonne per l'area dati Tablix.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="bc3aa-126">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse sul nome del gruppo, quindi scegliere **Modifica gruppo**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="bc3aa-127">Nella finestra di dialogo **Gruppo Tablix** fare clic su **Ordina**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="bc3aa-128">Per ogni espressione di ordinamento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bc3aa-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bc3aa-129">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bc3aa-130">Digitare o selezionare un'espressione in base alla quale ordinare i dati.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="bc3aa-131">Nell'elenco a discesa della colonna **Ordine** scegliere la direzione di ordinamento per ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bc3aa-132">L'opzione**A-Z** consente di disporre l'espressione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bc3aa-133">L'opzione**Z-A** consente di disporre l'espressione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="bc3aa-134">Per ordinare le etichette dell'asse X in ordine alfabetico su un grafico</span><span class="sxs-lookup"><span data-stu-id="bc3aa-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="bc3aa-135">Fare clic con il pulsante destro del mouse su un campo nell'area di rilascio dei campi categoria e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="bc3aa-136">Nella finestra di dialogo **Proprietà gruppo categorie** fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bc3aa-137">Per ogni espressione di ordinamento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bc3aa-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bc3aa-138">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bc3aa-139">Selezionare l'espressione che corrisponde al campo di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="bc3aa-140">È possibile verificare l'espressione per il campo di raggruppamento facendo clic su **Raggruppamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="bc3aa-141">Nell'elenco a discesa della colonna **Ordine** scegliere la direzione di ordinamento per ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bc3aa-142">L'opzione**A-Z** consente di disporre l'espressione in ordine alfabetico crescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="bc3aa-143">L'opzione**Z-A** consente di disporre l'espressione in ordine alfabetico decrescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="bc3aa-144">Per disporre i punti dati in ordine crescente o decrescente su un grafico</span><span class="sxs-lookup"><span data-stu-id="bc3aa-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="bc3aa-145">Fare clic con il pulsante destro del mouse su un campo nell'area di rilascio dei campi categoria e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="bc3aa-146">Nella finestra di dialogo **Proprietà gruppo categorie** fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bc3aa-147">Per ogni espressione di ordinamento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bc3aa-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bc3aa-148">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bc3aa-149">Selezionare l'espressione che corrisponde al campo dati.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="bc3aa-150">Nella maggior parte dei casi si tratta di un valore aggregato, ad esempio `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="bc3aa-151">Nell'elenco a discesa della colonna **Ordine** scegliere la direzione di ordinamento per ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bc3aa-152">L'opzione**A-Z** consente di disporre l'espressione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bc3aa-153">L'opzione**Z-A** consente di disporre l'espressione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="bc3aa-154">Per disporre i dati in ordine crescente o decrescente per la visualizzazione su un misuratore</span><span class="sxs-lookup"><span data-stu-id="bc3aa-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="bc3aa-155">Fare clic con il pulsante destro del mouse sul misuratore e scegliere **Aggiungi gruppo di dati**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="bc3aa-156">Nella finestra di dialogo **Proprietà gruppo di pannelli del misuratore** fare clic su **Generale** , se necessario.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="bc3aa-157">In **Espressioni di raggruppamento**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="bc3aa-158">Da **Raggruppa in base a**digitare o selezionare un'espressione in base alla quale raggruppare i dati.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="bc3aa-159">Ripetere i passaggi da 3 a 4 finché non saranno state aggiunte tutte le espressioni di raggruppamento desiderate.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="bc3aa-160">Fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="bc3aa-161">Per ogni espressione di ordinamento, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bc3aa-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bc3aa-162">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bc3aa-163">Selezionare l'espressione che corrisponde al campo di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="bc3aa-164">È possibile verificare l'espressione per il campo di raggruppamento facendo clic su **Raggruppamento**.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="bc3aa-165">Nell'elenco a discesa della colonna **Ordine** scegliere la direzione di ordinamento per ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bc3aa-166">L'opzione**A-Z** consente di disporre l'espressione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bc3aa-167">L'opzione**Z-A** consente di disporre l'espressione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bc3aa-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="bc3aa-168">Per altre informazioni sul raggruppamento dei dati in un misuratore, vedere [Misuratori &#40;Generatore report e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc3aa-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3aa-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc3aa-169">See Also</span></span>  
 <span data-ttu-id="bc3aa-170">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="bc3aa-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="bc3aa-171">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc3aa-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bc3aa-172">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc3aa-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bc3aa-173">Specificare i colori coerenti in più grafici con forme &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc3aa-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
