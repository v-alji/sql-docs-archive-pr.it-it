---
title: Aggiungere un gruppo dettagli (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628477"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="25a63-102">Aggiungere un gruppo dettagli (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="25a63-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="25a63-103">I dati dettaglio di un set di dati del report vengono specificati come gruppo senza espressione di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="25a63-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="25a63-104">È possibile aggiungere un gruppo dettagli a un'area dati Tablix esistente quando si desidera visualizzare i dati dettaglio per una matrice, aggiungere di nuovo i dati dettaglio eliminati da una tabella o un elenco oppure aggiungere ulteriori gruppi dettagli.</span><span class="sxs-lookup"><span data-stu-id="25a63-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="25a63-105">Per altre informazioni sui gruppi, vedere [Informazioni sui gruppi &#40;Generatore report e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25a63-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="25a63-106">Per aggiungere un gruppo dettagli a un'area dati Tablix</span><span class="sxs-lookup"><span data-stu-id="25a63-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="25a63-107">Nell'area di progettazione fare clic in un punto qualsiasi nell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="25a63-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="25a63-108">Nel riquadro di raggruppamento vengono visualizzati i gruppi di righe e colonne per l'area dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="25a63-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="25a63-109">Nel riquadro di raggruppamento fare clic con il pulsante destro del mouse su un gruppo che rappresenta il gruppo figlio più interno.</span><span class="sxs-lookup"><span data-stu-id="25a63-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="25a63-110">Scegliere **Aggiungi gruppo**, quindi fare clic su **Gruppo figlio**.</span><span class="sxs-lookup"><span data-stu-id="25a63-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="25a63-111">Verrà visualizzata la finestra di dialogo **Gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="25a63-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="25a63-112">In **Espressione di raggruppamento**lasciare vuota l'espressione.</span><span class="sxs-lookup"><span data-stu-id="25a63-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="25a63-113">In un gruppo dettagli non è presente alcuna espressione.</span><span class="sxs-lookup"><span data-stu-id="25a63-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="25a63-114">Selezionare **Mostra dati dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="25a63-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="25a63-115">Un nuovo gruppo dettagli verrà aggiunto come gruppo figlio nel riquadro di raggruppamento e nell'handle di riga per il gruppo selezionato al passaggio 1 verrà visualizzata l'icona del gruppo dettagli.</span><span class="sxs-lookup"><span data-stu-id="25a63-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="25a63-116">Per altre informazioni sugli handle, vedere [Celle, righe e colonne dell'area dati Tablix &#40;Generatore report e SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25a63-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a63-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25a63-117">See Also</span></span>  
 <span data-ttu-id="25a63-118">[Aggiunta o eliminazione di un gruppo in un'area dati &#40;Generatore report e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="25a63-119">[Informazioni sui gruppi &#40;Generatore report e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="25a63-120">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="25a63-121">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="25a63-122">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="25a63-123">[Elenca &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25a63-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="25a63-124">Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25a63-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
