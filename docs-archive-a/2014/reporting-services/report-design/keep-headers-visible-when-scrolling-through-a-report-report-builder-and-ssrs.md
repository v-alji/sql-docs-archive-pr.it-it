---
title: Mantenere visibili le intestazioni durante lo scorrimento di un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723416"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="1261c-102">Visualizzazione delle intestazioni durante lo scorrimento di un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1261c-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1261c-103">Per evitare che le etichette di riga e di colonna scorrano oltre l'area di visualizzazione dopo il rendering di un report, è possibile bloccare le intestazioni di riga o di colonna.</span><span class="sxs-lookup"><span data-stu-id="1261c-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="1261c-104">La modalità di controllo delle righe e delle colonne varia a seconda che si tratta di una tabella o di una matrice.</span><span class="sxs-lookup"><span data-stu-id="1261c-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="1261c-105">Se si dispone di una tabella, configurare i membri statici (intestazioni di riga e di colonna) in modo che rimangano visibili.</span><span class="sxs-lookup"><span data-stu-id="1261c-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="1261c-106">Se si dispone di una matrice, configurare le intestazioni di gruppi di riga e di colonna in modo che rimangano visibili.</span><span class="sxs-lookup"><span data-stu-id="1261c-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="1261c-107">Se si esporta il report in Excel, l'intestazione non verrà bloccata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1261c-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="1261c-108">È possibile bloccare il riquadro in Excel.</span><span class="sxs-lookup"><span data-stu-id="1261c-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="1261c-109">Per altre informazioni vedere la sezione **Intestazioni di pagina e piè di pagina del report** di [Esportazione in Microsoft Excel &#40;Generatore report e SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1261c-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1261c-110">Anche se una tabella include gruppi di righe e colonne, non è possibile mantenere visibili le intestazioni di gruppo durante lo scorrimento</span><span class="sxs-lookup"><span data-stu-id="1261c-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="1261c-111">Nell'immagine seguente viene illustrata una tabella.</span><span class="sxs-lookup"><span data-stu-id="1261c-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="1261c-112">![Tabella](../media/table.png "Tabella")</span><span class="sxs-lookup"><span data-stu-id="1261c-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="1261c-113">Nell'immagine seguente viene illustrata una matrice.</span><span class="sxs-lookup"><span data-stu-id="1261c-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="1261c-114">![Matrice](../media/matrix.png "Matrice")</span><span class="sxs-lookup"><span data-stu-id="1261c-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="1261c-115">Per mantenere visibili le intestazioni di gruppo di matrice durante lo scorrimento</span><span class="sxs-lookup"><span data-stu-id="1261c-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="1261c-116">Fare clic con il pulsante destro del mouse sulla riga o sulla colonna oppure sull'handle d'angolo di un'area dati Tablix, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="1261c-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="1261c-117">Nella scheda **Generale** sotto **Intestazioni riga** o **Intestazioni colonna**selezionare **Mantieni intestazione visibile durante lo scorrimento**.</span><span class="sxs-lookup"><span data-stu-id="1261c-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="1261c-118">Per mantenere visibile un membro Tablix statico (riga o colonna) durante lo scorrimento</span><span class="sxs-lookup"><span data-stu-id="1261c-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="1261c-119">Nell'area di progettazione fare clic in un punto qualsiasi della tabella per visualizzare i membri statici e i gruppi, nel riquadro di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="1261c-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="1261c-120">![Riquadro di raggruppamento](../media/grouppane-updated.png "Riquadro di raggruppamento")</span><span class="sxs-lookup"><span data-stu-id="1261c-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="1261c-121">Nel riquadro Gruppi di righe vengono visualizzati i membri statici e dinamici gerarchici per la gerarchia di gruppi di righe, mentre nel riquadro Gruppi di colonne è riportata una visualizzazione simile per la gerarchia di gruppi di colonne.</span><span class="sxs-lookup"><span data-stu-id="1261c-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="1261c-122">Sul lato destro del riquadro di raggruppamento fare clic sulla freccia rivolta verso il basso, quindi fare clic su **Modalità avanzata**.</span><span class="sxs-lookup"><span data-stu-id="1261c-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="1261c-123">Fare clic sul membro statico (riga o colonna) che si desidera mantenere visibile durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="1261c-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="1261c-124">Nel riquadro Proprietà verranno visualizzate le proprietà dei **membri Tablix** .</span><span class="sxs-lookup"><span data-stu-id="1261c-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="1261c-125">![Proprietà Membro Tablix](../media/grouppane-tablixmember-updated.png "Proprietà Membro Tablix")</span><span class="sxs-lookup"><span data-stu-id="1261c-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="1261c-126">Nel riquadro Proprietà impostare **FixedData** su `True` .</span><span class="sxs-lookup"><span data-stu-id="1261c-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="1261c-127">Ripetere questo passaggio per tutti i membri adiacenti che si desidera mantenere visibili durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="1261c-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="1261c-128">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1261c-128">Preview the report.</span></span>  
  
 <span data-ttu-id="1261c-129">Durante lo scorrimento verticale o orizzontale del report, i membri Tablix statici resteranno visibili.</span><span class="sxs-lookup"><span data-stu-id="1261c-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1261c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1261c-130">See Also</span></span>  
 <span data-ttu-id="1261c-131">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1261c-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1261c-132">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1261c-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1261c-133">[Esportazione di report &#40;Generatore report e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1261c-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1261c-134">[Visualizzare intestazioni e piè di pagina con un gruppo &#40;Generatore report e SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1261c-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1261c-135">[Visualizzare le intestazioni di riga e colonna in più pagine &#40;Generatore report e SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1261c-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1261c-136">Riquadro di raggruppamento &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="1261c-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
