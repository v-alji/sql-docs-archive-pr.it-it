---
title: Impostare una proprietà NoDataMessage per un'area dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713868"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="2f1a1-102">Impostare una proprietà NoDataMessage per un'area dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2f1a1-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2f1a1-103">Per specificare il testo da visualizzare nel report visualizzabile al posto di un'area dati senza dati, impostare la proprietà NoRowsMessage di un'area dati tabella, matrice o elenco, la proprietà NoDataMessage di un'area dati del grafico e la proprietà NoDataText per la scala dei colori per una mappa.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="2f1a1-104">In fase di esecuzione Elaborazione report esegue la query per ogni set di dati in un report. Tale query non può restituire alcun set di risultati.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="2f1a1-105">Per un'area dati associata a un set di dati vuoto, è possibile specificare il testo da visualizzare anziché visualizzare un'area dati vuota.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="2f1a1-106">È anche possibile impostare la proprietà NoRowsMessage per un sottoreport quando in nessun set di dati del sottoreport sono presenti dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="2f1a1-107">Per impostare la proprietà NoRowsMessage di una tabella, una matrice o un elenco</span><span class="sxs-lookup"><span data-stu-id="2f1a1-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="2f1a1-108">Nella visualizzazione Progettazione fare clic sull'area dati tabella, matrice o elenco o sul sottoreport nell'area di progettazione per selezionare l'elemento desiderato.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="2f1a1-109">Nel riquadro Proprietà vengono visualizzate le proprietà relative all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2f1a1-110">Nel riquadro Proprietà digitare il testo che si desidera visualizzare come messaggio nel `NoRowsMessage` campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="2f1a1-111">In alternativa, nell'elenco a discesa fare clic su **Espressione** per aprire la finestra di dialogo **Espressione** e creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="2f1a1-112">Per impostare la proprietà NoDataMessage di un grafico</span><span class="sxs-lookup"><span data-stu-id="2f1a1-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="2f1a1-113">Nella visualizzazione Progettazione fare clic sul grafico nell'area di progettazione per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="2f1a1-114">Nel riquadro Proprietà vengono visualizzate le proprietà relative all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2f1a1-115">Nel riquadro Proprietà espandere il nodo per `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="2f1a1-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="2f1a1-116">In **didascalia**Digitare il testo che si desidera visualizzare come messaggio nel campo della `NoDataMessage` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="2f1a1-117">In alternativa, nell'elenco a discesa fare clic su **Espressione** per aprire la finestra di dialogo **Espressione** e creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="2f1a1-118">Per impostare la proprietà NoRowsMessage di un sottoreport</span><span class="sxs-lookup"><span data-stu-id="2f1a1-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="2f1a1-119">Nella visualizzazione Progettazione fare clic sul sottoreport nell'area di progettazione per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="2f1a1-120">Nel riquadro Proprietà vengono visualizzate le proprietà relative all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2f1a1-121">Nel riquadro Proprietà digitare il testo che si desidera visualizzare come messaggio nel `NoRowsMessage` campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="2f1a1-122">In alternativa, nell'elenco a discesa fare clic su **Espressione** per aprire la finestra di dialogo **Espressione** e creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="2f1a1-123">Per impostare la proprietà NoDataText per una scala dei colori per una mappa</span><span class="sxs-lookup"><span data-stu-id="2f1a1-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="2f1a1-124">Nella visualizzazione Progettazione fare clic sulla scala dei colori nella mappa per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="2f1a1-125">Nel riquadro Proprietà vengono visualizzate le proprietà relative all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2f1a1-126">Nel riquadro proprietà `NoDataText` digitare il testo che si desidera visualizzare come etichetta per i colori senza valore di dati.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="2f1a1-127">In alternativa, nell'elenco a discesa fare clic su **Espressione** per aprire la finestra di dialogo **Espressione** e creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2f1a1-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1a1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f1a1-128">See Also</span></span>  
 <span data-ttu-id="2f1a1-129">[Sottoreport &#40;Generatore report e SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f1a1-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2f1a1-130">[Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f1a1-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2f1a1-131">[Grafici &#40;Generatore report e SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f1a1-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2f1a1-132">[Mappe &#40;Generatore report e SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f1a1-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2f1a1-133">Sottoreport &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1a1-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
