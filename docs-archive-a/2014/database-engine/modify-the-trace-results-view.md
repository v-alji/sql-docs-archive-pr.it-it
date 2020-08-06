---
title: Modificare la visualizzazione dei risultati della traccia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624894"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="bcd6d-102">Modificare la visualizzazione dei risultati della traccia</span><span class="sxs-lookup"><span data-stu-id="bcd6d-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="bcd6d-103">In questo argomento viene descritto come modificare la vista dei risultati di traccia di una sessione di Eventi estesi in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] eseguendo le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="bcd6d-104">Aggiungi o Rimuovi colonne</span><span class="sxs-lookup"><span data-stu-id="bcd6d-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="bcd6d-105">Creare, modificare o eliminare le colonne unite</span><span class="sxs-lookup"><span data-stu-id="bcd6d-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="bcd6d-106">Ordinare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="bcd6d-107">Raggruppare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="bcd6d-108">Aggregare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="bcd6d-109">Filtrare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="bcd6d-110">Cercare un testo nelle colonne</span><span class="sxs-lookup"><span data-stu-id="bcd6d-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="bcd6d-111">Modificare le impostazioni di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bcd6d-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="bcd6d-112">Aggiungi o Rimuovi colonne</span><span class="sxs-lookup"><span data-stu-id="bcd6d-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-113">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-114"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-115">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna, quindi **scegliere Scegli colonne**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="bcd6d-116">Nella sezione **Colonne disponibili** della finestra di dialogo **Scegli colonne** selezionare i nomi delle colonne che si desidera aggiungere, quindi fare clic su pulsante della freccia DESTRA.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-117">Per impostazione predefinita, le colonne sono disposte in base al nome.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="bcd6d-118">Per visualizzare le colonne in base all'evento, fare clic su **Disponi per evento**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="bcd6d-119">Per rimuovere colonne, nella sezione **Colonne selezionate** selezionare le colonne che si desidera rimuovere, quindi fare clic sulla freccia a sinistra.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="bcd6d-120">Per modificare la visualizzazione dell'ordine delle colonne, nella sezione **Colonne selezionate** fare clic rispettivamente su **Sposta su** o **Sposta giù** .</span><span class="sxs-lookup"><span data-stu-id="bcd6d-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="bcd6d-121">Non è possibile spostare più righe.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="bcd6d-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="bcd6d-123">Creare, modificare o eliminare colonne unite</span><span class="sxs-lookup"><span data-stu-id="bcd6d-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="bcd6d-124">Per creare colonne unite</span><span class="sxs-lookup"><span data-stu-id="bcd6d-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-125">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-126"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-127">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna, quindi fare clic su **Scegli colonne**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="bcd6d-128">Nella finestra di dialogo **Scegli colonne** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="bcd6d-129">Nella casella **Nome colonna unita** della finestra di dialogo **Nuova colonna unita** immettere un nome per le colonne unite.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="bcd6d-130">Nella casella **colonne originali da unire** selezionare due o più colonne da unire nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-131">Eventi estesi supporta solo l'unione di un massimo di cinque colonne.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="bcd6d-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="bcd6d-133">Per modificare colonne unite</span><span class="sxs-lookup"><span data-stu-id="bcd6d-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-134">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-135"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-136">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna, quindi fare clic su **Scegli colonne**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="bcd6d-137">Nella finestra di dialogo **Scegli colonne** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="bcd6d-138">Per modificare il nome della colonna unita, nella casella **Nome colonna unita** della finestra di dialogo **Nuova colonna unita** immettere il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="bcd6d-139">Per modificare le colonne che si desidera unire, nella casella **colonne originali da unire** selezionare le colonne da unire nell'elenco a discesa, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="bcd6d-140">Per eliminare colonne unite</span><span class="sxs-lookup"><span data-stu-id="bcd6d-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-141">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-142"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-143">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna, quindi fare clic su **Scegli colonne**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="bcd6d-144">Nella finestra di dialogo **Scegli colonne** selezionare il nome della colonna unita da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="bcd6d-145">Ordinare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="bcd6d-146">Per ordinare i risultati in ordine crescente o decrescente</span><span class="sxs-lookup"><span data-stu-id="bcd6d-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="bcd6d-147">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-148"> È possibile anche fare clic sul nome della sessione, selezionare **Controlla i dati dinamici**, quindi fare clic sul pulsante **Arresta feed di dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="bcd6d-149">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna che si desidera ordinare.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="bcd6d-150">Selezionare **Ordinamento crescente** o **Ordinamento decrescente** per ordinare le colonne rispettivamente in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="bcd6d-151">In caso di raggruppamento di colonne, il relativo ordinamento comporta l'esecuzione della stessa operazione esclusivamente per i dati all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="bcd6d-152">Raggruppare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="bcd6d-153">Per raggruppare i risultati per una sola colonna</span><span class="sxs-lookup"><span data-stu-id="bcd6d-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="bcd6d-154">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-155"> È possibile anche fare clic sul nome della sessione, selezionare **Controlla i dati dinamici**, quindi fare clic sul pulsante **Arresta feed di dati** sulla barra degli strumenti Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="bcd6d-156">Nella finestra dei risultati della traccia fare clic con il pulsante destro del mouse sull'intestazione di colonna che si desidera raggruppare, quindi scegliere **Raggruppa per questa colonna**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="bcd6d-157">Per raggruppare i risultati per più colonne</span><span class="sxs-lookup"><span data-stu-id="bcd6d-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-158">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-159"> È possibile anche fare clic sul nome della sessione, selezionare **Controlla i dati dinamici**, quindi fare clic sul pulsante **Arresta feed di dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="bcd6d-160">Fare clic sul pulsante **Raggruppamento** sulla barra degli strumenti Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="bcd6d-161">Nella casella **Colonne disponibili** della finestra di dialogo **Raggruppamento** selezionare le colonne che si desidera raggruppare, quindi fare clic sul pulsante della freccia DESTRA.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="bcd6d-162">Per modificare l'ordine di raggruppamento, nella sezione **Colonne raggruppate per** fare clic sulle frecce SU o GIÙ.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="bcd6d-163">Per rimuovere colonne dal raggruppamento, nella casella **Colonne raggruppate per** selezionare le colonne che si desidera rimuovere, quindi fare clic sulla freccia a sinistra.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="bcd6d-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="bcd6d-165">Risultati aggregati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-165">Aggregate Results</span></span>  
 <span data-ttu-id="bcd6d-166">Eventi estesi supporta cinque funzioni di aggregazione:</span><span class="sxs-lookup"><span data-stu-id="bcd6d-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="bcd6d-167">Somma</span><span class="sxs-lookup"><span data-stu-id="bcd6d-167">Sum</span></span>  
  
-   <span data-ttu-id="bcd6d-168">Min</span><span class="sxs-lookup"><span data-stu-id="bcd6d-168">Min</span></span>  
  
-   <span data-ttu-id="bcd6d-169">Max</span><span class="sxs-lookup"><span data-stu-id="bcd6d-169">Max</span></span>  
  
-   <span data-ttu-id="bcd6d-170">Media</span><span class="sxs-lookup"><span data-stu-id="bcd6d-170">Average</span></span>  
  
-   <span data-ttu-id="bcd6d-171">Conteggio</span><span class="sxs-lookup"><span data-stu-id="bcd6d-171">Count</span></span>  
  
 <span data-ttu-id="bcd6d-172">Sum, Min, Max e Average possono essere utilizzate solo con le colonne numeriche disponibili.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="bcd6d-173">Count è il numero di valori non Null esistente per la colonna selezionata nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="bcd6d-174">Per aggregare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="bcd6d-175">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-176"> È possibile anche fare clic sul nome della sessione, selezionare **Controlla i dati dinamici**, quindi fare clic sul pulsante **Arresta feed di dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-177">L'aggregazione viene eseguita su un gruppo, pertanto è necessario raggruppare i risultati prima di effettuare l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="bcd6d-178">Fare clic sul pulsante **Aggregazione** sulla barra degli strumenti Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="bcd6d-179">Verrà visualizzata la finestra di dialogo **Aggregazione** in cui vengono mostrate le colonne disponibili per l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="bcd6d-180">In **tipo di aggregazione**selezionare il modo in cui si desidera aggregare la colonna corrispondente dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="bcd6d-181">Nella casella **Ordina aggregazione per** selezionare la colonna in base alla quale si desidera eseguire l'ordinamento dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="bcd6d-182">Selezionare l'opzione **In ordine crescente** per ordinare il risultato dell'aggregazione in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="bcd6d-183">Selezionare l'opzione **In ordine decrescente** per ordinare il risultato dell'aggregazione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="bcd6d-184">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="bcd6d-185">Filtrare i risultati</span><span class="sxs-lookup"><span data-stu-id="bcd6d-185">Filter Results</span></span>  
 <span data-ttu-id="bcd6d-186">È possibile applicare filtri per limitare i risultati della traccia visualizzati nella finestra di traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="bcd6d-187">Nel filtro di visualizzazione sono inclusi un filtro temporale e un filtro avanzato.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="bcd6d-188">È possibile utilizzare il filtro temporale per filtrare i risultati della traccia in base al timestamp dell'evento e il filtro avanzato per costruire condizioni di filtro utilizzando i campi e le azioni dell'evento.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="bcd6d-189">Esiste una relazione AND logica tra i filtri temporale e avanzato.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="bcd6d-190">Per creare un filtro</span><span class="sxs-lookup"><span data-stu-id="bcd6d-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="bcd6d-191">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-192"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-193">Nella finestra dei risultati della traccia selezionare i risultati che si desidera filtrare, quindi nella barra degli strumenti Eventi estesi fare clic sul pulsante **Filtri** .</span><span class="sxs-lookup"><span data-stu-id="bcd6d-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="bcd6d-194">Nella finestra di dialogo **Filtri** selezionare **Imposta filtro temporale** per impostare il filtro temporale trascinando le barre del dispositivo di scorrimento per impostare la sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="bcd6d-195">Si noti che quando si spostano le barre del dispositivo di scorrimento, il valore dell'ora nell'apposita casella cambia di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="bcd6d-196">È possibile immettere l'ora anche nelle caselle dell'ora o selezionarla dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="bcd6d-197">Si noti che quando si immette l'ora, il dispositivo di scorrimento tempo a sinistra si sposterà di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="bcd6d-198">Nella sezione **filtri aggiuntivi** applicare i criteri di filtro e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="bcd6d-199">Una volta completata la creazione del filtro, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="bcd6d-200">Una situazione speciale si crea quando un campo relativo all'evento ha lo stesso nome di un'azione.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="bcd6d-201">Un esempio potrebbe essere session_id.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-201">An example of this would be session_id.</span></span> <span data-ttu-id="bcd6d-202">Ci sono diversi eventi che includono il campo session_id ed è anche possibile aggiungere l'azione session_id.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="bcd6d-203">Entrambe le informazioni vengono raccolte, ma la griglia di visualizzazione del profiler di Eventi estesi utilizza la logica indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="bcd6d-204">Solo una copia della colonna (session_id in questo caso) viene mostrata nella visualizzazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="bcd6d-205">Se i campi e l'azione esistono nei dati, viene mostrato il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="bcd6d-206">Se nei dati è presente solo il campo o l'azione, viene visualizzato il campo o l'azione.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="bcd6d-207">Se non è presente né l'azione né il campo, viene visualizzato NULL.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="bcd6d-208">Cerca testo nelle colonne</span><span class="sxs-lookup"><span data-stu-id="bcd6d-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="bcd6d-209">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-210"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-211">Fare clic sul pulsante **Trova** sulla barra degli strumenti Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="bcd6d-212">Nella casella **Trova** della finestra di dialogo **Trova in eventi estesi** immettere il testo che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="bcd6d-213">È possibile selezionare una delle ultime 20 stringhe di ricerca nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="bcd6d-214">Nella casella **Cerca in** selezionare il percorso in cui cercare il testo specificato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="bcd6d-215">Per la ricerca, utilizzare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcd6d-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="bcd6d-216">**Colonne della tabella**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-216">**Table Columns**.</span></span> <span data-ttu-id="bcd6d-217">Utilizzare questa opzione per eseguire ricerche in tutte le colonne visibili nella finestra di traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="bcd6d-218">**Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-218">**Details**.</span></span> <span data-ttu-id="bcd6d-219">Utilizzare questa opzione per eseguire la ricerca in tutte le colonne (promosse e non promosse) della finestra di traccia selezionate prima di aprire la finestra **di dialogo trova in eventi estesi** .</span><span class="sxs-lookup"><span data-stu-id="bcd6d-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="bcd6d-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-220">**\<Event column name>**.</span></span> <span data-ttu-id="bcd6d-221">Utilizzare questa opzione per eseguire ricerche in una colonna specifica dell'evento dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="bcd6d-222">Utilizzare le opzioni seguenti per specificare la modalità con cui si desidera definire la ricerca:</span><span class="sxs-lookup"><span data-stu-id="bcd6d-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="bcd6d-223">**Maiuscole/minuscole**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-223">**Match case**.</span></span> <span data-ttu-id="bcd6d-224">Utilizzare questa opzione per visualizzare i risultati della ricerca del testo immesso nella casella **trova** corrispondente sia per contenuto che per caso.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="bcd6d-225">**Parola intera**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-225">**Match whole word**.</span></span> <span data-ttu-id="bcd6d-226">Utilizzare questa opzione per visualizzare solo i risultati della ricerca del testo immesso che corrispondono a parole intere.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="bcd6d-227">**Cerca in alto**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-227">**Search up**.</span></span> <span data-ttu-id="bcd6d-228">Utilizzare questa opzione per eseguire la ricerca dalla posizione del cursore fino all'inizio dei risultati.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="bcd6d-229">**Usare**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-229">**Use**.</span></span> <span data-ttu-id="bcd6d-230">Usare questa opzione per interpretare le espressioni regolari e i caratteri speciali immessi nella casella **trova** .</span><span class="sxs-lookup"><span data-stu-id="bcd6d-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="bcd6d-231">Tra i caratteri speciali sono inclusi i caratteri jolly (\*) e (?) per rappresentare uno o più caratteri.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="bcd6d-232">Le espressioni regolari sono notazioni speciali utilizzate per definire i criteri del testo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="bcd6d-233">Fare clic su **Trova successivo** per cercare il successivo testo immesso nella casella **Trova** .</span><span class="sxs-lookup"><span data-stu-id="bcd6d-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="bcd6d-234">Modificare le impostazioni di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bcd6d-234">Change the Display Settings</span></span>  
 <span data-ttu-id="bcd6d-235">È possibile salvare le informazioni sulle colonne (ordine delle colonne, colonna di unione e larghezza delle colonne) e sul filtro di un risultato di traccia in un file di impostazioni di visualizzazione degli eventi estesi (con estensione viewsetting).</span><span class="sxs-lookup"><span data-stu-id="bcd6d-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="bcd6d-236">Dopo aver salvato il file, è possibile applicarlo ai risultati della traccia per modificare la vista.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="bcd6d-237">Per modificare le impostazioni di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bcd6d-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="bcd6d-238">Aprire un file XEL per visualizzare i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcd6d-239"> È anche possibile fare clic con il pulsante destro del mouse sul nome della sessione e scegliere **Controlla i dati dinamici**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="bcd6d-240">Nella finestra dei risultati della traccia, dal menu o sulla barra degli strumenti degli eventi estesi scegliere **Impostazioni di visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="bcd6d-241">Selezionare una delle opzioni seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="bcd6d-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="bcd6d-242">**Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-242">**Save as**.</span></span> <span data-ttu-id="bcd6d-243">Consente di salvare le informazioni sulle colonne e sul filtro di un risultato di traccia in un file con estensione viewsetting.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="bcd6d-244">**Aprire**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-244">**Open**.</span></span> <span data-ttu-id="bcd6d-245">Consente di aprire un file con estensione viewsetting esistente.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="bcd6d-246">**Apri recenti**.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-246">**Open recent**.</span></span> <span data-ttu-id="bcd6d-247">Consente di aprire un file con estensione viewsetting salvato recentemente.</span><span class="sxs-lookup"><span data-stu-id="bcd6d-247">Open a recently saved .viewsetting file.</span></span>  
  
  
