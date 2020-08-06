---
title: Aggiungere percorsi personalizzati a una mappa (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722564"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="88fad-102">Aggiungere percorsi personalizzati a una mappa (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="88fad-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="88fad-103">Dopo avere aggiunto una mappa a un report, è possibile aggiungere percorsi punto personalizzati.</span><span class="sxs-lookup"><span data-stu-id="88fad-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="88fad-104">Le proprietà di visualizzazione per tutti i punti su un livello vengono controllate impostando le opzioni per le proprietà punto per il livello.</span><span class="sxs-lookup"><span data-stu-id="88fad-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="88fad-105">Per un punto incorporato selezionato, è possibile ignorare le proprietà di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="88fad-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88fad-106">Quando si ignorano le proprietà di visualizzazione del livello per il punto incorporato, le modifiche apportate non sono reversibili.</span><span class="sxs-lookup"><span data-stu-id="88fad-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="88fad-107">Per altre informazioni, vedere [Variare la visualizzazione di poligoni, linee e punti in base a regole e dati analitici &#40;Generatore report e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="88fad-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="88fad-108">Per aggiungere un livello punto</span><span class="sxs-lookup"><span data-stu-id="88fad-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="88fad-109">Nell'area di progettazione del report fare clic sulla mappa per selezionarla e visualizzare il riquadro mappa.</span><span class="sxs-lookup"><span data-stu-id="88fad-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="88fad-110">Sulla barra degli strumenti fare clic su **Aggiungi livello**.</span><span class="sxs-lookup"><span data-stu-id="88fad-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="88fad-111">Nell'elenco a discesa fare clic su **Aggiungi livello punto**.</span><span class="sxs-lookup"><span data-stu-id="88fad-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="88fad-112">Alla mappa viene aggiunto un livello punto senza alcun punto.</span><span class="sxs-lookup"><span data-stu-id="88fad-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="88fad-113">Per impostazione predefinita, il livello punto è pronto per i punti incorporati.</span><span class="sxs-lookup"><span data-stu-id="88fad-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="88fad-114">Per aggiungere un punto personalizzato</span><span class="sxs-lookup"><span data-stu-id="88fad-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="88fad-115">Nell'area di progettazione del report fare clic sulla mappa per selezionarla e visualizzare il riquadro mappa.</span><span class="sxs-lookup"><span data-stu-id="88fad-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="88fad-116">Nel riquadro mappa fare clic con il pulsante destro del mouse su un livello punto con il tipo **Incorporato**, quindi scegliere **Aggiungi punto**.</span><span class="sxs-lookup"><span data-stu-id="88fad-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="88fad-117">Il cursore passa alla selezione di precisione.</span><span class="sxs-lookup"><span data-stu-id="88fad-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="88fad-118">Per aggiungere un punto fare clic su una posizione sulla mappa.</span><span class="sxs-lookup"><span data-stu-id="88fad-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="88fad-119">Un punto incorporato viene aggiunto al livello selezionato nella posizione scelta.</span><span class="sxs-lookup"><span data-stu-id="88fad-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="88fad-120">Per personalizzare la visualizzazione per un punto incorporato</span><span class="sxs-lookup"><span data-stu-id="88fad-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="88fad-121">Fare clic con il pulsante destro del mouse sul punto, quindi scegliere **Proprietà punto**.</span><span class="sxs-lookup"><span data-stu-id="88fad-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="88fad-122">Viene visualizzata la finestra di dialogo **Proprietà punto incorporato nella mappa** .</span><span class="sxs-lookup"><span data-stu-id="88fad-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="88fad-123">Fare clic su **Ignora opzioni punto per questo livello**.</span><span class="sxs-lookup"><span data-stu-id="88fad-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="88fad-124">Nel riquadro sinistro vengono visualizzate più pagine delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="88fad-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="88fad-125">Fare clic sulle pagine e impostare le proprietà di visualizzazione che si desidera applicare a questo punto.</span><span class="sxs-lookup"><span data-stu-id="88fad-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fad-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88fad-126">See Also</span></span>  
 <span data-ttu-id="88fad-127">[Mappe &#40;Generatore report e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="88fad-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="88fad-128">Variare la visualizzazione di poligoni, linee e punti in base a regole e dati analitici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="88fad-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
