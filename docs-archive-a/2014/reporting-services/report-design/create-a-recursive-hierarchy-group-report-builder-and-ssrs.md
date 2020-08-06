---
title: Creare un gruppo di gerarchie ricorsive (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627137"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="1a9d0-102">Creare un gruppo di gerarchie ricorsive (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1a9d0-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1a9d0-103">In un gruppo di gerarchie ricorsive è possibile organizzare dati da un unico set di dati di un report in cui sono inclusi più livelli gerarchici, ad esempio il report per definire la struttura di relazioni tra dipendenti in una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="1a9d0-104">Prima che sia possibile organizzare i dati in una tabella come un gruppo di gerarchie ricorsive, è necessario disporre di un unico set di dati che contiene tutti i dati gerarchici. È necessario disporre di campi separati per gli elementi da raggruppare e per l'elemento in base al quale eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="1a9d0-105">Un set di dati, ad esempio, in cui si desidera raggruppare i dipendenti in modo ricorsivo sotto il loro superiore, potrebbe contenere un nome, un nome di dipendente, un ID dipendente e un ID responsabile.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="1a9d0-106">Per creare un gruppo di gerarchie ricorsive</span><span class="sxs-lookup"><span data-stu-id="1a9d0-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="1a9d0-107">Nella visualizzazione della struttura aggiungere una tabella e trascinare i campi del set di dati da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="1a9d0-108">In genere, il campo che si desidera mostrare come una gerarchia si trova nella prima colonna.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="1a9d0-109">Fare clic con il pulsante destro del mouse in un punto qualsiasi della tabella per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="1a9d0-110">Nel riquadro di raggruppamento viene visualizzato il gruppo di dettagli per la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="1a9d0-111">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse su **Dettagli**, quindi scegliere **Modifica gruppo**.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="1a9d0-112">Verrà visualizzata la finestra di dialogo **Proprietà gruppo** .</span><span class="sxs-lookup"><span data-stu-id="1a9d0-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="1a9d0-113">In **Espressioni di raggruppamento**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="1a9d0-114">Nella griglia verrà visualizzata una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="1a9d0-115">Nell'elenco **Raggruppa in base a** digitare o selezionare il campo da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="1a9d0-116">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="1a9d0-117">Nell'elenco **Elemento padre ricorsivo** immettere o selezionare il campo in base al quale eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="1a9d0-118">Eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-118">Run the report.</span></span> <span data-ttu-id="1a9d0-119">Nel report viene visualizzato il gruppo di gerarchie ricorsive, anche se non è presente alcun rientro per indicare la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="1a9d0-120">Per formattare un gruppo di gerarchie ricorsive con livelli di rientro</span><span class="sxs-lookup"><span data-stu-id="1a9d0-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="1a9d0-121">Fare clic sulla casella di testo che contiene il campo cui si desidera aggiungere livelli di rientro per visualizzare un formato di gerarchia.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="1a9d0-122">Le proprietà per la casella di testo verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a9d0-123">Se il riquadro Proprietà non è visualizzato, fare clic su **Proprietà** nella scheda **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="1a9d0-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="1a9d0-124">Nel riquadro Proprietà espandere il `Padding` nodo, fare clic su a **sinistra**, quindi selezionare nell'elenco a discesa **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="1a9d0-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="1a9d0-125">Nel riquadro Espressione digitare l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="1a9d0-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="1a9d0-126">Per tutte le proprietà relative a Riempimento è necessario usare una stringa con il formato *nnyy*, dove *nn* è un numero e *yy* è l'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="1a9d0-127">L'espressione di esempio consente di compilare una stringa che utilizza la funzione `Level` per aumentare le dimensioni del riempimento in base al livello di ricorsione.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="1a9d0-128">A una riga di livello 1, ad esempio, verrà applicato un riempimento di (2 + (1\*10))=12pt e a una riga di livello 3 verrà applicato un riempimento di (2 + (3\*10))=32pt.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="1a9d0-129">Per informazioni sulla `Level` funzione, vedere [Level](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="1a9d0-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="1a9d0-130">Eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-130">Run the report.</span></span> <span data-ttu-id="1a9d0-131">Nel report viene visualizzata una vista gerarchica dei dati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="1a9d0-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9d0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a9d0-132">See Also</span></span>  
 <span data-ttu-id="1a9d0-133">[Creazione di gruppi di gerarchie ricorsive &#40;Generatore report e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a9d0-134">[Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a9d0-135">[Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="1a9d0-136">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a9d0-137">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a9d0-138">[Elenchi &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a9d0-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1a9d0-139">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1a9d0-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
