---
title: Azione di drill-down (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636567"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="bb5d3-102">Azione di drill-down (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb5d3-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bb5d3-103">Fornendo più o meno icone in una casella di testo, è possibile consentire agli utenti di nascondere e visualizzare gli elementi in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="bb5d3-104">Questa azione viene chiamata *drill-down* .</span><span class="sxs-lookup"><span data-stu-id="bb5d3-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="bb5d3-105">Per una tabella o una matrice, è possibile visualizzare o nascondere le righe e le colonne statiche o le righe e le colonne associate ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="bb5d3-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="bb5d3-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="bb5d3-107">In questa illustrazione l'utente fa clic sui segni più (+) nel report per mostrare dati dettaglio.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="bb5d3-108">È ad esempio possibile nascondere inizialmente tutte le righe, ad eccezione della riga di riepilogo del gruppo esterno di una tabella con gruppi di righe.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="bb5d3-109">Per ogni gruppo interno, incluso il gruppo dettagli, aggiungere un'icona per espandere o comprimere alla cella di raggruppamento del gruppo contenitore.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="bb5d3-110">Dopo il rendering del report, l'utente può fare clic sulla casella di testo per espandere e comprimere i dati dettaglio.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="bb5d3-111">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="bb5d3-112">Per consentire agli utenti di espandere o comprimere un elemento, impostare le proprietà di visibilità per tale elemento.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb5d3-113">Quando si crea un report con un'azione drill-down, è necessario impostare le informazioni relative alla visibilità sul gruppo, la colonna o la riga da nascondere e non solo su una singola casella di testo nella riga o nella colonna.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="bb5d3-114">Inoltre, la casella di testo utilizzata per l'elemento Toggle deve trovarsi in un ambito contenitore che controlla l'elemento da visualizzare o nascondere.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="bb5d3-115">Per nascondere, ad esempio, una riga associata a un gruppo nidificato, la casella di testo deve trovarsi in una riga associata al gruppo padre o a un elemento di livello superiore nella gerarchia di contenimento.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="bb5d3-116">Per informazioni sull'impostazione delle informazioni di visibilità sul gruppo, sulla colonna o sulla riga, vedere [Aggiungere un'azione Espandi o Comprimi a un elemento &#40;Generatore report e SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="bb5d3-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="bb5d3-117">Per altre informazioni su come nascondere elementi di report, vedere [Nascondere un elemento &#40;Generatore report e SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="bb5d3-118">Confronto tra report drill-down e drill-through</span><span class="sxs-lookup"><span data-stu-id="bb5d3-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="bb5d3-119">In un report drill-down un utente fa clic su un pulsante più o meno per espandere o comprimere una sezione di un report per mostrare dati dettaglio.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="bb5d3-120">I un report drill-through l'utente fa clic su un collegamento relativo a un valore di riepilogo, aprendo in questo modo un report separato, correlato contenente dati dettaglio.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="bb5d3-121">I dati dettaglio vengono recuperati solo quando il report dettagli è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="bb5d3-122">I report drill-through richiedono in genere un numero di risorse minore rispetto ai report drill-down.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="bb5d3-123">Per altre informazioni, vedere [Drill-through, drill-down, sottoreport e aree dati nidificate &#40;Generatore report e SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="bb5d3-124">Supporto delle estensioni per il rendering per elementi del report nascosti</span><span class="sxs-lookup"><span data-stu-id="bb5d3-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="bb5d3-125">L'elemento Toggle per visualizzare e nascondere gli elementi del report è supportato solo dalle estensioni per il rendering che supportano funzioni di interattività con gli utenti, ad esempio l'estensione per il rendering HTML utilizzata durante l'esecuzione di un report in Generatore report e in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="bb5d3-126">Le altre estensioni per il rendering consentono di visualizzare gli elementi nascosti.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="bb5d3-127">Nell'elenco seguente viene descritto il supporto per gli elementi del report con visibilità condizionale:</span><span class="sxs-lookup"><span data-stu-id="bb5d3-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="bb5d3-128">In HTML, se gli elementi sono nascosti, non sono visibili nell'origine HTML.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="bb5d3-129">Le estensioni per il rendering XML visualizzano tutti gli elementi del report, anche se nascosti.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="bb5d3-130">L'estensione per il rendering Excel visualizza ed espande le righe e le colonne nascoste di una tabella, una matrice o un elenco.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="bb5d3-131">Tutte le righe e le colonne sono visibili.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="bb5d3-132">Per altre informazioni, vedere [Tipi di rendering  &#40;Generatore report e SSRS &#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5d3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb5d3-133">See Also</span></span>  
 <span data-ttu-id="bb5d3-134">[Drill-through, drill-down, sottoreport e aree dati nidificate &#40;Generatore report e SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="bb5d3-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="bb5d3-135">[Ordinamento interattivo, mappe documento e collegamenti &#40;Generatore report e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb5d3-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb5d3-136">Esempi di espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bb5d3-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
