---
title: Aggiunta o eliminazione di un gruppo in un'area dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719607"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="833cd-102">Aggiunta o eliminazione di un gruppo in un'area dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="833cd-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="833cd-103">È possibile aggiungere un gruppo a un'area dati quando si desidera organizzare i dati in base a un valore o a un set di espressioni specifico per la visualizzazione e i calcoli.</span><span class="sxs-lookup"><span data-stu-id="833cd-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="833cd-104">A un gruppo sono associati un nome e un'espressione che consentono di identificare quali dati di un set di dati appartengono al gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="833cd-105">Per altre informazioni sui gruppi, vedere [Informazioni sui gruppi &#40;Generatore report e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="833cd-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="833cd-106">In un'area dati Tablix fare clic nella tabella, nella matrice o nell'elenco per visualizzare il riquadro di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="833cd-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="833cd-107">Trascinare i campi del set di dati nel riquadro Gruppo di righe e Gruppo di colonne per creare gruppi padre o gruppi figlio.</span><span class="sxs-lookup"><span data-stu-id="833cd-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="833cd-108">Fare clic con il pulsante destro del mouse su un gruppo esistente per aggiungere un gruppo adiacente.</span><span class="sxs-lookup"><span data-stu-id="833cd-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="833cd-109">Per definizione, il gruppo di dettagli è il gruppo più interno e può essere aggiunto solo come gruppo figlio.</span><span class="sxs-lookup"><span data-stu-id="833cd-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="833cd-110">Fare clic con il pulsante destro del mouse su un gruppo esistente per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="833cd-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="833cd-111">Verranno aggiunte automaticamente righe e colonne nelle quali è possibile visualizzare valori di gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="833cd-112">Per altre informazioni, vedere [Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="833cd-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="833cd-113">In un'area dati del grafico fare clic nel grafico per visualizzare le aree di rilascio.</span><span class="sxs-lookup"><span data-stu-id="833cd-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="833cd-114">Creare gruppi trascinando campi del set di dati nelle aree di rilascio dei campi categoria e serie.</span><span class="sxs-lookup"><span data-stu-id="833cd-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="833cd-115">Per aggiungere gruppi nidificati, aggiungere più campi all'area di rilascio.</span><span class="sxs-lookup"><span data-stu-id="833cd-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="833cd-116">Per impostazione predefinita, i gruppi non sono definiti in un misuratore.</span><span class="sxs-lookup"><span data-stu-id="833cd-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="833cd-117">Il comportamento predefinito per il misuratore è aggregare tutti i valori nel campo specificato in un unico valore visualizzato sul misuratore.</span><span class="sxs-lookup"><span data-stu-id="833cd-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="833cd-118">Per altre informazioni, vedere [Misuratori &#40;Generatore report e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="833cd-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="833cd-119">Per aggiungere un gruppo di righe o di colonne padre o figlio a un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-120">Trascinare un campo dal riquadro **Dati report** nel riquadro **Gruppi di righe** o nel riquadro **Gruppi di colonne** .</span><span class="sxs-lookup"><span data-stu-id="833cd-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="833cd-121">Se il riquadro Raggruppamento non è visualizzato, scegliere **Raggruppamento**dalla scheda Visualizza.</span><span class="sxs-lookup"><span data-stu-id="833cd-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="833cd-122">Rilasciare il campo al di sopra o al di sotto della gerarchia di gruppi utilizzando la barra della guida per posizionare il gruppo come gruppo padre o gruppo figlio di un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="833cd-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="833cd-123">Il gruppo verrà aggiunto con un nome, un'espressione di raggruppamento e un'espressione di ordinamento predefiniti che si basano sul nome del campo.</span><span class="sxs-lookup"><span data-stu-id="833cd-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="833cd-124">Per aggiungere un gruppo di righe o di colonne adiacenti a un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-125">Nel riquadro di raggruppamento fare clic con il pulsante destro del mouse su un gruppo di livello pari a quello che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="833cd-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="833cd-126">Fare clic su **Aggiungi gruppo**, quindi su **Adiacente prima** o su **Adiacente dopo** per specificare dove aggiungere il gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="833cd-127">Verrà visualizzata la finestra di dialogo **Gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="833cd-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="833cd-128">Nella casella **Nome**digitare un nome per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="833cd-129">In **Espressione di raggruppamento**digitare un'espressione o fare clic sul pulsante espressione (**fx**) per creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="833cd-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="833cd-130">Vengono aggiunti un nuovo gruppo al riquadro di raggruppamento e una riga o una colonna nelle quali visualizzare valori di gruppo all'area dati Tablix nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="833cd-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="833cd-131">Per aggiungere un gruppo dettagli a un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-132">Nel riquadro di raggruppamento fare clic con il pulsante destro del mouse sul gruppo figlio più interno, escluso il gruppo **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="833cd-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="833cd-133">Scegliere **Aggiungi gruppo**, quindi fare clic su **Gruppo figlio**.</span><span class="sxs-lookup"><span data-stu-id="833cd-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="833cd-134">Verrà visualizzata la finestra di dialogo **Gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="833cd-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="833cd-135">In **Espressione di raggruppamento**lasciare vuota l'espressione.</span><span class="sxs-lookup"><span data-stu-id="833cd-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="833cd-136">In un gruppo dettagli non è presente alcuna espressione.</span><span class="sxs-lookup"><span data-stu-id="833cd-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="833cd-137">Selezionare **Mostra dati dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="833cd-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="833cd-138">Un nuovo gruppo dettagli verrà aggiunto come gruppo figlio nel riquadro di raggruppamento e nell'handle di riga per il gruppo selezionato al passaggio 1 verrà visualizzata l'icona del gruppo dettagli.</span><span class="sxs-lookup"><span data-stu-id="833cd-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="833cd-139">Per altre informazioni sugli handle, vedere [Celle, righe e colonne dell'area dati Tablix &#40;Generatore report e SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="833cd-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="833cd-140">Per modificare un gruppo di righe o di colonne in un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-141">Nell'area di progettazione del report fare clic in un punto qualsiasi dell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="833cd-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="833cd-142">Nel riquadro di raggruppamento verranno visualizzati i gruppi di righe e di colonne.</span><span class="sxs-lookup"><span data-stu-id="833cd-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="833cd-143">Fare clic con il pulsante destro del mouse sul gruppo e scegliere **Proprietà gruppo**.</span><span class="sxs-lookup"><span data-stu-id="833cd-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="833cd-144">Nella casella **Nome**digitare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="833cd-145">In **Espressioni di raggruppamento**digitare o selezionare un'espressione semplice o fare clic sul pulsante Espressione (**fx**) per creare un'espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="833cd-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="833cd-146">Fare clic su **Aggiungi** per creare altre espressioni.</span><span class="sxs-lookup"><span data-stu-id="833cd-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="833cd-147">Tutte le espressioni specificate vengono combinate mediante un operatore logico AND in modo da specificare i dati per questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="833cd-148">(Facoltativo) Fare clic su **Interruzioni di pagina** per impostare le opzioni relative alle interruzioni di pagina.</span><span class="sxs-lookup"><span data-stu-id="833cd-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="833cd-149">(Facoltativo) Fare clic su **Ordinamento** per selezionare o digitare espressioni che specificano l'ordinamento per i valori del gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="833cd-150">(Facoltativo) Fare clic su **Visibilità** per selezionare le opzioni di visibilità per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="833cd-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="833cd-151">(Facoltativo) Fare clic su **Filtri** per impostare i filtri per questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="833cd-152">(Facoltativo) Fare clic su **Variabili** per definire variabili che hanno come ambito questo gruppo e che sono accessibili da qualsiasi gruppo figlio.</span><span class="sxs-lookup"><span data-stu-id="833cd-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="833cd-153">Per eliminare un gruppo da un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-154">Nel riquadro Raggruppamento fare clic con il pulsante destro del mouse sul gruppo e scegliere **Elimina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="833cd-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="833cd-155">Nella finestra di dialogo **Elimina gruppo** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="833cd-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="833cd-156">**Elimina gruppo e righe e colonne correlate** Scegliere questa opzione per eliminare la definizione di gruppo e tutte le righe correlate in cui sono visualizzati i dati di gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="833cd-157">Per il gruppo dettagli, se la stessa riga appartiene sia ai dati di dettaglio che a quelli di gruppo, verranno eliminate solo le righe dei dati di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="833cd-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="833cd-158">**Elimina solo gruppo** Scegliere questa opzione per mantenere inalterata la struttura dell'area dati Tablix ed eliminare solo la definizione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="833cd-159">Per eliminare un gruppo dettagli da un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="833cd-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="833cd-160">Nel riquadro Raggruppamento fare clic con il pulsante destro del mouse sul gruppo dettagli e scegliere **Elimina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="833cd-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="833cd-161">Nella finestra di dialogo **Elimina gruppo** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="833cd-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="833cd-162">**Elimina gruppo e righe e colonne correlate** Scegliere questa opzione per eliminare la definizione di gruppo e tutte le righe correlate in cui sono visualizzati i dati di gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="833cd-163">Per il gruppo dettagli, se la stessa riga appartiene sia ai dati di dettaglio che a quelli di gruppo, verranno eliminate solo le righe dei dati di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="833cd-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="833cd-164">**Elimina solo gruppo** Scegliere questa opzione per mantenere inalterata la struttura dell'area dati Tablix ed eliminare solo la definizione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="833cd-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="833cd-165">Il gruppo dettagli verrà eliminato.</span><span class="sxs-lookup"><span data-stu-id="833cd-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="833cd-166">Verificare che dopo avere rimosso una riga di dettaglio l'espressione in ogni cella specifichi un'espressione di aggregazione laddove appropriato.</span><span class="sxs-lookup"><span data-stu-id="833cd-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="833cd-167">Se necessario, modificare l'espressione in modo da specificare funzioni di aggregazione in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="833cd-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833cd-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="833cd-168">See Also</span></span>  
 <span data-ttu-id="833cd-169">[Riferimenti a raccolte di variabili di report e di gruppo &#40;Generatore report e SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="833cd-170">[Esempi di espressioni di raggruppamento &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="833cd-171">[Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="833cd-172">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="833cd-173">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="833cd-174">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="833cd-175">[Elenchi &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="833cd-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="833cd-176">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="833cd-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
