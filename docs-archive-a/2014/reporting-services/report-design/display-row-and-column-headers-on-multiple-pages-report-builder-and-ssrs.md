---
title: Visualizzare le intestazioni di riga e colonna in più pagine (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721173"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="76562-102">Visualizzare le intestazioni di riga e colonna in più pagine (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="76562-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="76562-103">È possibile specificare se ripetere le intestazioni di riga e di colonna in ogni pagina di un'area dati Tablix che si estende su più pagine.</span><span class="sxs-lookup"><span data-stu-id="76562-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="76562-104">Un'area dati Tablix può essere una tabella, una matrice o un elenco.</span><span class="sxs-lookup"><span data-stu-id="76562-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="76562-105">La modalità di controllo di righe e colonne dipende dalla presenza o meno delle intestazioni di gruppo nell'area dati Tablix.</span><span class="sxs-lookup"><span data-stu-id="76562-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="76562-106">Quando si fa clic in un'area dati Tablix che dispone di intestazioni di gruppo, una linea punteggiata indica le aree Tablix, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="76562-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="76562-107">![Aree dell'area dati Tablix](../media/rs-tablixareas.gif "Aree dell'area dati Tablix")</span><span class="sxs-lookup"><span data-stu-id="76562-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="76562-108">Le intestazioni dei gruppi di righe e di colonne vengono create automaticamente quando si aggiungono gruppi tramite la procedura guidata Nuova tabella o matrice o Nuovo grafico, aggiungendo campi al riquadro Raggruppamento o tramite i menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="76562-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="76562-109">Se nell'area dati Tablix è presente solo un'area del corpo della Tablix ma non sono disponibili intestazioni di gruppo, le righe e le colonne sono membri Tablix.</span><span class="sxs-lookup"><span data-stu-id="76562-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="76562-110">Per i membri statici, è possibile visualizzare le righe adiacenti superiori o le colonne adiacenti laterali in più pagine.</span><span class="sxs-lookup"><span data-stu-id="76562-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="76562-111">Per visualizzare le intestazioni di riga in più pagine</span><span class="sxs-lookup"><span data-stu-id="76562-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="76562-112">Fare clic con il pulsante destro del mouse sulla riga o sulla colonna oppure sull'handle d'angolo di un'area dati Tablix, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="76562-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="76562-113">In **Intestazioni riga**selezionare **Ripeti righe intestazione in ogni pagina**.</span><span class="sxs-lookup"><span data-stu-id="76562-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="76562-114">Per visualizzare le intestazioni di colonna in più pagine</span><span class="sxs-lookup"><span data-stu-id="76562-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="76562-115">Fare clic con il pulsante destro del mouse sulla riga o sulla colonna oppure sull'handle d'angolo di un'area dati Tablix, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="76562-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="76562-116">In **Intestazioni colonna**selezionare **Ripeti colonne intestazione in ogni pagina**.</span><span class="sxs-lookup"><span data-stu-id="76562-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="76562-117">Per visualizzare un membro Tablix statico (riga o colonna) in più pagine</span><span class="sxs-lookup"><span data-stu-id="76562-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="76562-118">Nell'area di progettazione fare clic sull'handle di riga o di colonna dell'area dati Tablix per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="76562-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="76562-119">Nel riquadro di raggruppamento verranno visualizzati i gruppi di righe e di colonne.</span><span class="sxs-lookup"><span data-stu-id="76562-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="76562-120">Sul lato destro del riquadro di raggruppamento fare clic sulla freccia rivolta verso il basso, quindi fare clic su **Modalità avanzata**.</span><span class="sxs-lookup"><span data-stu-id="76562-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="76562-121">Nel riquadro Gruppi di righe vengono visualizzati i membri statici e dinamici gerarchici per la gerarchia di gruppi di righe, mentre nel riquadro Gruppi di colonne è riportata una visualizzazione simile per la gerarchia di gruppi di colonne.</span><span class="sxs-lookup"><span data-stu-id="76562-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="76562-122">Fare clic sul membro statico che corrisponde al membro statico (riga o colonna) che si desidera mantenere visibile durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="76562-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="76562-123">Nel riquadro Proprietà verranno visualizzate le proprietà dei **membri Tablix** .</span><span class="sxs-lookup"><span data-stu-id="76562-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="76562-124">Se il riquadro Proprietà non è visualizzato, fare clic sulla scheda **Visualizza** nella parte superiore della finestra di Generatore report, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="76562-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="76562-125">Nel riquadro Proprietà impostare **RepeatOnNewPage** su True.</span><span class="sxs-lookup"><span data-stu-id="76562-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="76562-126">Impostare **KeepWithGroup** su Dopo.</span><span class="sxs-lookup"><span data-stu-id="76562-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="76562-127">Ripetere questo passaggio per tutti i membri adiacenti che si desidera ripetere.</span><span class="sxs-lookup"><span data-stu-id="76562-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="76562-128">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="76562-128">Preview the report.</span></span>  
  
 <span data-ttu-id="76562-129">Durante la visualizzazione delle pagine del report incluse nell'area dati Tablix, i membri Tablix statici vengono ripetuti su ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="76562-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76562-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76562-130">See Also</span></span>  
 <span data-ttu-id="76562-131">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76562-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="76562-132">[Esportazione di report &#40;Generatore report e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76562-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="76562-133">[Controllo di interruzioni di pagina, intestazioni, colonne e righe &#40;Generatore report e SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76562-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="76562-134">[Visualizzare intestazioni e piè di pagina con un gruppo &#40;Generatore report e SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76562-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="76562-135">Visualizzazione delle intestazioni durante lo scorrimento di un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="76562-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
