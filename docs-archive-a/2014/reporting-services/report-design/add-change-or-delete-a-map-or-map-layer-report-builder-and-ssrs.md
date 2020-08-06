---
title: Aggiungere, modificare o eliminare una mappa o un livello mappa (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628472"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="100c8-102">Aggiungere, modificare o eliminare una mappa o un livello mappa (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="100c8-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="100c8-103">Una mappa è una raccolta di livelli.</span><span class="sxs-lookup"><span data-stu-id="100c8-103">A map is a collection of layers.</span></span> <span data-ttu-id="100c8-104">Quando si aggiunge una mappa a un report, si definisce il primo livello.</span><span class="sxs-lookup"><span data-stu-id="100c8-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="100c8-105">È possibile creare livelli aggiuntivi tramite la creazione guidata del livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="100c8-106">Il modo più semplice per aggiungere, rimuovere o modificare le opzioni per un livello è utilizzare la creazione guidata del livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="100c8-107">È possibile inoltre modificare manualmente le opzioni dal riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="100c8-108">Per visualizzare il riquadro **Mappa** , fare clic nella mappa sull'area di progettazione del report.</span><span class="sxs-lookup"><span data-stu-id="100c8-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="100c8-109">Nella figura seguente vengono visualizzate le parti del riquadro:</span><span class="sxs-lookup"><span data-stu-id="100c8-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="100c8-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="100c8-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="100c8-111">I livelli mappa vengono disegnati dal basso verso l'alto nell'ordine in cui vengono visualizzati nel riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="100c8-112">Nella figura precedente, viene disegnato per primo il livello sezione e per ultimo il livello poligono.</span><span class="sxs-lookup"><span data-stu-id="100c8-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="100c8-113">I livelli disegnati in un secondo momento potrebbero nascondere elementi della mappa di livelli disegnati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="100c8-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="100c8-114">È possibile modificare l'ordine dei livelli tramite i tasti di direzione sulla barra degli strumenti del riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="100c8-115">Per mostrare o nascondere i livelli, attivare o disattivare l'icona della visibilità.</span><span class="sxs-lookup"><span data-stu-id="100c8-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="100c8-116">È possibile modificare la trasparenza di un livello nella `Visibility` pagina della finestra di dialogo proprietà **dati livello** .</span><span class="sxs-lookup"><span data-stu-id="100c8-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="100c8-117">Nella tabella seguente vengono visualizzate le icone della barra degli strumenti per il riquadro **Mappa** .</span><span class="sxs-lookup"><span data-stu-id="100c8-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="100c8-118">Simbolo</span><span class="sxs-lookup"><span data-stu-id="100c8-118">Symbol</span></span>|<span data-ttu-id="100c8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="100c8-119">Description</span></span>|<span data-ttu-id="100c8-120">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="100c8-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="100c8-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="100c8-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="100c8-122">Creazione guidata livello mappa</span><span class="sxs-lookup"><span data-stu-id="100c8-122">Map Layer Wizard</span></span>|<span data-ttu-id="100c8-123">Per aggiungere un livello tramite una procedura guidata, fare clic su **Creazione guidata nuovo livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="100c8-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="100c8-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="100c8-125">Aggiungi livello</span><span class="sxs-lookup"><span data-stu-id="100c8-125">Add Layer</span></span>|<span data-ttu-id="100c8-126">Per aggiungere manualmente un livello, fare clic su **Aggiungi livello**, quindi scegliere il tipo di livello mappa da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="100c8-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="100c8-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="100c8-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="100c8-128">Livello poligono</span><span class="sxs-lookup"><span data-stu-id="100c8-128">Polygon Layer</span></span>|<span data-ttu-id="100c8-129">Per aggiungere un livello mappa che visualizza aree o forme basate su set di coordinate del poligono.</span><span class="sxs-lookup"><span data-stu-id="100c8-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="100c8-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="100c8-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="100c8-131">Livello linea</span><span class="sxs-lookup"><span data-stu-id="100c8-131">Line Layer</span></span>|<span data-ttu-id="100c8-132">Per aggiungere un livello mappa che visualizza percorsi o itinerari basati su set di coordinate della linea.</span><span class="sxs-lookup"><span data-stu-id="100c8-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="100c8-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="100c8-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="100c8-134">Livello punto</span><span class="sxs-lookup"><span data-stu-id="100c8-134">Point Layer</span></span>|<span data-ttu-id="100c8-135">Per aggiungere un livello mappa che visualizza posizioni basate su set di coordinate del punto.</span><span class="sxs-lookup"><span data-stu-id="100c8-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="100c8-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="100c8-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="100c8-137">Livello sezione</span><span class="sxs-lookup"><span data-stu-id="100c8-137">Tile Layer</span></span>|<span data-ttu-id="100c8-138">Per aggiungere un livello mappa che visualizza le tessere mappa di Bing che corrispondono all'area della vista mappa corrente definita dal viewport.</span><span class="sxs-lookup"><span data-stu-id="100c8-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="100c8-139">Nella parte inferiore del riquadro della mappa si trova l'area della vista mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="100c8-140">Per modificare le opzioni di allineamento al centro o zoom della mappa, utilizzare i tasti di direzione in modo da regolare il centro della vista e il dispositivo di scorrimento che consente di modificare il livello di zoom.</span><span class="sxs-lookup"><span data-stu-id="100c8-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="100c8-141">Per altre informazioni sui livelli, vedere [Mappe &#40;Generatore report e SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="100c8-142">Per aggiungere un livello dalla Creazione guidata livello mappa</span><span class="sxs-lookup"><span data-stu-id="100c8-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="100c8-143">Nel menu **Inserisci** della barra multifunzione fare clic su **Mappa**, quindi scegliere **Creazione guidata mappa.**</span><span class="sxs-lookup"><span data-stu-id="100c8-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="100c8-144">La procedura guidata consente di aggiungere un livello alla mappa esistente.</span><span class="sxs-lookup"><span data-stu-id="100c8-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="100c8-145">La maggior parte delle pagine della Creazione guidata mappa e della Creazione guidata livello mappa sono identiche.</span><span class="sxs-lookup"><span data-stu-id="100c8-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="100c8-146">Per altre informazioni, vedere [Creazione guidata mappa e Creazione guidata livello mappa &#40;Generatore report e SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="100c8-147">Per modificare le opzioni di un livello tramite la Creazione guidata livello mappa</span><span class="sxs-lookup"><span data-stu-id="100c8-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="100c8-148">Eseguire la Creazione guidata livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-148">Run the map layer wizard.</span></span> <span data-ttu-id="100c8-149">Questa procedura guidata consente di modificare le opzioni per un livello creato tramite la Creazione guidata livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="100c8-150">Nel riquadro Mappa fare clic con il pulsante destro del mouse sul livello, quindi fare clic sul pulsante della creazione guidata del livello sulla barra degli strumenti (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="100c8-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="100c8-151">Per altre informazioni, vedere [Creazione guidata mappa e Creazione guidata livello mappa &#40;Generatore report e SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="100c8-152">Per aggiungere un livello punto, linea o poligono dalla barra degli strumenti del riquadro della mappa</span><span class="sxs-lookup"><span data-stu-id="100c8-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="100c8-153">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-154">Nella barra degli strumenti fare clic sul pulsante **Aggiungi livello** e, dall'elenco a discesa, scegliere il tipo di livello da aggiungere: **Punto**, **Linea** o **Poligono**.</span><span class="sxs-lookup"><span data-stu-id="100c8-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="100c8-155">Sebbene sia possibile aggiungere un livello alla mappa e configurarlo manualmente, è consigliabile utilizzare la Creazione guidata livello mappa per aggiungere nuovi livelli.</span><span class="sxs-lookup"><span data-stu-id="100c8-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="100c8-156">Per avviare la procedura guidata dal riquadro Mappa della barra degli strumenti, fare clic sul pulsante della creazione guidata del livello (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="100c8-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="100c8-157">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="100c8-158">In **Usa dati spaziali da**selezionare l'origine dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="100c8-159">Le opzioni variano in base alla selezione.</span><span class="sxs-lookup"><span data-stu-id="100c8-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="100c8-160">Se si desidera visualizzare i dati analitici del report su questo livello, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="100c8-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="100c8-161">Fare clic su **Dati analitici**.</span><span class="sxs-lookup"><span data-stu-id="100c8-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="100c8-162">In **Set di dati analitici**fare clic sul nome del set di dati che contiene i dati analitici e i campi delle corrispondenze per compilare una relazione tra i dati analitici e quelli spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="100c8-163">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="100c8-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="100c8-164">Digitare il nome del campo delle corrispondenze del set di dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="100c8-165">Digitare il nome del campo delle corrispondenze del set di dati analitici.</span><span class="sxs-lookup"><span data-stu-id="100c8-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="100c8-166">Per altre informazioni sul collegamento di dati spaziali e analitici, vedere [Personalizzazione dei dati e visualizzazione di una mappa o di un livello mappa &#40;Generatore report e SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="100c8-167">Per filtrare dati analitici per il livello</span><span class="sxs-lookup"><span data-stu-id="100c8-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="100c8-168">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-169">Fare clic con il pulsante destro del mouse sul livello nel riquadro della mappa, quindi scegliere  **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="100c8-170">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="100c8-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="100c8-171">Definire un'equazione di filtro per limitare i dati analitici utilizzati nella vista mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="100c8-172">Per altre informazioni, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="100c8-173">Per controllare le proprietà punto per un livello punto o per i punti centrali del poligono</span><span class="sxs-lookup"><span data-stu-id="100c8-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="100c8-174">Selezionare **Generale** nella finestra di dialogo **Proprietà punto mappa** per modificare le opzioni relative all'etichetta, alla descrizione comando e al tipo di indicatore per gli elementi della mappa seguenti:</span><span class="sxs-lookup"><span data-stu-id="100c8-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="100c8-175">Tutti i punti dinamici o incorporati su un livello punto.</span><span class="sxs-lookup"><span data-stu-id="100c8-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="100c8-176">Le regole relative al colore, alle dimensioni e al tipo di marcatore per i punti ignorano queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="100c8-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="100c8-177">Per sostituire le opzioni per un punto incorporato specifico, usare la pagina [Finestra di dialogo Proprietà punto incorporato mappa, Indicatore](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="100c8-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="100c8-178">Punto centrale per tutti i poligoni dinamici o incorporati su un livello poligono.</span><span class="sxs-lookup"><span data-stu-id="100c8-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="100c8-179">Le regole relative al colore, alle dimensioni e al tipo di marcatore per i punti centrali ignorano queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="100c8-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="100c8-180">Per sostituire le opzioni per un punto centrale specifico, usare la pagina [Finestra di dialogo Proprietà punto incorporato mappa, Indicatore](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="100c8-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="100c8-181">Per specificare i dati incorporati come origine di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="100c8-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="100c8-182">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-183">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="100c8-184">In **Usa dati spaziali da**selezionare **Dati incorporati nel report**.</span><span class="sxs-lookup"><span data-stu-id="100c8-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="100c8-185">Per caricare gli elementi della mappa da un report esistente o creare elementi della mappa basati su un file ESRI, fare clic su **Sfoglia**, scegliere il file, quindi scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="100c8-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="100c8-186">Gli elementi della mappa vengono incorporati in questa definizione del report.</span><span class="sxs-lookup"><span data-stu-id="100c8-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="100c8-187">I dati spaziali scelti devono corrispondere al tipo di livello.</span><span class="sxs-lookup"><span data-stu-id="100c8-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="100c8-188">Ad esempio per un livello punto, è necessario scegliere i dati spaziali che specificano set di coordinate del punto.</span><span class="sxs-lookup"><span data-stu-id="100c8-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="100c8-189">In **Campo spaziale**specificare il nome del campo che contiene dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="100c8-190">Potrebbe essere necessario determinare questo nome dall'origine dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="100c8-191">Se non si conosce il nome del campo ed è stato selezionato un file di forma ESRI, usare l'opzione **Collegamento a file di forma ESRI** anziché questa opzione.</span><span class="sxs-lookup"><span data-stu-id="100c8-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="100c8-192">Per specificare un file di forma ESRI come origine di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="100c8-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="100c8-193">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-194">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="100c8-195">In **Usa dati spaziali da**selezionare **Collegamento a file di forma ESRI**.</span><span class="sxs-lookup"><span data-stu-id="100c8-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="100c8-196">In **Nome file**digitare il percorso di un file di forma ESRI o fare clic su **Sfoglia** per selezionare un file di forma ESRI.</span><span class="sxs-lookup"><span data-stu-id="100c8-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="100c8-197">Se il file di forma si trova sul computer locale, i dati spaziali sono incorporati nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="100c8-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="100c8-198">Per recuperare in modo dinamico i dati durante l'elaborazione del report, è necessario caricare il file ESRI con estensione shp e il file di supporto con estensione dbf sul server di report.</span><span class="sxs-lookup"><span data-stu-id="100c8-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="100c8-199">Per altre informazioni, vedere "Procedura: Caricamento di un file o di un report (Gestione report)" nella [documentazione relativa a Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) inclusa nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="100c8-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="100c8-200">Per specificare un campo del set di dati del report come origine di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="100c8-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="100c8-201">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-202">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="100c8-203">In **Usa dati spaziali da**selezionare **Campo spaziale in un set di dati**.</span><span class="sxs-lookup"><span data-stu-id="100c8-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="100c8-204">In **Nome set di dati**fare clic sul nome di un set di dati del report che contiene i dati spaziali desiderati.</span><span class="sxs-lookup"><span data-stu-id="100c8-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="100c8-205">In **Nome campo spaziale**fare clic sul nome del campo del set di dati che contiene i dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="100c8-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="100c8-206">Per aggiungere un livello sezione</span><span class="sxs-lookup"><span data-stu-id="100c8-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="100c8-207">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-208">Sulla barra degli strumenti fare clic sul pulsante **Aggiungi livello** e, dall'elenco a discesa, scegliere **Livello sezione**.</span><span class="sxs-lookup"><span data-stu-id="100c8-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="100c8-209">Per altre informazioni sull'utilizzo delle tessere mappa di Bing nel report, vedere [Ulteriori condizioni di utilizzo](https://go.microsoft.com/fwlink/?LinkId=151371) e [Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="100c8-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="100c8-210">Fare clic con il pulsante destro del mouse sul livello sezione nel riquadro della mappa, quindi scegliere **Proprietà sezione**.</span><span class="sxs-lookup"><span data-stu-id="100c8-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="100c8-211">In **Opzioni sezioni**selezionare uno stile della sezione.</span><span class="sxs-lookup"><span data-stu-id="100c8-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="100c8-212">Se sono disponibili le tessere mappa di Bing, il livello sull'area di progettazione viene aggiornato con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="100c8-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="100c8-213">Un livello sezione può essere aggiunto anche quando si aggiunge un livello poligono, linea o punto nella Creazione guidata mappa o Creazione guidata livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="100c8-214">Nella pagina **Scegli opzioni di dati spaziali e vista mappa** selezionare l'opzione **Add a Bing Maps background for this map view (Aggiungi sfondo Bing Maps per la vista mappa)** .</span><span class="sxs-lookup"><span data-stu-id="100c8-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="100c8-215">Per modificare l'ordine di disegno di un livello</span><span class="sxs-lookup"><span data-stu-id="100c8-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="100c8-216">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-217">Fare clic sul livello nel riquadro della mappa per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="100c8-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="100c8-218">Sulla barra degli strumenti del riquadro della mappa fare clic sulla freccia in su o in giù per modificare l'ordine di disegno di ogni livello.</span><span class="sxs-lookup"><span data-stu-id="100c8-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="100c8-219">Per modificare la trasparenza di un livello poligono, linea o punto</span><span class="sxs-lookup"><span data-stu-id="100c8-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="100c8-220">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-221">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Dati livello**.</span><span class="sxs-lookup"><span data-stu-id="100c8-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="100c8-222">Fare clic su `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="100c8-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="100c8-223">In **Opzioni trasparenza**digitare un valore che rappresenta la percentuale di trasparenza, ad esempio **40**.</span><span class="sxs-lookup"><span data-stu-id="100c8-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="100c8-224">La trasparenza zero (0) % significa che il livello è opaco.</span><span class="sxs-lookup"><span data-stu-id="100c8-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="100c8-225">Trasparenza 100% significa che il livello non sarà visibile nel report.</span><span class="sxs-lookup"><span data-stu-id="100c8-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="100c8-226">Per modificare la trasparenza di un livello sezione</span><span class="sxs-lookup"><span data-stu-id="100c8-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="100c8-227">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-228">Fare clic con il pulsante destro del mouse sul livello, quindi scegliere **Proprietà sezione**.</span><span class="sxs-lookup"><span data-stu-id="100c8-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="100c8-229">Fare clic su `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="100c8-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="100c8-230">In **Opzioni trasparenza**digitare un valore che rappresenta la percentuale di trasparenza, ad esempio **40**.</span><span class="sxs-lookup"><span data-stu-id="100c8-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="100c8-231">Per specificare una connessione protetta per un livello sezione</span><span class="sxs-lookup"><span data-stu-id="100c8-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="100c8-232">Fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="100c8-233">Nel riquadro della mappa fare clic sul livello sezione per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="100c8-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="100c8-234">Nel riquadro Proprietà verranno visualizzate le proprietà del livello sezione.</span><span class="sxs-lookup"><span data-stu-id="100c8-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="100c8-235">Nel riquadro Proprietà impostare UseSecureConnection su **True**.</span><span class="sxs-lookup"><span data-stu-id="100c8-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="100c8-236">La connessione per il servizio Web di Bing Maps utilizzerà il servizio HTTP SSL (Secure Sockets Layer) per recuperare le tessere mappa di Bing per questo livello.</span><span class="sxs-lookup"><span data-stu-id="100c8-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="100c8-237">Per specificare la lingua per le etichette delle sezioni</span><span class="sxs-lookup"><span data-stu-id="100c8-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="100c8-238">Per impostazione predefinita, per gli stili delle sezioni che consentono di visualizzare le etichette, la lingua viene determinata in base alle impostazioni locali predefinite per Generatore report.</span><span class="sxs-lookup"><span data-stu-id="100c8-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="100c8-239">È possibile personalizzare l'impostazione della lingua per le etichette delle sezioni come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="100c8-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="100c8-240">Fare clic sulla mappa all'esterno del viewport per selezionare la mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="100c8-241">Nel riquadro Proprietà per la proprietà TileLanguage, selezionare un valore della lingua dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="100c8-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="100c8-242">Fare clic sullo sfondo del report per selezionare il report.</span><span class="sxs-lookup"><span data-stu-id="100c8-242">Click the report background to select the report.</span></span> <span data-ttu-id="100c8-243">Nel riquadro Proprietà per la proprietà Language, selezionare un valore della lingua dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="100c8-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="100c8-244">La lingua delle etichette delle sezioni viene impostata in base all'ordine di precedenza seguente: Language delle proprietà del report, impostazioni locali predefinite per Generatore report e TileLanguage delle proprietà della mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="100c8-245">Per nascondere un livello basato sul livello di zoom del viewport in base a specifiche condizioni</span><span class="sxs-lookup"><span data-stu-id="100c8-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="100c8-246">Impostare `Visibility` le opzioni per controllare la visualizzazione per un livello mappa.</span><span class="sxs-lookup"><span data-stu-id="100c8-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="100c8-247">Nel riquadro Livelli mappa fare clic con il pulsante destro del mouse su un livello per selezionarlo e sulla barra degli strumenti di Livelli mappa fare clic su Proprietà per aprire **Proprietà livello mappa**.</span><span class="sxs-lookup"><span data-stu-id="100c8-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="100c8-248">Fare clic su `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="100c8-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="100c8-249">In Visibilità livello selezionare **Mostra o nascondi in base a un valore di zoom**.</span><span class="sxs-lookup"><span data-stu-id="100c8-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="100c8-250">Immettere i valori di zoom minimo e massimo per la visualizzazione del livello.</span><span class="sxs-lookup"><span data-stu-id="100c8-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="100c8-251">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="100c8-251">Optional.</span></span> <span data-ttu-id="100c8-252">Immettere un valore per la trasparenza.</span><span class="sxs-lookup"><span data-stu-id="100c8-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="100c8-253">Inoltre è possibile nascondere il livello in base a condizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="100c8-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="100c8-254">Per altre informazioni, vedere [Nascondere un elemento &#40;Generatore report e SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="100c8-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="100c8-255">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="100c8-255">See Also</span></span>  
 <span data-ttu-id="100c8-256">[Mappe &#40;Generatore report e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="100c8-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="100c8-257">Risolvere problemi relativi ai report: Report mappa &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="100c8-257">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
