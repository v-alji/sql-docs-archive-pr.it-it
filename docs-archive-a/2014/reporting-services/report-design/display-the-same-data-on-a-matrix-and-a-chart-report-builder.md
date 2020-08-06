---
title: Visualizzare dati identici in una matrice e in un grafico (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721162"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="e94c4-102">Visualizzare dati identici in una matrice e in un grafico (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="e94c4-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="e94c4-103">Se si desidera visualizzare gli stessi dati in una matrice e in un grafico, è necessario impostare determinate proprietà su entrambe le aree dati per specificare lo stesso set di dati, nonché le stesse espressioni per filtri, gruppi, ordinamenti e dati.</span><span class="sxs-lookup"><span data-stu-id="e94c4-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="e94c4-104">Poiché entrambe le aree dati disporranno dello stesso predecessore per i dati (il set di dati del report), è possibile aggiungere alla matrice un pulsante di ordinamento interattivo che consente di modificare l'ordinamento sia per la matrice che per il grafico quando l'utente vi fa clic sopra.</span><span class="sxs-lookup"><span data-stu-id="e94c4-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="e94c4-105">Per altre informazioni, vedere [Aggiungere un ordinamento interattivo a una tabella o a una matrice &#40;Generatore report e SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e94c4-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e94c4-106">Per utilizzare i valori di gruppo delle colonne della matrice come legenda per il grafico, è necessario specificare i colori per i dati della serie sul grafico e quindi utilizzare gli stessi colori come colori di riempimento per lo sfondo delle caselle di testo nella cella della matrice in cui sono visualizzati i valori di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e94c4-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="e94c4-107">Per altre informazioni, vedere [Specifica di colori coerenti in più grafici con forme &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e94c4-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e94c4-108">In fase di esecuzione, il report potrebbe apparire poco chiaro se il numero dei valori di gruppo per le definizioni di gruppo è eccessivo.</span><span class="sxs-lookup"><span data-stu-id="e94c4-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="e94c4-109">In questo caso, potrebbe essere necessario filtrare i valori, combinare i gruppi o regolare la soglia in modo che il grafico combini i gruppi automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e94c4-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="e94c4-110">Per altre informazioni, vedere [Collegamento di più aree dati allo stesso set di dati &#40;Generatore report e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="e94c4-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="e94c4-111">Per aggiungere una matrice e un grafico in cui visualizzare gli stessi dati</span><span class="sxs-lookup"><span data-stu-id="e94c4-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="e94c4-112">Aprire un report in visualizzazione Progettazione.</span><span class="sxs-lookup"><span data-stu-id="e94c4-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="e94c4-113">Nel gruppo **Aree dati** della scheda **Inserisci** fare clic su **Matrice**e quindi fare clic nel corpo del report o in un rettangolo nel corpo del report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="e94c4-114">Verrà aggiunta una matrice al report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="e94c4-115">Nel gruppo **Aree dati** della scheda **Inserisci** fare clic su **Grafico**e quindi selezionare il tipo di grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="e94c4-116">Verrà aggiunto un grafico al report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="e94c4-117">(Facoltativo) Nel gruppo **Elementi del report** della scheda **Inserisci** fare clic su **Rettangolo**e quindi sul report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="e94c4-118">Verrà aggiunto un rettangolo al report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-118">A rectangle is added to the report.</span></span> <span data-ttu-id="e94c4-119">Trascinare nel rettangolo la matrice e il grafico creati ai passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="e94c4-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="e94c4-120">Mediante il posizionamento di più aree dati nel contenitore rettangolare, è possibile controllare la modalità di rendering della matrice e del grafico durante la visualizzazione del report.</span><span class="sxs-lookup"><span data-stu-id="e94c4-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="e94c4-121">Nei passaggi successivi si sceglierà lo stesso campo del set di dati da visualizzare nella matrice e nel grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="e94c4-122">Dal riquadro dei dati del report trascinare un campo del set di dati numerici nella cella di dati della matrice.</span><span class="sxs-lookup"><span data-stu-id="e94c4-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="e94c4-123">Per impostazione predefinita, la funzione di aggregazione Sum viene usata per calcolare il valore di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e94c4-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="e94c4-124">Se si modifica la funzione di aggregazione nella matrice, è necessario modificarla anche nel grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="e94c4-125">Nella matrice fare clic con il pulsante destro del mouse sulla cella contenente i dati, scegliere **Proprietà casella di testo**e quindi fare clic su **Numero**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="e94c4-126">Scegliere un formato adatto per il valore del campo del set di dati.</span><span class="sxs-lookup"><span data-stu-id="e94c4-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="e94c4-127">Trascinare lo stesso campo del set di dati scelto nel passaggio 3 nell'area **Valori** del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="e94c4-128">Nel grafico fare clic con il pulsante destro del mouse sull'asse Y, scegliere **Proprietà asse**e quindi fare clic su **Numero**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="e94c4-129">Scegliere per i dati lo stesso formato selezionato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e94c4-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e94c4-130">Nei passaggi successivi il gruppo di righe della matrice e il gruppo di serie del grafico verranno impostati sulla stessa espressione. Verrà inoltre impostato l'ordinamento per il gruppo di serie del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="e94c4-131">Dal riquadro dei dati del report trascinare sul riquadro Gruppi di righe il campo del set di dati in base al quale si desidera eseguire il raggruppamento delle righe della matrice.</span><span class="sxs-lookup"><span data-stu-id="e94c4-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="e94c4-132">Per impostazione predefinita, il gruppo di righe della matrice aggiunge un'espressione di ordinamento che equivale all'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="e94c4-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="e94c4-133">Trascinare lo stesso campo del set di dati usato nel passaggio 9 nell'area **Gruppi di serie** del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="e94c4-134">Fare clic con il pulsante destro del mouse sul gruppo nell'area **Gruppi di serie** e quindi scegliere **Proprietà gruppo serie**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="e94c4-135">Fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="e94c4-136">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-136">Click **Add**.</span></span> <span data-ttu-id="e94c4-137">Nella griglia delle espressioni di ordinamento verrà visualizzata una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="e94c4-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="e94c4-138">Nell'elenco a discesa **Ordina per**selezionare il campo del set di dati scelto nel passaggio 9 per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="e94c4-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e94c4-139">Nei passaggi successivi il gruppo di colonne della matrice e il gruppo di categorie del grafico verranno impostati sulla stessa espressione. Verrà inoltre impostato l'ordinamento per il gruppo di categorie del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="e94c4-140">Dal riquadro dei dati del report trascinare sul riquadro Gruppi di colonne il campo del set di dati in base al quale si desidera eseguire il raggruppamento delle colonne della matrice.</span><span class="sxs-lookup"><span data-stu-id="e94c4-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="e94c4-141">Per impostazione predefinita, il gruppo di colonne della matrice aggiunge un'espressione di ordinamento che equivale all'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="e94c4-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="e94c4-142">Trascinare lo stesso campo del set di dati usato nel passaggio 16 nell'area **Gruppi di categorie** del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="e94c4-143">Fare clic con il pulsante destro del mouse sul gruppo nell'area **Gruppi di categorie** e quindi scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="e94c4-144">Fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="e94c4-145">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e94c4-145">Click **Add**.</span></span> <span data-ttu-id="e94c4-146">Nella griglia delle espressioni di ordinamento verrà visualizzata una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="e94c4-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="e94c4-147">Nell'elenco a discesa **Ordina per**selezionare il campo del set di dati scelto nel passaggio 16 per il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="e94c4-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="e94c4-148">Visualizzare il risultato nell'anteprima.</span><span class="sxs-lookup"><span data-stu-id="e94c4-148">Preview the result.</span></span> <span data-ttu-id="e94c4-149">Nei gruppi di righe e di colonne della matrice verranno visualizzati gli stessi dati dei gruppi di categorie e di serie del grafico.</span><span class="sxs-lookup"><span data-stu-id="e94c4-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94c4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e94c4-150">See Also</span></span>  
 <span data-ttu-id="e94c4-151">[Collegamento di più aree dati allo stesso set di dati &#40;Generatore report e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e94c4-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e94c4-152">[Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="e94c4-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="e94c4-153">[Elenca &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e94c4-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e94c4-154">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e94c4-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
