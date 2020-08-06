---
title: Modificare l'altezza di riga o la larghezza di colonna (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635425"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="d902f-102">Modificare l'altezza di riga o la larghezza di colonna (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d902f-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d902f-103">Quando si imposta un'altezza di riga, si specifica l'altezza massima della riga nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="d902f-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="d902f-104">Per impostazione predefinita, tuttavia, le caselle di testo nella riga sono impostate in modo da ingrandirsi verticalmente per poter contenere i dati immessi in fase di esecuzione. Per questo motivo, può verificarsi che una riga si espanda oltre l'altezza specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d902f-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="d902f-105">Per impostare un'altezza di riga fissa è necessario modificare le proprietà della casella di testo in modo che non venga espansa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d902f-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="d902f-106">Quando si imposta una larghezza di colonna, si specifica la larghezza massima della colonna nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="d902f-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="d902f-107">Le colonne non si espandono automaticamente in senso orizzontale in base al testo.</span><span class="sxs-lookup"><span data-stu-id="d902f-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="d902f-108">Se una cella in una riga o in una colonna contiene un rettangolo o un'area dati, l'altezza e la larghezza minima della cella vengono determinate in base all'altezza e alla larghezza dell'elemento contenuto.</span><span class="sxs-lookup"><span data-stu-id="d902f-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="d902f-109">Per altre informazioni, vedere [Tipi di rendering  &#40;Generatore report e SSRS &#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d902f-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="d902f-110">Per modificare l'altezza delle righe spostando gli handle di riga</span><span class="sxs-lookup"><span data-stu-id="d902f-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="d902f-111">In visualizzazione della struttura fare clic in un punto qualsiasi dell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="d902f-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="d902f-112">Lungo il bordo esterno dell'area dati Tablix vengono visualizzati alcuni handle di riga grigi.</span><span class="sxs-lookup"><span data-stu-id="d902f-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="d902f-113">Passare con il puntatore del mouse sul bordo dell'handle di riga che si desidera espandere.</span><span class="sxs-lookup"><span data-stu-id="d902f-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="d902f-114">Verrà visualizzata una freccia doppia.</span><span class="sxs-lookup"><span data-stu-id="d902f-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="d902f-115">Fare clic per selezionare il bordo della riga e spostarlo più in alto o più in basso per regolare l'altezza della riga.</span><span class="sxs-lookup"><span data-stu-id="d902f-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="d902f-116">Per modificare l'altezza delle righe impostando le proprietà delle celle</span><span class="sxs-lookup"><span data-stu-id="d902f-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="d902f-117">In visualizzazione Progettazione fare clic su una cella nella riga di tabella.</span><span class="sxs-lookup"><span data-stu-id="d902f-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="d902f-118">![Cella selezionata in una tabella](../media/table-selectcell.png "Cella selezionata in una tabella")</span><span class="sxs-lookup"><span data-stu-id="d902f-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="d902f-119">Nel riquadro **Proprietà** visualizzato modificare la proprietà **Altezza** , quindi fare clic in un punto qualsiasi all'esterno del riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="d902f-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="d902f-120">![Riquadro Proprietà della cella di tabella selezionata](../media/cell-propertiespane.png "Riquadro Proprietà della cella di tabella selezionata")</span><span class="sxs-lookup"><span data-stu-id="d902f-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="d902f-121">Per impedire che una riga si espanda automaticamente in senso verticale</span><span class="sxs-lookup"><span data-stu-id="d902f-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="d902f-122">In visualizzazione della struttura fare clic in un punto qualsiasi dell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="d902f-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="d902f-123">Lungo il bordo esterno dell'area dati Tablix vengono visualizzati alcuni handle di riga grigi.</span><span class="sxs-lookup"><span data-stu-id="d902f-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="d902f-124">Fare clic sull'handle di riga per selezionare la riga.</span><span class="sxs-lookup"><span data-stu-id="d902f-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="d902f-125">Nel riquadro Proprietà impostare CanGrow su **False**.</span><span class="sxs-lookup"><span data-stu-id="d902f-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d902f-126">Se non viene visualizzato il riquadro Proprietà, scegliere **Proprietà** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="d902f-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="d902f-127">Per modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="d902f-127">To change column width</span></span>  
  
1.  <span data-ttu-id="d902f-128">In visualizzazione della struttura fare clic in un punto qualsiasi dell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="d902f-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="d902f-129">Lungo il bordo esterno dell'area dati Tablix vengono visualizzati alcuni handle di colonna grigi.</span><span class="sxs-lookup"><span data-stu-id="d902f-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="d902f-130">Passare con il puntatore del mouse sul bordo dell'handle di colonna che si desidera espandere.</span><span class="sxs-lookup"><span data-stu-id="d902f-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="d902f-131">Verrà visualizzata una freccia doppia.</span><span class="sxs-lookup"><span data-stu-id="d902f-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="d902f-132">Fare clic per selezionare il bordo della colonna e spostarlo verso sinistra o verso destra per regolare la larghezza della colonna.</span><span class="sxs-lookup"><span data-stu-id="d902f-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d902f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d902f-133">See Also</span></span>  
 <span data-ttu-id="d902f-134">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d902f-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d902f-135">[Celle, righe e colonne dell'area dati Tablix &#40;Generatore report&#41; e SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d902f-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d902f-136">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d902f-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d902f-137">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d902f-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d902f-138">[Elenca &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d902f-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d902f-139">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d902f-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
